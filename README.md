# LabAt01 - Laboratório de Docker

Trabalho da disciplina de **Cloud Computing** (Prof. Glestiano Tavares Tietre)
do curso de Bacharelado em Ciência da Computação - UNINASSAU Campina Grande.

Aluno: Gabriel Ventura De Freitas

## Sobre

Laboratório prático de Docker dividido em 21 etapas: preparação do ambiente
(WSL 2 e Docker Desktop), construção de uma imagem a partir de um Dockerfile,
execução de contêiner individual, orquestração de dois serviços da mesma
aplicação com Docker Compose, balanceador de carga Nginx em modo round robin,
teste de tolerância a falhas (stop/start de uma réplica) e atualização da
aplicação para a versão 2.0.

O relatório completo, com as capturas de tela de cada etapa, está no arquivo
`Cloud Computing_Gabriel Ventura De Freitas_04197780.docx` deste repositório.

## Como executar

Requisito: Docker Desktop (ou Docker Engine) instalado e rodando.

Na pasta do projeto, o contêiner de teste individual:

```
docker build -t lab-app:1.0 .
docker run -d --name teste-app -p 127.0.0.1:8085:8000 lab-app:1.0
```

Teste em http://localhost:8085

Os três serviços com Compose (app1, app2 e balanceador):

```
docker compose up -d
```

Balanceador em http://localhost:8090. Encerramento:

```
docker compose down
docker rm -f teste-app
```
