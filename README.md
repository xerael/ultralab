<div align="center">

# UltraLab

**Automatisation de revues systématiques de la littérature scientifique**
**Systematic literature review automation**

![Version](https://img.shields.io/badge/version-0.5.2--alpha-orange)
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
- 🎛️ **Contrôle des runs** : mise en pause qui conserve le travail déjà fait, reprise, et **relance ciblée** sur une catégorie (non traités, Maybe, résumé manquant, confiance faible, désaccords), avec changement de modèle pour la seule relance
- 📊 **Ranking** (score de pertinence) et **clustering** thématique

**4 · Lire et extraire**
- 📄 **Téléchargement de PDFs** en libre accès (Unpaywall, Europe PMC, CORE, Zotero) et **chasse aux PDFs manquants** avec statuts PRISMA
- 📖 **Lecture intégrale** : réévaluation de l'inclusion sur le PDF complet, motifs d'exclusion standardisés (PRISMA 16b)
- 📓 **Carnet d'interrogation des PDFs** (100 % local) : conversation suivie sur le plein texte, chaque affirmation **citant son passage** (article + page + extrait), choix des documents interrogés et liste de ceux qui ont réellement servi, notes et réponses épinglées exportables
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
- 🖥️ **Application native ou version web** : une fenêtre, ou l'interface ouverte dans votre navigateur et servie par UltraLab sur votre PC ; interface organisée par **étapes PRISMA**, **100 % bilingue FR / EN**, palette de commandes **Ctrl+K**, mode compact, visite guidée
- 🧭 **Assistant de premier paramétrage** : détecte les prérequis et guide l'installation pas à pas (Ollama, Docker, R, mode distant), pensé pour les personnes peu à l'aise avec l'informatique
- 🗑️ **Gestion des données** : supprimer runs et projets, effacer les caches, avec vue de l'espace occupé, depuis l'application
- 🛰️ **PC distant** privé (Tailscale) avec file d'attente, instances dédiées et panneau d'administration
- 🔌 **Connecteurs** : une carte par service, avec badge d'état et test réel en un clic
- 🔐 **Tout en local** : l'IA tourne sur votre PC (Ollama) ou sur votre PC distant privé. Aucune donnée envoyée à des tiers, aucune télémétrie.

### Quelle version a apporté quoi

Le détail des correctifs de chaque version se trouve dans les [notes de release](https://github.com/xerael/ultralab/releases).

| Version | Apports principaux |
| --- | --- |
| **0.5.2** | Fiabilité : les runs ne disparaissent plus sur les grands corpus, tri plus juste, nouvel écran de validation humaine, relecteur externe en module, accords publiés avec leur intervalle de confiance, limites de recherche dites |
| **0.5.1** | Correctif du mode distant : une instance de serveur de modèles indisponible ne bloque plus les requêtes ni ne fait déclarer une panne totale |
| **0.5.0** | Carnet d'interrogation des PDFs qui cite tous vos articles, projets rangés hors du Bureau enfin pris en charge, import d'un run venu d'un autre ordinateur, mémoire des cartes graphiques visible carte par carte, fermeture propre et diagnostics distants exacts |
| **0.4.9** | Carnet d'interrogation des PDFs, contrôle des runs (pause sans perte, reprise, relance ciblée), bouton de 2ᵉ avis, suivi des runs par le moteur, rigueur statistique renforcée |
| **0.4.8** | Assistant de premier paramétrage guidé, module « À valider » avec détail de l'article et traduction locale du résumé, suppression de données depuis l'application, mode distant fiabilisé avec diagnostic clair |
| **0.4.7** | Durcissement et stabilisation : pas de nouvelle fonctionnalité, correction de défauts de fiabilité issus d'un audit complet du code |
| **0.4.6** | Équations expertes respectées base par base, interrogation des PDFs du corpus, méta-analyse diagnostique, screening durci (calibration de Platt, test canari, vote de cohérence), très grands corpus |
| **0.4.5** | Statistiques niveau Cochrane, relecture en aveugle, pack relecteur autonome, chasse aux PDFs manquants, export des figures aux formats journal, reprise partielle, projets persistants |
| **0.4.4** | Copilote méthodologique, modules interactifs, hub PRISMA et file de validation, chaîne extraction vers méta-analyse, aide au choix du journal |
| **0.4.3** | Déduplication sémantique, méta-analyse en réseau, PRESS, assistant IA de configuration, screening multilingue, Gwet AC1 et PABAK |
| **0.4.2** | Apprentissage actif, analyses de sensibilité et de sous-groupes, rapport de projet consolidé |
| **0.4.1** | Module d'analyse statistique R complet, benchmark du screening, journal d'audit, bundle de reproductibilité |

## ⚠️ Statut : alpha en développement actif

Destinée aux **alpha-testeurs**. Bugs et changements rapides à prévoir. [Signaler un bug](https://github.com/xerael/ultralab/issues).

## Rejoindre l'alpha et licence

UltraLab est en phase de test. Son utilisation est **réservée aux participants admis par l'auteur**.

**Pour rejoindre l'alpha**, écrivez à **ultralab.app@gmail.com** en indiquant votre nom, votre établissement ou votre structure, et l'usage que vous envisagez (type de revue, discipline). L'admission se fait par un écrit de l'auteur qui vous désigne nommément, ou par la remise d'un code d'accès personnel. Les personnes qui utilisaient déjà UltraLab avant le 28 septembre 2026, dans une version obtenue auprès de l'auteur ou sur la page officielle de diffusion, sont admises d'office, sauf avis contraire écrit de l'auteur : il leur suffit d'accepter la licence. Les informations que vous envoyez servent à gérer l'alpha ; leur traitement et vos droits sont décrits à l'article 6 de la licence.

**Les règles de l'alpha, en résumé** (le texte complet est dans le fichier [LICENSE](LICENSE) ; sa version française fait foi) :

- **Usage personnel** : vous pouvez installer UltraLab sur les ordinateurs que vous utilisez vous-même, ainsi que sur un poste de calcul distant que vous administrez ou que vous êtes autorisé à utiliser, si seuls des participants s'en servent, et l'utiliser pour l'évaluer et pour vos travaux de recherche, d'étude ou d'enseignement, seul ou en équipe.
- **Pas de partage** : ni l'installeur, ni une copie du logiciel, ni votre code d'accès ne se transmettent, pas même à un collègue. Vous pouvez en revanche indiquer la page officielle de diffusion ; chaque personne intéressée demande elle-même à participer.
- **Pas de modification ni de réutilisation** du logiciel, de son code, de ses enchaînements de traitement ou de sa documentation sans autorisation écrite. Vous pouvez toutefois reprendre dans vos travaux et publications les éléments que le logiciel place dans vos résultats (brouillon de la section Méthodes, scripts d'analyse, réglages et invites, journal d'audit, pack relecteur), et citer le logiciel.
- **Pas d'usage commercial** : ni vente, location ou mise à disposition du logiciel comme service, ni prestation payée pour un tiers, ni usage par une entreprise ou pour son compte dans le cadre de son activité lucrative. Les travaux de recherche, d'étude ou d'enseignement menés au sein ou pour le compte d'un établissement d'enseignement supérieur ou de recherche public ou privé, d'un établissement de santé public ou privé à but non lucratif, d'une administration, d'une fondation ou d'une association ne sont pas un usage commercial, même lorsque vous êtes rémunéré par cet organisme ou que ces travaux sont financés ou publiés. Cette exception ne couvre pas les laboratoires pharmaceutiques, les fabricants de dispositifs médicaux, les prestataires de recherche sous contrat, les cabinets de conseil ni les éditeurs de logiciels. En cas de doute, écrivez à l'auteur.
- **Vos données et vos résultats** : l'auteur ne revendique aucun droit sur eux ; vous pouvez les conserver, les utiliser et les publier librement, sous réserve des droits des tiers sur les contenus repris (résumés, articles).
- **Version de test** : UltraLab peut comporter des erreurs ; vérifiez les résultats et gardez des sauvegardes. Il est fourni sans garantie et n'est pas destiné au diagnostic ni au traitement d'une personne.
- **Durée** : la licence dure jusqu'à la fin de l'alpha, annoncée au moins trente jours à l'avance ; l'auteur peut aussi y mettre fin avec un préavis de trente jours, ou plus tôt en cas de manquement à la licence. L'acceptation se fait dans l'installeur ou dans l'application.

La licence d'utilisation alpha régit les versions publiées à compter du 28 septembre 2026. Les versions 0.3.0-alpha à 0.5.2-alpha avaient été diffusées sous PolyForm Noncommercial 1.0.0 ; depuis cette date, l'auteur ne les propose plus sous cette licence, sans retirer les droits déjà acquis (article 13 de la licence). Les composants tiers intégrés et leurs licences sont listés dans [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt). La licence n'accorde aucun droit sur le nom ni sur le logo UltraLab (voir [NOTICE](NOTICE)).

## Installation

1. **Télécharger** `UltraLab-Setup.exe` depuis la [dernière release](https://github.com/xerael/ultralab/releases/latest).
2. **Pré-requis** : Windows 10/11, [Docker Desktop](https://www.docker.com/products/docker-desktop/), [Ollama](https://ollama.com/). UltraLab les détecte et peut les **installer automatiquement** (winget). Optionnel : [R](https://cran.r-project.org/) pour le module d'analyse statistique (+ RStudio, Quarto).
3. **Lancer l'installateur** (installeur et application auto-signés ; SmartScreen peut demander une confirmation).
4. **Vérifier l'intégrité** (optionnel) : comparer le SHA256 indiqué dans les notes de release.

## Premier lancement

Un assistant vérifie les composants, peut installer les prérequis et vous guide sur ce qui manque (modèle recommandé selon votre machine, mode IA local ou distant Tailscale). Il vous fait aussi choisir l'interface : application native (une fenêtre) ou version web (aucune fenêtre, UltraLab s'ouvre dans votre navigateur et se quitte depuis l'interface) ; le choix prend effet au prochain démarrage et se change dans Paramètres → Application → Interface. Le bouton **« ⚙ Configurer les services »** calibre Docker + n8n pas à pas (1ᵉʳ téléchargement d'images ~400 Mo, les phases s'affichent en direct). Le 1ᵉʳ téléchargement des modèles prend 5-15 min (1-3 Go chacun).

## Utilisation

- **Navigation par étapes PRISMA** : chaque module explique à quoi il sert ; corpus chargeable depuis un run, un projet, Zotero, un dossier de PDFs ou un fichier (glisser-déposer).
- **Projets** : créez un projet, pré-programmez une séquence de modules et suivez la timeline en direct ; tous les runs restent réutilisables.
- Les résultats sont regroupés dans des dossiers dédiés sur le Bureau. **Ctrl+K** pour naviguer au clavier.
- **Une seule copie à la fois** (application installée) : rouvrir UltraLab alors qu'il tourne déjà ne lance pas de seconde copie ; sa fenêtre revient au premier plan, même réduite, ou, en version web, l'onglet de l'interface se rouvre dans votre navigateur. Deux ouvertures lancées au même instant ne font plus deux copies ; seule une première copie bloquée plus de 2 secondes à son démarrage laisse passer la seconde.
- **Quitter pendant un run** : « Quitter UltraLab » et la croix de la fenêtre posent la même question quand un run tourne (les runs en cours sont nommés) ; choisir de rester garde la fenêtre et le run, et une seule question est posée à la fois. La question s'affiche dans la fenêtre de l'application, au clavier comme à la souris (Tab, Entrée, Échap pour rester) ; tant qu'elle est ouverte, un clic sur la croix ou sur « Fermer la fenêtre » dans la barre des tâches ramène la fenêtre au premier plan sans rien fermer. Toutes les confirmations de l'interface s'affichent de la même façon. Sans run, elles ferment comme avant. Une fenêtre dont l'interface ne répond plus se ferme au deuxième clic sur la croix. Rouvrir UltraLab pendant cette question, ou pendant l'arrêt qui suit « Quitter UltraLab » en version web, n'est pas perdu : l'application se relance. Tant que la question est affichée, les raccourcis clavier des écrans ne font rien (Entrée active le bouton qui a le focus, Échap fait rester). Limites connues, mesurées : un double clic sur la croix plus rapide que l'accusé de l'interface peut encore fermer sans question pendant un run (interface très occupée : 5 fois sur 5 à 5 et à 20 ms d'intervalle, 1 fois sur 5 à 80 ms ; interface libre : 1 fois sur 5 à 5 ms) ; en version web, rouvrir UltraLab pendant qu'un traitement empêche le moteur de répondre, puis quitter depuis ce nouvel onglet avant qu'il ne réponde, relance l'application ; enfin, si le moteur ne répond pas pendant son arrêt, l'onglet ouvert par la réouverture reste sur une page morte, à côté de celui de la relance.

## Réglages (Paramètres)

Onglets clairs : **IA et modèles** (modèles + strictesse + règles personnalisées + double relecture), **Connecteurs** (clés API avec test), **Mode distant** (IP, test, ports), **Rigueur scientifique** (journal d'audit, cache LLM), **Application** (démarrage, mode d'interface, mises à jour, veille planifiée, configuration initiale, données et stockage), **Dépannage** (rapport de diagnostic, console développeur, paramètres Ollama manuels). La langue et le thème se changent par les deux boutons en bas de la barre latérale.

## Mises à jour

Vérification automatique au démarrage. Nouvelle version → Paramètres → Application → Mises à jour. Dans l'application native, « Mettre à jour l'application » la télécharge et l'installe ; en version web ce bouton n'existe pas, et « Télécharger la mise à jour » donne le nouveau Setup à lancer (config préservée). Workflows seuls : Paramètres → Application → Mises à jour → « Mettre à jour les workflows ».

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
- 🎛️ **Run control**: pause that preserves the work already done, resume, and a **targeted re-run** on one category (unprocessed, Maybe, missing abstract, low confidence, disagreements), with a model switch for that re-run only
- 📊 **Ranking** (relevance score) and topic **clustering**

**4 · Read and extract**
- 📄 **Open access PDF download** (Unpaywall, Europe PMC, CORE, Zotero) and **missing PDF hunt** with PRISMA statuses
- 📖 **Full-text reading**: inclusion re-assessed on the complete PDF, standardised exclusion reasons (PRISMA 16b)
- 📓 **PDF library notebook** (100% local): an ongoing conversation over the full text, every claim **citing its passage** (article + page + excerpt), you pick which documents are queried and see which ones actually contributed, with exportable notes and pinned answers
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
- 🖥️ **Native application or web version**: a window, or the interface opened in your browser and served by UltraLab on your PC; interface organised by **PRISMA stages**, **fully bilingual FR / EN**, **Ctrl+K** command palette, compact mode, guided tour
- 🧭 **First-run setup assistant**: detects prerequisites and guides installation step by step (Ollama, Docker, R, remote mode), designed for people not comfortable with computers
- 🗑️ **Data management**: delete runs and projects, clear caches, with a view of disk usage, from within the application
- 🛰️ **Private remote PC** (Tailscale) with a queue, dedicated instances and an admin panel
- 🔌 **Connectors**: one card per service, with a status badge and a real one-click test
- 🔐 **Fully local**: the AI runs on your PC (Ollama) or on your own private remote PC. No data sent to third parties, no telemetry.

### Which version brought what

The detailed fix list for each version lives in the [release notes](https://github.com/xerael/ultralab/releases).

| Version | Main additions |
| --- | --- |
| **0.5.2** | Reliability: runs no longer disappear on large corpora, fairer screening, new human validation screen, external reviewer as a module, agreement published with its confidence interval, search limits stated |
| **0.5.1** | Remote mode fix: an unavailable model server instance no longer blocks requests nor triggers a false total failure |
| **0.5.0** | PDF library notebook now citing all your articles, projects stored outside the Desktop finally supported, importing a run from another computer, graphics card memory shown card by card, clean shutdown and accurate remote diagnoses |
| **0.4.9** | PDF library notebook, run control (lossless pause, resume, targeted re-run), 2nd opinion button, engine-side run tracking, stronger statistical rigour |
| **0.4.8** | Guided first-run setup assistant, "to validate" module with article detail and local abstract translation, in-app data deletion, reliable remote mode with clear diagnosis |
| **0.4.7** | Hardening and stabilisation: no new feature, reliability defects fixed following a full code audit |
| **0.4.6** | Expert equations honoured database by database, ask your corpus PDFs, diagnostic meta-analysis, hardened screening (Platt calibration, canary test, consistency voting), very large corpora |
| **0.4.5** | Cochrane-level statistics, blinded review, standalone reviewer pack, missing PDF hunt, journal-format figure export, partial resume, persistent projects |
| **0.4.4** | Methodological copilot, interactive modules, PRISMA hub and validation queue, extraction to meta-analysis chain, journal selection help |
| **0.4.3** | Semantic deduplication, network meta-analysis, PRESS, AI configuration assistant, multilingual screening, Gwet AC1 and PABAK |
| **0.4.2** | Active learning, sensitivity and subgroup analyses, consolidated project report |
| **0.4.1** | Complete R statistical analysis module, screening benchmark, audit log, reproducibility bundle |

## ⚠️ Status: active alpha

For **alpha testers**. Expect bugs and rapid changes. [Report a bug](https://github.com/xerael/ultralab/issues).

## Joining the alpha and license

UltraLab is in its test phase. Its use is **reserved for participants admitted by the author**.

**To join the alpha**, write to **ultralab.app@gmail.com** with your name, your institution or organization, and your intended use (type of review, field). Admission is granted by a written message from the author that names you, or by the delivery of a personal access code. People who were already using UltraLab before September 28, 2026, in a version obtained from the author or from the official distribution page, are admitted automatically, unless the author states otherwise in writing: they only need to accept the license. The information you send is used to manage the alpha; its processing and your rights are described in Section 6 of the license.

**The alpha rules, in short** (the full text, whose French version prevails, is in the [LICENSE](LICENSE) file):

- **Personal use**: you may install UltraLab on the computers you use yourself and on a remote computing station you administer or are authorized to use, provided only participants use it there, and use it to evaluate it and for your research, study or teaching work, alone or as part of a team.
- **No sharing**: the installer, a copy of the software or your access code must not be passed on to anyone, not even a colleague. You may, however, point to the official distribution page; each interested person applies to join themselves.
- **No modification or reuse** of the software, its code, its workflows or its documentation without written permission. You may, however, reuse in your work and publications the elements the software places in your results (draft Methods section, analysis scripts, settings and prompts, audit log, reviewer pack), and cite the software.
- **No commercial use**: no selling, renting or providing the software as a service, no paid service for a third party, no use by or on behalf of a company as part of its profit-making activity. Research, study or teaching work carried out within or on behalf of a public or private higher education or research institution, a public or private non-profit healthcare institution, a public administration, a foundation or an association is not commercial use, even when you are paid by that organization or the work is funded or published. This exception does not cover pharmaceutical companies, medical device manufacturers, contract research providers, consulting firms or software publishers. In case of doubt, write to the author.
- **Your data and your results**: the author claims no rights in them; you may keep, use and publish them freely, subject to third-party rights in the content they include (abstracts, articles).
- **Test version**: UltraLab may contain errors; check the results and keep backups. It is provided without warranty and is not intended for the diagnosis or treatment of any person.
- **Term**: the license lasts until the end of the alpha, announced at least thirty days in advance; the author may also end it with thirty days' notice, or earlier in case of breach of the license. Acceptance takes place in the installer or in the application.

The alpha use license governs the versions published on or after September 28, 2026. Versions 0.3.0-alpha to 0.5.2-alpha were distributed under the PolyForm Noncommercial License 1.0.0; since that date the author no longer offers them under that license, without withdrawing rights already acquired (Section 13 of the license). The third-party components included and their licenses are listed in [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt). The license grants no right to the UltraLab name or logo (see [NOTICE](NOTICE)).

## Installation

1. **Download** `UltraLab-Setup.exe` from the [latest release](https://github.com/xerael/ultralab/releases/latest).
2. **Requirements**: Windows 10/11, [Docker Desktop](https://www.docker.com/products/docker-desktop/), [Ollama](https://ollama.com/). UltraLab detects them and can **install them automatically** (winget). Optional: [R](https://cran.r-project.org/) for the statistical analysis module (+ RStudio, Quarto).
3. **Run the installer** (installer and app are self-signed; SmartScreen may prompt).
4. **Verify integrity** (optional): compare the SHA256 in the release notes.

## First launch

A wizard checks components, can install prerequisites and guides you through what is missing (model recommended for your machine, AI mode local or remote Tailscale). It also lets you choose the interface: native application (a window) or web version (no window, UltraLab opens in your browser and is quit from the interface); the choice takes effect at the next start and can be changed in Settings → Application → Interface. The **"⚙ Configure services"** button calibrates Docker + n8n step by step (first image download ~400 MB, phases shown live). First model download takes 5-15 min (1-3 GB each).

## Usage

- **PRISMA-stage navigation**: every module explains its purpose; corpus loadable from a run, a project, Zotero, a PDF folder or a file (drag & drop).
- **Projects**: create a project, pre-program a module sequence and follow the live timeline; every run stays reusable.
- Results are grouped in dedicated folders on the Desktop. **Ctrl+K** for keyboard navigation.
- **One copy at a time** (installed app): opening UltraLab again while it is already running does not start a second copy; its window comes back to the front, even if minimised, or, in the web version, the interface tab reopens in your browser. Two openings started at the same moment no longer make two copies; only a first copy stuck for more than 2 seconds while starting lets the second one through.
- **Quitting during a run**: "Quit UltraLab" and the window's close button ask the same question while a run is in progress (the running runs are named); choosing to stay keeps the window and the run, and only one question is asked at a time. The question is shown inside the application window, with the keyboard as with the mouse (Tab, Enter, Esc to stay); while it is open, a click on the close button or on "Close window" in the taskbar brings the window to the front without closing anything. Every confirmation in the interface is shown the same way. Without a run, they close as before. A window whose interface no longer responds closes on the second click on the close button. Opening UltraLab again during this question, or during the shutdown that follows "Quit UltraLab" in the web version, is not lost: the application restarts. While the question is shown, the screens' keyboard shortcuts do nothing (Enter activates the focused button, Esc stays). Known, measured limits: a double click on the close button faster than the interface's acknowledgement can still close without a question during a run (very busy interface: 5 times out of 5 at 5 and at 20 ms apart, 1 time out of 5 at 80 ms; idle interface: 1 time out of 5 at 5 ms); in the web version, opening UltraLab again while a task keeps the engine from answering, then quitting from that new tab before it answers, restarts the application; finally, if the engine does not answer while it stops, the tab opened by the reopening stays on a dead page, next to the restart's tab.

## Settings

Clear tabs: **AI & models** (models + strictness + custom rules + double review), **Connectors** (API keys with tests), **Remote mode** (IP, test, ports), **Scientific rigor** (audit log, LLM cache), **Application** (startup, interface mode, updates, scheduled monitoring, initial setup, data & storage), **Troubleshooting** (diagnostic report, developer console, manual Ollama params). Language and theme are switched with the two buttons at the bottom of the sidebar.

## Updates

Automatic check on startup. New version → Settings → Application → Updates. In the native application, "Update the app" downloads and installs it; in the web version this button does not exist, and "Download update" gives the new Setup to run (config preserved). Workflows only: Settings → Application → Updates → "Update workflows".

## Privacy

Your data (articles, PDFs, results) stays on your PC. The AI is local (Ollama). External APIs are queried only for bibliographic search (public queries). No telemetry.

## Credits

Built by [@xerael](https://github.com/xerael). Stack: Python · Flask · Tauri · Svelte · n8n · Ollama · Qdrant · Docker · R.
