
# Emparelhamento de VPC ![icons8-rede-com-cabos-32](https://github.com/user-attachments/assets/b1e82a35-1db6-4afd-a104-bf8773bc589f)


## Laborátório 🥼

## Objetivo

Permitir a comunicação entre as aplicações hospedadas em diferentes VPCs usando o emparelhamento de VPC.
As instâncias EC2 de marketing e desenvolviedor precisam acessar o servidor de serviços financeiros na VPC do departamento financeiro VPC do departamento financeiro.

### Diagrama do fluxo ✅

![chrome_0w7RFg0pqU](https://github.com/user-attachments/assets/40d44b84-89b5-4a9c-b0bd-dd0d0ba4f652)

# Execução 🚀

### Tutorial AWS VPC e EC2

1. **Iniciar Laboratório**
   - Analise os objetivos do laboratório prático na seção Conceito.
   - Clique em "Iniciar laboratório" e depois em "Abrir console da AWS".

2. **Configurar VPC**
   - Digite "vpc" na barra de pesquisa da AWS.
   - Clique em "VPC" nos resultados da pesquisa.
   - No painel esquerdo, clique em "Suas VPCs".
   - Analise as VPCs de marketing, finanças e desenvolvedores.

3. **Configurar EC2**
   - Digite "ec2" na barra de pesquisa da AWS.
   - Clique em "EC2" nos resultados da pesquisa.
   - Clique em "Instâncias (em execução)" na seção Recursos.

4. **Gerenciar Instâncias**
   - Selecione a instância do FinanceServer.
   - Verifique se não há endereço IPv4 público ou DNS preenchido.
   - Copie o endereço IPv4 privado fornecido e guarde-o.

5. **Analisar Sub-rede**
   - Verifique o ID da sub-rede e observe que é uma sub-rede privada.
   - Desmarque a instância do FinanceServer e selecione a instância do MarketingServer.
   - Na seção "Instâncias", clique em "Conectar".

6. **Conectar ao Servidor**
   - Selecione a guia "Gerenciador de sessões" e clique em "Conectar".
   - No terminal, execute o comando `ping` usando o endereço IP privado do FinanceServer.

7. **Verificar Conexão**
   - Verifique se o comando `ping` está travado e sem conexão.
   - Pressione `Ctrl+C` para sair do processo.

8. **Ver Detalhes da Instância**
   - No navegador anterior, clique no ID da instância do MarketingServer.

9. **Analisar Tabelas de Rotas**
   - Clique no ID da sub-rede e selecione o nome da sub-rede.
   - Na guia "Tabela de rotas", revise as regras de roteamento.

Claro! Aqui está a continuação do resumo do tutorial com o passo a passo:

### Conexões de Emparelhamento e Regras de Roteamento

1. **Criar Conexão de Emparelhamento**
   - No painel de navegação esquerdo, clique em "Conexões de emparelhamento".
   - Clique em "Criar conexão de peering".

2. **Configurar Conexão de Emparelhamento**
   - Em "Nome", digite: **Marketing <> Finanças**.
   - Para ID da VPC (Solicitante), escolha **Marketing VPC**.
   - Revise o intervalo de CIDR da VPC de marketing: **10.10.0.0/16**.
   - Para VPC ID (Aceitador), escolha a **VPC financeira**.
   - Revise o intervalo de CIDR da VPC financeira: **172.31.0.0/16**.
   - Clique em "Criar conexão de peering".

3. **Aceitar Solicitação de Peering**
   - Verifique a mensagem de sucesso e o status de "Aceitação pendente".
   - Clique em "Ações" e escolha "Aceitar solicitação".
   - Na pop-up, clique em "Aceitar solicitação".
   - Verifique se o status mudou para "Ativo".

4. **Configurar Regras de Roteamento**
   - Na seção "Instâncias" do Amazon EC2, selecione a instância do MarketingServer.
   - Clique em "ID da sub-rede" e selecione a sub-rede disponível.
   - Na "Tabela de rotas", clique no ID da rota fornecido.
   - Escolha a tabela de rotas de marketing, clique em "Edit routes", e adicione uma rota:
     - **Destino**: 172.31.0.0/16
     - **Target**: Conexão de emparelhamento (Marketing <> Finanças)
   - Salve as alterações.

5. **Regras de Roteamento na VPC Financeira**
   - Selecione a instância do FinanceServer.
   - Clique em "ID da sub-rede" e selecione a sub-rede disponível.
   - Na "Tabela de rotas", escolha a tabela de rotas financeiras.
   - Clique em "Edit routes", e adicione uma rota:
     - **Destino**: 10.10.0.0/16
     - **Target**: Conexão de emparelhamento (Marketing <> Finanças)
   - Salve as alterações.

6. **Teste de Conectividade**
   - Selecione a instância do MarketingServer e clique em "Conectar".
   - Use o "Gerenciador de sessões" e clique em "Conectar".
   - No terminal, execute o comando `ping` usando o endereço IP privado do FinanceServer (substitua <172.31.x.xx>):
     ```bash
     ping <172.31.x.xx>
     ```
   - Verifique se o comando `ping` ainda não está funcionando e pressione `Ctrl+C` para sair do processo.

7. **Configurar Regras de Segurança**
   - Selecione a instância do FinanceServer, clique na guia "Segurança" e no grupo de segurança do FinanceServer.
   - Na guia "Regras de entrada", clique em "Editar regras de entrada".
   - Adicione uma regra:
     - **Tipo**: ICMP personalizado - IPv4
     - **Origem**: 10.10.0.0/16
   - Salve as regras.

8. **Verificar Conectividade**
   - Conecte-se à instância MarketingServer e no terminal, execute novamente o comando `ping`:
     ```bash
     ping <172.31.x.xx>
     ```
   - Verifique se a comunicação com a instância do FinanceServer foi estabelecida.
  
   Lab: Skill Builder AWS : https://cloudquest.skillbuilder.aws/?skill_path=64ff2e01-483c-469d-8dbc-9a54620b6c2c

   ![chrome_D8D9dMC2KZ](https://github.com/user-attachments/assets/0e99255e-e5e5-476e-b097-fb825250f420)


Pronto! Agora, as instâncias devem conseguir se comunicar. 🚀
