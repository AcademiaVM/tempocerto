# AVM TempoCerto

Simulador de Horário Gratuito de Propaganda Eleitoral (HGPE) conforme Lei 9.504/97, art. 47, §2º.

Desenvolvido pela **Academia Vitorino & Mendonça** para uso em consultoria de marketing político e como material didático do Imersão Eleições.

## O que faz

Simula a distribuição de tempo de HGPE em rádio e TV entre chapas concorrentes aos cargos de presidente, governador, senador, deputado federal e deputado estadual — aplicando a fórmula legal de 1/3 igualitário + 2/3 proporcional à bancada da Câmara do início da legislatura em curso.

## Como usar

Abra `index.html` em qualquer navegador moderno. Não requer servidor, build ou dependências — é um arquivo HTML único com CSS e JavaScript embutidos.

Para versão publicada: acesse o GitHub Pages do repositório.

## Funcionalidades

- Simulação multi-cargo em uma única circunscrição
- Pré-população automática dos 30 partidos registrados no TSE para eleições proporcionais
- Marcação de federações como bloco atômico (FE Brasil, PSDB/Cidadania, PSOL/Rede)
- Bloqueio jurídico de coligação em dep. federal/estadual (EC 97/2017)
- Bloqueio de duplicidade (partido ou federação em duas chapas concorrentes)
- Cópia de chapas entre cargos (espelhamento governador → senador, etc.)
- Destaque "⭐ Meu candidato" com insights comparativos
- Cenários salvos em localStorage + exportação/importação em JSON
- Agenda estilo Google Agenda com navegação entre meses e detalhes por dia
- Memorial de cálculo completo para auditoria
- Impressão otimizada em PDF

## Base legal e fontes

- **Lei 9.504/97, art. 47, §2º** — fórmula de distribuição de tempo
- **Lei 9.504/97, art. 36** — período de propaganda eleitoral gratuita
- **EC 97/2017** — fim das coligações em eleições proporcionais
- **Lei 9.096/95** — federações partidárias
- Bancada de referência: Câmara dos Deputados, início da legislatura 2023 (eleita em 2022)

## Limitações conhecidas

- Inserções de 30s/60s: valores aproximados. A divisão exata entre cargos é definida pela Resolução do TSE de cada pleito.
- Não cobre 2º turno (regime específico, 10 min/dia entre 2 candidatos).
- Não cobre eleições municipais (prefeito/vereador, regime próprio).
- Tempo por candidato individual não é calculado: o HGPE distribui à legenda; a partição interna é decisão política.

## Estrutura do projeto

```
/
├── index.html          # Versão atual (v4f)
├── README.md           # Este arquivo
├── CHANGELOG.md        # Histórico de versões
├── archive/            # Versões anteriores preservadas
│   ├── v2.html
│   ├── v3.html
│   └── v4a.html ... v4f.html
└── docs/
    └── DECISIONS.md    # Memorial de decisões de produto
```

## Licença

Uso interno AVM. Direitos reservados.
