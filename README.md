# Laboratório de Pressão Hidrostática

Simulador interativo, no estilo das simulações do PhET, para explorar como a pressão muda com a profundidade, o fluido e a gravidade. Ele também relaciona a pressão com o estado da matéria e com a cavitação.

**Acesse online:** https://joaovitoribeiro2000.github.io/pressao_hidrostatica/

## O que dá para fazer

- **Arrastar o sensor** dentro do tanque (0 a 100 m) e ver a pressão mudar na hora.
- **Escolher o fluido:** água doce, água salgada, óleo ou mercúrio.
- **Escolher o planeta:** Terra, Marte, Vênus ou "Planeta X", com gravidade livre de 0,5 a 30 m/s².
- **Ajustar a temperatura** (de -50 a 1000 °C).
- **Ler a pressão** em Pa (kPa), atm, bar e psi, tanto manométrica quanto absoluta.
- **Acompanhar o manômetro**, que muda de escala conforme a pressão.
- **Ver o diagrama de fases** do fluido, com a condição atual marcada.
- **Comparar fluidos** no gráfico de pressão × profundidade.
- **Observar a cavitação** em um tubo de Venturi animado, com bolhas que aumentam conforme o risco.

## Física usada

Pressão manométrica:

```
P_man = ρ · g · h
```

Pressão absoluta:

```
P_abs = P_atm + ρ · g · h
```

| Símbolo | Significado | Unidade |
|---|---|---|
| ρ | densidade do fluido | kg/m³ |
| g | aceleração da gravidade | m/s² |
| h | profundidade | m |
| P_atm | pressão atmosférica (101 325 Pa) | Pa |

Densidades adotadas: água doce 1000, água salgada 1030, óleo 800 e mercúrio 13 600 kg/m³.

### Cavitação

A cavitação é avaliada pela razão entre a pressão de saturação e a pressão absoluta (`P_sat / P_abs`). Quanto mais perto de 1, ou acima disso, maior o risco de formação de bolhas.

| P_sat / P_abs | Situação |
|---|---|
| menor que 0,50 | sem cavitação |
| de 0,50 a 0,90 | risco baixo |
| de 0,90 a 1,00 | cavitação incipiente |
| de 1,00 a 1,50 | cavitação moderada |
| acima de 1,50 | cavitação intensa |

## Limitações

Este simulador é **didático**. Os modelos de saturação e as curvas de mudança de fase são simplificados:

- Para a água, a pressão de saturação usa a equação de Antoine entre 1 e 100 °C e uma aproximação acima disso.
- Para os demais fluidos, usa-se uma curva aproximada a partir dos pontos triplo e crítico.
- As linhas de fusão e sublimação do diagrama de fases são qualitativas.

Não use os resultados para projeto de engenharia nem para decisões de segurança.

## Como usar localmente

É um único arquivo HTML, sem dependências nem instalação:

1. Baixe o arquivo `index.html`.
2. Abra com dois cliques em qualquer navegador moderno.

## Estrutura do repositório

```
pressao_hidrostatica/
├── index.html   # o simulador completo (HTML, CSS e JavaScript)
└── README.md    # este arquivo
```

## Origem

O projeto foi adaptado de um notebook Python (Google Colab, com `matplotlib` e `ipywidgets`) para uma versão web que roda direto no navegador.
