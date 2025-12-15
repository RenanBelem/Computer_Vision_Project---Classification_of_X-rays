# Classificação de Infecções Através de Radiografias do Tórax

Este projeto de Visão Computacional utiliza técnicas de *Deep Learning* para auxiliar no diagnóstico de infeções pulmonares, incluindo COVID-19, através da análise automatizada de radiografias do tórax. O objetivo principal é fornecer uma ferramenta de suporte à decisão clínica, agilizando a triagem em cenários de alta procura, como o experienciado durante a pandemia.

## 👥 Autores

  * Gustavo Furini
  * Juliano Proença
  * Leonardo Nervino
  * Lucca Libanori
  * Renan Belem
  * Vitoria Izabel

## 📄 Sobre o Projeto

Durante a pandemia de COVID-19, as radiografias do tórax tornaram-se cruciais para o tratamento e contenção da doença. A análise manual destas imagens requer tempo e especialistas disponíveis. Este projeto visa testar diversas técnicas de redes neurais para classificar automaticamente as condições pulmonares com alta precisão.

### O Conjunto de Dados (Dataset)

A base de dados utilizada foi disponibilizada pela **Universidade do Catar** e contém um total de **21.165 imagens**, divididas em quatro categorias:

  * **COVID-19:** 3.616 imagens
  * **Infeções não-COVID:** 1.345 imagens (pneumonia viral ou bacteriana)
  * **Normal:** 10.192 imagens
  * **Opacidade Pulmonar (Lung Opacity):** 6.012 imagens

## 🛠️ Tecnologias Utilizadas

O projeto foi desenvolvido em **Python** utilizando as seguintes bibliotecas:

  * **TensorFlow / Keras:** Construção e treino dos modelos de *Deep Learning*.
  * **OpenCV (cv2):** Processamento de imagem.
  * **Matplotlib:** Visualização de dados e gráficos de desempenho.
  * **Scikit-learn:** Métricas de avaliação e divisão de dados.
  * **NumPy:** Manipulação de *arrays* e operações matemáticas.

## ⚙️ Metodologia e Arquitetura

O projeto seguiu um protocolo experimental rigoroso:

1.  **Pré-processamento:**
      * As imagens foram redimensionadas para o formato `(128, 128, 3)`.
      * Divisão dos dados: **70% para treino** e **30% para teste**.
2.  **Experimentos:**
      * **Experimento I:** Utilização dos dados originais sem técnicas adicionais. Modelo CNN sequencial com 5 camadas convolucionais, *Dropout* para evitar *overfitting* e ativação *Softmax* na saída.
      * **Experimento II:** Aplicação de **Data Augmentation** (rotação, zoom, inversão horizontal) para aumentar a variabilidade do treino.
      * **Experimento III:** Utilização de **Transfer Learning** com a arquitetura **VGG16** (pesos pré-treinados na ImageNet) para extração de características.

## 📊 Resultados

O modelo final atingiu métricas de desempenho competitivas na classificação das quatro classes.

  * **Acurácia (Accuracy):** \~90%.
  * **Desempenho Geral:** O modelo demonstrou capacidade robusta de generalização, com pontuações equilibradas de *Precision*, *Recall* e *F1-Score* entre as classes *Covid*, *Lung Opacity*, *Normal* e *Viral Pneumonia*.

## 🚀 Como Executar o Projeto

### Pré-requisitos

Certifique-se de ter o Python instalado e as bibliotecas necessárias. Pode instalá-las via `pip`:

```bash
pip install numpy opencv-python matplotlib tensorflow scikit-learn
```

### Execução

1.  Clone este repositório ou descarregue os ficheiros.
2.  Garanta que o *dataset* está organizado na estrutura de pastas correta (ex: pasta `covid/` contendo subpastas para cada classe, conforme o script de leitura).
3.  Abra o ficheiro principal no Jupyter Notebook ou Google Colab:
      * `PJBL_final.ipynb`
4.  Execute as células sequencialmente para carregar os dados, treinar o modelo (ou carregar os pesos `bestmodel_teste3.weights.h5`) e visualizar os resultados.

-----

*Projeto desenvolvido no âmbito académico para fins de estudo em Inteligência Artificial e Diagnóstico por Imagem.*
