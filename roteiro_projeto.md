# Roteiro do Projeto — Desafio Stellantis vs. Montadoras Chinesas

**Objetivo final:** Repositório no GitHub documentando todo o percurso + Apresentação no Gamma.app + Dashboard no Power BI + PDF executivo final.

---

## 0. Onde estamos agora (Checkpoint atual)

Já temos prontos:
- [x] `relatorio_stellantis_vs_chinesas.pdf` — relatório executivo (Sumário, SWOT, 3 pilares de recomendação)
- [x] `analise_stellantis_vs_chinesas.md` — documento técnico completo em Markdown
- [x] `base_dados_powerbi_stellantis_vs_chinesas_v4.xlsx` — base de dados final para Power BI, com 6 abas (Tabela_Modelos, Fato_Vendas, Market_Share, Crescimento_YoY, Panorama_Mercado, Fontes), 29 modelos, 9 marcas
- [x] **README.md** e **prompts_utilizados.md** já escritos
- [x] **Dashboard Power BI CONCLUÍDO** — 3 páginas construídas e validadas (ver seção 4 para a estrutura final real, que substitui o plano original de 5-7 páginas). O modelo de dados (Dim_Marca, Calendário, medida `Total_Vendas` corrigida) foi validado com o Claude, e a construção visual das 3 páginas foi finalizada com apoio do Gemini, usando a mesma base v4.
- [x] **Apresentação Gamma CONCLUÍDA** — 8 slides gerados a partir do prompt do roteiro, em PDF (`Stellantis-vs-Montadoras-Chinesas.pdf`). Ver seção 3 para a estrutura final real.
- [ ] Resposta em texto do Cenário 1 do formulário — já redigida, pendente de revisão final e cole no formulário
- [ ] Prints finais das 3 páginas do dashboard salvos em `dashboard/prints/` no repositório
- [ ] PDF final consolidado do projeto (opcional — ver Etapa 4)
- [ ] Documento final com suas próprias palavras/reflexão sobre o projeto (você vai escrever este — ver seção 7)

> **Histórico de versões da base de dados:** v1 (`base_dados_stellantis_vs_chinesas.xlsx`) → v2/v3 (`base_dados_powerbi_stellantis_vs_chinesas_v3.xlsx`, mesclou Tabela_Concorrencia e expandiu marcas) → **v4 (atual, `base_dados_powerbi_stellantis_vs_chinesas_v4.xlsx`)**, que corrigiu uma limitação de pesquisa: as versões anteriores só traziam rankings prontos de "Top 3" de vendas mensais de eletrificados, que não incluíam nenhuma marca Stellantis. A v4 buscou o volume de vendas diretamente por modelo e incluiu dados reais do Jeep Renegade MHEV, além de confirmar que o Jeep Compass 4xe (PHEV) não consta mais na linha 2026 vendida atualmente. **Todo o dashboard foi construído sobre a v4 — é a versão definitiva.**

Faltam: organizar os prints e o `.pbix` no repositório GitHub, e (opcionalmente) o PDF final consolidado. Depois disso, é só publicar.

---

## 1. Etapas do Projeto (ordem recomendada)

### Etapa 1 — Estruturar o repositório no GitHub ✅ CONCLUÍDA
1. [x] Repositório criado com a estrutura de pastas da seção 2.
2. [x] README.md e prompts_utilizados.md escritos e enviados.
3. [ ] Pendente: atualizar `data/` com a base v4, subir `dashboard/dashboard_stellantis.pbix` e os prints das 3 páginas reais.

> Lembrete de commits para essa rodada de upload:
> - `git commit -m "Atualiza base de dados para v4 — inclui volume real de Jeep Renegade MHEV e corrige status do Compass 4xe"`
> - `git commit -m "Adiciona dashboard Power BI finalizado (3 páginas) e prints"`
> - `git commit -m "Atualiza README e roteiro com a estrutura final do projeto"`

### Etapa 2 — Construir o Dashboard no Power BI ✅ CONCLUÍDA

O modelo de dados foi validado (relacionamentos `Dim_Marca` extraída via Referência da `Tabela_Modelos`, tabela `Calendario`, medida `Total_Vendas` corrigida para não contar duas vezes a linha "Peugeot + Citroën (combinado)"). A partir desse modelo validado, três páginas foram construídas — ver a estrutura final completa na **seção 4**, que documenta exatamente o que foi entregue (e substitui o plano original de 5 a 7 páginas por uma versão mais enxuta e consolidada, com 3 páginas bem construídas).

**Nota de processo:** a modelagem de dados (relacionamentos e medidas DAX) foi construída com apoio do Claude; a construção visual final das 3 páginas (gráficos, formatação, tema visual) foi finalizada com apoio do Gemini, usando a mesma base v4 já validada. Isso está registrado em `prompts_utilizados.md` para manter a transparência do processo exigida pelo desafio.

**Dois ajustes finos ainda pendentes (opcionais, não bloqueiam a entrega):**
- Página 3: renomear a coluna "Preço Base R$" para "Preço Base Médio (R$)" e confirmar que o modelo Yuan Pro (sem preço divulgado) não está distorcendo a média da BYD.
- Página 1: o gráfico anual por marca fica dominado visualmente pela barra da Fiat (~521 mil em 2024, único ano com dado disponível) — considerar destacar isso com uma nota, ou isolar a Fiat num cartão à parte.

### Etapa 3 — Montar a apresentação no Gamma.app ✅ CONCLUÍDA
1. [x] Prompt do roteiro (seção 3) usado no Gamma.
2. [x] Apresentação gerada em 8 slides, exportada em PDF (`Stellantis-vs-Montadoras-Chinesas.pdf`).
3. [ ] Pendente: subir o PDF para `docs/apresentacao_gamma.pdf` no repositório e, se o Gamma gerou um link público de compartilhamento, adicioná-lo ao README.

> A estrutura final ficou ligeiramente diferente da sugestão original (o Gamma reorganizou os tópicos à sua maneira, mantendo o limite de 8 slides) — ver a estrutura real na seção 3.

### Etapa 4 — Consolidar o PDF final
1. Revisar o `relatorio_stellantis_vs_chinesas.pdf` já criado — ele já serve como o PDF executivo.
2. Opcional: gerar uma versão "PDF final do projeto" que também referencie o link do dashboard Power BI e da apresentação Gamma, e incorpore os prints reais das 3 páginas (posso montar essa versão consolidada quando você tiver os links/arquivos finais).

### Etapa 5 — Publicar e finalizar
1. Repositório GitHub público (ou privado com convite para o recrutador, se preferir).
2. Link do dashboard Power BI (Power BI Service, se publicado) no README.
3. Link/arquivo da apresentação Gamma no README.
4. PDF final anexado na raiz do repositório ou em `docs/`.
5. Resposta do Cenário 1 revisada e colada no formulário do desafio.

---

## 2. Estrutura do Repositório GitHub (atualizada com os arquivos reais)

```
stellantis-vs-chinesas-brasil-2026/
│
├── README.md                          # Visão geral do projeto, contexto do desafio, como navegar
├── LICENSE                            # opcional
│
├── docs/
│   ├── relatorio_executivo.pdf        # PDF final (Sumário, SWOT, 3 pilares)
│   ├── analise_tecnica.md             # Documento técnico em Markdown
│   ├── resposta_cenario_1.md          # Resposta redigida para o formulário do desafio
│   └── apresentacao_gamma.pdf         # Export da apresentação do Gamma (renomeie Stellantis-vs-Montadoras-Chinesas.pdf para este nome)
│
├── data/
│   └── base_dados_powerbi_stellantis_vs_chinesas_v4.xlsx   # Base de dados final (6 abas, 9 marcas, 29 modelos)
│
├── dashboard/
│   ├── dashboard_stellantis.pbix      # Arquivo Power BI (3 páginas)
│   └── prints/
│       ├── 01_panorama_de_mercado.png
│       ├── 02_evolucao_e_crescimento_de_mercado.png
│       └── 03_comparativo_de_produtos_e_atributos.png
│
└── prompts/
    └── prompts_utilizados.md          # Log de todos os prompts de IA usados no projeto (Claude + Gemini)
```

**Estrutura do README.md:**
1. Título e contexto do desafio (copie o enunciado do Google Forms)
2. Objetivo da análise
3. Metodologia (fontes de dados, ferramentas de IA usadas — Claude para pesquisa/dados/relatórios, Gemini para construção visual final do dashboard)
4. Principais conclusões (resumo do diagnóstico — 3-5 bullets, ver README atualizado)
5. Estrutura do repositório (a árvore acima)
6. Links: Dashboard Power BI (Service), Apresentação Gamma, PDF do relatório
7. Ferramentas utilizadas (Claude, Gemini, Power BI, Gamma.app, GitHub)
8. Autor / contato

---

## 3. Apresentação Gamma — Estrutura Final (conforme entregue)

> Esta seção documenta os 8 slides realmente gerados pelo Gamma a partir do prompt abaixo — o Gamma reorganizou os tópicos à sua maneira, mas manteve o limite de 8 slides e cobriu todos os dados-chave pedidos.

### Slides entregues

1. **Capa** — "Stellantis vs. Montadoras Chinesas: Posicionamento em Elétricos e Híbridos na América do Sul — Análise Estratégica de Mercado" (Análise Executiva 2025)
2. **Cenário de Mercado: Participação e Volume (2025)** — Gráfico de rosca (donut) Stellantis 64,81% vs. Chinesas 35,19%; cartões com 956,19 mil (Stellantis) e 518,89 mil (Chinesas) unidades, volume total de 1,48 milhões
3. **Dinâmica de Crescimento: 2024 → 2025** — Gráfico de barras horizontais (GWM +46%, BYD +45,4%, Chery/CAOA +17,2%, Citroën +17,2%, Peugeot -16,9%) com 3 cartões de destaque textual
4. **Liderança de Mercado: BYD Assume Posição Estratégica** — Liderança no varejo geral (abr/2026), satisfação do consumidor (BYD 8,11 vs. Jeep), avanço no segmento premium-médio (R$ 170k-250k)
5. **Portfólio Stellantis: Descontinuação e Resposta** — 3 pontos numerados: Compass 4xe descontinuado, Renegade MHEV como resposta real, Leapmotor como aposta estrutural (51%)
6. **Análise Competitiva: Tecnologia e Posicionamento** — Diagrama comparativo de atributos (chinesas: potência/ADAS/preço/crescimento; Stellantis: herança SUV/MHEV/rede/portfólio BEV limitado) + 3 cartões de risco/força
7. **Estratégia Stellantis: Consolidação e Inovação** — 3 pilares em fluxo circular (Ponte MHEV → Expansão Leapmotor → Impulso Mid-Premium), com texto de alerta sobre velocidade de execução
8. **Conclusões e Implicações Estratégicas** — Crescimento assimétrico, risco de erosão, resposta necessária mas insuficiente, com implicação central em destaque (risco de a Stellantis passar de líder para seguidor defensivo)

**Arquivo final:** `Stellantis-vs-Montadoras-Chinesas.pdf`

### Prompt utilizado no Gamma.app

```
Crie uma apresentação profissional e executiva de NO MÁXIMO 8 SLIDES sobre 
"Stellantis vs. Montadoras Chinesas: Posicionamento em Elétricos e Híbridos na 
América do Sul", com tom técnico-analítico, para uma banca de avaliação de 
estágio em uma montadora. Respeite o limite de 8 slides — combine tópicos 
relacionados no mesmo slide em vez de criar slides adicionais.

Dados-chave a destacar (extraídos do dashboard Power BI já construído):
- Volume total analisado: 1,48 Mi de unidades — Stellantis com 956,19 Mil (~64,6%) 
  vs. Chinesas com 518,89 Mil (~35,4%) no recorte de marcas analisado
- Crescimento 2024→2025: GWM +46%, BYD +45,4%, Chery/Caoa Chery +17,24%, 
  Citroën +17,16%, Peugeot -16,88%
- BYD assumiu a liderança geral do varejo brasileiro em abril/2026 (não só EV)
- Jeep Compass 4xe (principal PHEV da Stellantis) está sendo descontinuado sem 
  substituto imediato, mas o Jeep Renegade MHEV surge como resposta real, com 
  volume mensal comparável ao BYD Song Pro/Plus
- Modelos chineses entregam mais potência e pacotes ADAS mais completos na 
  faixa de R$ 170 mil a R$ 250 mil, pressionando os SUVs médios tradicionais
- Stellantis aposta na joint-venture com a Leapmotor (51% de participação) como 
  resposta estratégica em BEV/REEV
- BYD lidera rankings de satisfação do consumidor (nota 8,11), à frente da própria Jeep

Estilo visual: cores da identidade Stellantis (azul escuro, branco, laranja/dourado 
como destaque), gráficos de barras e comparativos lado a lado, fontes limpas e 
corporativas — mantendo consistência visual com o dashboard Power BI já construído 
(fundo azul escuro com elementos gráficos ondulados).
```

---

## 4. Estrutura Final do Dashboard Power BI (conforme construído)

> Esta seção substitui o plano original de 5-7 páginas — na prática, o dashboard foi consolidado em **3 páginas** mais densas e completas, o que é uma solução igualmente válida (e mais direta de navegar).

### Página 1 — Panorama de Mercado
- **Cartões (KPIs):** Total de Vendas (1,48 Mi), Venda Stellantis (956,19 Mil), Vendas_Chinesas (518,89 Mil)
- **Gráfico de colunas agrupadas:** "Soma de Unidades_Vendidas por Ano e Marca" — todas as 7 marcas com dado anual (BYD, Chery/Caoa Chery, Citroën, Fiat, GWM, Jeep, Peugeot), 2023 a 2026
- **Slicer:** `Grupo` (Stellantis vs. Chinesa)
- *Ajuste fino pendente:* considerar destacar/isolar a barra da Fiat (521 mil em 2024) para não dominar visualmente a comparação entre as demais marcas

### Página 2 — Evolução e Crescimento de Mercado (2023-2025)
- **Gráfico de barras horizontais:** "Taxa de Crescimento Ano a Ano (%)" — GWM +46,00%, BYD +45,40%, Chery/Caoa Chery +17,24%, Citroën +17,16%, Peugeot -16,88% (2024→2025)
- **Gráfico de colunas agrupadas:** "Volume de Vendas Anual por Marca (Unidades)" — Volume 2023/2024/2025 lado a lado, por marca
- **Slicer:** `Grupo` (Stellantis vs. Chinesa)
- Esta é a página mais forte para o diagnóstico central do projeto: mostra visualmente o contraste entre o crescimento acelerado das chinesas e o desempenho misto da Stellantis

### Página 3 — Comparativo de Produtos e Atributos
- **Tabela/matriz:** Marca x Preço Base R$ (médio) x Potência (CV, médio) x Autonomia Elétrica (km) x Assistência ADAS — todas as 9 marcas, com expansão por modelo (ex: BYD expandido mostra Yuan Pro)
- **Gráfico de barras empilhadas:** "Tipos de Motores" por marca — contagem de modelos por `Tipo_Motor` (BEV, PHEV, MHEV, Flex, HEV), evidenciando o contraste entre o portfólio eletrificado das chinesas e o portfólio ainda majoritariamente Flex/MHEV da Stellantis
- **Gráfico de dispersão:** "Relação Preço Base vs. Potência (CV)", colorido por `Grupo`, tamanho da bolha proporcional — visualiza o custo-benefício de cada modelo
- **Slicers:** `Grupo` e `Segmento`

### Modelo de dados usado (válido para as 3 páginas)
- `Dim_Marca` extraída via Referência da `Tabela_Modelos` (9 linhas, sem duplicar)
- `Fato_Vendas[Marca]`, `Market_Share[Marca]` e `Crescimento_YoY[Marca]` relacionados com `Dim_Marca[Marca]` (muitos-para-um)
- `Fato_Vendas[Data]` relacionado com uma tabela `Calendario` separada
- Medida `Total_Vendas` com filtro `NOT CONTAINSSTRING(Fato_Vendas[Marca], "combinado")` para evitar contagem duplicada da linha "Peugeot + Citroën (combinado)"

---

## 5. Checklist Final de Entrega

- [ ] Repositório GitHub criado e público com a estrutura da seção 2
- [ ] README.md completo e atualizado com a estrutura final (3 páginas de dashboard + apresentação)
- [ ] Commits organizados mostrando o percurso (não um único commit final)
- [x] `base_dados_powerbi_stellantis_vs_chinesas_v4.xlsx` pronto para o repositório
- [x] `relatorio_stellantis_vs_chinesas.pdf` pronto para o repositório
- [x] `analise_stellantis_vs_chinesas.md` pronto para o repositório
- [x] Dashboard Power BI (.pbix) construído — 3 páginas finalizadas
- [ ] `dashboard_stellantis.pbix` e os 3 prints salvos em `dashboard/prints/` no repositório
- [x] Apresentação gerada no Gamma.app, exportada em PDF (`Stellantis-vs-Montadoras-Chinesas.pdf`)
- [ ] PDF da apresentação salvo em `docs/apresentacao_gamma.pdf` no repositório
- [ ] Link do dashboard (se publicado no Power BI Service) e da apresentação (se houver link público do Gamma) incluídos no README
- [x] Prompts de IA documentados em `prompts/prompts_utilizados.md` (exigência do desafio)
- [ ] Resposta do Cenário 1 revisada e colada no formulário
- [ ] Seu documento de reflexão final escrito (ver seção 7)
- [ ] Revisão final de todos os arquivos antes da entrega

---

## 6. Próximos Passos Imediatos

1. Base de dados v4 fechada e validada — ✅ concluído.
2. Repositório GitHub estruturado com README e log de prompts — ✅ concluído.
3. Dashboard Power BI construído (3 páginas) — ✅ concluído.
4. Apresentação Gamma gerada (8 slides, PDF) — ✅ concluído.
5. **Agora:** organizar os arquivos finais na estrutura de pastas da seção 2 (`.pbix`, 3 prints, PDF da apresentação) e subir tudo para o GitHub, junto com a base v4.
6. Revisar e colar a resposta do Cenário 1 no formulário do desafio.
7. Escrever seu documento de reflexão final (ver seção 7) — este é o único item que só você pode escrever.
8. Fazer os commits organizados (ver os comandos sugeridos na Etapa 1) e publicar o repositório.

---

## 7. Seu Documento Final (nas suas palavras)

Esse é o passo que fecha o projeto: um texto curto, escrito por você, contando o percurso — não é mais um entregável técnico, é a sua voz explicando o que foi feito e por quê. Pode virar o corpo da resposta do Cenário 1 no formulário, um `docs/reflexao_final.md` no repositório, ou as duas coisas.

Algumas perguntas que podem ajudar a estruturar esse texto, caso queira um ponto de partida:
- Por que você escolheu comparar essas marcas específicas (Stellantis multimarca vs. BYD/GWM/Chery/GAC) em vez de só uma marca de cada lado?
- Qual foi o achado que mais te surpreendeu ao longo da pesquisa? (ex: a queda de satisfação da Jeep, o Compass 4xe saindo de linha, o crescimento de 45-46% das chinesas)
- Como você usou as ferramentas de IA de forma crítica — não só pedindo respostas prontas, mas validando, corrigindo (ex: os erros de contagem duplicada que você mesmo identificou nos prints) e cruzando fontes?
- Se você estivesse na cadeira de um gestor de produto da Stellantis, qual dos 3 pilares de recomendação você priorizaria primeiro, e por quê?

Quando tiver esse texto pronto, me manda que posso revisar a coerência com os dados do projeto antes de você finalizar.
