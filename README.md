# Predição de Doenças Cardíacas utilizando Aprendizado de Máquina

## Objetivo
O objetivo deste projeto é desenvolver e avaliar modelos de *Machine Learning* capazes de prever a probabilidade de um paciente possuir doença cardíaca com base em seus exames clínicos e sintomas fisiológicos. Visando a aplicação em um cenário hospitalar real de alta criticidade, o escopo do projeto vai além da simples busca por acurácia, focando estrategicamente em maximizar a métrica de *Recall* través do ajuste metodológico do limiar de decisão, garantindo assim a triagem preventiva da grande maioria dos pacientes doentes e minimizando o risco de ocorrência dos Falsos Negativos no acolhimento médico.

## Integrantes
* Daivik Jain Celeste
* Kilvy Emanuel Costa Santos
* Yan Martins de Oliveira Villa Nova

## Divisão das Contribuições
* **Daivik Jain Celeste:** responsável pela etapa inicial de compreensão dos dados e a Análise Exploratória de Dados.
* **Kilvy Emanuel Costa Santos:** responsável pela realização dos testes finais (com o dataset de testes) com o limiar de 0,28 adotado, e pela extração e interpretação das métricas finais.
* **Yan Martins de Oliveira Villa Nova:** responsável pela etapa do pré-processamento dos dados, como também da etapa de escolha do modelo, através da técnica da validação cruzada.

## Fonte dos Dados
Os dados utilizados neste projeto foram extraídos do **Heart Failure Prediction Dataset**, disponível publicamente na plataforma Kaggle. Trata-se de uma combinação de 5 bases de dados cardiovasculares tradicionais, resultando em um conjunto robusto para pesquisa preditiva de mortalidade cardiovascular.
* **Link:** [Kaggle - Heart Failure Prediction](https://www.kaggle.com/fedesoriano/heart-failure-prediction)

## Tipo da Tarefa
Trata-se de uma tarefa de **Classificação**, onde a variável-alvo (`HeartDisease`) possui duas classes: `0` (Saudável) e `1` (Doente).

## Organização dos Arquivos
* `notebook_IA.ipynb`: o Jupyter Notebook principal contendo todo o fluxo do projeto (Compreensão dos Dados, Análise Exploratória (EDA), Pré-processamento via *Pipeline*, Validação Cruzada, Treinamento e Avaliação Final).
* `README.md`: arquivo de documentação geral do repositório.
* `heart.csv`: base de dados bruta utilizada para o treinamento.
* `link-video.txt`: link do vídeo de explicação.

## Como abrir o notebook no Google Colab
1. Baixe o arquivo `notebook_IA.ipynb` deste repositório.
2. Acesse o [Google Colab](https://colab.research.google.com/).
3. No menu principal do Google Colab, clique no botão referente à realização de  **upload de notebook**. Alternativamente, um novo notebook pode ser criado, e o upload do arquivo pode ser realizado a partir desta página do notebook vazio.
4. Selecione o arquivo baixado e confirme-o no Google Colab.
5. Conecte-se a uma runtime no Google Colab (caso já não esteja conectado a uma). A partir desse momento, o botão referente à execução de todas as células do notebook pode ser acionado. Com isso, todo o código presente será executado.

## Modelos Utilizados
Para a avaliação e seleção do melhor algoritmo, os seguintes modelos foram implementados e comparados através de Validação Cruzada (*Cross-Validation* com 5 folds):
* **DummyClassifier (Baseline):** modelo base de controle, utilizando a estratégia da classe mais frequente.
* **SGDClassifier:** representante dos modelos lineares, altamente sensível à escala dos dados e focado na otimização estocástica.
* **RandomForestClassifier (Escolhido):** algoritmo não-linear baseado em árvores de decisão.

## Principais Resultados
* O modelo **Random Forest** foi escolhido da modelagem devido à sua capacidade de lidar com a complexidade não-linear das variáveis fisiológicas. O modelo atingiu a maior acurácia e consistência frente ao SGD, como também obteve um excelente **AUC de 0.9333**, comprovando sua alta capacidade de discriminação entre pacientes saudáveis e doentes.
* **Ajuste de Limiar Médico:** durante a avaliação final no conjunto de testes, o limiar de decisão foi ajustado de 0.50 (o padrão) para 0.28. Esta decisão focada na saúde elevou a taxa de captura de doentes (Recall) para patamares acima de 95%, garantindo alta confiabilidade na triagem preventiva.
* O *Random Forest* obteve métricas altas durante a fase de testes, especialmente no *Recall* (considerando o limiar de decisão de 0,28 aplicado com a finalidade de aumentar o *Recall*) de 97%, aproximadamente, demonstrando a alta capacidade do modelo de reduzir falsos negativos.

## Vídeo de Apresentação
A explicação completa do projeto está disponível no link abaixo:
* [Link para o Google Drive](https://drive.google.com/file/d/1gW1lMfmmS_fFlQtVChCMqrpIMQZv9Opm/view?usp=sharing)

Alternativamente, o link do vídeo está diponível em um arquivo .txt neste repositório: `link-video.txt`.

## Declaração de Uso de Inteligência Artificial
Foi utilizada a ferramenta de inteligência artificial Google Gemini para o desenvolvimento dos códigos envolvendo os gráficos boxplots e histogramas presentes na seção 4 do Jupyter Notebook (análise exploratória dos dados), como também na construção do código para a geração do gráfico da curva ROC, presente na seção 6. A atuação da ferramenta foi validada por todo o grupo por meio de uma revisão crítica conjunta do código-fonte, realizando ajustes e refinamentos considerados essenciais e/ou válidos pelos membros do grupo.
