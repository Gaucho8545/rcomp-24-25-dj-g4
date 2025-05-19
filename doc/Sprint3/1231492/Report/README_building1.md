RCOMP 2024-2025 Project - Sprint 3 - 1231492 
=========================================================================

### Building 1

#### OSPF (Open Shortest Path First)

- Todas as rotas estáticas foram removidas, exceto a default route que permite acesso ao ISP.
- O router do Edifício 1 foi configurado com OSPF, inserindo as redes locais na área 1, e a ligação ao ISP na área 0 (backbone).

```
Router(config)# router ospf 1
Router(config-router)# network 10.25.32.0 0.0.1.255 area 1
Router(config-router)# network 10.25.33.0 0.0.0.255 area 1
Router(config-router)# network 10.25.32.128 0.0.0.127 area 1
Router(config-router)# network [IP_BACKBONE] [WILDCARD] area 0
Router(config-router)# default-information originate
```

#### HTTP Server

- Um segundo servidor foi adicionado na VLAN da DMZ (10.25.32.128/25).
- Foi ativado o serviço HTTP/HTTPS e criada uma página HTML simples identificando o Edifício 1.

#### DHCPv4 Service

- O router `B1_RT0` fornece DHCPv4 a todas as redes exceto a DMZ e o backbone.

```
ip dhcp excluded-address 10.25.32.1 10.25.32.10
ip dhcp excluded-address 10.25.32.129 10.25.32.135
ip dhcp excluded-address 10.25.33.1 10.25.33.10
ip dhcp excluded-address 10.25.33.129 10.25.33.135
ip dhcp excluded-address 10.25.33.193 10.25.33.199

ip dhcp pool GROUND_FLOOR
 network 10.25.33.192 255.255.255.192
 default-router 10.25.33.193
 dns-server 10.25.32.129
 domain-name building-1.rcomp-24-25-cc-gn

ip dhcp pool FLOOR_ONE
 network 10.25.33.128 255.255.255.192
 default-router 10.25.33.129
 dns-server 10.25.32.129
 domain-name building-1.rcomp-24-25-cc-gn

ip dhcp pool WIRELESS
 network 10.25.33.0 255.255.255.128
 default-router 10.25.33.1
 dns-server 10.25.32.129
 domain-name building-1.rcomp-24-25-cc-gn

ip dhcp pool VOIP
 network 10.25.32.0 255.255.255.128
 default-router 10.25.32.1
 dns-server 10.25.32.129
 domain-name building-1.rcomp-24-25-cc-gn
 option 150 ip 10.25.32.129
```

#### VoIP Service

- Foram ligados dois telefones Cisco 7960 com VLAN de voz (411).
- A interface dos switches ligada aos telefones tem:

```
switchport voice vlan 411
no switchport access vlan
```

- As chamadas entre edifícios foram configuradas com os comandos `dial-peer`:

```
dial-peer voice 10 voip
 destination-pattern 1...
 session target ipv4:10.25.32.1

dial-peer voice 20 voip
 destination-pattern 2...
 session target ipv4:[IP_ROUTER_BUILDING_2]

dial-peer voice 30 voip
 destination-pattern 3...
 session target ipv4:[IP_ROUTER_BUILDING_3]
```

#### DNS

- Foi criado o domínio raiz da equipa: `rcomp-24-25-dj-g4`.
- O servidor DNS foi configurado com:
  - Registo `A` → `ns.rcomp-24-25-dj-g4`
  - CNAME → `www`, `web`
  - NS e glue records para os servidores DNS dos outros edifícios.

> Exemplo de FQDN: `ns.rcomp-24-25-cc-gn`


#### NAT 

- NAT estático foi configurado para redirecionar HTTP/HTTPS para o servidor da DMZ:

```
ip nat inside source static tcp 10.25.32.129 interface FastEthernet0/0
ip nat inside source static tcp 10.25.32.129  interface FastEthernet0/0 
```

- Interfaces NAT:

```
interface FastEthernet0/0
 ip nat outside

interface FastEthernet0/1
 ip nat inside
```

#### Firewall (ACLs)

- ACL configurada para:
  - Bloquear spoofing
  - Permitir ping
  - Permitir apenas DNS e HTTP/HTTPS para a DMZ
  - Permitir apenas serviços essenciais ao router
  - Permitir todo o resto

```

