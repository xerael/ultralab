# Politique de securite UltraLab

## Statut alpha

UltraLab est actuellement en phase **alpha**, distribue a des testeurs identifies.
Aucun audit de securite formel n'a ete realise. L'application est destinee a un usage
en environnement controle (PC personnel, reseau prive type Tailscale).

## Signaler une vulnerabilite

Si vous decouvrez une vulnerabilite de securite dans UltraLab :

1. **NE l'ouvrez PAS en issue publique GitHub**
2. Envoyez les details a : *(adresse email a completer)*
3. Indiquez : description de la faille, fichiers/composants concernes, etapes pour reproduire, impact estime

Je m'engage a :
- Accuser reception sous 5 jours ouvres
- Confirmer ou non la faille sous 14 jours
- Publier un correctif via une nouvelle release si confirme
- Vous mentionner dans les credits si vous le souhaitez

## Donnees utilisateur

Voir la section "Confidentialite" du README. Resume :
- Aucune donnee envoyee a un serveur externe par UltraLab
- LLM en local (Ollama) -> les prompts ne quittent pas votre PC
- APIs publiques consultees (PubMed, OpenAlex, Crossref) : queries de recherche uniquement, pas de donnees personnelles

## Verification d'integrite des binaires

Chaque release inclut un fichier `UltraLab-Setup.exe.sha256`. Avant install :

```powershell
certutil -hashfile UltraLab-Setup.exe SHA256
```

Le hash affiche doit etre IDENTIQUE a celui du `.sha256`. Si different, NE lancez PAS
l'installateur et signalez immediatement.
