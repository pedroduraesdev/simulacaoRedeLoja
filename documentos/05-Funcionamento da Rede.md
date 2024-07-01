### Funcionamento da Rede

Este documento descreve a configuração e o funcionamento da rede da operadora, detalhando como a internet é distribuída aos clientes através de diferentes segmentos de rede.

#### Servidor da Operadora

O servidor DNS da operadora, com o IP 172.16.0.1, atua como o ponto de entrada da internet. A partir deste servidor, a conexão passa pelo roteador da operadora, que transmite a internet com o IP 172.16.0.2. Este IP é então retransmitido como 168.168.0.1 para a rede interna que será distribuída aos clientes.

#### Rede do Cliente

Na casa do cliente, o modem recebe a conexão e a transmite para o servidor local da loja com o IP 162.168.0.2.

#### Estrutura de Rede na Loja

O servidor da loja distribui a conexão para o roteador (ROTEADOR LOJA), que é configurado para gerenciar três redes distintas:

1. **Rede Servidor - Roteador:** IP 152.168.1.0
2. **Rede Roteador - Caixas:** IP 192.168.3.0
3. **Rede Roteador - Administrativo:** IP 182.168.2.0

### Configuração de Segurança

Para aumentar a segurança dos dados da loja, foram implementadas políticas de firewall no servidor da loja:

- **Bloqueio para Caixas (IP 192.0.0.0):** Foi configurada uma regra no firewall do servidor para bloquear o acesso à internet (DNS) para todos os computadores na faixa de IP 192.0.0.0, utilizando o protocolo TCP. Outros protocolos foram permitidos para esta faixa de IP.
  
- **Permissões para Administrativo (IP 182.0.0.0):** Computadores na faixa de IP 182.0.0.0 têm permissão para acessar sites normalmente, com todos os protocolos permitidos.

### Configuração do Firewall

A configuração do firewall foi realizada através do acesso ao Servidor da Loja > Desktop > Firewall, selecionando a placa de rede apropriada e criando as regras de filtragem de acordo com as políticas de segurança estabelecidas.
