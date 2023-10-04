# Ponderada Semana 5

# Informações do Aluno  
Aluno | Curso | Módulo | Turma
:---: | :---: | :---: | :---:
Antonio Angelo Teixeira | Engenharia da Computação | 7 | 2

## Estrutura de Pastas
```
📦semana 7
 ┣ 📂amb
 ┃ ┣ 📂Include
 ┃ ┣ 📂Lib
 ┃ ┣ 📂Scripts
 ┃ ┣ 📂share
 ┃ ┣ 📜pyvenv.cfg
 ┣ 📂pages
 ┣ 📂content
 ┣ 📜pyvenv.cfg
 ┣ 📜Dockerfile
 ┣ 📜logs.log
 ┣ 📜main.py
 ┣ 📜minha_api.pkl
 ┣ 📜minha_api.py
 ┣ 📜modelo_2.pkl
 ┣ 📜READ.MD
 ┣ 📜requirements.txt
 ┣ 📜style.css
```
## Explicação da Atividade
A atividade proposta demanda conceitos de alguns serviços AWS, machinelearning com Pycaret para Automl e streamlit para criação de dahsboards para visualização das predições realizadas. O objetivo é enviar um arquivo CSV para a API de um  modelo machine learning gerado pelo Pycaret e retorna no formato JSON a predição de cada linha do Parquet.
Consoante a isso, o arquivo parquet selecionado pelo aluno foi "Customer Segmentation". 

As colunas contidas nesse dataframe são:
- CustomerID
- Gender 
- Age
- Annual Income (k$) - COLUNA RENOMEADA APENAS PARA "INCOME" POR MOTIVOS DE PRATICIDADE
- Spending Score (1-100) - COLUNA RENOMEADA APENAS PARA "SCORE" POR MOTIVOS DE PRATICIDADE

# Tecnologias usadas

As tecnologias usadas para essa ponderada são listadas abaixo e descritas:
## Streamlit
Streamlit é uma ferramenta Open Source que permite construir aplicações web sem necessidade de conhecimentos avançados em desenvolvimento frontend. No caso da ponderada, ele consome os dados diretamente do arquivo CSV na página main.py.
Além disso, a estrutura do streamlit contém um diretório chamado pages, com o predict consumindo da API de predição. 

Para visualização, optei por três gráficos diferentes:

- Gráfico de comparação de Age x Select data. Com essa última variável podendo assumir dois valores: Income e Score

<p align="center">
<img src="(content/main_graph.png)">

<p align="center"> 1 — Demonstração do processo manual de separação de amostras realizado pelo IPT.</p>

</p>


**Link para o DockerHub**: https://hub.docker.com/repository/docker/antonioangelo2/entrega5/general

## Como Executar:
### Localmente
Para fazer o pull da imagem contida no dockerhub basta usar o seguinte comando no terminal: 
```docker push antonioangelo2/entrega5:tagname```

Após isso, rode o comando ```docker images``` para garantir que a imagem está contida no docker.

Rode o comando ```docker run -d --name <nome-do-seu-container> -p 8000:8000 antonioangelo2/entrega5:v1.0``` para criar um container e rodá-lo, a fim de executar a aplicação.

Após isso, projeto pode ser acessado em **(http://localhost:8000)**

Pronto. tudo certo para requisitar uma predição. Agora basta usar a URL do modelo com a API específica (http://localhost:8000/predict).

O dataset escolhido trata-se de um dataset de score de gasto com base nas seguintes características: gênero, idade, Income(quanto de dinheiro esse consumidor ganha anualmente em milhares). Fora esses, o Id costumer também estava contido no dataset, porém, ao gerar o Pycaret, optei por ignorar essa feature, pois se trata de uma feature irrelevante ao modelo.
<br>

Por fim, para rodar o modelo, basta acessar um softare de teste de API, thunderclient, por exemplo, e passar um Json semelhante a essa na URL específica do modelo
{
    "Gender": "Male",
    "Age": 30,
    "Income": 15
}

O resultado esperado é um retorno de predição do score de gasto.


