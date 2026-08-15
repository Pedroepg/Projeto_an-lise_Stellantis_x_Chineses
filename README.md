# Stellantis vs. Montadoras Chinesas — Posicionamento em Elétricos e Híbridos na América do Sul

> Desafio Prático de Inteligência Competitiva — Processo Seletivo de Estágio, Stellantis
> Análise de posicionamento de mercado usando ferramentas de IA (Claude/Anthropic + Gemini/Google)

---

## 📋 Contexto do Desafio

A Stellantis opera diversas marcas na América do Sul (Fiat, Jeep, Peugeot, Citroën, Leapmotor). Fabricantes chinesas — como BYD, GWM, Chery/Caoa Chery e GAC — vêm expandindo rapidamente sua presença na região, especialmente nos segmentos de veículos elétricos e híbridos.

**Tarefa:** utilizando ferramentas de IA, pesquisar e analisar como as marcas da Stellantis na América do Sul estão atualmente posicionadas em relação aos concorrentes chineses no segmento de elétricos/híbridos, considerando preço, disponibilidade de produtos, percepção do consumidor e participação de mercado.

## 🎯 Objetivo da Análise

Diagnosticar a posição competitiva real da Stellantis frente ao avanço chinês no segmento eletrificado e propor recomendações estratégicas acionáveis, com base exclusivamente em dados públicos verificáveis — sem estimativas genéricas ou dados desatualizados.

## 🔍 Metodologia

- **Fontes de dados:** FENABRAVE, ANFAVEA, ABVE, Tabela FIPE (Webmotors/Mobiauto), sites oficiais das marcas (Stellantis Media, BYD Brasil, GWM Brasil, CAOA Chery, GAC), relatório oficial da Stellantis N.V. (SEC Form 6-K), estudos de satisfação do consumidor (Decoupling/Harvard-methodology, Reclame Aqui) e imprensa especializada do setor automotivo.
- **Ferramentas de IA:** Claude (Anthropic), com busca na web em tempo real, usado para pesquisa, estruturação de dados, geração dos relatórios e modelagem do dashboard Power BI (relacionamentos e medidas DAX); Gemini (Google), usado para a construção visual final das 3 páginas do dashboard. Ver [`prompts/prompts_utilizados.md`](prompts/prompts_utilizados.md) para o log completo.
- **Escopo de marcas:**
  - **Stellantis:** Fiat, Jeep, Peugeot, Citroën, Leapmotor (joint-venture, 51% Stellantis)
  - **Chinesas:** BYD, GWM (Haval/Ora/Wey), Chery/Caoa Chery (Tiggo/Jaecoo), GAC Aion
- **Princípio de dados:** todo dado quantitativo tem fonte pública identificada. Valores calculados a partir de variações percentuais divulgadas (quando o número absoluto não foi encontrado) estão sinalizados explicitamente como "CALCULADO" na base de dados — nenhum número foi inventado ou estimado sem base documentada.

## 📊 Principais Conclusões

1. **A liderança da Stellantis em volume é real, mas concentrada em poucas marcas.** No recorte de dados analisado no dashboard, a Stellantis soma 956,19 mil unidades (~64,6%) contra 518,89 mil das chinesas (~35,4%) — mas essa liderança é sustentada quase inteiramente por Fiat e Jeep, enquanto Peugeot e Citroën têm participação marginal.
2. **O ritmo de crescimento é assimétrico e favorece as chinesas.** Entre 2024 e 2025, GWM cresceu +46%, BYD +45,4% e Chery/Caoa Chery +17,24%, enquanto a Peugeot caiu -16,88% no mesmo período — um contraste direto entre expansão acelerada e estagnação/retração.
3. **O principal produto híbrido da Stellantis está saindo de linha — mas há uma resposta real surgindo.** O Jeep Compass 4xe (PHEV) foi confirmado fora da linha 2026, sem substituto imediato. Em contrapartida, o Jeep Renegade MHEV (lançado em 2026) já tem volume mensal comparável ao BYD Song Pro/Plus, mostrando que a resposta da Stellantis existe, mas está concentrada em um único modelo.
4. **Os produtos chineses entregam mais tecnologia por um preço competitivo.** No comparativo de preço x potência do dashboard, os modelos chineses concentram maior potência e pacotes ADAS mais completos na faixa de R$ 170 mil a R$ 250 mil, pressionando diretamente os SUVs médios tradicionais da Stellantis.
5. **A percepção de risco do "carro chinês" está sendo derrubada.** A BYD lidera rankings de satisfação do consumidor (nota 8,11 no estudo Decoupling), à frente da própria Jeep, e recebeu o selo RA1000 do Reclame Aqui.
6. **A resposta estratégica já está em curso.** A aliança da Stellantis com a Leapmotor (51% de participação na joint-venture) é a aposta mais relevante do grupo para reduzir essa distância no segmento elétrico.

O diagnóstico completo, a matriz SWOT e as recomendações em 3 pilares estão no [Relatório Executivo](docs/relatorio_executivo.pdf).

## 📈 Dashboard Power BI

O dashboard interativo tem 3 páginas, construídas sobre a base de dados v4:

| Página | Conteúdo |
|---|---|
| **1. Panorama de Mercado** | KPIs de volume total (Stellantis vs. Chinesas) e evolução anual de vendas por marca (2023-2026) |
| **2. Evolução e Crescimento de Mercado** | Taxa de crescimento ano a ano (2024→2025) e volume anual comparado por marca — a página mais direta para visualizar o contraste de ritmo entre os dois grupos |
| **3. Comparativo de Produtos e Atributos** | Matriz de preço/potência/autonomia/ADAS por marca, distribuição de tipos de motor (BEV/PHEV/MHEV/Flex) e gráfico de dispersão preço x potência |

Prints das 3 páginas em [`dashboard/prints/`](dashboard/prints/); arquivo fonte em [`dashboard/dashboard_stellantis.pbix`](dashboard/dashboard_stellantis.pbix).

## 🎤 Apresentação Executiva

Apresentação de 8 slides gerada no Gamma.app a partir dos dados do dashboard, cobrindo cenário de mercado, dinâmica de crescimento, liderança da BYD, portfólio Stellantis (descontinuação e resposta), análise competitiva, estratégia e conclusões finais.

Arquivo em [`docs/apresentacao_gamma.pdf`](docs/apresentacao_gamma.pdf).

## 🗂️ Estrutura do Repositório

```
stellantis-vs-chinesas-brasil-2026/
│
├── README.md                          # Este arquivo
│
├── docs/
│   ├── relatorio_executivo.pdf        # Relatório executivo (Sumário, SWOT, recomendações)
│   ├── analise_tecnica.md             # Documento técnico completo em Markdown
│   ├── resposta_cenario_1.md          # Resposta redigida para o formulário do desafio
│   └── apresentacao_gamma.pdf         # Apresentação exportada do Gamma.app
│
├── data/
│   └── base_dados_powerbi_stellantis_vs_chinesas_v4.xlsx   # Base de dados (6 abas, 9 marcas, 29 modelos)
│
├── dashboard/
│   ├── dashboard_stellantis.pbix      # Arquivo Power BI (3 páginas)
│   └── prints/
│       ├── 01_panorama_de_mercado.png
│       ├── 02_evolucao_e_crescimento_de_mercado.png
│       └── 03_comparativo_de_produtos_e_atributos.png
│
└── prompts/
    └── prompts_utilizados.md          # Log de todos os prompts de IA usados no projeto
```

## 🔗 Links

- 📊 **Dashboard Power BI:** [`dashboard/dashboard_stellantis.pbix`](dashboard/dashboard_stellantis.pbix) _(link do Power BI Service a preencher, se publicado)_
- 🎤 **Apresentação Gamma:** [`docs/apresentacao_gamma.pdf`](docs/apresentacao_gamma.pdf) _(link público do Gamma a preencher, se houver)_
- 📄 **Relatório Executivo (PDF):** [`docs/relatorio_executivo.pdf`](docs/relatorio_executivo.pdf)

## 🛠️ Ferramentas Utilizadas

| Ferramenta | Uso no projeto |
|---|---|
| **Claude (Anthropic)** | Pesquisa de dados via web search, análise, estruturação da base de dados, geração dos relatórios e modelagem do Power BI (relacionamentos e medidas DAX) |
| **Gemini (Google)** | Construção visual final das 3 páginas do dashboard Power BI e apoio na redação da resposta do Cenário 1 |
| **Microsoft Excel** | Base de dados estruturada para modelagem dimensional |
| **Power BI** | Dashboard interativo de visualização dos dados |
| **Gamma.app** | Geração da apresentação executiva |
| **GitHub** | Versionamento e documentação do percurso do projeto |

## 👤 Autor

Pedro Eduardo — Estudante de Sistemas de Informação, candidato ao Programa de Estágio Stellantis (área de Elétricos & Híbridos / Dados / BI)

---

*Este projeto foi desenvolvido como parte de um desafio prático de inteligência competitiva. Todos os dados foram coletados de fontes públicas entre julho e agosto de 2026 — ver [`data/`](data/) para a base completa e fontes.*
