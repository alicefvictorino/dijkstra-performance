# Análise de Desempenho e Pegada de Carbono: Algoritmos de Dijkstra

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter)](https://jupyter.org/)
[![CodeCarbon](https://img.shields.io/badge/CodeCarbon-Medindo%20CO%E2%82%82-brightgreen?style=for-the-badge&logo=leafygreen)](https://github.com/mlco2/codecarbon)
[![Plotly](https://img.shields.io/badge/Plotly-Gr%C3%A1ficos%20Interativos-blueviolet?style=for-the-badge&logo=plotly)](https://plotly.com/)

Um benchmark comparativo do tempo de execução ($O(V^2)$ vs $O((V+E)\log V)$) e das emissões de CO₂ de diferentes implementações do algoritmo de Dijkstra, conforme solicitado na disciplina de Algoritmos e Estruturas de Dados II (DCA3702 - UFRN).

---

## 1. Sobre o Projeto

Este projeto realiza uma análise de benchmark comparativa entre três abordagens do algoritmo de Dijkstra para encontrar o caminho mínimo em grafos ponderados:

1.  **Dijkstra Clássico:** Implementação de sala com complexidade $O(V^2)$.
2.  **Dijkstra com Min-Heap:** Implementação de sala com complexidade $O((V+E)\log V)$.
3.  **Referência `NetworkX`:** A implementação otimizada da biblioteca `networkx` como linha de base.

O objetivo é avaliar o impacto prático da complexidade algorítmica em duas métricas principais:
* **Tempo de Execução (s):** O tempo médio necessário para executar o algoritmo.
* **Pegada de Carbono (kg CO₂e):** A emissão de dióxido de carbono estimada para cada execução, medida com a biblioteca `CodeCarbon`.

O experimento foi conduzido em grafos aleatórios ponderados de tamanhos variando de 100 até 100.000 nós, com 20 repetições por tamanho para garantir robustez estatística.

## 2. Tecnologias Utilizadas

* **Python 3.10+**
* **Jupyter Notebook / Lab**
* **Pandas:** Para coleta e agregação dos dados estatísticos.
* **NetworkX:** Para geração de grafos e como algoritmo de referência.
* **Matplotlib & Seaborn:** Para a geração dos gráficos estáticos (`.png`).
* **Plotly:** Para a geração dos gráficos interativos (`.html`).
* **CodeCarbon:** Para medição da pegada de carbono.
* **Pickle:** Para salvar e recarregar o progresso do benchmark (checkpoints).

## 3. Como Executar Localmente

Você pode replicar este experimento em sua máquina local seguindo os passos abaixo.

### 3.1. Pré-requisitos

* [Python 3.10 ou superior](https://www.python.org/downloads/)
* `pip` (gerenciador de pacotes do Python)

### 3.2. Instalação

1.  Clone este repositório:
    ```bash
    git clone [https://github.com/](https://github.com/)[SEU-USUARIO]/[SEU-REPOSITORIO].git
    cd [SEU-REPOSITORIO]
    ```

2.  (Opcional, mas recomendado) Crie e ative um ambiente virtual:
    ```bash
    python -m venv venv
    source venv/bin/activate  # No macOS/Linux
    .\venv\Scripts\activate   # No Windows (PowerShell/CMD)
    ```

3.  Instale as dependências necessárias:
    ```bash
    pip install -r requirements.txt
    ```

### 3.3. Execução

1.  Inicie o servidor Jupyter:
    ```bash
    jupyter-lab
    ```
    (Ou `jupyter notebook` se preferir a interface clássica)

2.  Abra o arquivo `trab.ipynb` no seu navegador.

3.  No menu do Jupyter, clique em **Run (Executar) -> Run All Cells (Executar Todas as Células)**.

O notebook irá:
* Executar o benchmark completo (pode levar um tempo considerável).
* Salvar os resultados brutos em `resultados_benchmark/checkpoint_all_results.pkl`.
* Salvar a tabela de resumo em `resultados_benchmark/benchmark_dijkstra_resultados_com_co2.csv`.
* Gerar todos os gráficos estáticos (em `graficos_estaticos_barras_erro/`) e interativos (em `graficos_interativos_plotly/`).

**Observação:** O sistema de checkpoint está ativado. Se a execução for interrompida, você pode simplesmente dar "Run All" novamente, e o script pulará os tamanhos de grafo que já foram concluídos.

## 4. Resultados e Análises

Os resultados completos da execução, incluindo a tabela de resumo (`.csv`) e todos os gráficos (`.png` e `.html`), estão salvos nas pastas `/graficos_estaticos` e `/graficos_plotly`.

## 5. Apresentação em Vídeo

Uma explicação detalhada da metodologia, execução do código e análise dos resultados está disponível no vídeo de apresentação:

**link**

## 6. Autores

* **Alice Victorino** - [GitHub](https://github.com/alicefvictorino)
* **Erick Justino** - [GitHub](https://github.com/erickjustino)