# S.O. 2025.1 - Atividade 01 - Introdução a docker

## Informações gerais

- **Objetivo do repositório**: Repositório da disciplina para atividade avaliativa dos alunos
- **Assunto**: Introdução a docker
- **Público alvo**: alunos da disciplina de SO (Sistemas Operacionais) do curso de TADS (Superior em Tecnologia em Análise e Desenvolvimento de Sistemas) no CNAT-IFRN (Instituto Federal de Educação, Ciência e Tecnologia do Rio Grande do Norte - Campus Natal-Central).
- disciplina: **SO** [Sistemas Operacionais](https://github.com/sistemas-operacionais/)
- professor: [Leonardo A. Minora](https://github.com/leonardo-minora)
- Aluna: [Anaíse Da S. Gomes](https://github.com/anaisegomes)



## **Introdução ao Docker**

Docker é uma plataforma de virtualização que permite criar, distribuir e executar aplicativos em contêineres. Um contêiner é uma unidade leve e portátil que inclui tudo o que é necessário para executar um aplicativo: código, runtime, bibliotecas e dependências.

### **Principais Conceitos**

1. **Imagem**: Uma imagem Docker é um pacote imutável que contém tudo o que é necessário para executar um aplicativo. As imagens são usadas para criar contêineres.
2. **Contêiner**: Um contêiner é uma instância em execução de uma imagem. Ele é isolado do sistema hospedeiro e de outros contêineres.
3. **Dockerfile**: Um arquivo de texto que contém instruções para construir uma imagem Docker.
4. **Docker Hub**: Um repositório público onde você pode armazenar e compartilhar imagens Docker.



## Sequência de passos

Vamos criar um contêiner Docker que execute um código Python da máquina hospedeira.

1. Fork desse repositório para sua conta no github
2. Adicionar na linha 10 deste arquivo o nome do aluno. Use o formato igual a do professor, conforme linha 9.
3. Criar o código Python.
4. Criar o Dockerfile
5. Construir a imagem docker
6. Executar o contêiner docker



#### **Passo 3: Criar o Código Python**

Crie um arquivo chamado `app.py` com o seguinte conteúdo:

```python
print("Olá, Docker!")
```


#### **Passo 4: Criar o Dockerfile**

Crie um arquivo chamado `Dockerfile` no mesmo diretório que o `app.py` com o seguinte conteúdo:

```Dockerfile
# Usar uma imagem base do Python
FROM python:3.9-slim

# Copiar o código Python para o contêiner
COPY app.py /app.py

# Executar o código Python
CMD ["python", "/app.py"]
```


#### **Passo 5: Construir a Imagem Docker**

No terminal, navegue até o diretório onde estão os arquivos `app.py` e `Dockerfile` e execute o seguinte comando para construir a imagem Docker:

```sh
docker build -t python-app .
```


#### **Passo 6: Executar o Contêiner Docker**

Depois de construir a imagem, execute o contêiner com o seguinte comando:

```sh
docker run python-app
```

Você verá a saída `Olá, Docker!` no terminal, indicando que o código Python foi executado com sucesso dentro do contêiner.
