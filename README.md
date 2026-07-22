<div align="center">

# UltraLab

**Automatisation de revues systématiques de la littérature scientifique**
**Systematic literature review automation**

![Version](https://img.shields.io/badge/version-0.4.7--alpha-orange)
![Plateforme](https://img.shields.io/badge/Windows-10%2F11-blue)
![Statut](https://img.shields.io/badge/statut-alpha-yellow)
![Langues](https://img.shields.io/badge/UI-FR%20%2F%20EN-success)

[**📥 Télécharger / Download**](https://github.com/xerael/ultralab/releases/latest) · [Installation](#installation) · [Bug](https://github.com/xerael/ultralab/issues)

</div>

---

# 🇫🇷 Version française

## Présentation

UltraLab est une application de bureau (Windows) qui automatise les étapes d'une revue systématique de littérature scientifique, **en gardant vos données et l'IA en local**.

### Ce que fait UltraLab

UltraLab couvre la revue systématique **de bout en bout**, étape PRISMA par étape PRISMA. Chaque module est utilisable seul, et les runs se réutilisent d'un module à l'autre.

**1 · Cadrer la revue**
- 🧭 **Copilote méthodologique** : décrivez votre projet en langage naturel, l'IA recommande les modules, l'ordre et le pourquoi, et **pré-programme le pipeline** en un clic
- 🗺️ **État de l'art automatique** : bilan des revues systématiques et méta-analyses existantes (filtrage par type de publication, tri par pertinence) et des travaux en cours, avec synthèse d'orientation
- 📝 **Protocole PROSPERO-ready** et **PRISMA-ScR** (revues de portée)
- 🗣️ **Assistant IA de configuration** : réglez le logiciel en langage naturel, avec confirmation

**2 · Rechercher**
- 🔍 **Recherche multi-bases** : PubMed, OpenAlex, Crossref, Semantic Scholar, DOAJ, BASE, Lens.org, ScienceDirect, avec **requête dérivée de votre équation pour chaque base**, dates natives, plafonds et activation par base
- 📋 **Transparence PRISMA** : panneau de la requête réellement exécutée par base, alertes sur les comptages suspects
- 🧪 **Littérature grise** : ClinicalTrials.gov, Europe PMC (préprints), ISRCTN, pour réduire le biais de publication
- 🔎 **Aide à la revue de l'équation (PRESS)** : vérifications automatiques et suggestions (synonymes, MeSH, orthographe)
- ❄️ **Snowballing** (chaînage de citations) : OpenAlex, Semantic Scholar, Europe PMC, OpenCitations, itérable jusqu'à saturation
- 🔁 **Veille planifiée** et **living review** : recherches favorites relancées tous les N jours, alertes à l'ouverture
- 📥 **Imports** : Rayyan, Covidence (décisions conservées), Zotero, dossier de PDFs, fichier en glisser-déposer

**3 · Trier**
- ♻️ **Déduplication** : DOI, puis titre et année avec fusion de champs, plus une passe **sémantique** par embeddings ; mode **grand corpus** au-delà de 10 000 références
- 🧠 **Pré-screening IA** (Include / Maybe / Exclude) : justification **critère par critère**, score de confiance, drapeau de vérification humaine
- 🤖 **Apprentissage actif** : file de priorité qui apprend de vos décisions, jauge d'arrêt
- 👥 **Double relecture** avec un 2ᵉ modèle obligatoirement différent, et **accord inter-juges** (kappa de Cohen, Gwet AC1, PABAK)
- 🙋 **Relecture humaine** intégrée, **en aveugle**, **surlignage des critères**, et **pack relecteur autonome** (HTML autoporté, co-relecteur sans installation)
- 🤝 **Réconciliation à deux relecteurs** avec arbitrage des désaccords
- 📐 **Calibration de la confiance** (ECE, sensibilité du seuil) et **benchmark du screening** (WSS@95 %, rappel, travail économisé)
- 📊 **Ranking** (score de pertinence) et **clustering** thématique

**4 · Lire et extraire**
- 📄 **Téléchargement de PDFs** en libre accès (Unpaywall, Europe PMC, CORE, Zotero) et **chasse aux PDFs manquants** avec statuts PRISMA
- 📖 **Lecture intégrale** : réévaluation de l'inclusion sur le PDF complet, motifs d'exclusion standardisés (PRISMA 16b)
- 📚 **Interroger les PDFs du corpus** (100 % local) : question en langage naturel sur le plein texte, réponse **citant chaque passage** (article + page + extrait)
- 📋 **Extraction structurée** : PICO, PECO, SPIDER, SPICE, ECLIPSE, COSMIN et champs personnalisés, avec **vérification humaine des chiffres** avant analyse
- 🩺 **Risque de biais** : 7 outils (RoB 2, ROBINS-I, Newcastle-Ottawa cohorte et cas-témoins, AXIS, QUADAS-2, AMSTAR-2) plus un **outil personnalisé**
- 🧬 **Qualité du corpus** : regroupement des **companion papers** (la méta compte par étude, pas par article), **alerte rétractations**, **détection de revues prédatrices**

**5 · Analyser**
- 📈 **Méta-analyse** : forest et funnel, I², effets poolés, estimateurs τ² REML et Paule-Mandel, ajustement Hartung-Knapp, intervalle de prédiction
- 🔬 **Biais de publication** : Egger, Begg, trim-and-fill, funnel à contours ; **imputation des statistiques manquantes** ; garde-fous d'unité d'analyse
- 🩺 **Variantes** : méta-analyse **diagnostique** (Reitsma, SROC), **en réseau**, **de proportions**, **par critère de jugement**, analyses de **sensibilité et sous-groupes**
- 📋 **GRADE** et table **Summary of Findings** au format Cochrane
- 📊 **Analyse statistique en langage naturel (R)** : 3 modes (Automatique, Guidé, Libre), import CSV/Excel ou run UltraLab, **rapport HTML Quarto**, **rapport d'interprétation**, export des figures en **TIFF / PDF / EPS 300-600 dpi** aux largeurs journal, ouverture dans RStudio

**6 · Rédiger et publier**
- ✅ **Checklist et diagramme de flux PRISMA 2020**, générés depuis le corpus fusionné, avec **flux PRISMA vivant** cliquable
- 📄 **Brouillon de la section Méthodes** (FR et EN) rédigé depuis les traces réelles des runs
- 📤 **Exports** : Word (.docx), RevMan, GRADEpro, RIS, nbib, BibTeX, Excel, plus `methods.json` pour la reproductibilité
- 📮 **Aide au choix du journal** : revues candidates depuis vos études incluses et des travaux similaires, open access et APC, prédatrices écartées
- 🧩 **Mode Fusion** (plusieurs dossiers ou un projet entier) et **rapport consolidé** prêt-soumission

**Transversal**
- 📁 **Mode projet** : les runs de tous les modules regroupés dans le dossier du projet, réutilisables comme corpus, avec **pipeline pré-programmé** et reprise depuis l'étape en échec
- ⚡ **Modules interactifs** : screening **en direct** avec correction tracée, **méta-analyse live** (forest cliquable, leave-one-out), GRADE et risque de biais re-jugeables, **points d'arrêt** dans le pipeline
- ⏱️ **Avancement temps réel**, **reprise de run** interrompu, et **reprise partielle** sur les seuls articles en échec
- 🔬 **Rigueur et traçabilité** : **journal d'audit** horodaté, **bundle de reproductibilité** par run, sorties du modèle contraintes par schéma
- 🖥️ **Application native ou version web**, interface organisée par **étapes PRISMA**, **100 % bilingue FR / EN**, palette de commandes **Ctrl+K**, mode compact, visite guidée
- 🛰️ **PC distant** privé (Tailscale) avec file d'attente, instances dédiées et panneau d'administration
- 🔌 **Connecteurs** : une carte par service, avec badge d'état et test réel en un clic
- 🔐 **Tout en local** : l'IA tourne sur votre PC (Ollama) ou sur votre PC distant privé. Aucune donnée envoyée à des tiers, aucune télémétrie.

### Quelle version a apporté quoi

Le détail des correctifs de chaque version se trouve dans les [notes de release](https://github.com/xerael/ultralab/releases).

| Version | Apports principaux |
| --- | --- |
| **0.4.7** | Durcissement et stabilisation : pas de nouvelle fonctionnalité, correction de défauts de fiabilité issus d'un audit complet du code |
| **0.4.6** | Équations expertes respectées base par base, interrogation des PDFs du corpus, méta-analyse diagnostique, screening durci (calibration de Platt, test canari, vote de cohérence), très grands corpus |
| **0.4.5** | Statistiques niveau Cochrane, relecture en aveugle, pack relecteur autonome, chasse aux PDFs manquants, export des figures aux formats journal, reprise partielle, projets persistants |
| **0.4.4** | Copilote méthodologique, modules interactifs, hub PRISMA et file de validation, chaîne extraction vers méta-analyse, aide au choix du journal |
| **0.4.3** | Déduplication sémantique, méta-analyse en réseau, PRESS, assistant IA de configuration, screening multilingue, Gwet AC1 et PABAK |
| **0.4.2** | Apprentissage actif, analyses de sensibilité et de sous-groupes, rapport de projet consolidé |
| **0.4.1** | Module d'analyse statistique R complet, benchmark du screening, journal d'audit, bundle de reproductibilité |

## ⚠️ Statut : alpha en développement actif

Destinée aux **alpha-testeurs**. Bugs et changements rapides à prévoir. [Signaler un bug](https://github.com/xerael/ultralab/issues).

## Installation

1. **Télécharger** `UltraLab-Setup.exe` depuis la [dernière release](https://github.com/xerael/ultralab/releases/latest).
2. **Pré-requis** : Windows 10/11, [Docker Desktop](https://www.docker.com/products/docker-desktop/), [Ollama](https://ollama.com/). UltraLab les détecte et peut les **installer automatiquement** (winget). Optionnel : [R](https://cran.r-project.org/) pour le module d'analyse statistique (+ RStudio, Quarto).
3. **Lancer l'installateur** (installeur et application auto-signés ; SmartScreen peut demander une confirmation).
4. **Vérifier l'intégrité** (optionnel) : comparer le SHA256 indiqué dans les notes de release.

## Premier lancement

Un assistant vérifie les composants, peut installer les prérequis, puis configure : interface (native / web) → mode IA (local / distant Tailscale) → modèles recommandés selon votre machine. Le bouton **« ⚙ Configurer les services »** calibre Docker + n8n pas à pas (1ᵉʳ téléchargement d'images ~400 Mo, les phases s'affichent en direct). Le 1ᵉʳ téléchargement des modèles prend 5-15 min (1-3 Go chacun).

## Utilisation

- **Navigation par étapes PRISMA** : chaque module explique à quoi il sert ; corpus chargeable depuis un run, un projet, Zotero, un dossier de PDFs ou un fichier (glisser-déposer).
- **Projets** : créez un projet, pré-programmez une séquence de modules et suivez la timeline en direct ; tous les runs restent réutilisables.
- Les résultats sont regroupés dans des dossiers dédiés sur le Bureau. **Ctrl+K** pour naviguer au clavier.

## Réglages (Paramètres)

Onglets clairs : **IA et modèles** (modèles + strictesse + règles personnalisées + double relecture), **Connecteurs** (clés API avec test), **Mode distant** (IP, test, ports), **Rigueur scientifique** (journal d'audit, cache LLM), **Application**, **Avancé** (console, diagnostic, maintenance Docker/n8n).

## Mises à jour

Vérification automatique au démarrage. Nouvelle version → Paramètres → Mises à jour → télécharger le nouveau Setup et relancer (config préservée). Workflows seuls : Paramètres → Mettre à jour les workflows.

## Confidentialité

Vos données (articles, PDFs, résultats) restent sur votre PC. L'IA est locale (Ollama). Les APIs externes ne sont consultées que pour la recherche bibliographique (requêtes publiques). Aucune télémétrie.

## Crédits

Développé par [@xerael](https://github.com/xerael). Stack : Python · Flask · Tauri · Svelte · n8n · Ollama · Qdrant · Docker · R.

---

# 🇬🇧 English version

## Overview

UltraLab is a Windows desktop app that automates the steps of a systematic literature review **while keeping your data and the AI local**.

### What UltraLab does

UltraLab covers a systematic review **end to end**, PRISMA stage by PRISMA stage. Every module works on its own, and runs are reusable from one module to the next.

**1 · Frame the review**
- 🧭 **Methodological copilot**: describe your project in plain language, the AI recommends the modules, the order and the rationale, and **pre-programmes the pipeline** in one click
- 🗺️ **Automatic state of the art**: overview of existing systematic reviews and meta-analyses (filtered by publication type, ranked by relevance) and of ongoing work, with an orientation summary
- 📝 **PROSPERO-ready protocol** and **PRISMA-ScR** (scoping reviews)
- 🗣️ **AI configuration assistant**: set the software up in plain language, with confirmation

**2 · Search**
- 🔍 **Multi-database search**: PubMed, OpenAlex, Crossref, Semantic Scholar, DOAJ, BASE, Lens.org, ScienceDirect, with a **query derived from your equation for each database**, native date filters, caps and per-database toggles
- 📋 **PRISMA transparency**: panel showing the query actually executed per database, with warnings on suspicious counts
- 🧪 **Grey literature**: ClinicalTrials.gov, Europe PMC (preprints), ISRCTN, to reduce publication bias
- 🔎 **Search strategy review (PRESS)**: automatic checks and suggestions (synonyms, MeSH, spelling)
- ❄️ **Snowballing** (citation chaining): OpenAlex, Semantic Scholar, Europe PMC, OpenCitations, iterable until saturation
- 🔁 **Scheduled monitoring** and **living review**: favourite searches re-run every N days, alerts on opening
- 📥 **Imports**: Rayyan, Covidence (decisions preserved), Zotero, a folder of PDFs, drag and drop files

**3 · Screen**
- ♻️ **Deduplication**: DOI, then title and year with field merging, plus a **semantic** pass using embeddings; **large corpus** mode beyond 10,000 references
- 🧠 **AI pre-screening** (Include / Maybe / Exclude): **criterion-by-criterion** justification, confidence score, human verification flag
- 🤖 **Active learning**: priority queue that learns from your decisions, with a stopping gauge
- 👥 **Double screening** with a mandatorily different second model, and **inter-rater agreement** (Cohen's kappa, Gwet AC1, PABAK)
- 🙋 **Built-in human review**, **blinded**, with **criteria highlighting**, and a **standalone reviewer pack** (self-contained HTML, co-reviewer needs no installation)
- 🤝 **Two-reviewer reconciliation** with arbitration of disagreements
- 📐 **Confidence calibration** (ECE, threshold sensitivity) and **screening benchmark** (WSS@95%, recall, work saved)
- 📊 **Ranking** (relevance score) and topic **clustering**

**4 · Read and extract**
- 📄 **Open access PDF download** (Unpaywall, Europe PMC, CORE, Zotero) and **missing PDF hunt** with PRISMA statuses
- 📖 **Full-text reading**: inclusion re-assessed on the complete PDF, standardised exclusion reasons (PRISMA 16b)
- 📚 **Ask your corpus PDFs** (100% local): natural-language questions against the full text, answers **citing every passage** (article + page + excerpt)
- 📋 **Structured extraction**: PICO, PECO, SPIDER, SPICE, ECLIPSE, COSMIN and custom fields, with **human verification of the figures** before analysis
- 🩺 **Risk of bias**: 7 tools (RoB 2, ROBINS-I, Newcastle-Ottawa cohort and case-control, AXIS, QUADAS-2, AMSTAR-2) plus a **custom tool**
- 🧬 **Corpus quality**: **companion papers** grouped (the meta-analysis counts studies, not articles), **retraction alerts**, **predatory journal detection**

**5 · Analyse**
- 📈 **Meta-analysis**: forest and funnel plots, I², pooled effects, τ² REML and Paule-Mandel estimators, Hartung-Knapp adjustment, prediction interval
- 🔬 **Publication bias**: Egger, Begg, trim-and-fill, contour-enhanced funnel; **imputation of missing statistics**; unit-of-analysis safeguards
- 🩺 **Variants**: **diagnostic** meta-analysis (Reitsma, SROC), **network**, **proportion**, **per outcome**, plus **sensitivity and subgroup** analyses
- 📋 **GRADE** and Cochrane-format **Summary of Findings** table
- 📊 **Natural-language statistical analysis (R)**: 3 modes (Automatic, Guided, Free), CSV/Excel import or an UltraLab run, **Quarto HTML report**, **interpretation report**, figure export in **TIFF / PDF / EPS at 300-600 dpi** at journal widths, opening in RStudio

**6 · Write and publish**
- ✅ **PRISMA 2020 checklist and flow diagram**, generated from the merged corpus, with a clickable **living PRISMA flow**
- 📄 **Methods section draft** (French and English) written from the actual run traces
- 📤 **Exports**: Word (.docx), RevMan, GRADEpro, RIS, nbib, BibTeX, Excel, plus `methods.json` for reproducibility
- 📮 **Journal selection help**: candidate journals from your included studies and similar work, open access and APC information, predatory ones filtered out
- 🧩 **Merge mode** (several folders or a whole project) and a submission-ready **consolidated report**

**Across the whole app**
- 📁 **Project mode**: runs from every module gathered in the project folder, reusable as a corpus, with a **pre-programmed pipeline** and resume from the failed step
- ⚡ **Interactive modules**: **live** screening with traced corrections, **live meta-analysis** (clickable forest, leave-one-out), re-judgeable GRADE and risk of bias, **breakpoints** in the pipeline
- ⏱️ **Real-time progress**, **resume interrupted runs**, and **partial resume** on failed articles only
- 🔬 **Rigour and traceability**: timestamped **audit log**, per-run **reproducibility bundle**, schema-constrained model output
- 🖥️ **Native application or web version**, interface organised by **PRISMA stages**, **fully bilingual FR / EN**, **Ctrl+K** command palette, compact mode, guided tour
- 🛰️ **Private remote PC** (Tailscale) with a queue, dedicated instances and an admin panel
- 🔌 **Connectors**: one card per service, with a status badge and a real one-click test
- 🔐 **Fully local**: the AI runs on your PC (Ollama) or on your own private remote PC. No data sent to third parties, no telemetry.

### Which version brought what

The detailed fix list for each version lives in the [release notes](https://github.com/xerael/ultralab/releases).

| Version | Main additions |
| --- | --- |
| **0.4.7** | Hardening and stabilisation: no new feature, reliability defects fixed following a full code audit |
| **0.4.6** | Expert equations honoured database by database, ask your corpus PDFs, diagnostic meta-analysis, hardened screening (Platt calibration, canary test, consistency voting), very large corpora |
| **0.4.5** | Cochrane-level statistics, blinded review, standalone reviewer pack, missing PDF hunt, journal-format figure export, partial resume, persistent projects |
| **0.4.4** | Methodological copilot, interactive modules, PRISMA hub and validation queue, extraction to meta-analysis chain, journal selection help |
| **0.4.3** | Semantic deduplication, network meta-analysis, PRESS, AI configuration assistant, multilingual screening, Gwet AC1 and PABAK |
| **0.4.2** | Active learning, sensitivity and subgroup analyses, consolidated project report |
| **0.4.1** | Complete R statistical analysis module, screening benchmark, audit log, reproducibility bundle |

## ⚠️ Status: active alpha

For **alpha testers**. Expect bugs and rapid changes. [Report a bug](https://github.com/xerael/ultralab/issues).

## Installation

1. **Download** `UltraLab-Setup.exe` from the [latest release](https://github.com/xerael/ultralab/releases/latest).
2. **Requirements**: Windows 10/11, [Docker Desktop](https://www.docker.com/products/docker-desktop/), [Ollama](https://ollama.com/). UltraLab detects them and can **install them automatically** (winget). Optional: [R](https://cran.r-project.org/) for the statistical analysis module (+ RStudio, Quarto).
3. **Run the installer** (installer and app are self-signed; SmartScreen may prompt).
4. **Verify integrity** (optional): compare the SHA256 in the release notes.

## First launch

A wizard checks components, can install prerequisites, then configures: interface (native / web) → AI mode (local / remote Tailscale) → models recommended for your machine. The **"⚙ Configure services"** button calibrates Docker + n8n step by step (first image download ~400 MB, phases shown live). First model download takes 5-15 min (1-3 GB each).

## Usage

- **PRISMA-stage navigation**: every module explains its purpose; corpus loadable from a run, a project, Zotero, a PDF folder or a file (drag & drop).
- **Projects**: create a project, pre-program a module sequence and follow the live timeline; every run stays reusable.
- Results are grouped in dedicated folders on the Desktop. **Ctrl+K** for keyboard navigation.

## Settings

Clear tabs: **AI & models** (models + strictness + custom rules + double review), **Connectors** (API keys with tests), **Remote mode** (IP, test, ports), **Scientific rigor** (audit log, LLM cache), **Application**, **Advanced** (console, diagnostics, Docker/n8n maintenance).

## Updates

Automatic check on startup. New version → Settings → Updates → download the new Setup and reinstall (config preserved). Workflows only: Settings → Update workflows.

## Privacy

Your data (articles, PDFs, results) stays on your PC. The AI is local (Ollama). External APIs are queried only for bibliographic search (public queries). No telemetry.

## Credits

Built by [@xerael](https://github.com/xerael). Stack: Python · Flask · Tauri · Svelte · n8n · Ollama · Qdrant · Docker · R.
