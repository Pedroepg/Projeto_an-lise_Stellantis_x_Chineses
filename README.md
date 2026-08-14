# Stellantis vs. Montadoras Chinesas — Posicionamento em Elétricos e Híbridos na América do Sul

> Desafio Prático de Inteligência Competitiva — Processo Seletivo de Estágio, Stellantis
> Análise de posicionamento de mercado usando ferramentas de IA (Claude, Anthropic)

---

## 📋 Contexto do Desafio

A Stellantis opera diversas marcas na América do Sul (Fiat, Jeep, Peugeot, Citroën, Leapmotor). Fabricantes chinesas — como BYD, GWM, Chery/Caoa Chery e GAC — vêm expandindo rapidamente sua presença na região, especialmente nos segmentos de veículos elétricos e híbridos.

**Tarefa:** utilizando ferramentas de IA, pesquisar e analisar como as marcas da Stellantis na América do Sul estão atualmente posicionadas em relação aos concorrentes chineses no segmento de elétricos/híbridos, considerando preço, disponibilidade de produtos, percepção do consumidor e participação de mercado.

## 🎯 Objetivo da Análise

Diagnosticar a posição competitiva real da Stellantis frente ao avanço chinês no segmento eletrificado e propor recomendações estratégicas acionáveis, com base exclusivamente em dados públicos verificáveis — sem estimativas genéricas ou dados desatualizados.

## 🔍 Metodologia

- **Fontes de dados:** FENABRAVE, ANFAVEA, ABVE, Tabela FIPE (Webmotors/Mobiauto), sites oficiais das marcas (Stellantis Media, BYD Brasil, GWM Brasil, CAOA Chery, GAC), relatório oficial da Stellantis N.V. (SEC Form 6-K), estudos de satisfação do consumidor (Decoupling/Harvard-methodology, Reclame Aqui) e imprensa especializada do setor automotivo.
- **Ferramenta de IA:** Claude (Anthropic), com busca na web em tempo real, usado para pesquisa, estruturação de dados e geração dos entregáveis. Ver [`prompts/prompts_utilizados.md`](prompts/prompts_utilizados.md) para o log completo.
- **Escopo de marcas:**
  - **Stellantis:** Fiat, Jeep, Peugeot, Citroën, Leapmotor (joint-venture, 51% Stellantis)
  - **Chinesas:** BYD, GWM (Haval/Ora/Wey), Chery/Caoa Chery (Tiggo/Jaecoo), GAC Aion
- **Princípio de dados:** todo dado quantitativo tem fonte pública identificada. Valores calculados a partir de variações percentuais divulgadas (quando o número absoluto não foi encontrado) estão sinalizados explicitamente como "CALCULADO" na base de dados — nenhum número foi inventado ou estimado sem base documentada.

## 📊 Principais Conclusões

1. **A liderança da Stellantis é real, mas está fora do segmento que mais cresce.** O grupo lidera o mercado geral (27% Brasil / 20% América do Sul), mas nenhum modelo Stellantis apareceu no Top 3 de vendas de elétricos/híbridos nos meses pesquisados de 2026.
2. **O ritmo de crescimento é assimétrico.** Entre 2023 e 2025, BYD cresceu +522%, GWM +271% e Chery/Caoa Chery +127%, enquanto a Jeep caiu -4,98% e Peugeot+Citroën somadas cresceram apenas +1,68%.
3. **O principal produto híbrido da Stellantis está saindo de linha.** O Jeep Compass 4xe (PHEV) está sendo descontinuado sem substituto imediato, justamente enquanto GWM Haval H6, BYD Song Pro/Plus e Chery Tiggo 7 Pro PHEV dominam o segmento de SUV médio eletrificado.
4. **A percepção de risco do "carro chinês" está sendo derrubada.** A BYD lidera rankings de satisfação do consumidor (nota 8,11 no estudo Decoupling), à frente da própria Jeep, e recebeu o selo RA1000 do Reclame Aqui.
5. **A resposta estratégica já está em curso.** A aliança da Stellantis com a Leapmotor (51% de participação na joint-venture) é a aposta mais relevante do grupo para reduzir essa distância no segmento elétrico.

O diagnóstico completo, a matriz SWOT e as recomendações em 3 pilares estão no [Relatório Executivo](docs/relatorio_executivo.pdf).

## 🗂️ Estrutura do Repositório

```
stellantis-vs-chinesas-brasil-2026/
│
├── README.md                          # Este arquivo
│
├── docs/
│   ├── relatorio_executivo.pdf        # Relatório executivo (Sumário, SWOT, recomendações)
│   ├── analise_tecnica.md             # Documento técnico completo em Markdown
│   └── apresentacao_gamma.pdf         # Apresentação exportada do Gamma.app
│
├── data/
│   └── base_dados_powerbi_stellantis_vs_chinesas_v3.xlsx   # Base de dados (6 abas, 9 marcas, 29 modelos)
│
├── dashboard/
│   ├── dashboard_stellantis.pbix      # Arquivo Power BI
│   └── prints/                        # Screenshots das páginas do dashboard
│
└── prompts/
    └── prompts_utilizados.md          # Log de todos os prompts de IA usados no projeto
```

## 🔗 Links

- 📊 **Dashboard Power BI:** _[a preencher após publicação no Power BI Service]_
- 🎤 **Apresentação Gamma:** _[a preencher após geração]_
- 📄 **Relatório Executivo (PDF):** [`docs/relatorio_executivo.pdf`](docs/relatorio_executivo.pdf)

## 🛠️ Ferramentas Utilizadas

| Ferramenta | Uso no projeto |
|---|---|
| **Claude (Anthropic)** | Pesquisa de dados via web search, análise, estruturação da base de dados e geração dos relatórios |
| **Microsoft Excel** | Base de dados estruturada para modelagem dimensional |
| **Power BI** | Dashboard interativo de visualização dos dados |
| **Gamma.app** | Geração da apresentação executiva |
| **GitHub** | Versionamento e documentação do percurso do projeto |

## 👤 Autor

Pedro Eduardo — Estudante de Sistemas de Informação, candidato ao Programa de Estágio Stellantis (área de Elétricos & Híbridos / Dados / BI)

---

*Este projeto foi desenvolvido como parte de um desafio prático de inteligência competitiva. Todos os dados foram coletados de fontes públicas entre julho e agosto de 2026 — ver [`data/`](data/) para a base completa e fontes.*
