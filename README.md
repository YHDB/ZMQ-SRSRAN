
# ZMQ-SRSRAN : Simulation LTE/5G avec ZeroMQ, srsRAN et Open5GS

## 🧠 Présentation du projet

Ce projet vise à mettre en place une infrastructure LTE/5G **100 % logicielle**, sans besoin de matériel physique, en utilisant :

- `srsRAN` : pour la simulation des composants radio (gNB, UE)
- `ZeroMQ (ZMQ)` : comme middleware pour connecter les modules
- `GNU Radio` : en tant que broker ZMQ pour router les flux
- `Open5GS` : pour simuler le cœur de réseau 5G

## 🏗️ Architecture

![Architecture LTE/5G avec ZeroMQ](architecture_zmq_srsran.png)

## ⚙️ Technologies utilisées

| Composant     | Rôle                                                          |
|---------------|---------------------------------------------------------------|
| `srsUE`       | Simulation d’UEs (User Equipments)                            |
| `srsENB/gNB`  | Point d’accès radio connecté au 5GC                           |
| `ZeroMQ`      | Canal de transport des flux entre UE et gNB                   |
| `GNU Radio`   | Broker et connecteur entre les flux (ZMQ Source/Sink)        |
| `Open5GS`     | Cœur EPC/5GC (AMF, SMF, UPF, HSS, etc.)                       |

... (reste du fichier identique)
