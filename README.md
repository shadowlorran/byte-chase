<div align="center">

# Byte Chase

### Jogo 2D com Pathfinding A* em Python + Pygame

Projeto acadêmico desenvolvido para a disciplina de **Inteligência Artificial**, aplicando **busca heurística A\*** e **máquina de estados** no comportamento dos inimigos em um jogo 2D de labirinto.

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Pygame](https://img.shields.io/badge/Pygame-2.x-green)
![Status](https://img.shields.io/badge/status-conclu%C3%ADdo-success)
![Disciplina](https://img.shields.io/badge/Disciplina-Intelig%C3%AAncia%20Artificial-purple)

</div>

---

## Informações acadêmicas

| Campo | Informação |
|---|---|
| **Aluno** | Lorran Teodoro Camilo |
| **Curso** | Bacharel em Sistemas de Informação |
| **Instituição** | UNIS GAEAD |
| **Disciplina** | Inteligência Artificial |
| **Tema do projeto** | Aplicação do algoritmo A* em um jogo 2D |

---

## Sumário

- [Sobre o projeto](#sobre-o-projeto)
- [Objetivo acadêmico](#objetivo-acadêmico)
- [Diferencial do jogo](#diferencial-do-jogo)
- [Funcionalidades](#funcionalidades)
- [Conceitos de IA aplicados](#conceitos-de-ia-aplicados)
- [Estrutura do projeto](#estrutura-do-projeto)
- [Representação do mapa](#representação-do-mapa)
- [Tecnologias utilizadas](#tecnologias-utilizadas)
- [Como executar](#como-executar)
- [Controles](#controles)
- [Fluxo de funcionamento](#fluxo-de-funcionamento)
- [Destaques técnicos](#destaques-técnicos)
- [Melhorias futuras](#melhorias-futuras)
- [Conclusão](#conclusão)
- [Autor](#autor)

---

## Sobre o projeto

**Byte Chase** é um jogo 2D de labirinto inspirado em jogos clássicos de perseguição, mas com proposta própria. O jogador controla um agente digital que precisa coletar fragmentos de dados espalhados pelo mapa enquanto evita drones de segurança que patrulham o cenário.

O foco principal do projeto não está apenas na jogabilidade, mas na aplicação prática de **Inteligência Artificial em jogos**, especialmente por meio do algoritmo **A\*** para **pathfinding** em tempo real.

Quando o jogador entra em uma área de alerta, os inimigos deixam o comportamento aleatório e passam a calcular a melhor rota possível até o alvo, respeitando as paredes e a estrutura do labirinto.

---

## Objetivo acadêmico

Este trabalho foi desenvolvido com o objetivo de demonstrar, de forma prática e visual, a aplicação de conceitos de **Inteligência Artificial** em um ambiente interativo.

### Principais metas do projeto

- representar um ambiente em **grade 2D**;
- implementar o algoritmo **A\*** para navegação inteligente;
- modelar comportamentos com **máquina de estados**;
- integrar IA com mecânicas de jogo em tempo real;
- estruturar o código de forma modular e organizada.

---

## Diferencial do jogo

Embora o projeto seja inspirado no gênero de perseguição em labirintos, ele foi desenvolvido com identidade própria.

### Elementos que diferenciam o projeto

- tema digital/cyber em vez de uma cópia direta de jogos clássicos;
- inimigos com **comportamento por estados**;
- perseguição baseada em **A\*** e não apenas em seguir direção simples;
- power-up que altera temporariamente a lógica dos inimigos;
- estrutura modular pensada para evolução futura.

---

## Funcionalidades

- movimentação do jogador em quatro direções;
- mapa em grade 2D;
- coleta de pontos e power-ups;
- sistema de pontuação;
- sistema de vidas;
- condição de vitória e derrota;
- inimigos com patrulha, perseguição e fuga;
- perseguição inteligente com **A\***;
- reinício da partida após fim de jogo.

---

## Conceitos de IA aplicados

## 1. Pathfinding com A*

O algoritmo **A\*** foi utilizado para que os inimigos encontrem o menor caminho até o jogador dentro do labirinto.

### Componentes da busca

- **Nó inicial:** posição atual do inimigo;
- **Nó objetivo:** posição atual do jogador;
- **Vizinhos válidos:** células livres do mapa;
- **g(n):** custo acumulado do início até o nó atual;
- **h(n):** heurística estimada até o objetivo;
- **f(n):** soma entre custo real e heurístico.

### Heurística utilizada

Foi utilizada a **distância de Manhattan**, adequada para cenários em grade com movimentação apenas horizontal e vertical.

```python
f(n) = g(n) + h(n)
```

Essa escolha torna a busca eficiente e coerente com a lógica do jogo.

---

## 2. Máquina de estados dos inimigos

Os inimigos não executam apenas uma ação fixa. Eles alternam comportamento de acordo com a situação do jogo.

### Estados principais

- **Patrulha:** movimentação aleatória quando o jogador está distante;
- **Perseguição:** ativada quando o jogador entra no raio de alerta;
- **Fuga:** ativada quando o jogador coleta um power-up.

Essa abordagem deixa o comportamento mais realista e demonstra uma aplicação importante de IA baseada em regras e estados.

---

## Estrutura do projeto

```text
byte_chase/
├── README.md
├── main.py
├── game.py
├── entities.py
├── astar.py
├── level_data.py
└── settings.py
```

### Descrição dos arquivos

| Arquivo | Responsabilidade |
|---|---|
| `main.py` | Ponto de entrada da aplicação |
| `game.py` | Loop principal, HUD, colisões, pontuação e estados do jogo |
| `entities.py` | Classes do jogador e dos inimigos |
| `astar.py` | Implementação do algoritmo A* |
| `level_data.py` | Layout do mapa/labirinto |
| `settings.py` | Configurações e constantes globais |

---

## Representação do mapa

O cenário é definido por uma lista de strings, onde cada caractere representa um elemento do ambiente.

| Símbolo | Significado |
|---|---|
| `#` | Parede |
| `.` | Item coletável |
| `O` | Power-up |
| `P` | Posição inicial do jogador |
| `E` | Posição inicial do inimigo |

Essa estratégia simplifica a manutenção do mapa e facilita a expansão para novas fases.

---

## Tecnologias utilizadas

- **Python 3**
- **Pygame**
- **Algoritmo A\*** para pathfinding
- Estruturas de dados nativas do Python (`set`, `list`, `dict`, `tuple`)

---

## Como executar

### 1. Clonar ou baixar o projeto

```bash
git clone <url-do-repositorio>
cd byte_chase
```

### 2. Instalar dependências

```bash
pip install pygame
```

### 3. Executar o jogo

```bash
python main.py
```

---

## Controles

| Tecla | Ação |
|---|---|
| `Setas do teclado` | Movimentação |
| `ENTER` | Reiniciar após vitória ou derrota |

---

## Fluxo de funcionamento

1. O mapa é carregado a partir de uma estrutura em grade.
2. O jogador se movimenta apenas por células válidas.
3. Os itens coletáveis aumentam a pontuação.
4. Ao pegar um power-up, os inimigos entram em modo de fuga.
5. Ao detectar o jogador, os inimigos calculam uma rota com **A\***.
6. O jogo termina quando todos os itens são coletados ou quando as vidas acabam.

---

## Destaques técnicos

- organização modular do código;
- separação entre lógica do jogo e lógica de IA;
- uso de busca heurística aplicada em tempo real;
- modelagem de comportamento com máquina de estados;
- base pronta para expansão com fases, sprites, sons e novos tipos de inimigo.

---

## Melhorias futuras

- adição de múltiplas fases;
- menu inicial e tela de pausa;
- sprites personalizados;
- efeitos sonoros e trilha;
- diferentes perfis de inimigos;
- comparação entre A\* e outros algoritmos de busca;
- sistema de dificuldade progressiva.

---

## Conclusão

O projeto **Byte Chase** demonstra de forma clara como conceitos de **Inteligência Artificial** podem ser aplicados ao desenvolvimento de jogos digitais. A utilização do algoritmo **A\*** permite que os inimigos tomem decisões de navegação de forma eficiente, enquanto a máquina de estados amplia a complexidade do comportamento dos agentes.

Além da parte técnica, o projeto foi organizado de forma modular, legível e escalável, o que reforça boas práticas de desenvolvimento de software em contexto acadêmico e profissional.

---

## Autor

**Lorran Teodoro Camilo**  
**Bacharel em Sistemas de Informação**  
**UNIS GAEAD**  
**Disciplina: Inteligência Artificial**

---

<div align="center">
Feito para fins acadêmicos, com foco em aplicação prática de Inteligência Artificial em jogos 2D.
</div>
