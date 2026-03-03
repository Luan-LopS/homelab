# 🏠 HomeLab Infrastructure Lab

Projeto onde vou alinhar teoria com a prática.  
Para cada item que estudar, realizarei configurações e explicações com o intuito de documentar e aprimorar meus conhecimentos em todos os tópicos abordados aqui. 

Para acompanhar em qual fase de estudo estou, basta verificar o [CHANGELOG](CHANGELOG.md), o qual mostrará qual tema estou estudando e o nível aproximado em cada conteúdo.  

## 🎯 Objetivo

Aprimorar e desenvolver conhecimento nas áreas abaixo:

- [Linux](linux/README.md)
- Rede
- Segurança
- Docker
- Terraform
- Virtualização
- CI/CD
- Dev
- Firewall
- Monitoramento e Observabilidade
- Pentest
- IA

## 🧠 Metodologia 

O aprendizado será baseado em:

1. Estudo teórico (cursos e documentação oficial)
2. Implementação prática no homelab
3. Documentação técnica das configurações
4. Registro de evolução no CHANGELOG
5. Versionamento utilizando Git

## 🚀 Propósito 

Este laboratório tem como objetivo:

- Simular ambiente de infraestrutura real
- Aplicar boas práticas de segurança
- Desenvolver pensamento arquitetural e crítico
- Evoluir competências em infraestrutura e segurança 

## 🏗️ Arquitetura do Laboratório

O ambiente é composto por três camadas principais:  

### 🔥 Firewall dedicado
- pfSense 
- Hardware
    - Plataforma
    - Processador
    - 8 GB de RAM DDR2
    - SSD 120 GB de armazenamento

- Função
    - Controle de tráfego
    - Regras de firewall
    - VPN
    - IDS/IPS (Suricata)
    - NAC

### 🖥️ Ambiente de Virtualização
- Proxmox VE
- Hardware
    - Plataforma X79
    - Processador Xeon
    - 32 GB de RAM DDR3
    - SSD 500 GB de armazenamento
    - Esta máquina terá vários ambientes

- Função:
    - Hospedar VMs e Dockers de teste
    - Ambiente Linux
    - Laboratórios
        - Redes
        - Linux
        - Monitoramento
        - Portainer
        - Pentest

### 💾 NAS dedicado

- TrueNAS
- Hardware
    - Plataforma
    - Processador
    - 4 GB de RAM
    - 3 discos de 1 TB

- Função
    - Backups
    - Armazenamento de ISOs
    - Armazenamento de dados (ciclo de vida dos dados)
    - RAID 5  