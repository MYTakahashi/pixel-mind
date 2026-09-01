# 🧠 PixelMind: Classificação de Imagens & Machine Learning

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white)
![License](https://img.shields.io/badge/Licença-MIT-green)

> **PixelMind** é um pipeline preditivo ponta a ponta de Visão Computacional e Aprendizado de Máquina focado na classificação de dígitos manuscritos (*MNIST dataset*). O projeto explora a transição da extração de matrizes de pixels para modelos estatísticos clássicos e redes neurais profundas, incluindo testes rigorosos com imagens próprias desenhadas à mão! ✍️🎨

---

## 📌 Sumário
- [🎯 Objetivo do Projeto](#-objetivo-do-projeto)
- [🛠️ Ferramentas & Tecnologias](#️-ferramentas--tecnologias)
- [📂 Estrutura do Repositório](#-estrutura-do-repositório)
- [🚀 Fluxo do Pipeline & Fases](#-fluxo-do-pipeline--fases)
- [📊 Modelos e Resultados Obtidos](#-modelos-e-resultados-obtidos)
- [🧪 Teste Extremo (Imagens Próprias - Out of Distribution)](#-teste-extremo-imagens-próprias---out-of-distribution)
- [🏁 Como Executar o Projeto](#-como-executar-o-projeto)
- [🤝 Contribuição e Licença](#-contribuição-e-licença)

---

## 🎯 Objetivo do Projeto

O **PixelMind** busca comparar e avaliar o desempenho de algoritmos de **Machine Learning Clássico** vs. **Redes Neurais Artificiais** na tarefa de reconhecer caracteres e dígitos manuscritos. 

Além disso, o projeto estressa os modelos treinados submetendo-os a imagens reais capturadas manualmente (fora da distribuição do MNIST), avaliando pré-processamento digital de imagens, centralização de massa, inversão de escala e resiliência de inferência.

---

## 🛠️ Ferramentas & Tecnologias

O projeto foi desenvolvido em **Python 3.9+** utilizando bibliotecas consolidadas do ecossistema de Ciência de Dados:

| Categoria | Tecnologias Utilizadas |
| :--- | :--- |
| **Linguagem & Ambiente** | `Python`, `Jupyter Notebook` / `VS Code` |
| **Manipulação & Análise** | `NumPy`, `Pandas` |
| **Visão Computacional & Imagem** | `OpenCV`, `Pillow (PIL)`, `Matplotlib`, `Seaborn` |
| **Machine Learning Clássico** | `scikit-learn` *(SVM, Random Forest, KNN, SGDClassifier)* |
| **Deep Learning** | `TensorFlow` / `Keras` *(MLP / Dense Layers)* |

---

## 📂 Estrutura do Repositório

```text
pixel-mind/
│
├── 📁 data/                  # Conjuntos de dados e dados locais (MNIST, amostras)
│   ├── raw/                  # Imagens brutas desenhadas à mão (.png / .jpg)
│   └── processed/            # Imagens processadas em escala 28x28 pixels
│
├── 📁 notebooks/             # Notebooks com análises exploratórias e treinos
│   └── pixel_mind_pipeline.ipynb
│
├── 📁 src/                   # Módulos Python reutilizáveis
│   ├── preprocessing.py      # Pipeline de conversão, inversão e normalização
│   ├── models.py             # Definição e ajuste de hiperparâmetros
│   └── evaluate.py           # Matriz de confusão e relatórios de métricas
│
├── .gitignore                # Arquivos ignorados pelo Git
├── README.md                 # Documentação principal do projeto
└── requirements.txt          # Dependências do projeto para reprodutibilidade
```
--- 

## 📊 Modelos e Resultados Obtidos

Modelo | Hiperparâmetros  | Ajustados Acurácia (Teste) | F1-Score (Macro)  
|---------|------------|----------------------|----------------
Random Forest   | n_estimators=100, max_depth=20 |  96.8% |  0.97 
SVM (RBF Kernel) | C=10, kernel='rbf' | 98.2% | 0.98  
Rede Neural (MLP) | Dense(128, relu) + Dropout(0.2) + Softmax | 98.5% | 0.98

---

## 🧪 Teste Extremo: Imagens Próprias (Out of Distribution)
Nesta etapa, validamos a generalização dos modelos usando dígitos escritos à mão em papel e fotografados:  

Amostra Real  | Dígito Real | Predição do Modelo | Probabilidade | Status  
|-------------|-------------|--------------------|---------------|-------  
✍️ Amostra A | 5 | 5 | 99.2% | ✅ Sucesso   
✍️ Amostra B | 3 | 3 | 95.8% | ✅ Sucesso  
✍️ Amostra C | 8 | 8 | 89.4% | ✅ Sucesso

---
## 🏁 Como Executar o Projeto
Clone este repositório:

```Bash
git clone https://github.com/seu-usuario/pixel-mind.git
cd pixel-mind
```
```Bash
Crie e ative um ambiente virtual:
python -m venv venv
# Windows:
venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate
```
```Bash
Instale as dependências necessárias:
pip install -r requirements.txt
```
```Bash
Execute o notebook:  
jupyter notebook notebooks/pixel_mind_pipeline.ipynb
```