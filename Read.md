# CrustyCrypto — Crypto ScoreTotal PRO

CrustyCrypto est une page **HTML/CSS/JS** (sans framework) qui affiche en temps réel une liste de cryptos et calcule un score de sélection inspiré d’un “pré-pump scanner”.

**Slogan : _Crypto ScoreTotal PRO_**

> Objectif : repérer rapidement des actifs avec un mix **fondamentaux (proxys)** + **activité/momentum** + **volatilité**, tout en évitant les entrées trop tardives grâce à une pénalité “overextension”.

---

## ✨ Features

- ✅ Données temps réel via **CoinGecko** (prix, variations, volume, market cap, rank)
- ✅ Calcul du **ScoreTotal PRO** (tri du Top N)
- ✅ Auto-refresh (sans chevauchement des requêtes)
- ✅ Pénalité automatique d’overextension (évite d’acheter “trop haut”)
- ✅ Interface simple, rapide, responsive
- ✅ 100% front (un seul fichier)

---

## 🧮 Formule — ScoreTotal PRO

Chaque critère est noté sur une échelle **0 → 5** (proxies automatiques + quelques valeurs par défaut).

\[
\textbf{ScoreTotal PRO} =
0.7 \times (\text{Narratif} + \text{Produit} + \text{Exposure} + \text{Tokenomics} + \text{Structure})
+ 3 \times \text{Catalyst Imminent}
+ 4 \times \text{Pré-Pump Technical / On-Chain}
+ \text{Volatilité Pré-Pump}
+ \text{Bonus Early Momentum}
- \textbf{Overextension Penalty}
\]

### Notes sur les proxys
- **Narratif / Produit / Structure** : critères “humains” ⇒ valeurs par défaut dans le code (modifiable via overrides).
- **Exposure** : proxy basé sur le **rank market cap** (plus le rank est haut, plus l’exposition est forte).
- **Tokenomics** : proxy basé sur `circulating_supply / total_supply` (si dispo).
- **Pré-Pump Technical / On-Chain** : proxy basé sur `volume/marketcap` + momentum.
- **Volatilité Pré-Pump** : proxy basé sur `(high_24h - low_24h) / price`.
- **Overextension Penalty** : proxy basé sur % 24h et % 7j (si déjà monté trop vite, pénalité).

---

## 🚀 Installation / Utilisation

### Option A — Simple (local)
1. Télécharge le fichier `crustyCrypto.html`
2. Ouvre-le dans ton navigateur (double-clic)

> Si ton navigateur bloque certaines requêtes, lance un petit serveur local :
- **Python**
  ```bash
  python -m http.server 8080
