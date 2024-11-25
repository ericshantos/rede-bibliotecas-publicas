<h1 align='center'>Rede de Bibliotecas Públicas - A3 de Ambientes Computacionais e Conectividade</h1>

### Descrição do Projeto

Este trabalho foi desenvolvido como parte da Unidade Curricular de **Ambientes Computacionais e Conectividade** (A3). O projeto consiste na criação de uma rede de computadores para uma biblioteca pública, implementada no **Cisco Packet Tracer**. A rede foi projetada para atender às necessidades tanto dos funcionários quanto dos visitantes, garantindo conectividade e segurança.

### Estrutura da Rede

- **Classe de Rede**: Classe C (192.168.0.0/12)
  - **Máscara de Sub-rede**: /24 (255.255.255.0)

### Segmentação e Organização em Sub-redes e VLANs

A biblioteca constitui uma sub-rede isolada, com a configuração de VLANs para separar e organizar os dispositivos e os tipos de usuários:

- **VLAN 10 (Usuários)**: Para computadores de uso público.
- **VLAN 20 (Funcionários)**: Para os dispositivos da equipe da biblioteca.
- **VLAN 30 (Internet gratuita)**: Para acesso gratuito a internet.

### Acesso à Internet

A biblioteca possui acesso gratuito à internet, configurado no roteador para permitir que todos os dispositivos dentro da rede tenham acesso à web. Esse acesso será gerenciado pela política de segurança de rede, garantindo que o tráfego de dados seja monitorado e controlado.

### Mapa Analítico dos Dispositivos

A biblioteca segue a estrutura básica de rede e alocação de IPs:

#### Biblioteca (192.168.0.0/24)
- **Switch Core**: Modelo 2960
- **Roteador**: Modelo 2811
- **Servidores DHCP**: IP: 172.16.10.1 – VLAN 10; IP: 192.168.20.1 - VLAN 20; IP: 192.168.30.1 - VLAN 30 
- **Computadores Públicos**: 5 PCs (IPs: 192.168.10.1 - 192.168.10.6) – VLAN 10
- **Computadores para Funcionários**: 3 PCs (IPs: 192.168.20.1 - 192.168.20.5) – VLAN 20
- **Telefone IP**: 1x telefone por funcionário (IPs: 192.168.30.1 - 192.168.30.6) - VLAN 30
- **Impressora**: Conectada à VLAN FUNCIONARIOS, IP: 192.168.20.1 – VLAN 20

### Configuração de VLANs e Roteamento

- Configuração das **VLANs** nos switches para separar o tráfego de usuários e funcionários.
- Uso de **trunking** para permitir a passagem de múltiplas VLANs através dos switches.
- **Roteamento** configurado no roteador para permitir comunicação entre as sub-redes das bibliotecas e para fornecer o acesso à rede MAN.

## Ferramentas Utilizadas

- **Cisco Packet Tracer**: Para a modelagem e simulação da rede.
- **Configuração VLAN**: Gerenciamento de tráfego e segmentação de rede.

## Estrutura do Arquivo

- O arquivo `.pkt` contém a simulação completa da rede no Cisco Packet Tracer.
- Configurações detalhadas, como IPs e VLANs, estão documentadas no simulador.

---

### Segurança e Controle de Acesso

- Isolamento de tráfego entre **VLANs** para segurança dos dados.
- Acesso restrito entre as **VLANs** de Usuários e Funcionários.
