# Amazon EFS

## Laborátório 🥼

## Objetivo

- Executar e configurar um sistema de arquivos do Amazon EFS
- Montar o sistema de arquivos em uma instância do Amazon EC2
- Conectar uma segunda instância do EC2 ao mesmo sistema de arquivos.
- Compartilhar arquivos entre as duas instâncias EC2

### Diagrama do fluxo ✅

![image](https://github.com/user-attachments/assets/d7aa1494-492b-48c2-8f29-e06f4e31f425)


# Execução 🚀

1 - Ir até as instâncias EC2

![image](https://github.com/user-attachments/assets/4a23a8e9-fc13-46f7-af6d-b12e25a2bbf2)

A-  Em Zona de Disponibilidade, revise a Zona de Disponibilidade de cada instância.
B - No painel de navegação esquerdo, role para baixo até Rede e Segurança.
C - Clique em Security Groups.

2 - 2 Criar um Security Group

A. Em Nome do security group, digite:
PetModels-EFS-1-SG

B. Em Descrição, digite: 
Restrinja o acesso somente aos servidores web.

C. Para VPC, no menu suspenso, escolha PetModels.
- Talvez seja necessário remover a VPC existente clicando em X.

D. Na seção Regras de entrada, selecione Adicionar regra.

![image](https://github.com/user-attachments/assets/2c431534-8d34-49d7-9fbe-e273ec06d5f6)

3- Criar um EFS

A- Criar um sistema de arquivos
B. Nome: PetModels-EFS-1
C. Rede VPC compartilhada

![image](https://github.com/user-attachments/assets/59c7ad71-36f7-4584-a07d-06d00df238db)

4 - Configuração do EFS

A - Nome
B - Habilitar backup Automático
C- Na seção Configurações de desempenho, para o modo Throughput, escolha o botão para selecionar Bursting
D- Deixar apenas 1 grupo de segurança PetModels-EFS-1-SG.
E - Criar 

![image](https://github.com/user-attachments/assets/c4979a81-09df-46a2-a208-c4d2b06f74ae)


5 - Montar a imagem do EFS na EC2

A. sudo mount -t efs -o tls fs-0e7828536862e808a:/ efs
B. EC2 (Instalar o utilitário EFS "sudo yum install -y amazon-efs-utils"

6 - Compartilhar o EFS em 3 sub-redes.

![image](https://github.com/user-attachments/assets/e8a1ba84-c492-4cd8-9842-e2f6426e1ab5)

