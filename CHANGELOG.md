# Changelog

Todas as mudanças relevantes neste projeto.

## [v4f] — 2026-04-13

### Alterado
- Após salvar um cenário, o usuário é redirecionado automaticamente para a home (tela de cenários)

## [v4e] — 2026-04-13

### Adicionado
- Agenda estilo Google Agenda com grade mensal navegável (agosto, setembro, outubro de 2026)
- Botões de navegação entre meses (‹ Anterior, HGPE, Próximo ›)
- Modal detalhado ao clicar em qualquer dia útil, com horários (📻 07:00, 12:00; 📺 13:00, 20:30) e bolo por cargo
- Destaque especial para 04/out (dia do 1º turno) em dourado

### Corrigido
- Impressão em PDF: CSS @media print reescrito com @page A4, print-color-adjust exato, page-breaks corretos entre abas, forçando display do sc3 e ocultando demais telas
- prepPrint() agora guarda e restaura a aba ativa após impressão

## [v4d] — 2026-04-13

### Adicionado
- UI específica para dep. federal/estadual: pré-popula com os 30 partidos registrados no TSE + 3 federações como blocos atômicos, todas ativadas por padrão
- Premissa realista "todos disputam" para eleições proporcionais (usuário desmarca quem não terá candidato)
- Marcação "⭐ Meu candidato" destacando a chapa nos resultados com fundo amarelo e ícone
- Banner de insight no resultado: posição do meu candidato no ranking e gap para o líder
- Botões rápidos: Marcar todos, Desmarcar todos, Só com bancada > 0

### Corrigido
- Bug conceitual: antes, calcular tempo proporcional com só 1 ou 2 partidos marcados gerava números irrealistas (partido único levava o bolo inteiro)

## [v4c] — 2026-04-13

### Adicionado
- Bloqueio de federação já usada em outra chapa (antes, só partido individual era bloqueado)
- Campo editável de nome da chapa no header de cada chapa
- Separação visual de Rádio (2 blocos: 7h e 12h) e TV (2 blocos: 13h e 20h30) na tabela de resultado
- Agenda diária do HGPE 2026 (27/ago a 01/out), com 4 blocos por dia útil

### Corrigido
- Função prepPrint() para garantir impressão com todas as abas abertas e details expandido

## [v4b] — 2026-04-13

### Adicionado
- Botão "📋 Copiar para..." em cada chapa, para mover entre cargos
- Botão "⇄ Espelhar de..." no canvas do cargo, para replicar todas as chapas de outro cargo
- Adaptação automática na cópia: coligações majoritárias são desmembradas em chapas individuais quando copiadas para cargos proporcionais (dep. fed./est.)
- Federações mantidas como bloco único em todas as cópias

## [v4a] — 2026-04-13

### Adicionado
- Tela home com lista de cenários salvos
- Persistência em localStorage
- Exportação/importação de cenários em JSON
- Dois templates pré-carregados (SP 2026 base; Presidência 2026 com 4 chapas)
- Granularidade escolhida pelo usuário na hora de salvar (UF completa ou UF + 1 cargo)
- Barra de nome do cenário ativo com indicador de salvo/modificado
- Passo "⌂ Cenários" adicionado ao stepper

## [v3] — 2026-04-13

### Alterado (UX completa)
- Fluxo redesenhado em 3 passos guiados: Configurar → Montar chapas → Resultado
- Passo 2 com sidebar vertical de cargos + canvas à direita (um cargo por vez)
- Passo 3 com calendário hero + abas por cargo + memorial em details colapsável
- Bancada da Câmara movida para modal acessível por botão
- Cargos como cards ilustrados com ícone
- Busca de partidos dentro de cada chapa
- Federação como bloco atômico (marcar/desmarcar afeta todos os membros)

### Adicionado
- Seletor de ano da bancada (2022 para pleito 2026; 2026 para pleito 2030)
- Inserções de 30s/60s integradas ao cálculo e à tabela de resultado
- Nota explícita de que presidente é circunscrição nacional

### Removido
- Cálculo de tempo por candidato individual (conceitualmente incorreto: HGPE distribui à legenda, não ao candidato)

## [v2] — 2026-04-13

### Primeira versão multi-cargo
- Simulação simultânea de até 5 cargos (presidente, governador, senador, dep. federal, dep. estadual)
- Configuração de chapas por cargo
- Calendário visual da semana-tipo
- Lista completa dos 30 partidos TSE com bancada editável
- Marcação de federações dentro de cada chapa
- Bloqueio de coligação para dep. federal/estadual
- Bloqueio do mesmo partido em chapas concorrentes
- Memorial de cálculo passo a passo
