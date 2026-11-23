# Plan d'adressage

[← Retour au homelab](../README.md)

## VLAN

| VLAN | Nom | Réseau | Passerelle | DHCP |
| --- | --- | --- | --- | --- |
| 10 | Serveurs | 192.168.10.0/24 | sur le Cisco 1921 | Non, adresses fixes |
| 20 | Clients | 192.168.20.0/24 | sur le Cisco 1921 | Oui, pool sur le routeur |
| 30 | Labo | 192.168.30.0/24 | sur le Cisco 1921 | Non sur le routeur (DHCP testé sur des VM) |

Le routage inter-VLAN se fait sur le Cisco 1921. Le lien entre le routeur et le Netgear GS308E est un trunk 802.1Q.

## Adresses fixes

| Hôte | Rôle | VLAN | Adresse |
| --- | --- | --- | --- |
| `srv-ub-dc1` | Contrôleur de domaine Samba AD (Ubuntu Server, VM Hyper-V) | 10 | 192.168.10.20 |
| `client-VM` | Client Ubuntu, serveur d'impression CUPS | 10 | 192.168.10.21 |
| `PLACIDE` | PC Windows 11 Pro avec RSAT, joint à `samba.lan` | 10 | 192.168.10.40 |
| `PC-PLACIDE` | PC Windows 11, joint à `samba.lan` | 20 | DHCP |
| Canon MF264dw | Imprimante réseau | 20 | 192.168.20.30 |

## Pourquoi le VLAN 30 n'a pas de DHCP sur le routeur

Le VLAN 30 sert à mes exercices. J'y installe mes propres serveurs DHCP (Windows Server, isc-dhcp-server) sur des VM. Sans DHCP sur le routeur, il n'y a pas deux serveurs qui répondent en même temps aux clients.
