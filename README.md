<div align="center">

# UltraLab

**Automatisation de revues systématiques de la littérature scientifique**
**Systematic literature review automation**

![Version](https://img.shields.io/badge/version-0.3.0--alpha-orange)
![Plateforme](https://img.shields.io/badge/Windows-10%2F11-blue)
![Statut](https://img.shields.io/badge/statut-alpha-yellow)
![Langues](https://img.shields.io/badge/UI-FR%20%2F%20EN-success)

[**📥 Télécharger / Download**](https://github.com/xerael/ultralab/releases/latest) · [Installation](#installation) · [Bug](https://github.com/xerael/ultralab/issues)

</div>

---

# 🇫🇷 Version française

## Présentation

UltraLab est une application de bureau (Windows) qui automatise les étapes d'une revue systématique de littérature scientifique, **en gardant vos données et l'IA en local**.

### Fonctionnalités (v0.2.9)

- 🌍 **Interface 100 % bilingue FR / EN** (bascule instantanée dans Paramètres)
- 🧪 **Évaluation du risque de biais** : 9 outils au choix (RoB 2, Jadad, PEDro, ROBINS-I, Newcastle-Ottawa, Downs & Black, AXIS, QUADAS-2, AMSTAR-2, ROBIS) — détection automatique du devis + override, une colonne par item + justification + score global, double relecture IA
- 🔗 **Snowballing (chaînage de citations)** : références (backward) et citations (forward) via OpenAlex, Semantic Scholar, Europe PMC et OpenCitations, dédupliquées vs le corpus (candidats prêts à re-screener)
- 📋 **Checklist PRISMA 2020 (27 items)** auto-remplie depuis un run existant (HTML + Markdown)
- 🔁 **Living review + favoris de requêtes** : requêtes sauvegardées, relance et signalement des **nouveaux articles depuis la dernière exécution**
- 🚩 **Détection de rétractations** (Crossref) intégrée au scan des revues prédatrices
- 🔍 **Recherche multi-bases** : PubMed, OpenAlex, Crossref, Semantic Scholar, DOAJ, BASE, Lens.org, ScienceDirect — équation adaptée par base, dates natives, plafonds par base, activation/désactivation par base
- ♻️ **Déduplication** (DOI puis titre+année, fusion de champs) + **récupération des abstracts manquants** par DOI via Semantic Scholar
- 🧠 **Pré-screening IA** (Include / Maybe / Exclude) : justification **critère par critère** (esprit PRISMA), **score de confiance**, drapeau « vérification humaine »
- 👥 **Double relecture optionnelle** : 2ᵉ modèle (obligatoirement différent) + **accord inter-juges (kappa de Cohen)** ; s'applique au screening, à la lecture intégrale et à l'extraction
- 📖 **Lecture intégrale** (full-text) : réévaluation de l'inclusion sur le PDF complet
- 📊 **Ranking** (score de pertinence 0-100, double notation optionnelle avec **ICC + Spearman**) et **clustering** thématique
- 🚩 **Détection de revues prédatrices** (liste Beall + heuristiques éditeur)
- 📄 **Téléchargement de PDFs** en libre accès (Unpaywall, Europe PMC, CORE, Zotero)
- 📋 **Extraction de données structurée** adaptable à tout cadre méthodologique : **PICO, PECO, SPIDER, SPICE, ECLIPSE, COSMIN** + champs personnalisés
- 📑 **Diagramme de flux PRISMA 2020** (visuel) + **motifs d'exclusion** + `methods.json` (reproductibilité) + export RIS / nbib / BibTeX / Excel
- 🔐 **Tout en local** : l'IA tourne sur votre PC (Ollama) ou un PC distant privé (Tailscale). Aucune donnée utilisateur n'est envoyée à des tiers, aucune télémétrie.

## ⚠️ Statut : alpha en développement actif

Destinée aux **alpha-testeurs**. Bugs et changements rapides à prévoir. [Signaler un bug](https://github.com/xerael/ultralab/issues).

## Installation

1. **Télécharger** `UltraLab-Setup.exe` depuis la [dernière release](https://github.com/xerael/ultralab/releases/latest).
2. **Pré-requis** : Windows 10/11, [Docker Desktop](https://www.docker.com/products/docker-desktop/), [Ollama](https://ollama.com/) (UltraLab aide à les détecter/lancer).
3. **Lancer l'installateur** (l'exe interne est signé self-signed « Mika Gavaudan » ; SmartScreen peut demander une confirmation).
4. **Vérifier l'intégrité** (optionnel) : comparer le SHA256 indiqué dans les notes de release.

## Premier lancement

Un assistant en 5 étapes : vérification Docker/Ollama → mode (local / distant Tailscale) → modèle de chat → modèle d'embedding → finalisation. Le 1ᵉʳ téléchargement des modèles prend 5-15 min (1-3 Go chacun).

## Utilisation

L'UI s'ouvre sur `http://localhost:3456/`. Deux onglets :
- **Pipeline complet** : question + critères → recherche → dédup → ranking → clustering → screening → PDFs → extraction → export PRISMA.
- **Module isolé** : lancer une seule étape (ex. extraction depuis des PDFs, ou recherche API → fichier .nbib).

Les résultats sont regroupés dans un dossier dédié sur le Bureau.

## Réglages avancés IA / LLM (Paramètres)

Un seul encart contrôle le comportement des modèles pour **tous les modules et le pipeline** :
- **Strictesse** + **règles personnalisées** pour le screening, le ranking et l'extraction.
- **Double relecture IA** (optionnelle, défaut OFF) : active un 2ᵉ modèle de contrôle + le calcul de l'accord inter-juges pour tous les modules qui le permettent. À réserver aux machines suffisamment puissantes (coût ~2× le temps de traitement).

## Mises à jour

Vérification automatique au démarrage. Nouvelle version → Paramètres → Mises à jour → télécharger le nouveau Setup et relancer (config préservée). Workflows seuls : Paramètres → Mettre à jour les workflows.

## Confidentialité

Vos données (articles, PDFs, résultats) restent sur votre PC. L'IA est locale (Ollama). Les APIs externes ne sont consultées que pour la recherche bibliographique (requêtes publiques). Aucune télémétrie.

## Crédits

Développé par [@xerael](https://github.com/xerael). Stack : Python · Flask · n8n · Ollama · Qdrant · Docker.

---

# 🇬🇧 English version

## Overview

UltraLab is a Windows desktop app that automates the steps of a systematic literature review **while keeping your data and the AI local**.

### Features (v0.2.9)

- 🌍 **Fully bilingual UI (FR / EN)** with instant switching in Settings
- 🧪 **Risk-of-bias assessment**: choose from 9 tools (RoB 2, Jadad, PEDro, ROBINS-I, Newcastle-Ottawa, Downs & Black, AXIS, QUADAS-2, AMSTAR-2, ROBIS) — automatic design detection + override, one column per item + justification + global score, AI double review
- 🔗 **Snowballing (citation chasing)**: backward references and forward citations via OpenAlex, Semantic Scholar, Europe PMC and OpenCitations, deduplicated against your corpus (candidates ready to re-screen)
- 📋 **PRISMA 2020 checklist (27 items)** auto-filled from an existing run (HTML + Markdown)
- 🔁 **Living review + favorite queries**: saved queries, re-run and flagging of **new articles since the last run**
- 🚩 **Retraction detection** (Crossref) integrated into the predatory-journal scan
- 🔍 **Multi-database search**: PubMed, OpenAlex, Crossref, Semantic Scholar, DOAJ, BASE, Lens.org, ScienceDirect — per-database query syntax, native date filters, per-database caps and on/off toggles
- ♻️ **Deduplication** (DOI then title+year, field merge) + **missing-abstract recovery** by DOI via Semantic Scholar
- 🧠 **AI pre-screening** (Include / Maybe / Exclude): **per-criterion** justification (PRISMA-minded), **confidence score**, "human review" flag
- 👥 **Optional double review**: a 2nd (necessarily different) model + **inter-rater agreement (Cohen's kappa)**; applies to screening, full-text and extraction
- 📖 **Full-text screening**: re-assess inclusion on the complete PDF
- 📊 **Ranking** (0-100 relevance, optional double scoring with **ICC + Spearman**) and thematic **clustering**
- 🚩 **Predatory journal detection** (Beall list + publisher heuristics)
- 📄 **Open-access PDF fetching** (Unpaywall, Europe PMC, CORE, Zotero)
- 📋 **Structured data extraction** adaptable to any framework: **PICO, PECO, SPIDER, SPICE, ECLIPSE, COSMIN** + custom fields
- 📑 **PRISMA 2020 flow diagram** (visual) + **exclusion reasons** + `methods.json` (reproducibility) + RIS / nbib / BibTeX / Excel export
- 🔐 **Fully local**: AI runs on your PC (Ollama) or a private remote PC (Tailscale). No user data sent to third parties, no telemetry.

## ⚠️ Status: active alpha

For **alpha testers**. Expect bugs and rapid changes. [Report a bug](https://github.com/xerael/ultralab/issues).

## Installation

1. **Download** `UltraLab-Setup.exe` from the [latest release](https://github.com/xerael/ultralab/releases/latest).
2. **Requirements**: Windows 10/11, [Docker Desktop](https://www.docker.com/products/docker-desktop/), [Ollama](https://ollama.com/) (UltraLab helps detect/start them).
3. **Run the installer** (inner exe is self-signed "Mika Gavaudan"; SmartScreen may prompt).
4. **Verify integrity** (optional): compare the SHA256 in the release notes.

## First launch

A 5-step wizard: Docker/Ollama check → mode (local / remote Tailscale) → chat model → embedding model → finish. First model download takes 5-15 min (1-3 GB each).

## Usage

The UI opens at `http://localhost:3456/`. Two tabs:
- **Full pipeline**: question + criteria → search → dedup → ranking → clustering → screening → PDFs → extraction → PRISMA export.
- **Single module**: run one step (e.g. extraction from PDFs, or API search → .nbib file).

Results are grouped in a dedicated folder on the Desktop.

## Advanced AI / LLM settings (Settings)

A single panel drives model behaviour for **all modules and the pipeline**:
- **Strictness** + **custom rules** for screening, ranking and extraction.
- **Double AI review** (optional, default OFF): enables a 2nd control model + inter-rater agreement for every module that supports it. Best on capable machines (~2× processing time).

## Updates

Automatic check on startup. New version → Settings → Updates → download the new Setup and reinstall (config preserved). Workflows only: Settings → Update workflows.

## Privacy

Your data (articles, PDFs, results) stays on your PC. The AI is local (Ollama). External APIs are queried only for bibliographic search (public queries). No telemetry.

## Credits

Built by [@xerael](https://github.com/xerael). Stack: Python · Flask · n8n · Ollama · Qdrant · Docker.
