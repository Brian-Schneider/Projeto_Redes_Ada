# Projeto de Redes - Vem Ser Tech (DevOps)

## Objetivo

Criar duas redes diferentes e realizar a comunicação via ICMP (Internet Control Message Protocol) entre uma e outra, de modo que um dos Desktops da Rede A, consiga colocar em seu navegador interno, o endereço do Site do Servidor Web que está na Rede B, e a página possa ser carregada corretamente, validando deste modo o Roteamento entre as Redes, DNS e a camada da Aplicação funcionando corretamente.

## Resultado Esperado

![](/final.jpg)

## Parâmetros de Configuração

### Rede A

- 192.168.10.0/24 (Rede);
- 192.168.10.254 (Gateway);
- 192.168.10.253 (DHCP e DNS);
- IP Estático para os servidores e Dinâmico (DHCP) para os PCs.

### Rede B

- 172.15.0.0/24 (Rede);
- 172.15.0.254 (Gateway);
- 172.15.0.253 (DHCP e DNS);
- 172.15.0.252 (Servidor Web);
- IP Estático para os servidores e Dinâmico (DHCP) para os PCs.

## Equipamentos

- 1 Router 1841
- 2 Switches 2960 24TT
- 8 PCs
- 3 Servers - PT

## Roteamento

Para que exista a comunicação entre as duas redes, é de suma importância a configuração correta do Roteador. Para isso, configura-se as portas FastEthernet (após ligá-las) com os IPs que serão utilizados como Gateway pelas respectivas redes a quem se encontram conectadas (nesse caso, a F0/0 conectada à Rede A e a F0/1 à Rede B).

Entretanto isso não basta para que possa haver troca de informações entre as redes, necessitando adicionar ambas as redes (192.168.10.0 e 172.15.0.0) ao RIP (Routing Information Protocol).

## DNS (Domain Name Service)

O DNS tem como função "traduzir" nomes de domínios legíveis para humanos em endereços IP. Nesse caso, ambos os Servidores DHCP/DNS terão "ademas" como nome de domínio, sendo o mesmo correspondente ao IP do Servidor Web (172.15.0.252).