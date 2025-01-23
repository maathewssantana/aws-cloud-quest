
# Banco de dados NoSQL


## Laborátório 🥼

## Objetivo

- Criar um banco de dados NoSQL como uma tabela do Amazon DynamoDB
- Adicionar registros, com esquema dinâmico, á tabela do DynamoDB
- Consultar a tabela do DynamoDB

### Diagrama do fluxo ✅

![image](https://github.com/user-attachments/assets/9167b625-2466-4e96-bf10-e9777b70babc)

# Execução 🚀


## Tutorial Básico: Criando uma Tabela no DynamoDB

### 1. Acessar o DynamoDB na Console AWS
- Entre no serviço do DynamoDB na Console AWS.

### 2. Criar uma Nova Tabela
- Clique em "Create Table" para iniciar a criação de uma nova tabela.

### 3. Configurar Detalhes da Tabela
1. **Nome da Tabela**:
    - Para o nome da tabela, digite: `UserVideoHistory`.

2. **Chave de Partição (partition key)**:
    - Na caixa de texto à esquerda, digite: `userId`.
    - Nota: Certifique-se de digitar a chave de partição exatamente como mostrado, com "I" maiúsculo, pois as chaves são sensíveis a maiúsculas e minúsculas.
    - No menu dropdown à direita, escolha `String`.

3. **Chave de Classificação (sort key)**:
    - Na caixa de texto à esquerda, digite: `lastDateWatched`.
    - No menu dropdown à direita, escolha `Number`.

### 4. Criar a Tabela
- Após configurar os detalhes, clique em "Create Table" para criar a tabela.


![Diagrama do Fluxo](https://github.com/user-attachments/assets/9167b625-2466-4e96-bf10-e9777b70babc)

Espero que este tutorial seja útil!

![image](https://github.com/user-attachments/assets/2c768ac6-25ee-4e12-a49f-9b184cb26136)


Após isso clique em criar tabela. 

![image](https://github.com/user-attachments/assets/b30c80ad-5b90-4ce7-9575-68fa8ee35f4f)

Adicione os itens na tabela

Após isso realizamos a conta e o intem foi retornado.

![image](https://github.com/user-attachments/assets/d45eebf8-5f6a-4480-86e9-3d5233611ded)


![image](https://github.com/user-attachments/assets/ed76fa0f-d444-462d-9f7d-8ecce7323edf)

Desafio.

Criar um novo item de usuário com um ID Exclusivo.
Adicone um novo atributo chamado "rating" com um tipo de dados number.


   
