
# ZMQ-SRSRAN : Simulation LTE/5G avec ZeroMQ, srsRAN et Open5GS

## 🧠 Présentation du projet

Ce projet vise à mettre en place une infrastructure LTE/5G **100 % logicielle**, sans besoin de matériel physique, en utilisant :

- `srsRAN` : pour la simulation des composants radio (gNB, UE)
- `ZeroMQ (ZMQ)` : comme middleware pour connecter les modules
- `GNU Radio` : en tant que broker ZMQ pour router les flux
- `Open5GS` : pour simuler le cœur de réseau 5G

Objectif principal : simuler une communication **multi-UE ↔ gNB ↔ 5GC** via un canal ZMQ.

## ⚙️ Technologies utilisées

| Composant     | Rôle                                                          |
|---------------|---------------------------------------------------------------|
| `srsUE`       | Simulation d’UEs (User Equipments)                            |
| `srsENB/gNB`  | Point d’accès radio connecté au 5GC                           |
| `ZeroMQ`      | Canal de transport des flux entre UE et gNB                   |
| `GNU Radio`   | Broker et connecteur entre les flux (ZMQ Source/Sink)        |
| `Open5GS`     | Cœur EPC/5GC (AMF, SMF, UPF, HSS, etc.)                       |

## 🏗️ Architecture

```
[ srsUE ] <--> [ GNU Radio + ZMQ ] <--> [ gNB (srsENB) ] <--> [ Open5GS ]
```

## 🚀 Mise en place

1. **Installer les dépendances** (`srsRAN`, `GNU Radio`, `Open5GS`)
2. **Configurer les fichiers :**
   - `subscriber_db.csv` pour les UEs
   - `open5gs.env` pour la base de données des abonnés
3. **Lancer dans l’ordre :**
   - `Open5GS`
   - `gNB`
   - `GNU Radio + Flowgraph ZMQ`
   - `UEs` (via script ou terminal)
4. **Tester la connectivité avec `ping` entre gNB et UE**

## 📊 Mesures de performance

- 📶 **RSRP** : Variation mesurée avec `pathloss` modifié
- 📡 **Uplink/Downlink** : Activité observée via `ping` et graphiques
- 🔁 **Multi-UE** : Communication simultanée démontrée

## 📌 Résultats

- ✅ Communication fonctionnelle multi-UE ↔ gNB ↔ 5GC
- ✅ Visualisation en temps réel via GNU Radio
- ✅ Résilience grâce au transport asynchrone de ZeroMQ

## ⚠️ Limites identifiées

- Stabilité affectée avec > 3 UEs
- Optimisation des buffers ZMQ nécessaire
- Gestions d'erreurs à renforcer pour la scalabilité

## 💡 Perspectives

- Intégration Docker pour tout le pipeline
- Ajout d'une interface Web de supervision
- Simulation de traffic IoT/VoLTE dans les UEs

## 📚 Ressources

- [srsRAN](https://docs.srsran.com/projects/project/en/latest/)
- [Open5GS](https://open5gs.org/open5gs/)
- [GNU Radio ZMQ Blocks](https://wiki.gnuradio.org/index.php/ZMQ)

## 👤 Auteur

**Yassine KABBAJ**  
Encadré par : **Mohamed LABIOD**
