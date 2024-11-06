<h1 align='center'>Rede de Bibliotecas Públicas - A3 de Ambientes Computacionais e Conectividade</h1>

> Este projeto é parte da A3 da Unidade Curricular de **Ambientes Computacionais e Conectividade** do curso de **Ciências da Computação**.

### Descrição do Projeto

O objetivo deste projeto é desenvolver uma rede integrada e escalável para cinco bibliotecas públicas interligadas em uma rede metropolitana (MAN). O projeto visa aplicar conceitos avançados de conectividade, segurança e escalabilidade, utilizando VLANs para segmentação de rede e uma configuração que permite a adição de novas unidades de forma fácil e organizada.

### Estrutura da Rede

- **Classe de Rede**: Classe B (172.16.0.0/12)
  - **Máscara de Sub-rede**: /12 (255.240.0.0), garantindo uma faixa de IPs ampla para expansão.

### Segmentação e Organização em Sub-redes e VLANs

Cada biblioteca constitui uma sub-rede isolada, com a configuração de VLANs para separar e organizar os dispositivos e os tipos de usuários:

- **VLAN 10 (Usuários)**: Para computadores de uso público.
- **VLAN 20 (Funcionários)**: Para os dispositivos da equipe da biblioteca.
- **VLAN 30 (Administração)**: Para servidores e dispositivos críticos de rede.

### Dispositivos de Rede em Cada Biblioteca

Cada biblioteca possui uma configuração padrão de dispositivos conectados, conforme listado a seguir:

- **Switch Core**: Switch principal que conecta todos os dispositivos e gerencia o tráfego entre VLANs.
- **Roteador**: Conecta a biblioteca à rede MAN.
- **Servidor Local**: Servidor de arquivos – VLAN 30.
- **Computadores Públicos**: 5 PCs para acesso do público – VLAN 10.
- **Computadores para Funcionários**: Até 7 PCs – VLAN 20.
- **Telefone IP**: Um dispositivo IP por cada computador, conectados via portas adicionais nos switches.
- **Impressora**: Uma impressora compartilhada por cada biblioteca, conectada à rede para uso de funcionários e usuários.

### Acesso à Internet

Cada biblioteca possui acesso gratuito à internet, configurado no roteador para permitir que todos os dispositivos dentro da rede tenham acesso à web. Esse acesso será gerenciado pela política de segurança de rede, garantindo que o tráfego de dados seja monitorado e controlado.

### Mapa Analítico dos Dispositivos

Cada biblioteca segue a mesma estrutura básica de rede e alocação de IPs:

#### Biblioteca 1 (Sub-rede 172.16.0.0/16)
- **Switch Core**: Modelo 2960, IP: 172.16.0.1
- **Roteador**: Modelo 2811, IP: 172.16.0.254
- **Servidor de Arquivos**: IP: 172.16.0.10 – VLAN 30
- **Computadores Públicos**: 5 PCs (IPs: 172.16.1.1 - 172.16.1.5) – VLAN 10
- **Computadores para Funcionários**: 7 PCs (IPs: 172.16.2.1 - 172.16.2.7) – VLAN 20
- **Telefone IP**: Associado a cada computador público e dos funcionários
- **Impressora**: Conectada à rede local, IP: 172.16.0.20 – VLAN 30

#### Bibliotecas 2 a 5

As demais bibliotecas seguem o mesmo padrão de configuração de dispositivos e IPs, sendo alocadas em sub-redes distintas.

### Dispositivos Necessários para Simulação no Cisco Packet Tracer

- **Switch Cisco 2960**: Usado para gerenciar a conectividade de dispositivos e VLANs.
- **Roteador Cisco 2811**: Conecta as sub-redes das bibliotecas e a rede MAN.
- **PCs**: Computadores de uso público (5 PCs por biblioteca) e para funcionários (7 PCs por biblioteca).
- **Telefone IP**: Um telefone IP por biblioteca.
- **Servidor**: Servidor de arquivos para as bibliotecas, conectado à VLAN 30.
- **Impressora**: Conectada à rede da biblioteca, compartilhada entre funcionários e usuários.
- **Acesso à Internet**: Configuração no roteador para permitir o acesso à internet a todos os dispositivos da rede.

### Configuração de VLANs e Roteamento

- Configuração das **VLANs** nos switches para separar o tráfego de usuários e funcionários.
- Uso de **trunking** para permitir a passagem de múltiplas VLANs através dos switches.
- **Roteamento** configurado no roteador para permitir comunicação entre as sub-redes das bibliotecas e para fornecer o acesso à rede MAN.

### Expansão e Flexibilidade

Com o uso de rede Classe B e sub-redes individuais, a configuração permite fácil expansão, com a possibilidade de adicionar novas bibliotecas na faixa de IPs da rede principal.

### Compatibilidade com Cisco Packet Tracer

Verificação dos dispositivos e componentes disponíveis no Cisco Packet Tracer para simulação:

- **Switch Cisco 2960**: Disponível para gerenciar a conexão de dispositivos e VLANs.
- **Roteador Cisco 2811**: Disponível para gerenciar a interconexão entre as sub-redes.
- **PC**: Disponível e configurável para VLANs e endereçamento IP.
- **Telefone IP**: Disponível para integração com a rede.
- **Servidor**: Disponível para simulação de arquivos e serviços locais.
- **Impressora**: Disponível para configuração na rede e compartilhamento entre dispositivos.

### Segurança e Controle de Acesso

- Isolamento de tráfego entre **VLANs** para segurança dos dados.
- Acesso restrito entre as **VLANs** de Usuários e Funcionários.
- Possível implementação de **ACLs** (Access Control Lists) para maior controle e segurança no acesso à internet e outros recursos.

### Conclusão

O projeto de rede atende aos requisitos de segurança, organização e escalabilidade. A separação em **VLANs** oferece isolamento e controle sobre o acesso de diferentes dispositivos, e todos os componentes são compatíveis com o **Cisco Packet Tracer** para simulação, permitindo testes e ajustes eficazes. A inclusão de impressoras e acesso gratuito à internet garante que as bibliotecas atendam às necessidades dos usuários e funcionários, proporcionando um ambiente de trabalho funcional e seguro.
