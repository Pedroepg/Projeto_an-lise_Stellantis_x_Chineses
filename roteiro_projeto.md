# Roteiro do Projeto — Desafio Stellantis vs. Montadoras Chinesas

**Objetivo final:** Repositório no GitHub documentando todo o percurso + Apresentação no Gamma.app + Dashboard no Power BI + PDF executivo final.

---

## 0. Onde estamos agora (Checkpoint atual)

Já temos prontos:
- [x] `relatorio_stellantis_vs_chinesas.pdf` — relatório executivo (Sumário, SWOT, 3 pilares de recomendação)
- [x] `analise_stellantis_vs_chinesas.md` — documento técnico completo em Markdown
- [x] `base_dados_powerbi_stellantis_vs_chinesas_v3.xlsx` — base de dados final para Power BI, com 6 abas:
  - **Tabela_Modelos** — tabela única (modelo + dados de marca/concorrência mesclados), 29 modelos, 9 marcas
  - **Fato_Vendas** — 29 registros de volume de vendas (anual 2023-2025 + mensal eletrificados 2026)
  - **Market_Share** — 11 indicadores de participação de mercado
  - **Crescimento_YoY** — crescimento ano a ano de 8 marcas (2023→2025)
  - **Panorama_Mercado** — indicadores agregados do mercado total (contexto/denominador)
  - **Fontes** — todas as referências consultadas
- [x] Marcas cobertas: **Stellantis** (Fiat, Jeep, Peugeot, Citroën, Leapmotor) vs. **Chinesas** (BYD, GWM, Chery/Caoa Chery, GAC Aion)

> Nota: essa base substitui as versões anteriores (`base_dados_stellantis_vs_chinesas.xlsx` e `base_dados_powerbi_stellantis_vs_chinesas.xlsx`, sem o "_v3") — use sempre a v3 daqui em diante, é a mais completa e com a Tabela_Concorrencia já mesclada na Tabela_Modelos.

Faltam: repositório GitHub estruturado, apresentação Gamma, dashboard Power BI, e o PDF final consolidado (pode ser o mesmo relatório executivo revisado, ou uma versão "final" que referencie os outros entregáveis).

---

## 1. Etapas do Projeto (ordem recomendada)

### Etapa 1 — Estruturar o repositório no GitHub
1. Criar repositório novo (ex.: `stellantis-vs-chinesas-brasil-2026` ou nome que preferir).
2. Criar a estrutura de pastas abaixo (veja seção 2).
3. Subir os 3 arquivos que já temos.
4. Escrever o `README.md` principal contando a história do desafio (contexto, objetivo, o que foi entregue, como navegar no repo).
5. Fazer commits **separados e com mensagens claras** por etapa (isso é o que mostra o "percurso do desenvolvimento" — não suba tudo de uma vez em um único commit).

> Dica para a vaga de estágio: recrutadores de dados/BI costumam olhar o histórico de commits para entender seu processo de raciocínio, não só o resultado final. Vale a pena documentar decisões no próprio README ou em um `docs/decisoes.md`.

### Etapa 2 — Construir o Dashboard no Power BI
1. Importar `base_dados_powerbi_stellantis_vs_chinesas_v3.xlsx` no Power BI Desktop (as 6 abas viram 6 tabelas).
2. Modelar as tabelas: `Fato_Vendas[Marca]` e `Market_Share[Marca]` se relacionam com `Tabela_Modelos[Marca]` (muitos-para-um). Como a `Tabela_Modelos` tem várias linhas por marca (uma por modelo), o ideal é criar uma tabela `Dim_Marca` enxuta (só marca + grupo, sem duplicar) para ser o lado "1" do relacionamento — posso te ajudar a extrair isso com Power Query se quiser.
3. Criar uma Tabela Calendário (Data) e relacionar com `Fato_Vendas[Data]` para habilitar Time Intelligence (DAX).
4. Criar as páginas de dashboard (estrutura sugerida na seção 4).
5. Exportar um `.pbix` e, se possível, publicar no Power BI Service para gerar um link público/embed.
6. Tirar prints das páginas principais para usar na apresentação Gamma e no README.

### Etapa 3 — Montar a apresentação no Gamma.app
1. Usar o conteúdo da seção 3 deste roteiro como prompt/roteiro de slides para o Gamma.
2. Incluir capturas de tela do dashboard Power BI como imagens dentro dos slides.
3. Exportar a apresentação em PDF e também guardar o link público do Gamma.
4. Subir o PDF da apresentação e o link no repositório GitHub.

### Etapa 4 — Consolidar o PDF final
1. Revisar o `relatorio_stellantis_vs_chinesas.pdf` já criado — ele já serve como o PDF executivo.
2. Opcional: gerar uma versão "PDF final do projeto" que também referencie o link do dashboard Power BI e da apresentação Gamma (posso montar essa versão consolidada quando você tiver os links).

### Etapa 5 — Publicar e finalizar
1. Repositório GitHub público (ou privado com convite para o recrutador, se preferir).
2. Link do dashboard Power BI (Power BI Service) no README.
3. Link/arquivo da apresentação Gamma no README.
4. PDF final anexado na raiz do repositório ou em `docs/`.

---

## 2. Estrutura Sugerida do Repositório GitHub

```
stellantis-vs-chinesas-brasil-2026/
│
├── README.md                          # Visão geral do projeto, contexto do desafio, como navegar
├── LICENSE                            # opcional
│
├── docs/
│   ├── relatorio_executivo.pdf        # PDF final (o que já geramos)
│   ├── analise_tecnica.md             # Documento técnico em Markdown (já gerado)
│   └── apresentacao_gamma.pdf         # Export da apresentação do Gamma
│
├── data/
│   └── base_dados_powerbi_stellantis_vs_chinesas_v3.xlsx   # Base de dados final (6 abas, 9 marcas)
│
├── dashboard/
│   ├── dashboard_stellantis.pbix      # Arquivo Power BI
│   └── prints/                        # Screenshots das páginas do dashboard
│       ├── panorama_mercado.png
│       ├── comparativo_precos.png
│       └── satisfacao_percepcao.png
│
└── prompts/
    └── prompts_utilizados.md          # Log de todos os prompts de IA usados no projeto (Claude, Gemini, Gamma)
```

**Sugestão de README.md (estrutura de seções):**
1. Título e contexto do desafio (copie o enunciado do Google Forms)
2. Objetivo da análise
3. Metodologia (fontes de dados, ferramentas de IA usadas)
4. Principais conclusões (resumo do diagnóstico — 3-5 bullets)
5. Estrutura do repositório (a árvore acima)
6. Links: Dashboard Power BI (Service), Apresentação Gamma, PDF do relatório
7. Ferramentas utilizadas (Claude, Gemini, Power BI, Gamma.app)
8. Autor / contato

---

## 3. Dados e Roteiro para o Gamma.app

Ao colar no Gamma, você pode usar este roteiro de slides como prompt estruturado (o Gamma aceita um "outline" para gerar a apresentação automaticamente).

### Estrutura sugerida de slides (15-16 slides)

1. **Capa** — Título: "Stellantis vs. Montadoras Chinesas: Posicionamento em Elétricos e Híbridos na América do Sul" | Subtítulo: Desafio de Inteligência Competitiva | Seu nome
2. **O Desafio** — Contexto do problema: avanço agressivo das chinesas (BYD, GWM, Chery/Caoa Chery, GAC) no segmento de elétricos/híbridos na América do Sul
3. **Metodologia** — Fontes de dados (ANFAVEA, ABVE, FIPE, sites oficiais), ferramentas de IA usadas (Claude com web search), escopo de marcas analisadas (5 Stellantis vs. 4 chinesas)
4. **Panorama de Mercado** — Stellantis 27% Brasil / 20% América do Sul vs. crescimento de 170-195% a/a do segmento eletrificado (usar prints do Power BI aqui)
5. **Crescimento Ano a Ano — o contraste** — BYD +522% (2023→2025), GWM +271%, Chery/Caoa Chery +127% vs. Jeep -4,98% e Peugeot+Citroën +1,68% no mesmo intervalo
6. **BYD assume a liderança do varejo** — Dado de abril/2026: BYD lidera o varejo geral do Brasil, não só o segmento elétrico
7. **Comparativo de Produtos — Segmento de Entrada** — Fiat Pulse / Peugeot 208-2008 (MHEV) vs. BYD Dolphin Mini / GAC Aion UT (BEV)
8. **Comparativo de Produtos — SUV Médio** — Jeep Compass 4xe (em descontinuação) vs. GWM Haval H6 vs. BYD Song Pro/Plus vs. Chery Tiggo 7 Pro PHEV (317cv, 63km elétricos)
9. **Ranking de Vendas por Categoria** — Top 3 BEV e Híbrido (mostrar que nenhum modelo Stellantis aparece no Top 3)
10. **Rede de Concessionárias** — comparativo Fiat (521) e Peugeot+Citroën (338) vs. BYD (217), GWM (130), GAC (60) — onde a Stellantis ainda vence e onde a distância está encolhendo
11. **Percepção do Consumidor** — Satisfação: BYD líder no ranking Decoupling (8,11); queda da Jeep no Top 10; selo RA1000 da BYD
12. **A Jogada da Stellantis: Aliança com a Leapmotor** — JV 51%, produtos B10/C10, uso da rede Stellantis como diferencial
13. **Matriz SWOT** — Forças, Fraquezas, Oportunidades, Ameaças (resumo visual)
14. **Recomendação em 3 Pilares** — (1) Aceleração da eletrificação robusta, (2) Precificação agressiva no segmento de entrada, (3) Recuperação da percepção de marca/pós-venda
15. **Dashboard Power BI** — Screenshot/link do dashboard interativo
16. **Fechamento** — Conclusão + ferramentas e prompts utilizados no processo

### Prompt sugerido para colar no Gamma.app

```
Crie uma apresentação profissional e executiva sobre "Stellantis vs. Montadoras 
Chinesas: Posicionamento em Elétricos e Híbridos na América do Sul", com tom 
técnico-analítico, para uma banca de avaliação de estágio em uma montadora.

Use a seguinte estrutura de slides: [colar a lista de 16 slides acima]

Dados-chave a destacar:
- Stellantis lidera o mercado geral (27% Brasil / 20% América do Sul) mas fica 
  fora do Top 3 em vendas de elétricos/híbridos
- Entre 2023 e 2025, BYD cresceu +522%, GWM +271% e Chery/Caoa Chery +127%, 
  enquanto Jeep caiu -4,98% e Peugeot+Citroën somadas cresceram só +1,68%
- BYD assumiu a liderança geral do varejo brasileiro em abril/2026 (não só EV)
- Mercado eletrificado cresce 170-195% ao ano, dez vezes mais rápido que o mercado total
- Jeep Compass 4xe (principal PHEV da Stellantis) está sendo descontinuado sem 
  substituto imediato
- GWM Haval H6, BYD Song Pro/Plus e Chery Tiggo 7 Pro PHEV (317cv, 63km de autonomia 
  elétrica) dominam o segmento SUV híbrido médio
- A Fiat ainda tem a maior rede do país (521 concessionárias) mas BYD (217), GWM (130) 
  e GAC (60, marca recém-chegada) crescem rápido em capilaridade
- Stellantis aposta na joint-venture com a Leapmotor (51% de participação) como 
  resposta estratégica
- BYD lidera rankings de satisfação do consumidor (nota 8,11), à frente da própria Jeep

Estilo visual: cores da identidade Stellantis (azul escuro, branco, laranja/dourado 
como destaque), gráficos de barras e comparativos lado a lado, fontes limpas e 
corporativas.
```

---

## 4. Estrutura Sugerida do Dashboard Power BI

### Página 1 — Panorama de Mercado
- Cartões (KPIs): % de mercado Stellantis Brasil, % América do Sul, crescimento do segmento eletrificado (a/a), total de emplacamentos eletrificados no ano (fonte: aba `Panorama_Mercado`)
- Gráfico de barras: evolução mensal de emplacamentos eletrificados por marca (maio → julho/2026), a partir de `Fato_Vendas` filtrado por `Granularidade = Mensal`
- Segmentação (slicer) por `Grupo` (Stellantis vs. Chinesa) aplicável a todas as páginas

### Página 2 — Crescimento Ano a Ano (a página mais forte para o diagnóstico)
- Gráfico de colunas agrupadas: `Crescimento_YoY` — Volume 2023/2024/2025 lado a lado por marca
- Gráfico de barras: % de crescimento 2023→2024 e 2024→2025 por marca, ordenado do maior para o menor (destaque visual para o contraste BYD/GWM/Chery vs. Jeep/Peugeot)
- Cuidado: sinalizar no rodapé do visual quais valores são "CALCULADO" (ver coluna de observação na aba original)

### Página 3 — Comparativo de Produtos (Preço x Tecnologia)
- Tabela/matriz: `Tabela_Modelos` filtrada por Segmento, mostrando Preço, Potência, Autonomia Elétrica e Nível de ADAS lado a lado
- Gráfico de dispersão: Preço x Autonomia Elétrica, colorido por `Grupo`, com cada bolha sendo um modelo — ótimo para visualizar o "custo-benefício elétrico" de cada marca
- Filtro por Segmento (Entrada, SUV Médio, Premium)

### Página 4 — Ranking de Vendas de Eletrificados
- Gráfico de barras horizontais: Top modelos mais vendidos por categoria (BEV / Híbrido), a partir de `Fato_Vendas` (linhas `Mensal`), com destaque visual para a ausência de modelos Stellantis no Top 3
- Comparativo mês a mês (maio vs. julho/2026)

### Página 5 — Rede de Concessionárias e Presença Comercial
- Gráfico de barras: `Concessionárias_Marca` por marca (extraída da `Tabela_Modelos`, uma linha por marca) — mostra onde a Stellantis ainda lidera (Fiat, Peugeot+Citroën) e onde as chinesas avançam rápido (BYD, GWM, GAC)
- Cartão: Ano de chegada ao Brasil por marca chinesa (2017-2021), mostrando como consolidaram rede em pouco tempo

### Página 6 — Satisfação e Percepção de Marca
- Gráfico de barras: nota de satisfação por marca (Decoupling), disponível só para BYD e Jeep na `Tabela_Modelos` — completar com os dados de percepção geral do relatório PDF (interesse por marcas chinesas +515%, importados chineses 37,6%) como cartões de texto
- Destaque textual: queda da Jeep no ranking de satisfação

### Página 7 — Aliança Leapmotor + Recomendações
- Infográfico/tabela: estrutura da JV Stellantis-Leapmotor (51%)
- Cards com os 3 pilares de recomendação estratégica

**Modelo de dados no Power BI:**
- `Tabela_Modelos` é a dimensão principal — 1 linha por modelo, com os dados de marca já embutidos (concessionárias, satisfação, produção local). Para relacionamentos limpos, recomendo extrair via Power Query uma tabela `Dim_Marca` (marca + grupo, sem duplicar) a partir dela, evitando o efeito "muitos-para-muitos" ao relacionar com `Fato_Vendas` e `Market_Share`.
- `Fato_Vendas` relaciona com `Dim_Marca[Marca]` (muitos-para-um) e com uma Tabela Calendário separada via `Data` (para Time Intelligence em DAX).
- `Market_Share` e `Crescimento_YoY` também relacionam com `Dim_Marca[Marca]`.
- `Panorama_Mercado` fica solta, usada só via cartões/KPIs (é contexto de mercado total, não tem chave de marca).

---

## 5. Checklist Final de Entrega

- [ ] Repositório GitHub criado e público com a estrutura da seção 2
- [ ] README.md completo e bem escrito
- [ ] Commits organizados mostrando o percurso (não um único commit final)
- [ ] `base_dados_powerbi_stellantis_vs_chinesas_v3.xlsx` no repositório
- [ ] `relatorio_stellantis_vs_chinesas.pdf` no repositório
- [ ] `analise_stellantis_vs_chinesas.md` no repositório
- [ ] Dashboard Power BI (.pbix) criado e, se possível, publicado no Power BI Service
- [ ] Prints do dashboard salvos em `dashboard/prints/`
- [ ] Apresentação gerada no Gamma.app, exportada em PDF e salva em `docs/`
- [ ] Link do dashboard e da apresentação incluídos no README
- [ ] Prompts de IA documentados em `prompts/prompts_utilizados.md` (exigência do desafio)
- [ ] Revisão final de todos os arquivos antes da entrega

---

## 6. Próximos Passos Imediatos

1. Base de dados fechada e validada (v3, 6 abas, 9 marcas) — ✅ concluído.
2. Você cria o repositório vazio no GitHub e me passa o nome/link (ou eu te ajudo a estruturar os arquivos localmente para você subir).
3. Levamos os dados do Excel para o Power BI — posso te guiar passo a passo na modelagem (incluindo a extração da `Dim_Marca` via Power Query, ver seção 4).
4. Depois de ter os prints do dashboard, voltamos aqui para gerar o prompt final do Gamma já com as imagens referenciadas.
5. Por fim, fechamos o PDF consolidado do projeto com todos os links.

Quer que eu já comece organizando os arquivos localmente na estrutura de pastas do repositório (para você só arrastar para o GitHub), ou prefere ir etapa por etapa comigo pelo Power BI primeiro?
