<div align="center">

# UltraLab

**Automatisation de revues systématiques de la littérature scientifique**
**Systematic literature review automation**

![Version](https://img.shields.io/badge/version-0.3.0--alpha-orange)
![Plateforme](https://img.shields.io/badge/Windows-10%2F11-blue)
![Statut](https://img.shields.io/badge/statut-alpha-yellow)
![Langues](https://img.shields.io/badge/UI-FR%20%2F%20EN-success)

[**📥 Télécharger / Download**](https://github.com/xerael/ultralab/releases/latest) · [Installation](#installation) · [Protocole scientifique](PROTOCOL.md) · [Bug](https://github.com/xerael/ultralab/issues)

</div>

---

# 🇫🇷 Version française

## Présentation

UltraLab est une application de bureau (Windows) qui automatise les étapes d'une revue systématique de littérature scientifique, **en gardant vos données et l'IA en local**.

### Fonctionnalités (v0.3.0)

- 🌍 **Interface 100 % bilingue FR / EN** (bascule instantanée dans Paramètres)
- 🔍 **Recherche multi-bases** : PubMed, OpenAlex, Crossref, Semantic Scholar, DOAJ, BASE, Lens.org, ScienceDirect — équation adaptée par base, dates natives, plafonds par base, activation/désactivation par base
- 🧪 **Littérature grise** : ClinicalTrials.gov (registres d'essais, optionnel) pour réduire le biais de publication
- ♻️ **Déduplication** (DOI puis titre+année, fusion de champs) + **enrichissement des abstracts manquants** multi-sources (Semantic Scholar + OpenAlex)
- 🧠 **Pré-screening IA** (Include / Maybe / Exclude) : justification **critère par critère** (esprit PRISMA), **score de confiance**, drapeau « vérification humaine »
- 👥 **Double relecture optionnelle** : 2ᵉ modèle (obligatoirement différent) + **accord inter-juges (kappa de Cohen)** ; s'applique au screening, à la lecture intégrale et à l'extraction
- 🙋 **Relecture humaine intégrée** (opt-in, a posteriori) avec accord humain–IA (κ)
- 📖 **Lecture intégrale** (full-text) : réévaluation de l'inclusion sur le PDF complet
- 📊 **Ranking** (score de pertinence 0-100) et **clustering** thématique
- 🩺 **Évaluation du risque de biais** : 10 outils (RoB 2, ROBINS-I, Newcastle-Ottawa, AMSTAR-2…), score par item + double relecture (κ)
- 🔗 **Snowballing** (chaînage de citations) : OpenAlex, Semantic Scholar, Europe PMC, OpenCitations
- 🚩 **Détection de revues prédatrices** (liste Beall + heuristiques) + **rétractations** (Crossref)
- 📄 **Téléchargement de PDFs** en libre accès (Unpaywall, Europe PMC, CORE, Zotero)
- 📋 **Extraction de données structurée** : **PICO, PECO, SPIDER, SPICE, ECLIPSE, COSMIN** + champs personnalisés
- 📈 **Méta-analyse** (forest/funnel, I², effets poolés) + **GRADE** (certitude des preuves, Summary of Findings)
- 🧩 **Mode Fusion** (multi-dossiers → corpus unifié) + **rapport consolidé** prêt-soumission
- ✅ **Checklist + diagramme de flux PRISMA 2020** + `methods.json` (reproductibilité) + export RIS / nbib / BibTeX / Excel
- ⏱️ **Avancement temps réel** par module + **reprise de run** interrompu (cache LLM) + **living review** (favoris de requêtes)
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

### Features (v0.3.0)

- 🌍 **Fully bilingual UI (FR / EN)** with instant switching in Settings
- 🔍 **Multi-database search**: PubMed, OpenAlex, Crossref, Semantic Scholar, DOAJ, BASE, Lens.org, ScienceDirect — per-database query syntax, native date filters, per-database caps and on/off toggles
- 🧪 **Grey literature**: ClinicalTrials.gov (trial registries, optional) to reduce publication bias
- ♻️ **Deduplication** (DOI then title+year, field merge) + **multi-source missing-abstract enrichment** (Semantic Scholar + OpenAlex)
- 🧠 **AI pre-screening** (Include / Maybe / Exclude): **per-criterion** justification (PRISMA-minded), **confidence score**, "human review" flag
- 👥 **Optional double review**: a 2nd (necessarily different) model + **inter-rater agreement (Cohen's kappa)**; applies to screening, full-text and extraction
- 🙋 **Built-in human review** (opt-in, after the fact) with human–AI agreement (κ)
- 📖 **Full-text screening**: re-assess inclusion on the complete PDF
- 📊 **Ranking** (0-100 relevance) and thematic **clustering**
- 🩺 **Risk-of-bias assessment**: 10 tools (RoB 2, ROBINS-I, Newcastle-Ottawa, AMSTAR-2…), per-item score + double review (κ)
- 🔗 **Snowballing** (citation chasing): OpenAlex, Semantic Scholar, Europe PMC, OpenCitations
- 🚩 **Predatory journal detection** (Beall list + heuristics) + **retractions** (Crossref)
- 📄 **Open-access PDF fetching** (Unpaywall, Europe PMC, CORE, Zotero)
- 📋 **Structured data extraction**: **PICO, PECO, SPIDER, SPICE, ECLIPSE, COSMIN** + custom fields
- 📈 **Meta-analysis** (forest/funnel, I², pooled effects) + **GRADE** (certainty of evidence, Summary of Findings)
- 🧩 **Fusion mode** (multiple folders → unified corpus) + **submission-ready consolidated report**
- ✅ **PRISMA 2020 checklist + flow diagram** + `methods.json` (reproducibility) + RIS / nbib / BibTeX / Excel export
- ⏱️ **Real-time per-module progress** + **resume interrupted runs** (LLM cache) + **living review** (favorite queries)
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
