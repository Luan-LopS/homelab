

# Firewall e Básico de Redes

## pfSense

O **pfSense** é um firewall/roteador open source baseado no **FreeBSD**.

* Licença: **BSD (Open Source)**
* Herda diversas funcionalidades do **FreeBSD**
* Muito utilizado para:

  * Firewalls corporativos
  * Gateways de rede
  * Servidores de borda

### Principais recursos

* VLAN
* VPN
* Packet Filter (pf)
* NAT
* CARP (failover / alta disponibilidade)
* Rate limit
* Filtragem por MAC
* Framework modular
* Interface web para gerenciamento

---

# Introdução a Redes

Uma **rede de computadores** é a conexão entre **dois ou mais dispositivos** que permite comunicação e compartilhamento de recursos.

## Conceitos básicos

**Host**
Dispositivo conectado à rede (computador, servidor, impressora, etc).

**Servidor**
Host que **oferece serviços ou recursos** para outros dispositivos na rede.

**Cliente**
Dispositivo ou aplicação que **consome serviços do servidor**.

**Localhost**
Endereço que representa **a própria máquina**.

Exemplo:

```
127.0.0.1
```

**Remote Host**
Máquina remota acessada pela rede.

Protocolos comuns:

* RDP
* SSH

---

## Servidor Proxy

Um **proxy** atua como intermediário entre o cliente e a internet.

Funções principais:

* Ocultar o IP real do cliente
* Filtrar tráfego
* Controle de acesso
* Cache de conteúdo
* Monitoramento

Fluxo:

```
Cliente → Proxy → Internet
Internet → Proxy → Cliente
```

---

# Protocolos de Rede

## NetBIOS

API de rede antiga criada pela **IBM/Microsoft** para comunicação em redes locais.

Funções:

* Compartilhamento de arquivos
* Compartilhamento de impressoras
* Identificação de hosts na rede

Muito usado em redes **Windows antigas**.

---

## TCP/IP

O **TCP/IP** é o conjunto de protocolos que permite a comunicação na internet.

Ele divide a comunicação em **camadas** e envia os dados em **pacotes**.

Componentes principais:

* **TCP (Transmission Control Protocol)**
  Protocolo confiável orientado à conexão.

* **IP (Internet Protocol)**
  Responsável por endereçamento e roteamento.

Camadas do modelo TCP/IP:

1. Aplicação
2. Transporte
3. Internet
4. Acesso à rede

---

## Bluetooth

Tecnologia de comunicação sem fio de **curto alcance (WPAN)**.

Características:

* Frequência: **2.4 GHz**
* Baixo consumo de energia
* Comunicação entre dispositivos próximos

Exemplos:

* Fones de ouvido
* Teclados
* Smartphones

---

## Instant Messaging (IM)

Protocolos de mensagens instantâneas permitem troca de:

* Texto
* Voz
* Arquivos

Protocolos populares:

* **XMPP**
* **Matrix**
* **Signal Protocol**
* **RCS**

---

## Internet

A **Internet** é uma rede mundial formada pela interconexão de diversas redes menores.

---

## ARPANET

A **ARPANET** foi a primeira rede de computadores de grande escala.

Desenvolvida por:

* Departamento de Defesa dos EUA
* Universidades

Ela deu origem à **Internet moderna**.

---

# Modelo OSI

O **Modelo OSI (Open Systems Interconnection)** divide a comunicação em **7 camadas**.

| Camada       | Função                         |
| ------------ | ------------------------------ |
| Aplicação    | Interface com softwares        |
| Apresentação | Formatação, criptografia       |
| Sessão       | Controle de sessões            |
| Transporte   | Entrega confiável de dados     |
| Rede         | Endereçamento e roteamento     |
| Enlace       | Endereçamento físico (MAC)     |
| Física       | Transmissão elétrica ou óptica |

---

# Modelo TCP/IP

Modelo utilizado na internet.

| Camada TCP/IP | Equivalente OSI                   |
| ------------- | --------------------------------- |
| Aplicação     | Aplicação + Apresentação + Sessão |
| Transporte    | Transporte                        |
| Internet      | Rede                              |
| Acesso à rede | Enlace + Física                   |

---

## Tipos de comunicação

### Orientado à conexão

Exemplo:

**TCP**

Características:

* Confiável
* Controle de erro
* Confirma entrega

---

### Não orientado à conexão

Exemplo:

**UDP**

Características:

* Mais rápido
* Sem confirmação de entrega
* Usado em streaming, DNS, VoIP

---

# PPP e PPPoE

**PPP (Point-to-Point Protocol)** é usado para comunicação ponto a ponto.

Estrutura:

```
Header | Dados | Trailer
```

Muito utilizado em:

* Conexões DSL
* PPPoE (PPP over Ethernet)

---

# ICMP

**ICMP (Internet Control Message Protocol)** é usado para diagnóstico e controle da rede.

Exemplo de comando:

```bash
ping google.com -4
```

### Tipos de mensagens ICMP

| Código | Significado              |
| ------ | ------------------------ |
| 0      | Echo Reply               |
| 3      | Destination Unreachable  |
| 4      | Source Quench (obsoleto) |
| 5      | Redirect                 |
| 8      | Echo Request             |
| 11     | Time Exceeded            |
| 12     | Parameter Problem        |

---

# Encapsulamento de Pacotes

Processo de adicionar **headers** aos dados conforme passam pelas camadas.

Fluxo:

```
Aplicação → Dados

Transporte
TCP → Segmento
UDP → Datagrama

Rede
IP → Pacote

Enlace
Frame → Quadro
```

Estrutura completa:

```
Frame Header | IP Header | TCP/UDP Header | Dados | Frame Trailer
```

---

# Verificação de Integridade

Para validar se os dados sofreram alteração usamos **checksums**.

Exemplo:

```
sha256sum arquivo.iso
```

---

# Endereçamento MAC

Endereço físico da placa de rede.

Formato:

```
01:3A:1D:54:6B:32
```

Divisão:

* **Primeiros 3 bytes → fabricante (OUI)**
* **Últimos 3 bytes → identificador da interface**

Verificar no Linux:

```bash
ip a
```

---

# Endereçamento IPv4

Exemplo:

```
192.168.110.23
```

Máscara:

```
255.255.255.0
```

Divisão:

```
Rede: 192.168.110.0
Host: .23
```

### Endereços importantes

| Tipo             | Exemplo         |
| ---------------- | --------------- |
| Endereço da rede | 192.168.110.0   |
| Host             | 192.168.110.23  |
| Broadcast        | 192.168.110.255 |

**Broadcast** envia pacotes para **todos os dispositivos da rede**.

Excesso pode causar **broadcast storm**.

---

# Classes de IPv4

| Classe | Bits iniciais | Máscara padrão | Faixa                       |
| ------ | ------------- | -------------- | --------------------------- |
| A      | 0             | 255.0.0.0      | 0.0.0.0 – 127.255.255.255   |
| B      | 10            | 255.255.0.0    | 128.0.0.0 – 191.255.255.255 |
| C      | 110           | 255.255.255.0  | 192.0.0.0 – 223.255.255.255 |
| D      | 1110          | —              | 224.0.0.0 – 239.255.255.255 |
| E      | 1111          | —              | 240.0.0.0 – 255.255.255.255 |

---

# Redes Privadas (RFC 1918)

| Classe | Faixa                         |
| ------ | ----------------------------- |
| A      | 10.0.0.0 – 10.255.255.255     |
| B      | 172.16.0.0 – 172.31.255.255   |
| C      | 192.168.0.0 – 192.168.255.255 |

---

# Loopback

Endereço que aponta para **a própria máquina**.

```
127.0.0.1
```

Interface:

```
lo
```

---

# IPv6

O IPv6 foi criado para resolver a **escassez de endereços IPv4**.

Padronizado pela **IETF**.

Implementação global começou por volta de **2012**.

---

## Formato do IPv6

Possui **128 bits**.

Representado por **8 grupos hexadecimais**:

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

Zeros podem ser omitidos:

```
2001:db8::8a2e:370:7334
```

---

## Tipos de endereços IPv6

| Tipo         | Faixa     |
| ------------ | --------- |
| Loopback     | ::1       |
| Multicast    | FF00::/8  |
| Link-local   | FE80::/10 |
| Unique local | FC00::/7  |
| Global       | 2000::/3  |

---

## Link-local

Equivalente ao **169.254.0.0/16 no IPv4**.

Usado para comunicação dentro da mesma rede.

Nunca é roteado.

---

# SLAAC

**Stateless Address Autoconfiguration**

Permite que um host configure seu IPv6 automaticamente.

O roteador envia:

**RA (Router Advertisement)**

---

# Neighbor Discovery (ND)

Substitui o **ARP** no IPv6.

Baseado no **ICMPv6**.

Mensagens principais:

| Tipo | Função                 |
| ---- | ---------------------- |
| NS   | Neighbor Solicitation  |
| NA   | Neighbor Advertisement |
| RS   | Router Solicitation    |
| RA   | Router Advertisement   |

---

# DNS

**Domain Name System**

Responsável por traduzir:

```
IP → Nome
Nome → IP
```

Exemplo:

```
google.com → 8.8.8.8
```

Servidor DNS público do Google:

```
8.8.8.8
```

Servidor DNS pode ser implementado com:

* **BIND**
* **Unbound**
* **PowerDNS**

---

# DHCP

**Dynamic Host Configuration Protocol**

Protocolo que distribui automaticamente:

* Endereço IP
* Gateway
* DNS
* Máscara de rede

Fluxo básico:

```
DHCPDISCOVER
DHCPOFFER
DHCPREQUEST
DHCPACK
```

---