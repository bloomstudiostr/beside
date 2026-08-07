# beside.

> every setup, one click.

![Dernière version](https://img.shields.io/github/v/release/bloomstudiostr/beside?label=version)
![Plateforme](https://img.shields.io/badge/plateforme-macOS%2013%2B-lightgrey)
![Licence](https://img.shields.io/badge/licence-tous%20droits%20r%C3%A9serv%C3%A9s-red)

Petite app macOS en barre de menu qui repositionne l'écran interne d'un
MacBook par rapport à un écran externe (à gauche, en dessous ou à droite)
en un clic, au lieu de faire glisser les rectangles dans Réglages Système >
Moniteurs.

Utile quand on change souvent de poste : clavier/souris avec le MacBook à
gauche au bureau, à droite ailleurs, en dessous à la maison.

## Ce que ça fait

- Une icône dans la barre de menu, pas de fenêtre, pas d'icône dans le Dock.
- Trois positions, chacune illustrée par un petit schéma des deux écrans.
- L'écran interne est **centré** sur l'axe perpendiculaire à celui de
  l'écran externe.
- Un halo lumineux apparaît sur le bord des deux écrans, du côté où ils se
  rejoignent : un repère visuel pour confirmer le choix avant de valider.
- La dernière position est mémorisée et **réappliquée automatiquement** au
  branchement d'un écran externe.
- Repose sur l'API publique Quartz Display Services (`CGConfigureDisplayOrigin`),
  donc aucune permission d'accessibilité, aucune extension système, aucune
  collecte de données.

## Installation

1. **[Télécharger la dernière version (DMG)](https://github.com/bloomstudiostr/beside/releases/latest/download/beside.dmg)**
2. Ouvrir le DMG, glisser `beside.app` dans `Applications`.
3. Premier lancement : voir ci-dessous, macOS bloque l'app au premier
   démarrage.

### Premier lancement : l'app n'est pas encore notariée par Apple

Je suis designer digital, pas développeur professionnel : beside. c'est un
projet que je bidouille sur mon temps libre pour le fun, et je n'ai pas
(encore) de compte Apple Developer (99 $/an). Du coup l'app est signée en
ad-hoc, pas notariée, et macOS la bloque par précaution au premier
lancement avec un message du genre *« Apple n'a pas pu vérifier... »*.
C'est normal, l'app n'est pas endommagée.

Deux façons de l'ouvrir quand même :

**Option 1, sans terminal**
Réglages Système → Confidentialité et sécurité → faire défiler jusqu'en
bas → cliquer sur **« Ouvrir quand même »** → relancer l'app.

**Option 2, terminal**
Après avoir glissé l'app dans `Applications`, exécuter :

```bash
xattr -dr com.apple.quarantine /Applications/beside.app
```

Puis relancer l'app normalement.

> Aucun fichier source n'est présent dans le DMG ni dans l'app : c'est un
> binaire compilé, comme n'importe quelle app macOS.

## Prérequis

- macOS 13 (Ventura) ou plus récent

## Mises à jour

Le lien de téléchargement tout en haut de cette page pointe toujours vers
la dernière version disponible. Pas besoin de revenir vérifier ici : si tu
retélécharges plus tard avec ce même lien, tu auras automatiquement la
version la plus récente.

Pour être averti par mail dès qu'une nouvelle version sort, sans avoir à
repasser sur cette page : tout en haut de ce dépôt GitHub, à droite du nom
du projet, il y a un bouton **« Watch »**. Cliquer dessus, choisir
**« Custom »**, cocher uniquement **« Releases »**, puis valider. Tu
recevras une notification uniquement pour les nouvelles versions, pas pour
le reste de l'activité du projet.

Historique de toutes les versions : [page Releases](https://github.com/bloomstudiostr/beside/releases).

## Limites connues

- Gère **exactement deux écrans** : l'interne plus un externe. Au-delà,
  l'app le signale et ne touche à rien, faute de pouvoir deviner quel
  écran sert de référence.
- Suppose un affichage étendu, pas en recopie vidéo.

## Bugs & suggestions

Le code source de cette app n'est pas public, et ce dépôt n'accepte pas de
pull requests. En revanche les [Issues](https://github.com/bloomstudiostr/beside/issues)
sont ouvertes pour signaler un bug ou proposer une idée.

## Soutenir le projet

beside. est gratuit et le restera. Si l'app te rend service, un coup de
pouce via [Patreon](https://www.patreon.com/cw/thebloom) m'aide à passer
plus de temps dessus, et pourquoi pas un jour financer un compte Apple
Developer pour que l'app soit notariée et s'ouvre sans les étapes ci-dessus.

## Licence

© Bloom Studio, Maxime Almy. Tous droits réservés. Voir [LICENSE](LICENSE).
