# Amazon Scaling

## Laborátório 🥼

## Objetivo

- Criar um grupo do Amazon EC2 Auto Scaling.
- Atribuir instâncias do EC2 ao grupo do Auto Scaling.

### Diagrama do fluxo ✅

![image](https://github.com/user-attachments/assets/71491f04-d013-4a7b-a4b1-56c9879d1bb8)


# Execução 🚀

Reduzir o número de instâncias para 0   após 01h manhã, ação deve ser executada diariamente.

1 - Ir até as instâncias EC2 
(Game Server)

2 - Criar uma imagem da instância em funcionamento.

![image](https://github.com/user-attachments/assets/efee6ebc-3110-420a-8993-fcdb200890f2)

3 - Criado um template a partir da imagem.

![image](https://github.com/user-attachments/assets/fe7f8c84-a302-405f-b118-907f2a2db399)

4 - Criar um Auto Scaling Group com o template.

![image](https://github.com/user-attachments/assets/647b341c-52e6-40f9-b815-ab2b26e2b2c5)

Configurações Auto Scaling:
- CPU acima de 70%
- CloudWatch Alarme de monitoramento

5 - Configuramos uma ação para desligar os servidores de jogos conforme a solicitação do cliente, após 01:00 da manhã.

![image](https://github.com/user-attachments/assets/5c989c41-c573-4b05-bc1e-2bb48cda95aa)

Site do cliente: 

![image](https://github.com/user-attachments/assets/2e920351-5e4b-4dc0-bcc6-425ed6e84199)


Com essa ação nosso cliente se beneficia aumentando o desempenho durante o uso, e economiza com a redução quando não houver mais utilização.
