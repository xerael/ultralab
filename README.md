<div align="center">

# UltraLab

**Automatisation de revues systématiques de la littérature scientifique**
**Systematic literature review automation**

![Version](https://img.shields.io/badge/version-0.4.5--alpha-orange)
![Plateforme](https://img.shields.io/badge/Windows-10%2F11-blue)
![Statut](https://img.shields.io/badge/statut-alpha-yellow)
![Langues](https://img.shields.io/badge/UI-FR%20%2F%20EN-success)

[**📥 Télécharger / Download**](https://github.com/xerael/ultralab/releases/latest) · [Installation](#installation) · [Bug](https://github.com/xerael/ultralab/issues)

</div>

---

# 🇫🇷 Version française

## Présentation

UltraLab est une application de bureau (Windows) qui automatise les étapes d'une revue systématique de littérature scientifique, **en gardant vos données et l'IA en local**.

### Fonctionnalités (v0.4.5)

**Nouveau en 0.4.5 :**
- 📐 **Statistiques niveau Cochrane** : estimateurs τ² REML/Paule-Mandel + ajustement Hartung-Knapp + intervalle de prédiction ; suite de biais de publication (Egger, Begg, trim-and-fill, funnel à contours) ; **méta-analyse de proportions** (Freeman-Tukey) ; **imputation des stats manquantes** (Wan 2014, vérifiée contre R) ; **garde-fous d'unité d'analyse** (contrôle partagé, grappes, cross-over) ; checklist **PRISMA-S**
- 🧑‍🔬 **Terrain** : **relecture en aveugle** (κ humain-IA valide), **surlignage des critères** dans les abstracts + Annuler (Z), **pack relecteur autonome** (HTML autoporté, co-relecteur sans installation), **chasse aux PDFs manquants** (statuts + case PRISMA « not retrieved »), **export figures TIFF/PDF/EPS 300-600 dpi** aux largeurs journal
- 🔁 **Reprise partielle** : relancer un run interrompu **uniquement sur les articles échoués**, fusion dans le run d'origine
- 📁 **Projets persistants** : contexte (question/critères/équation) enregistré dans le projet, dossier personnalisable, **snapshots ZIP** restaurables, planificateur séparé
- 🛡️ **Fiabilité** : sorties LLM **contraintes par schéma JSON** (fin des réponses malformées), socle de **19 tests automatiques** (maths méta figées), **projet démo « Revue express »** sans Docker ni modèle, **mise à jour intégrée** de l'app, « **Citer UltraLab** » + fiche transparence


- 🗺️ **État de l'art automatique** : avant de commencer, bilan des revues systématiques existantes + travaux en cours (Europe PMC, préprints, OSF, lien PROSPERO) avec synthèse d'orientation par l'IA locale
- 📮 **Aide au choix du journal** : revues candidates depuis vos études incluses + travaux similaires (OpenAlex) + open access / APC (DOAJ), prédatrices écartées
- 📋 **Table Summary of Findings (GRADE)** au format Cochrane (effets absolus pour 1000, certitude ⊕) + **brouillon de la section Méthodes (FR+EN)** rédigé depuis les traces réelles des runs
- 🧬 **Companion papers** : les rapports d'une même étude sont regroupés — la méta compte par étude, pas par article ; **motifs d'exclusion standardisés** (PRISMA 16b) ; **alerte rétractations** sur tout corpus
- 🎯 **Calibration entre relecteurs** (pilote 20 articles, κ/AC1 + verdict) et **méta-analyses par critère de jugement**
- 🔁 **Import Rayyan / Covidence** (décisions conservées) + **veille planifiée** (recherches favorites relancées tous les N jours, alertes à l'ouverture)
- 🖥️ **Interface repensée** : hub PRISMA cliquable en accueil de projet, file **« À valider »** unifiée (badge nav), explorateur de résultats intégré (+ visuels, + régénération des fichiers après correction), bandeau contexte, mode compact + raccourcis I/M/E, visite guidée, notifications système
- 🛰️ **Contrôle admin du PC distant** (jeton partagé, ports en temps réel, multi-run) + guide de connexion intégré ; **préfixe EZproxy** pour l'accès institutionnel aux PDFs

- 🧭 **Copilote méthodologique** : décrivez votre projet en langage naturel, l'IA recommande les modules, l'ordre et le pourquoi, répond à vos questions et **pré-programme le pipeline** en un clic
- ⚡ **Modules interactifs** : screening **en direct** avec correction humaine tracée, **méta-analyse live** (forest cliquable, leave-one-out instantané), **GRADE** et **risque de biais re-jugeables**, clustering ajustable, dédup arbitrée, comptage de recherche en temps réel, **essai sur 3 articles**, **points d'arrêt** dans le pipeline
- 🔗 **Chaîne extraction → méta-analyse** : cadre « données chiffrées », **vérification humaine des chiffres** avant pooling, la méta réutilise sans ré-extraire ; extraction possible **depuis les abstracts** (priorité au PDF)
- ❄️ **Snowballing actionnable** : screener les candidats en un clic (abstracts récupérés — y compris **par titre sans DOI** —, question/critères pré-remplis), itération manuelle jusqu'à saturation, fusion guidée des inclus
- 📋 **PRISMA de bout en bout** : checklist générée **depuis le corpus fusionné** (identification multi-sources + méthodes agrégées), **flux PRISMA vivant** du projet (cliquable), équations mémorisées
- 📏 **Gwet AC1 + PABAK** en plus du kappa de Cohen (corrige le paradoxe de prévalence)
- 🖥️ **Application native** (fenêtre) ou **version web** (navigateur) au choix — interface organisée par **étapes PRISMA**, **100 % bilingue FR / EN**, palette de commandes **Ctrl+K**
- 🤖 **Screening par apprentissage actif** file de priorité qui apprend de vos décisions, jauge d'arrêt, idéal pour trancher les « Maybe » — 100 % local
- 📐 **Calibration de la confiance IA** (ECE / fiabilité) + **sensibilité du seuil** + **courbe rappel vs proportion lue** dans le benchmark
- 🔎 **Aide à la revue de l'équation (PRESS)** : vérifications automatiques + suggestions (synonymes, MeSH, orthographe)
- 🗣️ **Assistant IA de configuration** : réglez le logiciel en langage naturel (avec confirmation) ; **screening multilingue**
- 🧠 **Rapport d'interprétation du module R** : significativité, précautions et lecture globale, reliées à chaque graphique ; **méta-analyse en réseau** + analyses de sensibilité/sous-groupes
- ♻️ **Déduplication sémantique** (embeddings) en complément du DOI + titre
- 📝 **Protocole PROSPERO-ready**, **PRISMA-ScR** (revues de portée), **export RevMan / GRADEpro**, **rapports Word (.docx)**
- 📁 **Mode projet** : les runs de tous les modules regroupés dans un dossier projet, réutilisables comme corpus par les autres modules — avec **pipeline pré-programmé** (recherche → dédup → screening → … → rapport) et **reprise depuis l'étape en échec**
- 🔍 **Recherche multi-bases** : PubMed, OpenAlex, Crossref, Semantic Scholar, DOAJ, BASE, Lens.org, ScienceDirect — équation adaptée par base, dates natives, plafonds et activation par base
- 🧪 **Littérature grise** : ClinicalTrials.gov, **Europe PMC (préprints)** et **ISRCTN** (optionnels) pour réduire le biais de publication
- ♻️ **Déduplication** (DOI puis titre+année, fusion de champs) + **enrichissement des abstracts manquants** multi-sources
- 🧠 **Pré-screening IA** (Include / Maybe / Exclude) : justification **critère par critère** (esprit PRISMA), **score de confiance**, drapeau « vérification humaine »
- 👥 **Double relecture optionnelle** : 2ᵉ modèle (obligatoirement différent) + **accord inter-juges (kappa de Cohen, Gwet AC1, PABAK)** ; s'applique au screening, à la lecture intégrale et à l'extraction
- 🙋 **Relecture humaine intégrée** (opt-in, a posteriori) avec accord humain–IA (κ)
- 📖 **Lecture intégrale** (full-text) : réévaluation de l'inclusion sur le PDF complet
- 📊 **Ranking** (score de pertinence 0-100) et **clustering** thématique
- 🩺 **Évaluation du risque de biais** : 7 outils (RoB 2, ROBINS-I, Newcastle-Ottawa cohorte & cas-témoins, AXIS, QUADAS-2, AMSTAR-2) + **outil personnalisé** (JSON ou PDF), réponses question par question → Excel détaillé + synthèse prête pour publication
- 🔗 **Snowballing** (chaînage de citations) : OpenAlex, Semantic Scholar, Europe PMC, OpenCitations
- 🚩 **Détection de revues prédatrices** (liste Beall + heuristiques) + **rétractations** (Crossref)
- 📄 **Téléchargement de PDFs** en libre accès (Unpaywall, Europe PMC, CORE, Zotero)
- 📋 **Extraction de données structurée** : **PICO, PECO, SPIDER, SPICE, ECLIPSE, COSMIN** + champs personnalisés
- 📈 **Méta-analyse** (forest/funnel, I², effets poolés) + **GRADE** (certitude des preuves, Summary of Findings)
- 📊 **Analyse statistique en langage naturel (R)** : 3 modes (Automatique / Guidé / Libre), import CSV/Excel ou run UltraLab, figures interactives, **rapport HTML Quarto** en un clic, ouverture dans **RStudio** — nécessite R installé
- 🔬 **Rigueur scientifique** : **benchmark du screening** (WSS@95 %, rappel, travail économisé), **journal d'audit** horodaté, **bundle de reproductibilité** par run
- 🧩 **Mode Fusion** (multi-dossiers ou projet entier → corpus unifié) + **rapport consolidé** prêt-soumission
- ✅ **Checklist + diagramme de flux PRISMA 2020** + `methods.json` (reproductibilité) + export RIS / nbib / BibTeX / Excel
- ⏱️ **Avancement temps réel** par module + **reprise de run** interrompu (cache LLM) + **living review** (favoris de requêtes)
- 🔌 **Connecteurs** : cartes par service (Semantic Scholar, Lens, ScienceDirect, Unpaywall, Zotero…) avec badge d'état et **test réel en un clic**
- 🔐 **Tout en local** : l'IA tourne sur votre PC (Ollama) ou un PC distant privé (Tailscale), plusieurs utilisateurs en parallèle (file d'attente + instances dédiées). Aucune donnée utilisateur envoyée à des tiers, aucune télémétrie.

## ⚠️ Statut : alpha en développement actif

Destinée aux **alpha-testeurs**. Bugs et changements rapides à prévoir. [Signaler un bug](https://github.com/xerael/ultralab/issues).

## Installation

1. **Télécharger** `UltraLab-Setup.exe` depuis la [dernière release](https://github.com/xerael/ultralab/releases/latest).
2. **Pré-requis** : Windows 10/11, [Docker Desktop](https://www.docker.com/products/docker-desktop/), [Ollama](https://ollama.com/) — UltraLab les détecte et peut les **installer automatiquement** (winget). Optionnel : [R](https://cran.r-project.org/) pour le module d'analyse statistique (+ RStudio, Quarto).
3. **Lancer l'installateur** (installeur et application auto-signés ; SmartScreen peut demander une confirmation).
4. **Vérifier l'intégrité** (optionnel) : comparer le SHA256 indiqué dans les notes de release.

## Premier lancement

Un assistant vérifie les composants, peut installer les prérequis, puis configure : interface (native / web) → mode IA (local / distant Tailscale) → modèles recommandés selon votre machine. Le bouton **« ⚙ Configurer les services »** calibre Docker + n8n pas à pas (1ᵉʳ téléchargement d'images ~400 Mo — les phases s'affichent en direct). Le 1ᵉʳ téléchargement des modèles prend 5-15 min (1-3 Go chacun).

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

### Features (v0.4.5)

**New in 0.4.5:**
- 📐 **Cochrane-grade statistics**: REML/Paule-Mandel τ² estimators + Hartung-Knapp adjustment + prediction interval; publication-bias suite (Egger, Begg, trim-and-fill, contour-enhanced funnel); **meta-analysis of proportions** (Freeman-Tukey); **missing-statistics imputation** (Wan 2014, verified against R); **unit-of-analysis safeguards** (shared control, clusters, cross-over); **PRISMA-S** checklist
- 🧑‍🔬 **Field work**: **blind review** (valid human-AI κ), **criteria highlighting** in abstracts + Undo (Z), **standalone reviewer pack** (self-contained HTML, co-reviewer installs nothing), **missing-PDF hunt board** (statuses + PRISMA “not retrieved” box), **TIFF/PDF/EPS figure export** at 300–600 dpi journal widths
- 🔁 **Partial resume**: relaunch an interrupted run **only on failed articles**, merged back into the original run
- 📁 **Persistent projects**: context (question/criteria/query) saved in the project, customisable folder, restorable **ZIP snapshots**, separate run scheduler
- 🛡️ **Reliability**: LLM outputs **constrained by JSON schema** (no more malformed replies), **19 automated tests** (frozen meta maths), **“Express review” demo project** without Docker or a model, **integrated app updater**, “**Cite UltraLab**” + transparency sheet


- 🗺️ **Automated state of the art**: before starting, survey of existing systematic reviews + ongoing work (Europe PMC, preprints, OSF, PROSPERO link) with a local-AI orientation summary
- 📮 **Journal finder**: candidate journals from your included studies + similar works (OpenAlex) + open access / APC (DOAJ), predatory filtered out
- 📋 **GRADE Summary of Findings table** in Cochrane format (absolute effects per 1,000, certainty ⊕) + **Methods-section draft (FR+EN)** written from actual run traces
- 🧬 **Companion papers**: reports of the same study are grouped — meta counts studies, not articles; **standardized exclusion reasons** (PRISMA 16b); **retraction alerts** on any corpus
- 🎯 **Reviewer calibration exercise** (20-article pilot, κ/AC1 + verdict) and **per-outcome meta-analyses**
- 🔁 **Rayyan / Covidence import** (decisions preserved) + **scheduled monitoring** (favorite searches re-run every N days, alerts at startup)
- 🖥️ **Redesigned interface**: clickable PRISMA hub as project home, unified **“To validate”** queue (nav badge), built-in results explorer (+ charts, + file regeneration after corrections), review-context banner, compact mode + I/M/E shortcuts, guided tour, system notifications
- 🛰️ **Remote PC admin control** (shared token, live port states, multi-run) + built-in connection guide; **EZproxy prefix** for institutional PDF access

- 🧭 **Methodology copilot**: describe your project in natural language, the AI recommends modules, order and rationale, answers your questions and **pre-programs the pipeline** in one click
- ⚡ **Interactive modules**: **live screening** with tracked human correction, **live meta-analysis** (clickable forest, instant leave-one-out), **re-judgeable GRADE** and **risk of bias**, adjustable clustering, arbitrated dedup, real-time search counts, **3-article trial**, pipeline **checkpoints**
- 🔗 **Extraction → meta-analysis chain**: "numeric data" framework, **human verification of extracted numbers** before pooling, meta reuses without re-extracting; extraction **from abstracts** possible (PDF takes priority)
- ❄️ **Actionable snowballing**: screen candidates in one click (abstracts recovered — including **by title without DOI** —, question/criteria pre-filled), manual iteration until saturation, guided merge of included
- 📋 **PRISMA end to end**: checklist generated **from the merged corpus** (multi-source identification + aggregated methods), **living project PRISMA flow** (clickable), remembered search queries
- 📏 **Gwet's AC1 + PABAK** on top of Cohen's kappa (corrects the prevalence paradox)
- 🖥️ **Native app** (window) or **web version** (browser) — UI organized by **PRISMA stages**, **fully bilingual FR / EN**, **Ctrl+K** command palette
- 🤖 **Active-learning screening** a priority queue that learns from your decisions, stopping gauge, ideal to resolve "Maybe" — fully local
- 📐 **AI confidence calibration** (ECE / reliability) + **threshold sensitivity** + **recall vs proportion screened curve** in the benchmark
- 🔎 **Search-string review help (PRESS)**: automatic checks + suggestions (synonyms, MeSH, spelling)
- 🗣️ **AI configuration assistant**: tune the app in natural language (with confirmation); **multilingual screening**
- 🧠 **R-module interpretation report**: significance, caveats and global reading, tied to each chart; **network meta-analysis** + sensitivity/subgroup analyses
- ♻️ **Semantic deduplication** (embeddings) on top of DOI + title
- 📝 **PROSPERO-ready protocol**, **PRISMA-ScR** (scoping reviews), **RevMan / GRADEpro export**, **Word (.docx) reports**
- 📁 **Project mode**: runs from every module grouped in one project folder and reusable as corpus by other modules — with a **pre-programmed pipeline** (search → dedup → screening → … → report) and **resume from the failed step**
- 🔍 **Multi-database search**: PubMed, OpenAlex, Crossref, Semantic Scholar, DOAJ, BASE, Lens.org, ScienceDirect — per-database query syntax, native date filters, per-database caps and on/off toggles
- 🧪 **Grey literature**: ClinicalTrials.gov, **Europe PMC (preprints)** and **ISRCTN** (optional) to reduce publication bias
- ♻️ **Deduplication** (DOI then title+year, field merge) + **multi-source missing-abstract enrichment**
- 🧠 **AI pre-screening** (Include / Maybe / Exclude): **per-criterion** justification (PRISMA-minded), **confidence score**, "human review" flag
- 👥 **Optional double review**: a 2nd (necessarily different) model + **inter-rater agreement (Cohen's kappa, Gwet's AC1, PABAK)**; applies to screening, full-text and extraction
- 🙋 **Built-in human review** (opt-in, after the fact) with human–AI agreement (κ)
- 📖 **Full-text screening**: re-assess inclusion on the complete PDF
- 📊 **Ranking** (0-100 relevance) and thematic **clustering**
- 🩺 **Risk-of-bias assessment**: 7 tools (RoB 2, ROBINS-I, Newcastle-Ottawa cohort & case-control, AXIS, QUADAS-2, AMSTAR-2) + **custom tool** (JSON or PDF), question-by-question answers → detailed Excel + publication-ready summary
- 🔗 **Snowballing** (citation chasing): OpenAlex, Semantic Scholar, Europe PMC, OpenCitations
- 🚩 **Predatory journal detection** (Beall list + heuristics) + **retractions** (Crossref)
- 📄 **Open-access PDF fetching** (Unpaywall, Europe PMC, CORE, Zotero)
- 📋 **Structured data extraction**: **PICO, PECO, SPIDER, SPICE, ECLIPSE, COSMIN** + custom fields
- 📈 **Meta-analysis** (forest/funnel, I², pooled effects) + **GRADE** (certainty of evidence, Summary of Findings)
- 📊 **Natural-language statistical analysis (R)**: 3 modes (Automatic / Guided / Free), CSV/Excel or UltraLab-run input, interactive figures, one-click **Quarto HTML report**, open in **RStudio** — requires R installed
- 🔬 **Scientific rigor**: **screening benchmark** (WSS@95%, recall, work saved), timestamped **audit log**, per-run **reproducibility bundle**
- 🧩 **Fusion mode** (multiple folders or a whole project → unified corpus) + **submission-ready consolidated report**
- ✅ **PRISMA 2020 checklist + flow diagram** + `methods.json` (reproducibility) + RIS / nbib / BibTeX / Excel export
- ⏱️ **Real-time per-module progress** + **resume interrupted runs** (LLM cache) + **living review** (favorite queries)
- 🔌 **Connectors**: one card per service (Semantic Scholar, Lens, ScienceDirect, Unpaywall, Zotero…) with status badge and **real one-click test**
- 🔐 **Fully local**: AI runs on your PC (Ollama) or a private remote PC (Tailscale), several users in parallel (queue + dedicated instances). No user data sent to third parties, no telemetry.

## ⚠️ Status: active alpha

For **alpha testers**. Expect bugs and rapid changes. [Report a bug](https://github.com/xerael/ultralab/issues).

## Installation

1. **Download** `UltraLab-Setup.exe` from the [latest release](https://github.com/xerael/ultralab/releases/latest).
2. **Requirements**: Windows 10/11, [Docker Desktop](https://www.docker.com/products/docker-desktop/), [Ollama](https://ollama.com/) — UltraLab detects them and can **install them automatically** (winget). Optional: [R](https://cran.r-project.org/) for the statistical analysis module (+ RStudio, Quarto).
3. **Run the installer** (installer and app are self-signed; SmartScreen may prompt).
4. **Verify integrity** (optional): compare the SHA256 in the release notes.

## First launch

A wizard checks components, can install prerequisites, then configures: interface (native / web) → AI mode (local / remote Tailscale) → models recommended for your machine. The **"⚙ Configure services"** button calibrates Docker + n8n step by step (first image download ~400 MB — phases shown live). First model download takes 5-15 min (1-3 GB each).

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
