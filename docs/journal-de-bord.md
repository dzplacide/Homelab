# Journal de bord

[← Retour au homelab](../README.md)

Les mises à jour les plus récentes sont en haut. Mes travaux pratiques réalisés dans le homelab sont notés ici comme des étapes du homelab.

<!-- Modèle pour une nouvelle entrée :
## AAAA-MM-JJ — Titre court
- Ce que j'ai fait
- Problème rencontré et solution
- Ce que j'ai appris
-->

## Novembre 2026 — Serveur d'impression (en cours)
- Imprimante Canon MF264dw branchée par Ethernet dans le VLAN 20 (via le TL-SG105), adresse fixe 192.168.20.30.
- Installation de CUPS sur le client Ubuntu (192.168.10.21) pour partager l'imprimante avec les postes du domaine.

## Novembre 2026 — Services Linux dans le domaine samba.lan
- DNS du domaine géré avec `samba-tool` et RSAT depuis Windows 11.
- Postes clients placés dans le VLAN 10 pour les tests.

## Novembre 2026 — Utilisateurs, disques et partages
- Script Bash qui crée les utilisateurs et les groupes Samba AD à partir d'un fichier CSV.
- Disques, quotas, RAID 1 logiciel avec `mdadm` et partages de fichiers Samba.

## Contrôleur de domaine Samba AD
- Installation du contrôleur de domaine Samba sur Ubuntu Server : domaine `samba.lan`, royaume `SAMBA.LAN`, serveur `srv-ub-dc1` (192.168.10.20).
- Deux PC Windows 11 joints au domaine. Le poste `PLACIDE` administre le domaine avec RSAT.

## Réseau de base
- Configuration des VLAN 10, 20 et 30 sur le Cisco 1921 et le Netgear GS308E.
- Routage inter-VLAN validé de bout en bout.
- Accès d'administration au routeur en SSH.

## Serveur
- Dell PowerEdge R320 : 4 disques en RAID 5 (≈ 2,5 To), Hyper-V pour les machines virtuelles.

## Prochaines étapes
- [ ] Contrôleur de domaine Windows Server dans une VM dédiée (révision Serveurs I : UO, GPO, DFS, profils itinérants)
- [ ] Second contrôleur de domaine Samba sur une autre VM Ubuntu
- [ ] Relier les VM Hyper-V au VLAN 30 par le 2e port réseau du R320
