# Memorial de decisões de produto

Registro das decisões tomadas no desenvolvimento, para referência futura.

## Decisões conceituais

### Não calcular tempo por candidato individual
**Decisão:** remover o cálculo.
**Razão:** o HGPE distribui tempo à legenda, não ao candidato. A partição entre os nomes lançados é decisão política interna — tipicamente concentrada em poucos puxadores, não dividida em média aritmética. Fazer "tempo da legenda ÷ número de candidatos" produz números que induzem ao erro (ex.: 42s ÷ 70 = 0,6s, que não representa nada da realidade).

### Proporcionais usam modelo "opt-out" com 30 partidos pré-carregados
**Decisão:** para dep. federal e estadual, todas as unidades vêm ativadas por padrão.
**Razão:** em qualquer eleição estadual brasileira, praticamente todos os partidos com estrutura lançam candidatos a deputado. Modelo "opt-in" (só entra quem o usuário marca) produzia cenários irrealistas — se você marcasse só o PT, o app calculava como se o PT fosse o único disputante e levasse o bolo inteiro.

### Federação como bloco atômico
**Decisão:** marcar uma federação adiciona todos os membros de uma vez; não permite desmarcar membros individualmente.
**Razão:** federação é registrada no TSE como bloco único. "FE Brasil sem o PV" não existe juridicamente.

### Presidente em UF estadual
**Decisão:** manter simulável junto com cargos estaduais, com nota explicativa.
**Razão:** embora a circunscrição seja nacional, o usuário tipicamente quer ver "o HGPE do dia em SP" incluindo o bloco presidencial que vai ao ar lá.

## Decisões de escopo

### Não cobrimos 2º turno (por enquanto)
**Razão:** regime completamente diferente (10 min/dia entre 2 candidatos). Merece tratamento próprio, não cabe estender o modelo atual.

### Não cobrimos eleições municipais (por enquanto)
**Razão:** regime próprio (5 min/dia no 1º turno; só TV em algumas praças). Produto hoje é "nacional + estadual".

### Inserções com valores aproximados
**Razão:** a divisão exata entre cargos é definida pela Resolução do TSE de cada pleito. Usamos aproximação didática (70min rádio + 70min TV por dia, divididos proporcionalmente).

## Decisões de UX

### Stepper de 3 passos (+ home)
**Razão:** formulário único era opressor. Separar em Configurar → Montar → Resultado dá ritmo e reduz carga cognitiva.

### Sidebar vertical no passo 2
**Razão:** 5 cargos lado a lado viraria scroll infinito. Navegação lateral permite focar em um cargo por vez, com indicador visual (bolinha verde) de progresso.

### Calendário como hero do passo 3
**Razão:** é o elemento mais visualmente atrativo e contextualiza imediatamente o "quando" antes do "quanto".

### Agenda estilo Google Agenda (v4e)
**Razão:** tabela rolável funcionava mas não era convidativa. Grade mensal clicável com modal por dia é metáfora que qualquer usuário reconhece instantaneamente.

### Cópia de chapas entre cargos (v4b)
**Razão:** solicitação de quem usa na prática. Governador e senador tipicamente têm a mesma coligação; duplicar manualmente é perda de tempo. A adaptação automática (coligação → chapas individuais em cargos proporcionais) resolve a assimetria jurídica.

### Destaque "⭐ Meu candidato"
**Razão:** o caso de uso real é "quanto meu cliente vai ter comparado aos adversários?". Sem destaque, o usuário se perde entre 28 unidades na tabela.

## Decisões técnicas

### HTML único
**Razão:** portabilidade máxima. Sem build, sem dependências, sem servidor. Entrega via e-mail, WhatsApp, Google Drive ou GitHub Pages indiferentemente.

### localStorage + JSON export/import
**Razão:** atende uso pessoal (localStorage) e compartilhamento entre máquinas (JSON). Não requer backend.

### Sem framework
**Razão:** o app não justifica a complexidade de React/Vue. Vanilla JS com manipulação direta do DOM é suficiente e mantém o arquivo único.

## Decisões pendentes (próximas versões)

- **Comparar 2 cenários lado a lado** (previsto para Rodada B)
- **Card de insights automáticos** (previsto para Rodada B)
- **Card de tradução em peças** ("seu tempo dá para X VTs de 30s") (previsto para Rodada B)
- **Modos simples/avançado/auditoria** (previsto para Rodada C)
- **Mobile decente** (previsto para Rodada C)
- **2º turno** e **eleições municipais** (sem prazo)
