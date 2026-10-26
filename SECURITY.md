# Politique de sécurité d'UltraLab

*Français, puis anglais. / French, then English.*

## Statut alpha

UltraLab est en phase **alpha**, réservée aux participants admis par l'auteur. Aucun audit de sécurité
formel n'a été réalisé. L'application est destinée à un usage en environnement contrôlé : votre PC et, en
mode distant, un PC joint par votre réseau privé (de type Tailscale).

## Signaler une vulnérabilité

Si vous découvrez une vulnérabilité de sécurité dans UltraLab :

1. **Ne l'ouvrez PAS en ticket public.**
2. Envoyez les détails à **ultralab.app@gmail.com**.
3. Indiquez : la description de la faille, les fichiers ou composants concernés, les étapes pour la
   reproduire et l'impact estimé.

L'auteur s'engage à :
- accuser réception sous 5 jours ouvrés ;
- confirmer ou non la faille sous 14 jours ;
- publier un correctif dans une nouvelle version si elle est confirmée ;
- vous mentionner dans les crédits si vous le souhaitez.

## Données utilisateur

Voir la section « Confidentialité » du README. En résumé :
- L'IA tourne sur votre PC ou sur votre PC distant privé : aucun texte n'est confié à un service d'IA en ligne.
- Aucune statistique d'usage n'est envoyée, ni par UltraLab ni par ses composants internes, et le moteur de
  workflows n'envoie pas ses rapports d'erreurs.
- Sortent du poste : les requêtes que vous lancez vers les bases bibliographiques et les sources de texte
  intégral (avec les clés et l'adresse de contact que vous avez saisies), l'envoi à votre gestionnaire de
  références en ligne si vous le demandez, les téléchargements que vous lancez (par exemple modèles, paquets
  R, prérequis installés par l'assistant, base des articles rétractés), la vérification de mise à jour, le
  téléchargement des composants au premier lancement et quand une mise à jour en change la version, et la
  résolution de noms du moteur de workflows par un DNS public.

## Relais local du mode distant

Depuis la version 0.5.3, le relais local du mode distant (port 11435) n'écoute que ce poste (127.0.0.1). Il
refuse une requête venue d'une autre machine, d'une page web ou sous un autre nom d'hôte, et ne relaie que
les routes du serveur de modèles qu'UltraLab emploie.

## Vérification d'intégrité des binaires

Chaque version publiée inclut un fichier `UltraLab-Setup.exe.sha256`, et `UltraLab-Monitor-Setup.exe.sha256`
quand le programme du PC distant est publié avec elle. Avant l'installation :

```powershell
certutil -hashfile UltraLab-Setup.exe SHA256
```

L'empreinte affichée doit être IDENTIQUE à celle du fichier `.sha256`. Sinon, NE lancez PAS l'installateur et
signalez-le immédiatement.

---

# UltraLab security policy

## Alpha status

UltraLab is in its **alpha** phase, reserved for participants admitted by the author. No formal security
audit has been carried out. The application is meant for use in a controlled environment: your PC and, in
remote mode, a PC reached through your private network (such as Tailscale).

## Reporting a vulnerability

If you find a security vulnerability in UltraLab:

1. **Do NOT open it as a public issue.**
2. Send the details to **ultralab.app@gmail.com**.
3. Include: a description of the flaw, the files or components involved, the steps to reproduce it and the
   estimated impact.

The author commits to:
- acknowledging receipt within 5 working days;
- confirming or not the flaw within 14 days;
- publishing a fix in a new version if it is confirmed;
- mentioning you in the credits if you wish.

## User data

See the "Privacy" section of the README. In short:
- The AI runs on your PC or on your private remote PC: no text is handed to an online AI service.
- No usage statistics are sent, neither by UltraLab nor by its internal components, and the workflow engine
  does not send its error reports.
- What leaves your computer: the requests you launch to bibliographic databases and full-text sources (with
  the keys and contact address you entered), sending to your online reference manager if you ask for it, the
  downloads you launch (for example models, R packages, prerequisites installed by the setup assistant, the
  database of retracted articles), the update check, the download of the components at first launch and when
  an update changes their version, and the workflow engine name resolution through a public DNS.

## Local relay of the remote mode

Since version 0.5.3, the local relay of the remote mode (port 11435) listens only on this computer
(127.0.0.1). It refuses a request coming from another machine, from a web page or under another host name,
and relays only the model server routes that UltraLab uses.

## Verifying the integrity of the binaries

Each published version includes a `UltraLab-Setup.exe.sha256` file, and `UltraLab-Monitor-Setup.exe.sha256`
when the remote PC program is published with it. Before installing:

```powershell
certutil -hashfile UltraLab-Setup.exe SHA256
```

The hash shown must be IDENTICAL to the one in the `.sha256` file. If it differs, do NOT run the installer
and report it immediately.
