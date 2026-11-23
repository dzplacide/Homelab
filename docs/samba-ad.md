# Contrôleur de domaine Samba AD

[← Retour au homelab](../README.md)

| Paramètre | Valeur |
| --- | --- |
| Système | Ubuntu Server (VM sur Hyper-V) |
| Nom du serveur | `srv-ub-dc1` |
| Adresse | 192.168.10.20 (VLAN 10) |
| Domaine | `samba.lan` |
| Royaume Kerberos | `SAMBA.LAN` |
| Clients | 2 PC Windows 11, 1 client Ubuntu |

## Vérifications utiles

```bash
# Niveau fonctionnel du domaine
sudo samba-tool domain level show

# Utilisateurs et ordinateurs du domaine
sudo samba-tool user list
sudo samba-tool computer list

# DNS : enregistrement du contrôleur de domaine
host -t SRV _ldap._tcp.samba.lan
host -t A srv-ub-dc1.samba.lan

# Kerberos
kinit administrator@SAMBA.LAN
klist
```

## Administration depuis Windows

Le poste `PLACIDE` (Windows 11 Pro) a les outils **RSAT** : Utilisateurs et ordinateurs Active Directory, Gestionnaire DNS et Gestion des stratégies de groupe fonctionnent sur le domaine Samba comme sur un domaine Windows.

## Création d'utilisateurs en masse

Un script Bash lit un fichier CSV et crée les groupes et les utilisateurs avec `samba-tool`. *(Script à publier ici une fois nettoyé : sans mots de passe.)*
