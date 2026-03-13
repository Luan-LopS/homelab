# Firewall 
O curso que estou utiliza o pfsense mas utilizarei  o opSense, pelo seguinte motivo quero uma  imagem oficial, segura e sem ter que fazer cadastro em nenhum local.
Dito isso as duas  distribuições são muito parecidas.

#### OPNsense
https://opnsense.org/get-started/


Hardware:

    Processador: Pentium 4 CPU 3.00GHz
    Placa mãe: Itautec ST 4150  
    Memoria:  DDR2 4GB não  suporta mais que isso
    armazenamento:  128 Ssd sata


Realizar o  dowload de imagem ISO  conforme  configuração de Hardware  disponivel, crie um pendrive com a ISO, pode utilizar o balena Etcher para fazer o pendrive bootavel.
 
Com o pendrive em mãos partiremos para intalação  da ISO, iniciando o processo  de  instalação.

Acessando a BIOS do computador, atraves do botão  DEL OU F2, ou  procure no google qual o botão  correto para a sua placa, tendo  acessado a BIOS uma   tela azul pra que nunca acessou kk, va nas configurações de BOOT e altere a hierarquia de dispositivos colocando  pendrive como primeiro para iniciar a instalação, feito isso salve e saia. 

A maquina irá reiniciar e provavelmente  será pelo pendrive, espere  o   sistema carregar as suas configurações, no primeiro acesso tera um modo live onde devemos realizar  o  login  com a credenciar padão do sistema no  caso do opnsense  é  user  root  e senha  opnsense, *observação devera  ser alterado no futuro.

Login realizado, teremos   acesso a interface do sistema  onde tera 12 opções se não  estiver errado, a primeira coisa que devemos verificar é  se o sistema conseguiu identificar  as  interfaces de  rede, caso não  acessamos  a opção 1  onde realizaremos a configuração da interfaces LAN e WAN. Verifique o MAC de pelo menos uma  interface para facilitar  na hora de  configura no meu caso a rede  LAN o MAC iniciava com 00.1A.  Terminado de configurar a as interfaces podemos realizar  o acesso web ou shh.

interface  web 192.168.1.1  é  endereço padão e ao  ssh root@192.168.1.1, no  meu  caso  acessei  a interface web onde realizaremos o restante das  configurações.

![alt text](image.png)

Uma indicação: ainda na etapa de instalação, realize a configuração de WAN e LAN e verifique com sua operadora qual o tipo de conexão utilizado, por exemplo: PPPoE, PPP ou DHCP. Realize  a configuração do mesmo antes de alterar a configuração de  rede de   router para  bridge, pois quando alterado  para  bridge o responsavel  por gerenciar  os ips sera o firewall.
