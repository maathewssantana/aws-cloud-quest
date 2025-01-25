
# Segurança IAM 

## Laborátório 🥼

## Objetivo

- Criar um grupo de usuários do IAM
- Anexar uma política gerenciada AWS a um grupo de usuários

### Diagrama do fluxo ✅

![image](https://github.com/user-attachments/assets/ce99efff-bd29-4e07-8f96-78400bb1a010)

# Execução 🚀

1- Na seção Grupos de usuários, clique em Criar grupo

A. Em Nome do grupo de usuários, digite: 
- SupportEngineer

- ![image](https://github.com/user-attachments/assets/48aaaa2d-234b-4e7e-8180-3b4b360992fa)


B. Na caixa de pesquisa Anexar políticas de permissões, digite:  
- AmazonEC2ReadOnlyAccess

2 - Na etapa Especificar detalhes do usuário, em Nome do usuário, digite: 
- support-engineer

3 - Na etapa Analisar e criar, na seção Tags, clique em Adicionar nova tag.

A. Para Chave, digite:
job-title

B. Em Valor, digite:
Support Engineer

Desafio: 
- Conceda permissões de leitura para o grupo de Engineer no Amazon RDS

- ![image](https://github.com/user-attachments/assets/7051f0dd-1d2e-4081-9a34-7879685a55f3)


  

