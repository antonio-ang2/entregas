# PONDERADA 4

# INFORMAÇÕES DO ALUNO
Aluno | Curso | Módulo | Turma
:---: | :---: | :---: | :---:
Antonio Angelo Teixeira | Engenharia da Computação | 8 | 2


## DESCRIÇÃO DA ATIVIDADE


A proposta da segunda atividade ponderada visa a implementação de dois lançadores contendo pacotes distintos. O primeiro lançador tem como finalidade inicializar o pacote de navegação, composto por três módulos essenciais: RVIZ para visualização e abertura do NAV2, Gazebo para a exibição visual e o Cartographer. Já o segundo lançador será responsável por ativar o pacote do script desenvolvido pelo aluno, o qual assume a responsabilidade de definir a pose inicial no Gazebo e especificar a trajetória de pose para o robô simulado seguir.

O propósito central dessa atividade é desafiar o aluno a criar um mapa integralmente utilizando as funcionalidades oferecidas pelo NAV2. O enfoque está na avaliação e aplicação dos conhecimentos em ROS2, utilizando pacotes e lançadores de forma coordenada para atingir o objetivo proposto

# COMO EXECUTAR O PROJETO

## INSTALAÇÃO

Instalar  o Modelo Ollama:

Para instalar o modelo do chatbot na máquina, utilize o seguinte comando:

```bash
ollama create security-expert -f Modelfile
```

### INSTALAR DEPENDÊNCIAS:

Instale as dependências necessárias executando o seguinte comando:

```bash
pip install -r requirements.txt
```

### Execução
Depois de completar a instalação, execute o chatbot usando o seguinte comando:

```bash
python chat.py
```


# Vídeo de Demonstração


<video src="m8_ponderada4.mp4" controls title="Title"></video>
