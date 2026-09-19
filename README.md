# Busca Heurística - Rota de Emergência Urbana

**AT2 - Inteligência Artificial**

Aplicação web interativa que implementa uma Busca Heurística para encontrar a rota entre uma **Base de Atendimento** e um **Hospital Central** através de uma rede de vias urbanas fictícia.

## Objetivo

Demonstrar o funcionamento da Busca Heurística com visualização animada passo a passo, mostrando como a função heurística h(n) influencia as decisões do algoritmo durante a exploração do grafo.

## Como Executar

### Opção 1: Abrir diretamente no navegador
Basta abrir o arquivo `index.html` em qualquer navegador moderno (Chrome, Firefox, Edge).

### Opção 2: Servidor local (recomendado)
```bash
# Com npx (Node.js)
npx http-server . -p 8080

# Ou com Python
python -m http.server 8080
```
Acesse `http://localhost:8080` no navegador.

## Como Usar

1. **Executar Automático** - Roda a busca completa com animação
2. **Passo a Passo** - Avança um passo por clique
3. **Reset** - Reinicia a busca
4. **Comparar Heurísticas** - Executa com heurística original e modificada, exibindo análise comparativa

### Trocar Heurística
Use o seletor no painel de controle para alternar entre:
- **Original** - Valores baseados em distância estimada
- **Modificada** - Valores alterados propositalmente

### Velocidade
Ajuste o slider para controlar a velocidade da animação (100ms a 1500ms).

## Estrutura do Projeto

```
AT2-IA/
├── index.html            ← Página principal
├── css/
│   └── style.css         ← theme 
├── js/
│   ├── graph.js          ← Grafo: estados, conexões, heurísticas
│   ├── search.js         ← Algoritmo Greedy Best-First Search
│   ├── visualization.js  ← Renderização Cytoscape.js
│   └── app.js            ← Orquestrador e interface
├── docs/
│   └── relatorio.md      ← Relatório completo do projeto
└── README.md             ← Este arquivo
```

## Algoritmo

**Greedy Best-First Search** com:
- Seleção por **menor h(n)** entre todos os estados disponíveis
- **Desempate por ordem alfabética**
- Controle de estados visitados para evitar ciclos
- Registro de predecessores para reconstrução do caminho

## Grafo

- **12 estados** com nomes urbanos (Base, Centro, Rodoviária, Parque, Shopping, Universidade, Terminal, Ponte, Aeroporto, Hospital, Estádio, Praça)
- **16 conexões** direcionadas
- **3+ caminhos** distintos entre origem e destino
- **1 beco sem saída** (Aeroporto)
- **1 caminho enganoso** (Centro → Shopping → Terminal)

## Tecnologias

- **HTML5** — Estrutura semântica
- **CSS3** — Dark theme com glassmorphism e animações
- **JavaScript** — Lógica do algoritmo e interface
- **Cytoscape.js** — Visualização interativa do grafo
- **Google Fonts** — Tipografia Inter

## Licença

Projeto acadêmico — AT2 Inteligência Artificial.
