AccessConfig
============

Un sélecteur de styles, simple et open source, pour permettre aux personnes en situation de handicap d’adapter votre site à leurs besoins.

[Contribuer sur GitHub](https://github.com/access42/AccessConfig) et [découvrez nos autres outils](https://access42.net/outils).

Nous vous invitons à lire la documentation détaillée sur le [site dédié à AccessConfig](https://accessconfig.a11y.fr).

Présentation
------------

AccessConfig est un composant JavaScript offrant plusieurs options pour **personnaliser l’affichage des contenus web**, et les rendre plus faciles à lire pour les utilisateurs ayant besoin de contrastes forts, les personnes dyslexiques, ainsi que pour les personnes déficientes visuelles ayant besoin de remplacer les images-textes par leur alternative.

Le script insère, à l’intérieur de l’attribut `class` de la balise `body`, des classes CSS spécifiques en fonction des paramètres sélectionnés par l’utilisateur :

*   **Contrastes**
    *   Défaut : `.a42-ac-default-contrast`
    *   Renforcés : `.a42-ac-high-contrast`
    *   Inversés : `.a42-ac-inv-contrast`
*   **Interlignage**
    *   Défaut : `.a42-ac-default-spacing`
    *   Adapté : `.a42-ac-dys-spacing`
*   **Police**
    *   Défaut : `.a42-ac-default-font`
    *   Adapté : `.a42-ac-dys-font`
*   **Justification**
    *   Défaut : `.a42-ac-default-justify`
    *   Adapté : `.a42-ac-cancel-justify`
*   **Remplacement d’image**
    *   Défaut : `.a42-ac-default-img`
    *   Adaptée : `.a42-ac-text-img`
    *   Note : le remplacement s’effectue par un traitement JavaScript.

Installation
------------

Pour installer AccessConfig, copier le dossier `/accessconfig` à la racine de votre projet.

Ce dossier contient notamment :

*   un dossier `/js` où sont rangés les fichiers JavaScript (JS) d’AccessConfig (version minifiée et version non minifiée) ;
*   un dossier `/css` où sont rangés :
    *   les feuilles de styles CSS d’AccessConfig (version minifiée et version non minifiée),
    *   le sous-dossier `/fonts`, contenant les fichiers `.woff` et `.woff2` utilisés pour la police adaptée à la dyslexie.

### Installation des CSS

Appeler la feuille de styles `accessconfig.min.css` **après** vos styles personnels, de sorte que ceux-ci soient écrasés lorsqu’AccessConfig est actif.

    <link rel="stylesheet" href="accessconfig/css/accessconfig.min.css" type="text/css" media="screen" />

#### Classes `CSS` adaptées

La feuille de styles d’AccessConfig contient les styles de la fenêtre modale ainsi que quelques styles déjà configurés pour fonctionner avec les options proposées par AccessConfig.

**Vous pouvez bien sûr modifier ou surcharger ces styles selon vos besoins.**

### Installation du script

Appeler le script `accessconfig.min.js` dans votre document HTML dans la balise `head` de la page.

    <script src="accessconfig/js/accessconfig.min.js" type="text/javascript"></script>

### Initialisation d’AccessConfig

Une fois que le script, les CSS et les polices sont installés, il faut initialiser AccessConfig dans votre page HTML.

Pour cela, copiez le code suivant et collez-le à l’endroit où vous souhaitez faire apparaître le bouton permettant de lancer AccessConfig :

    <div id="accessconfig" data-accessconfig-buttonname="Paramètres d’accessibilité" data-accessconfig-params='{ "Prefix" : "a42-ac", "ContainerClass" : "","ModalCloseButton" : "","ModalTitle" : "","FormFieldset" : "","FormFieldsetLegend" : "","FormRadio" : ""}' ></div>

AccessConfig met à votre disposition un certain nombre de paramètres, disponibles depuis ce code HTML. Il n’est pas nécessaire d’aller modifier le script pour les modifier. Nous les détaillons ci-après.

#### Modification du préfixe

Par défaut, les classes et les identifiants relatifs à AccessConfig et de ses cookies sont préfixés par `a42-ac`.

Mais il vous est possible de définir votre propre préfixe en modifiant le code d’initialisation d’AccessConfig : `data-accessconfig-params='{ "Prefix": "xxx" … }'`.

#### Autres options de personnalisation

Vous pouvez également configurer les paramètres suivants :

*   `ContainerClass` : la valeur de la classe de la fenêtre modale ;
*   `ModalCloseButton` : la valeur de la classe du bouton de fermeture de la fenêtre modale ;
*   `ModalTitle` : la valeur de la classe du titre de la fenêtre modale ;
*   `FormFieldset` : la valeur de la classe des éléments `fieldset` à l’intérieur de la fenêtre modale ;
*   `FormFieldsetLegend` : la valeur de la classe des éléments `legend` à l’intérieur de la fenêtre modale ;
*   `FormRadio` : la valeur de la classe des `input[type="radio"]` à l’intérieur de la fenêtre modale.