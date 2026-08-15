# Log de Prompts e Ferramentas de IA Utilizados

Este documento registra o processo de desenvolvimento do projeto, incluindo os prompts utilizados na interação com o Claude (Anthropic), conforme exigido pelo desafio.

**Ferramenta principal:** Claude (Anthropic), com acesso a busca na web em tempo real, geração de arquivos (Excel, PDF, Markdown) e execução de código.

---

## Etapa 1 — Pesquisa e Análise Inicial

**Prompt utilizado (resumo do prompt estruturado original):**

```
[Persona]: Pesquisador/professor especialista no mercado automotivo no Brasil, 
com 30 anos de experiência.

[Contexto]: Análise dos concorrentes de vendas de automóveis no Brasil, focado 
em veículos elétricos e híbridos na América do Sul, considerando o avanço 
agressivo das montadoras chinesas (BYD e GWM) em preço, disponibilidade, e 
percepção do consumidor.

[Tarefa]: Pesquisar e analisar como as marcas da Stellantis na América do Sul 
estão posicionadas em relação aos concorrentes chineses no segmento de 
elétricos/híbridos, considerando preço, disponibilidade de produtos, percepção 
do consumidor e participação de mercado.

[Critérios]: Dados reais e atuais (2026), sem dados genéricos, inventados ou 
desatualizados; modelos reais existentes no mercado.

[Formato de saída]: Relatório executivo em PDF (Sumário, SWOT, Recomendação em 
3 Pilares, ferramentas/prompts utilizados), documento técnico em Markdown, 
tabelas organizadas em categorias.
```

**O que foi produzido:** `analise_stellantis_vs_chinesas.md` (documento técnico completo) e `relatorio_stellantis_vs_chinesas.pdf` (relatório executivo com Sumário, matriz SWOT e recomendações em 3 pilares).

**Processo:** o Claude realizou múltiplas buscas na web (participação de mercado, preços por modelo, especificações técnicas, satisfação do consumidor, percepção de marcas chinesas, dados da joint-venture Leapmotor-Stellantis) antes de consolidar a análise.

---

## Etapa 2 — Base de Dados para Power BI (v1)

**Prompt utilizado:**

```
Crie um arquivo em Excel com todos os dados necessários e importantes que você 
utilizou para criar os dois arquivos acima (relatório e análise técnica).
```

**O que foi produzido:** `base_dados_stellantis_vs_chinesas.xlsx` — 8 abas com panorama de mercado, ranking de vendas, preços, especificações técnicas, satisfação, percepção de marca, Leapmotor e fontes.

---

## Etapa 3 — Roteiro Completo do Projeto

**Prompt utilizado (resumo):**

```
Preciso colocar todo esse projeto dentro do GitHub mostrando o percurso do 
desenvolvimento, criar uma apresentação no Gamma.app, e ter dashboards no 
Power BI. Crie um roteiro de tudo que precisaremos fazer, do começo do 
projeto até a entrega final (repositório GitHub, apresentação Gamma, 
dashboards Power BI, PDF final).
```

**O que foi produzido:** `roteiro_projeto.md` — plano completo com estrutura de pastas do GitHub, roteiro de slides para o Gamma, estrutura sugerida do dashboard Power BI e checklist de entrega.

---

## Etapa 4 — Refinamento da Base de Dados (v2 → v3)

**Prompt utilizado (resumo):**

```
Preciso que os dados sejam primariamente focados em veículos da Stellantis e 
concorrentes chineses. Quero planilhas com indicadores de: Volume de Vendas, 
Market Share %, Crescimento YoY (24 meses), Faixa de Preço, Segmentação de 
Produto, Disponibilidade/Portfólio, Autonomia, Potência, Tecnologia Embarcada 
(ADAS/OTA), Índice de Satisfação, Capilaridade da Rede. Estruture em: Tabela 
de Modelos, Tabela de Vendas (Fato), Tabela de Concorrência.
```

Em seguida:

```
Preciso de mais modelos comparativos (Stellantis e chinesas). Elimine a 
Tabela_Concorrencia e mescle todas as informações na Tabela_Modelos, deixando 
apenas uma tabela organizada. Na Fato_Vendas, Market_Share e Crescimento_YoY, 
preciso de mais marcas que englobem o espectro da Stellantis e dos 
concorrentes chineses.
```

**O que foi produzido:** `base_dados_powerbi_stellantis_vs_chinesas_v3.xlsx` — 6 abas (Tabela_Modelos mesclada, Fato_Vendas, Market_Share, Crescimento_YoY, Panorama_Mercado, Fontes), cobrindo 9 marcas (Fiat, Jeep, Peugeot, Citroën, Leapmotor / BYD, GWM, Chery-Caoa Chery, GAC Aion) e 29 modelos.

**Processo:** pesquisa adicional na web para expandir a cobertura de marcas — dados de preço, especificações e vendas anuais de Peugeot, Citroën, Chery/Caoa Chery e GAC Aion, previamente ausentes da base.

---

## Etapa 5 — Verificação de Integridade dos Dados

**Prompts utilizados:**

```
Diz para mim, todos os carros e modelos relacionados nas planilhas são dados 
reais? Não quero dados inventados no arquivo.
```

```
Nos meus dados, a marca Peugeot faz parte do grupo Stellantis? As marcas 
concorrentes que tu descreveu como chinesa são mesmo chinesas?
```

**Resposta/processo:** o Claude auditou a própria base de dados, identificando e sinalizando explicitamente os pontos de menor confiança (ex.: modelos citados em fonte única, como Jeep Renegade/Commander MHEV; lançamentos anunciados mas não confirmados, como Citroën C3 Aircross/Basalt Hybrid; e valores calculados a partir de percentuais divulgados). Confirmou a classificação societária de cada marca (Stellantis vs. chinesa), incluindo as nuances da Leapmotor (joint-venture 51% Stellantis) e da Caoa Chery (joint-venture local com tecnologia chinesa).

---

## Etapa 6 — Documentação do Repositório

**Prompt utilizado:**

```
Atualize o roteiro_projeto.md com os novos dados criados.
```

```
Já criei a estrutura de pastas, qual o próximo passo?
```

**O que foi produzido:** `README.md` (documentação principal do repositório) e este arquivo (`prompts_utilizados.md`).

---

## Etapa 7 — Modelagem de Dados no Power BI (com Claude)

**Processo:** o Claude guiou, passo a passo e por meio de imagens da tela do Power BI Desktop enviadas pelo usuário, a modelagem de dados a partir da base v4:
- Importação das 6 abas via Power Query, com limpeza de cabeçalho
- Extração de uma tabela `Dim_Marca` (via Referência, não Duplicação) a partir da `Tabela_Modelos`, para evitar duplicação de linhas nos relacionamentos
- Criação de uma tabela `Calendario` para Time Intelligence
- Criação dos relacionamentos entre `Fato_Vendas`, `Market_Share`, `Crescimento_YoY` e `Dim_Marca`
- Criação e correção iterativa da medida DAX `Total_Vendas` — identificado e corrigido um erro de contagem duplicada causado pela linha "Peugeot + Citroën (combinado)" aparecer somada junto com as linhas individuais de Peugeot e Citroën

Esse processo envolveu 3 rodadas de diagnóstico de erro (double counting), cada uma feita a partir da leitura de prints reais da tela do Power BI enviados pelo usuário, comparando os valores exibidos nos cartões com o que seria matematicamente esperado.

---

## Etapa 8 — Construção Visual do Dashboard (com Gemini)

**Ferramenta:** Google Gemini, usando a mesma base de dados v4 e o modelo de dados já validado com o Claude.

**O que foi produzido pelo usuário com apoio do Gemini** (resumo do próprio usuário, registrado aqui para transparência do processo):

1. **Reestruturação e Refinamento do Power BI:**
   - Diagnóstico da Página 3 (Comparativo de Produtos): identificação de que a soma de preços e a filtragem isolada da Stellantis estavam poluindo a visualização
   - Implementação de gráfico de dispersão (Preço Base vs. Potência), com ajuste de escala e tamanho dos marcadores
   - Substituição de gráfico de pizza por gráfico de barras empilhadas (Tipos de Motores por Marca)
   - Renomeação de cabeçalhos para termos executivos (Preço Base, Potência, Autonomia Elétrica, Assistência ADAS)

2. **Análise e extração de insights das 3 páginas construídas:**
   - Volume absoluto: Stellantis lidera o volume acumulado analisado (~64,6%), sustentada por Fiat e Jeep
   - Velocidade de crescimento: GWM +46% e BYD +45,4% a/a (2024-2025), enquanto marcas tradicionais enfrentam estagnação/retração
   - Produto: modelos chineses entregam maior potência e pacotes ADAS na faixa de R$ 170 mil a R$ 250 mil

3. **Redação da resposta do Cenário 1 do formulário**, articulando o diagnóstico com a estratégia multimarca da Stellantis (Fiat/Citroën na proteção de volume via Bio-Hybrid, Jeep no SUV Premium/PHEV, Leapmotor como resposta tecnológica em BEV/REEV)

4. **Ajustes visuais e de design:** correção de zoom/canvas, alinhamento de plano de fundo, diretrizes de captura de prints para o GitHub e a apresentação

**Resultado final:** 3 páginas de dashboard — Panorama de Mercado, Evolução e Crescimento de Mercado (2023-2025), e Comparativo de Produtos e Atributos — todas construídas sobre o modelo de dados validado na Etapa 7.

---

## Etapa 9 — Consolidação Final da Documentação (com Claude)

**Prompt utilizado:**

```
Preciso que atualize todos os documentos (roteiro, relatórios) com base no novo 
dashboard construído. Substitua o que veio antes pelo que veio depois dos novos 
dados. Depois de tudo atualizado vou precisar atualizar meu GitHub.
```

**O que foi produzido:** atualização do `roteiro_projeto.md` (seção 4 reescrita para refletir a estrutura real de 3 páginas do dashboard, em vez do plano original de 5-7 páginas) e deste arquivo (`prompts_utilizados.md`), documentando a etapa de trabalho com o Gemini para manter o registro fiel do percurso do projeto.

---

## Observações sobre o Processo

- Todas as buscas na web foram feitas em tempo real pelo Claude, com múltiplas consultas por tópico (preços, especificações, vendas, satisfação) para cruzar fontes antes de consolidar cada dado na base.
- Nenhum modelo, preço ou métrica foi inventado. Onde a informação pública era incompleta, o campo foi marcado como "N/D" (não disponível) em vez de estimado.
- Valores derivados matematicamente a partir de percentuais de crescimento divulgados oficialmente (quando o valor absoluto não estava disponível) foram sinalizados como "CALCULADO" diretamente nas células de observação da planilha.
- O processo combinou duas ferramentas de IA em etapas distintas: o **Claude** foi usado para pesquisa de dados, estruturação da base de dados, geração dos relatórios e modelagem do Power BI (relacionamentos e medidas DAX); o **Gemini** foi usado para a construção visual final das 3 páginas do dashboard e para a redação inicial da resposta do Cenário 1 do formulário. Essa divisão de ferramentas está registrada de forma transparente neste log, conforme exigido pelo desafio.
- O processo incluiu uma tentativa inicial com o Gemini para geração de um arquivo Excel (etapa anterior à Etapa 1 deste log), que apresentou um bug de geração de link de download — o que motivou a migração do trabalho de estruturação de dados para o Claude. O Gemini foi reintroduzido mais adiante, com sucesso, na etapa de construção visual do dashboard (Etapa 8).
