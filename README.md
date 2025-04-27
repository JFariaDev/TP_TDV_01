# TP_TDV_01
Este trabalho prático corresponde à análise da implementação de um jogo2D recolhido nos meios técnicos disponíveis (GIT).

Pac-Man Clone - Projeto em MonoGame

Descrição Geral:
-----------------
Recriação do clássico Pac-Man usando MonoGame e C#. Este projeto explora movimentação de personagens, colisões, IA básica de inimigos e desenho de mapas baseados em matrizes.

Controles:
----------
- Setas direcionais: movimentar o Pac-Man.

Estrutura de Código e Descrição das Classes:
--------------------------------------------

1. Game1.cs
-----------
Classe principal que gere o ciclo de vida do jogo.

Funções:
- **Initialize()**: 
  - Inicializa as variáveis e estados do jogo.
- **LoadContent()**: 
  - Carrega os recursos (imagens, fontes, sons) necessários para o jogo.
- **Update(GameTime gameTime)**:
  - Atualiza a lógica do jogo a cada frame (input, movimentação, colisões).
- **Draw(GameTime gameTime)**:
  - Desenha na tela o labirinto, o Pac-Man, os fantasmas e os pontos.

2. Player.cs
------------
Classe que representa o Pac-Man, controlado pelo jogador.

Funções:
- **Update(GameTime gameTime)**:
  - Atualiza a posição do Pac-Man com base na tecla pressionada.
  - Verifica colisões contra paredes.
  - Trata a animação de abrir/fechar a boca.
- **Draw(SpriteBatch spriteBatch)**:
  - Desenha o Pac-Man na tela em sua posição atual.
- **ResetPosition()** (se existir):
  - Reposiciona o Pac-Man na posição inicial (usado ao reiniciar o jogo).

3. Ghost.cs
-----------
Classe que representa um fantasma inimigo.

Funções:
- **Update(GameTime gameTime)**:
  - Move o fantasma de forma automática (geralmente aleatória ou padronizada).
  - Pode incluir lógicas futuras de perseguição ao Pac-Man.
- **Draw(SpriteBatch spriteBatch)**:
  - Desenha o fantasma na posição atual no labirinto.
- **ResetPosition()**:
  - Reposiciona o fantasma na posição inicial (útil para quando o Pac-Man pega um power-up ou reinicia o nível).

4. Level.cs
-----------
Classe que gerencia o labirinto do jogo.

Funções:
- **LoadMap()**:
  - Carrega a matriz do labirinto (paredes, pontos e power pellets).
- **Draw(SpriteBatch spriteBatch)**:
  - Desenha o labirinto com base nos dados da matriz (paredes, pontos, espaços).
- **CheckCollision(Rectangle playerRectangle)**:
  - Verifica se o jogador (ou fantasma) colidiu com uma parede.
- **CollectPoint(Rectangle playerRectangle)**:
  - Verifica se o Pac-Man passou por cima de um ponto e coleta-o, aumentando a pontuação.

5. Assets.cs (caso usado)
-------------------------
Classe utilitária para gerenciar o carregamento dos sprites e sons.

Funções:
- **LoadTextures(ContentManager content)**:
  - Carrega todas as texturas (sprites do Pac-Man, fantasmas, labirinto).
- **LoadSounds(ContentManager content)**:
  - Carrega sons como efeitos de comer ponto ou morrer.

Funcionamento Interno:
----------------------
- O jogo é organizado em um loop onde o `Game1.cs` chama a atualização (`Update`) e o desenho (`Draw`) de todas as entidades (Player, Ghosts, Level).
- A matriz de mapa define a posição das paredes e dos pontos no cenário.
- A detecção de colisão é feita usando retângulos (`Rectangle`) para identificar contato entre o Pac-Man, paredes e fantasmas.

Sugestões de Melhorias Futuras:
-------------------------------
- Adicionar sistema de vidas.
- Implementar IA real dos fantasmas (Blinky, Pinky, Inky, Clyde).
- Criar menus de início e de Game Over.
- Adicionar efeitos sonoros de vitória e derrota.

Autor:
------
José Guilherme Antunes Faria 24903
Márcio José da Cunha Cardoso 24888
2025
