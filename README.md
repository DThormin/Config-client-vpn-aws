# AWS VPN

As soluções do AWS Virtual Private Network estabelecem conexões seguras entre redes locais, escritórios remotos, 
dispositivos de clientes e a rede global da AWS. O AWS VPN é composto por dois serviços: AWS Site-to-Site VPN e 
AWS Client VPN. Juntos, eles entregam uma solução de VPN na nuvem gerenciada, altamente disponível e elástica para 
proteger o tráfego da sua rede.
O AWS Site-to-Site VPN cria túneis criptografados entre a sua rede e as Amazon Virtual Private Clouds ou os AWS 
Transit Gateways. Para gerenciar o acesso remoto, o AWS Client VPN conecta seus usuários à AWS ou a recursos 
locais por meio de um cliente de software VPN.

# AWS Client VPN

O AWS Client VPN é um serviço VPN gerenciado com base no cliente que permite acessar com segurança seus recursos da 
AWS e recursos em sua rede local. Com o Client VPN, você pode acessar seus recursos de qualquer local usando um 
cliente VPN baseado em OpenVPN.

# Configuração Client VPN

Para realizar a configuração é necessário baixar a configuração do Endpoint da Client VPN. No arquivo de configuração baixado, deve ser adicionado as linhas que apontam para o certificado e a chave utilizados na configuração da VPN entre as linhas 33 - "</ca>" e 36 - "reneg-sec 0":

cert C:/Users/usuario/Desktop/openvpn/client1.domain.tld.crt

key C:/Users/usuario/Desktop/openvpn/client1.domain.tld.key

# OpenVPN Client para desktop

Este é o software cliente OpenVPN Connect oficial para plataformas de estação de trabalho desenvolvido e mantido pela OpenVPN Inc. Este é o programa cliente recomendado para o OpenVPN Access Server para habilitar VPN para Windows. A versão mais recente do OpenVPN para está disponível no site.
Você pode conectar seu computador diretamente ao AWS VPN para uma experiência VPN de ponta a ponta com os software OpenVPN Client. O cliente de software é compatível com todos os recursos do AWS VPN.

# Windows

1 - Inicialmente vamos para a página OpenVPN e vamos baixar o instalador do cliente Openvpn. Para isso vamos digitar o link abaixo.

https://openvpn.net/community-downloads/

2 - Depois de baixar o instalador do cliente OpenVPN, vamos executar o arquivo que acabamos de baixar. Para fazer isso, vamos clicar duas vezes com o mouse.

3 - Clicar em “Instalar agora”.

4 - Instalar cliente OpenVPN

5 - Depois disso, vamos dar permissão ao instalador do OpenVPN para acessar o disco.

6 - Vamos abrir o cliente OpenVPN, clicar em File, e importar o arquivo downloaded-client-config.ovpn para criar um novo perfil

7 - Vamos abrir o perfil no cliente OpenVPN e clicar em conectar

# Mac

1 - Inicialmente vamos para a página OpenVPN e vamos baixar o instalador do cliente Openvpn. Para isso vamos digitar o link abaixo.

https://tunnelblick.net/downloads.html

2 - Depois de baixar o instalador do cliente Tunnelblick, vamos executar o arquivo que acabamos de baixar. Para fazer isso, vamos clicar duas vezes com o mouse.

3 - Clicar em “Abrir”.

4 - Arrastar o arquivo de configuração downloaded-client-config.ovpn para o aplicativo

5 - Clicar em "Conectar a downloaded-client-config" no aplicativo.

# Linux 

Existem vários métodos que podem ser usados para instalar o cliente OpenVPN Client. Use o método fornecido na opção a seguir. 

1 - Antes de tudo, faça login na máquina cliente e instale o pacote OpenVPN com o seguinte comando:
$ sudo apt update
$ sudo apt install openvpn -y

2 – Conecte-se ao servidor OpenVPN com as configurações baixadas da AWS
$ openvpn --config downloaded-client-config.ovpn

3 - Verifique a conexão
$ ip a show tun0
