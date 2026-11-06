# Simulador de Entregas: Meadowfield

Projeto desenvolvido para a disciplina de **Autoração Multimídia 2**, do curso de **Sistemas e Mídias Digitais**.

O projeto é uma reinterpretação visual e interativa do clássico exercício **"A Robot"**, do livro [Eloquent JavaScript](https://eloquentjavascript.net/), de Marijn Haverbeke. A ideia original — um robô que se move por um mapa de vilarejo entregando encomendas — foi transformada em uma simulação gráfica rodando em **HTML5 Canvas**, com controles interativos para escolher o algoritmo do robô e acompanhar a simulação em tempo real.

## 🎯 Sobre o projeto

A aplicação simula a vila fictícia de **Meadowfield**, representada como um grafo de locais conectados por estradas (casas, correio, prefeitura, mercado, etc.). Encomendas são geradas aleatoriamente, cada uma com um local de origem e um endereço de destino, e um robô percorre o mapa entregando-as.

O usuário pode escolher entre três algoritmos/estratégias de robô:

- **Aleatório (Random)** — o robô se move para um local vizinho escolhido ao acaso a cada passo.
- **Rota Fixa (Route)** — o robô segue uma rota pré-definida que passa por todos os locais da vila.
- **Inteligente (Pathfinder)** — o robô calcula o caminho mais curto até a encomenda/destino mais próximo usando busca em grafo (BFS).

Durante a simulação, a interface exibe:
- O **mapa** desenhado em canvas, com os locais, estradas, o robô e as encomendas sendo movimentados visualmente;
- O **número de passos** dados até o momento;
- A **quantidade de encomendas restantes**;
- Um **log de ações** em tempo real (movimentações e entregas realizadas).

## 🛠️ Tecnologias utilizadas

- **HTML5** — estrutura da página e elemento `<canvas>` para o mapa
- **CSS3** — estilização complementar do canvas e do log de ações
- **[Tailwind CSS](https://tailwindcss.com/)** (via CDN) — estilização da interface (painéis, botões, layout)
- **JavaScript puro (vanilla JS)** — toda a lógica da simulação: modelagem do grafo da vila, estado imutável (`VillageState`), algoritmos dos robôs, busca de rota (BFS) e renderização no canvas

Não há dependências de back-end, build tools ou pacotes externos — o projeto roda inteiramente no navegador.

## 📁 Estrutura de arquivos

```
├── index.html     # Estrutura da página e interface de controles
├── script.js       # Lógica da simulação (modelo, robôs e renderização no canvas)
├── style.css       # Estilos complementares (canvas e log de ações)
└── assets/          # Imagens usadas no mapa (robô, encomendas, casas, prédios etc.)
```

> ⚠️ A pasta `assets/` com as imagens (`robot.png`, `parcel.png`, `house.png`, `cabin.png`, `townhall.png`, `postoffice.png`, `marketplace.png`, `shop.png`) precisa estar presente no repositório/pasta do projeto para que o mapa seja desenhado corretamente.

## ✅ Pré-requisitos

Como o projeto é 100% front-end (HTML, CSS e JavaScript puro), não é necessário instalar Node.js, dependências ou qualquer ferramenta de build. Você só precisa de:

- Um **navegador web moderno** (Chrome, Edge, Firefox etc.);
- **Conexão com a internet**, pois o Tailwind CSS é carregado via CDN (`cdn.tailwindcss.com`) diretamente no `index.html`.

## ▶️ Como rodar o projeto

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/YuriCardosoSMD/AM2-Projeto_de_Desenvolvimento_Web.git
   cd AM2-Projeto_de_Desenvolvimento_Web
   ```

2. **Abra o arquivo `index.html` diretamente no navegador** — basta dar duplo clique nele ou arrastá-lo para uma aba do navegador.

   *(Opcional)* Para evitar eventuais restrições do navegador ao carregar arquivos locais, você também pode servir a pasta com um servidor estático simples, por exemplo:
   ```bash
   npx serve .
   ```
   ou, com Python instalado:
   ```bash
   python -m http.server
   ```
   e então acessar o endereço exibido no terminal (ex: `http://localhost:8000`).

3. **Use a simulação:**
   - Escolha o algoritmo do robô no menu suspenso (**Aleatório**, **Rota Fixa** ou **Inteligente**);
   - Clique em **Iniciar** para começar a simulação;
   - Acompanhe o mapa, o contador de passos, as encomendas restantes e o log de ações;
   - Clique em **Resetar** para gerar um novo cenário e recomeçar.

## 📌 Observações

- Este projeto tem finalidade **acadêmica**, sendo uma atividade da disciplina de Autoração Multimídia 2.
- A base conceitual (grafo da vila, estado imutável e algoritmos dos robôs) é inspirada diretamente no exercício "A Robot" do livro *Eloquent JavaScript*, com a adição de uma interface gráfica interativa e renderização visual em canvas.
