RCOMP 2024-2025 Project - Sprint 3 - 1220834
=========================================================================

### Building 2

#### OSPF (Open Shortest Path First)

- Todas as rotas estáticas foram removidas, exceto a default route que permite acesso ao ISP.
- O router do Edifício 2 foi configurado com OSPF, inserindo as redes locais na área 2, e a ligação ao ISP na área 0 (backbone).

#### HTTP Server

- Um segundo servidor foi adicionado na VLAN da DMZ (10.25.36.3/25).
- Foi ativado o serviço HTTP/HTTPS e criada uma página HTML simples identificando o Edifício 2.

#### DHCPv4 Service

- O router `B2_RT0` fornece DHCPv4 a todas as redes exceto a DMZ e o backbone.

#### VoIP Service

- Foram ligados dois telefones Cisco 7960 com VLAN de voz (414).

#### DNS

- Foi criado o domínio raiz da equipa: `rcomp-24-25-dj-g4`.
- O servidor DNS foi configurado com:
    - Registo `A` → `ns.rcomp-24-25-dj-g4`
    - CNAME → `www`, `web`
    - NS e glue records para os servidores DNS dos outros edifícios.

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