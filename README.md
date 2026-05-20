<div align="center">

# ultraLab

**Automatisation de revues systématiques de la littérature scientifique**

![Version](https://img.shields.io/badge/version-alpha-orange)
![Plateforme](https://img.shields.io/badge/Windows-10%2F11-blue)
![Statut](https://img.shields.io/badge/statut-en%20développement-yellow)

[**📥 Télécharger la dernière version**](https://github.com/xerael/ultralab/releases/latest) · [Guide d'installation](#installation) · [Premier lancement](#premier-lancement) · [Signaler un bug](https://github.com/xerael/Ultralab/issues)

</div>

---

## Présentation

UltraLab est une application de bureau qui automatise les étapes d'une revue systématique de littérature scientifique :

- 🔍 **Recherche multi-bases** : PubMed, OpenAlex, Crossref (et bientôt Embase, Scopus...)
- 🧠 **Screening IA** : décisions Include/Maybe/Exclude assistées par LLM local
- 📊 **Ranking et clustering** thématique automatisés
- 📄 **Téléchargement de PDFs** OA (Unpaywall, Europe PMC, CORE)
- 📋 **Extraction structurée** (PICOS) depuis PDFs via LLM
- 📑 **Export PRISMA** + RIS + Excel

L'IA tourne **localement** sur votre PC (via Ollama) ou sur un PC distant (via Tailscale) — vos données ne quittent jamais votre infrastructure.

---

## ⚠️ Statut : Alpha en développement actif

Cette version est destinée aux **alpha-testeurs**. Bugs et changements rapides à prévoir. Pour signaler un bug, ouvrez une issue [ici](https://github.com/xerael/ultralab/issues).

---

## Installation

### 1. Télécharger l'installateur

➡ **[Page Releases : télécharger UltraLab-Setup.exe](https://github.com/xerael/ultralab/releases/latest)**

Cliquez sur le fichier `UltraLab-Setup.exe` dans la liste **Assets** de la dernière release.

### 2. Pré-requis

Avant de lancer l'installateur, installez ces 2 outils gratuits :

| Outil | Lien | Pourquoi |
|---|---|---|
| **Docker Desktop** | https://www.docker.com/products/docker-desktop/ | Fait tourner n8n + Qdrant (la base de données vectorielle) |
| **Ollama** | https://ollama.com/download | Fait tourner les modèles LLM en local |

L'installateur UltraLab vous redemandera ces 2 outils s'ils sont manquants — vous pouvez aussi les installer après.

### 3. Lancer l'installateur

1. Double-cliquez sur `UltraLab-Setup.exe`
2. **Windows va probablement afficher "SmartScreen a protégé votre PC"** (signature self-signed). Cliquez sur **Informations complémentaires** → **Exécuter quand même**. *(C'est normal pour une app alpha non signée EV — c'est l'équivalent ~300€/an, on l'achètera plus tard quand l'app sera stable.)*
3. Suivez l'assistant (Suivant, Suivant, Installer)
4. UltraLab démarre et affiche son icône dans la zone de notification Windows (à côté de l'horloge — cliquez la flèche `^` si vous ne la voyez pas)

### 4. Vérifier l'intégrité du fichier (optionnel mais recommandé)

Chaque release contient un fichier `UltraLab-Setup.exe.sha256`. Vérifiez que le hash correspond :

```powershell
certutil -hashfile UltraLab-Setup.exe SHA256
```

Le hash affiché doit être identique à celui du `.sha256`. Si différent, **ne lancez pas l'installateur** et signalez-le.

---

## Premier lancement

À la première ouverture, un **wizard** vous guide en 5 étapes :

1. **Vérification** : confirme que Docker et Ollama sont bien installés
2. **Mode** : Local (l'IA tourne sur ce PC) ou Distant (autre PC via Tailscale)
3. **Modèle de chat** : choix du LLM principal (par défaut `qwen2.5:3b` — léger, équilibré). Téléchargé automatiquement.
4. **Modèle d'embedding** : pour la recherche sémantique (par défaut `embeddinggemma:300m` — très léger)
5. **Finalisation** : tout est prêt, le wizard se ferme et l'UI principale s'ouvre dans votre navigateur

Le premier téléchargement des modèles peut prendre 5-15 min selon votre connexion (les modèles font 1-3 Go chacun).

---

## Utilisation

L'UI s'ouvre sur `http://localhost:3456/`. Vous avez 2 onglets :

- **Pipeline complet** : saisissez votre question + critères, le pipeline fait tout de A à Z (recherche → screening → ranking → clustering → PDFs → extraction → export PRISMA)
- **Module isolé** : si vous avez déjà un fichier RIS/BibTeX, vous pouvez lancer un module précis (ex : juste l'extraction de données depuis des PDFs)

Tous les résultats sont sauvegardés sur votre Bureau dans un dossier `<question> review ultralab/`.

---

## Mises à jour

L'app vérifie automatiquement les mises à jour au démarrage. Quand une nouvelle version est disponible :

1. Settings → Mises à jour → **Une mise à jour est disponible**
2. Bouton **Télécharger la nouvelle version** → ouvre la page Releases GitHub
3. Téléchargez le nouveau `UltraLab-Setup.exe`
4. Relancez l'installateur (votre config est préservée)

Pour les workflows uniquement (sans nouvelle version d'app) : Settings → **Mettre à jour les workflows** (re-fetch automatique depuis GitHub).

---

## Désinstallation

3 options :

1. **Windows** : Panneau de configuration → Programmes → UltraLab → Désinstaller
2. **Via l'installateur** : si vous avez gardé `UltraLab-Setup.exe`, relancez-le → option Uninstall
3. **Script complet** (recommandé pour tout nettoyer) : téléchargez [`uninstall-ultralab.bat`](https://github.com/xerael/ultralab/releases/latest) (dans la même release), lancez-le. Il propose étape par étape de supprimer les containers Docker, les volumes, la config user, les modèles Ollama, les exclusions Defender.

---

## Aide & support

- 🐛 **Bug** : ouvrir une issue sur https://github.com/xerael/ultralab/issues
- 💡 **Suggestion** : idem, label "enhancement"
- 📧 **Contact direct** : *(à compléter)*

---

## Confidentialité

- **Vos données restent locales** : les articles, PDFs et résultats ne quittent pas votre PC
- **L'IA est locale** (Ollama) : les prompts envoyés au LLM ne transitent pas par un serveur externe
- **Mode distant optionnel** : si vous utilisez un PC distant via Tailscale, les données transitent uniquement entre vos deux PCs (réseau privé chiffré)
- **APIs externes consultées** : PubMed, OpenAlex, Crossref, Europe PMC, CORE — uniquement pour la recherche bibliographique (queries publiques, aucune donnée utilisateur envoyée)
- **Aucune télémétrie** dans UltraLab (pas de tracking, pas d'analytics)

---

## Crédits

UltraLab est développé par [@xerael](https://github.com/xerael).

Stack : Python · Flask · pystray · PyInstaller · n8n · Ollama · Qdrant · Docker
