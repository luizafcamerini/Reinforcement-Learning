# Reinforcement Learning - Evacuação de cabine

## Objetivo

Este projeto implementa um ambiente de simulação em Reinforcement Learning para treinar um agente a executar uma sequência de evacuação em uma cabine de avião. O objetivo principal é:

1. soltar o cinto de segurança;
2. deslocar-se até o botão de emergência;
3. acionar o botão;
4. ir até a saída traseira e abrir a porta somente após a liberação do botão.

A lógica foi modelada para refletir uma situação realista de emergência, em que o agente precisa seguir uma ordem específica e lidar com obstáculos, penalidades e recompensas.

## Funcionalidade principal

O notebook `agent.ipynb` define um ambiente customizado com Gymnasium (`CabinEnv`) e utiliza Q-learning para aprender a política ótima. O agente recebe observações sobre:

- posição atual;
- estado do cinto;
- estado da saída;
- posição das malas;
- passos restantes no episódio.

As ações disponíveis são:

- mover para cima, baixo, esquerda e direita;
- apertar o botão de emergência;
- soltar o cinto;
- abrir a saída.

O ambiente inclui:

- assentos como obstáculos;
- corredores navegáveis;
- penalidades por tentativas inválidas;
- recompensas por progresso e conclusão correta da missão.

## Como o sistema funciona

O fluxo do projeto é:

- criação do mapa visual da cabine em Pygame;
- definição do estado do ambiente e regras de transição;
- execução de cada ação pelo agente;
- atualização da tabela Q com base nas recompensas recebidas;
- avaliação do desempenho por episódio;
- geração de gráficos com retorno médio e progresso das etapas.

A lógica de treinamento busca reduzir a dimensionalidade do espaço de estados para tornar a tabela Q mais eficiente, agrupando estados equivalentes por posição e fase do episódio.

## Estrutura do repositório

- `agent.ipynb`: notebook principal com ambiente, treinamento e avaliação;
- `map.png`: representação visual do mapa da cabine;
- `README.md`: documentação do projeto.

## Uso

1. Abra o notebook `agent.ipynb` em um ambiente Jupyter;
2. execute as células em sequência;
3. aguarde o treinamento e a análise dos resultados.

O projeto foi desenvolvido como estudo prático de Reinforcement Learning e de modelagem de ambientes simulados.
