# Cadastro de Produtos com Djando Admin

## Objetivo

Criar uma aplicação de que utiliza o Django Admin para facilitar o cadastro, edição, listagem e inativação de produtos.

## Tecnologias utilizadas

- Django;
- Python;
- SQLite.

## Como executar

Abra o terminal, certifique-se de que está na raiz do projeto e rode o comando:

```bash
py manage.py runserver
```

## Como acessar o admin

Após rodar o comando acima, acesse o painel do administrador pelo navegador:

http://127.0.0.1:8000/

## Funcionalidades

- Acessar o painel administrativo do Django;
- Cadastrar produtos;
- Editar produtos existentes;
- Listar produtos cadastrados;
- Buscar produtos pelo nome;
- Filtrar produtos por status ativo/inativo;
- Inativar produtos através do campo ativo;
- Visualizar data de criação e data da última atualização do produto.

## Estrutura do produto

O projeto possui uma model chamada `Produto`, definida em Python através do Django ORM.
Essa model representa a estrutura da tabela de produtos no banco de dados, evitando a necessidade de criar comandos SQL manualmente para esse cadastro.

## Regras de validação

A classe `Produto` possui as seguintes regras em seu modelo:

- **nome:** campo de texto obrigatório, com tamanho máximo de 200 caracteres;
- **descricao:** campo de texto opcional, com tamanho máximo de 1000 caracteres;
- **preco:** campo obrigatório do tipo decimal, com valor mínimo maior de 0,001, até 10 dígitos no total e 2 casas decimais;
- **ativo:** campo booleano, criado por padrão com valor `True`;
- **criado_em:** campo de data e hora preenchido automaticamente na criação do produto;
- **atualizado_em:** campo de data e hora preenchido automaticamente sempre que o produto é alterado.

## Observações gerais

- O projeto utiliza SQLite como banco de dados local;
- O cadastro é realizado pelo Django Admin;
- A inativação de produtos é lógica, feita através do campo `ativo`;
- Após qualquer alteração no arquivo `models.py`, é necessário gerar e aplicar as migrations para refletir as mudanças no banco de dados.

Para gerar uma migration, rode:

```bash
py manage.py makemigrations
```

Depois, aplique a migration com:

```bash
py manage.py migrate
```
