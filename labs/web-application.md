# Aplicativo Web de Alta Disponibilidade

## Laborátório 🥼

## Objetivo

- Configurar um grupo de Auto Scaling para usar um Application Load Balancer
- Configurar o health checks do load balancer para o grupo do Auto Scaling.
- Adicionar uma segunda zona de disponibilidade ao grupo de Auto Scaling.

### Diagrama do fluxo ✅

![image](https://github.com/user-attachments/assets/36361d7d-a011-47a7-83ec-5d80035454fc)

# Execução 🚀

1. Entrar nas instâncias EC2
2. No painel de navegação esquerdo, clique em Grupos de Auto Scaling.
3. Na seção Grupos do Auto Scaling, selecione TravelAgencyWebServers.
4. Na guia Detalhes, revise os detalhes da capacidade atual.

   ![image](https://github.com/user-attachments/assets/bb8ec402-0fc3-4f5c-96c2-c26605bc6898)
   
Verificamos que existe uma configuração de auto-scaling pré configurada.

Na seção Rede, verifique se o grupo Auto Scaling está configurado com uma única sub-rede de uma zona de disponibilidade

![image](https://github.com/user-attachments/assets/46c2e368-e984-436b-bf4c-3015f7cfc597)


Vamos adicionar um Load Balancer dentro do Auto Scaling, inserindo mais duas zonas de disponibilidades.

![image](https://github.com/user-attachments/assets/019002bc-be3e-4dd2-a7e9-34e48de58a59)


Na seção Regras de entrada, em Tipo, escolha HTTP.
Para permitir todo o tráfego de entrada, em Origem, na caixa Pesquisa personalizada, escolha 0.0.0.0/0.
Na seção Regras de saída, em Tipo, escolha HTTP.
Em Destino, escolha o security group TravelAgencyWebServer.
Remova o destino 0.0.0.0/0 (não mostrado).

![image](https://github.com/user-attachments/assets/ad739158-87cb-4299-8d6c-c87ead26a4b8)

Para aumentar a segurança vamos editar o grupo de segurança usados pela EC2, permitindo somente tráfego através do load balancer.

![image](https://github.com/user-attachments/assets/900e52a1-cb0a-447e-ba8b-9e93aaa10ff4)

Verificamos que o load balancer após aplicado está funcionado.

![image](https://github.com/user-attachments/assets/74301e47-af6f-4a8a-a7fd-5cf80b232677)

Ajustamos para crição de 3 instâncias em 3 zonas de disponibilidade.

![image](https://github.com/user-attachments/assets/94d2bdb8-1509-483e-bfdc-e264e1db758d)

![image](https://github.com/user-attachments/assets/0ca7b0ed-4c93-47c6-812d-6fb0b569ca06)

health check.

Site: 

![image](https://github.com/user-attachments/assets/5cb508c3-b333-47b0-92ba-0c95fef3fc63)

![chrome_Nbx2vFGnLv](https://github.com/user-attachments/assets/e3f9688c-c780-4fbb-b50d-e8b20e793ab7)





