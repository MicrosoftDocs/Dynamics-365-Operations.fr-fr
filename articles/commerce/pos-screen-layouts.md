---
title: Configurations visuelles de l’interface utilisateur de PDV
description: Cette rubrique fournit des informations sur les mises en page de l’écran pour les expériences pour PDV Dynamics 365 Commerce.
author: boycezhu
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 17379dc97c7a8b22912482a7aeebd0d8ac08dc496fa7b1661952bca10a21c75b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765878"
---
# <a name="pos-user-interface-visual-configurations"></a>Configurations visuelles de l’interface utilisateur de PDV

[!include [banner](includes/banner.md)]


L’interface utilisateur du point de vente (PDV) Microsoft Dynamics 365 Commerce peut être configurée avec une combinaison de profils visuels et de mises en page de l’écran, qui sont affectés aux magasins, aux registres et/ou aux utilisateurs. Cette rubrique offre des informations à propos de ces options de configuration.

L’illustration suivante présente les relations entre les différentes entités qui constituent les aspects configurables de l’interface utilisateur du POS.

![Entité Mise en page de l’écran du POS.](../commerce/media/POS-layout-configuration-entities-diagram.png)

## <a name="visual-profile"></a>Profil visuel

Les profils visuels sont affectés aux registres et ils spécifient les éléments visuels qui sont spécifiques aux registres et qui sont partagés par plusieurs utilisateurs. Chaque utilisateur qui se connecte au registre voit les mêmes thèmes, mise à jour, couleurs et images.

![Écran d’accueil de POS avec un thème clair.](../commerce/media/POS-Welcome-Screen-with-Light-theme.png)

![Écran de transaction de POS avec un thème foncé.](../commerce/media/POS-Transaction-Screen-with-Dark-theme.png)

- **Numéro de profil** – Le numéro de profil est l’identificateur unique du profil visuel.
- **Description** – Vous pouvez spécifier un nom significatif qui permet d’identifier le profil correct pour votre cas.
- **Thème** – Vous pouvez choisir entre les thèmes d’application **Clair** et **Foncé**. Le thème affecte les couleurs de police et d’arrière-plan dans l’application.
- **Couleur d’accentuation** – La couleur d’accentuation est utilisée dans le POS pour différencier ou mettre en évidence des éléments visuels spécifiques tels que des vignettes, des boutons de commande et des liens hypertextes. En général, ces éléments sont modifiables.
- **Couleur d’en-tête** – Vous pouvez configurer la couleur de l’en-tête de page pour répondre aux exigences de marque du détaillant.
- **Schéma de police** - Vous pouvez choisir entre les schémas de police **Standard** et **Grand**. Le schéma de police a un impact sur la taille de la police dans toute l’application. La sélection par défaut est **Standard**.
- **Toujours afficher les étiquettes de la barre d’application** - Lorsque cette option est activée, le texte de l’étiquette est toujours visible sous les boutons de la barre d’application.
- **Disposition** - Vous pouvez choisir entre les mises en page **Centré** et **Droite**. La disposition affecte l’alignement de la boîte de connexion sur l’écran de connexion. La sélection par défaut est **Centré**.
- **Afficher la date/l’heure** - Lorsque cette option est activée, la date et l’heure actuelles sont affichées dans l’en-tête du PDV et sur l’écran de connexion.
- **Clavier** - Vous pouvez choisir entre **Clavier OS par défaut** et **Afficher le pavé numérique** pour spécifier le clavier par défaut utilisé pour la saisie sur l’écran de connexion. Le pavé numérique est un clavier virtuel utilisé principalement pour les appareils tactiles. La sélection par défaut est **Clavier OS par défaut**.
- **Image de logo** - Vous pouvez spécifier une image de logo qui s’affiche sur l’écran de connexion. Nous vous recommandons d’utiliser une image qui a un arrière-plan transparent. La taille du fichier des images d’arrière-plan devrait être aussi petite que possible, car le stockage et le chargement de fichiers volumineux peuvent affecter le comportement et les performances de l’application.
- **Arrière-plan de connexion** – Vous pouvez spécifier une image d’arrière-plan pour l’écran de connexion. La taille de fichier des images d’arrière-plan devrait être aussi petite que possible.
- **Arrière-plan** – Vous pouvez spécifier une image d’arrière-plan qui est utilisée à la place de la couleur de thème unie dans l’application. En ce qui concerne les images d’arrière-plan de l’écran de connexion, la taille du fichier doit être aussi petite que possible.

> [!NOTE]
> Le disposition **Droite** et l’affichage de la date/de l’heure ne s’appliquent pas à l’écran de connexion en vue compacte.

Vous devez exécuter la tâche de programme de distribution **1090** (**Caisses enregistreuses**) pour synchroniser les dernières configurations de profil visuel avec la base de données des canaux.

## <a name="screen-layouts"></a>Mises en page de l’écran

Les configurations de la mise en page de l’écran déterminent les actions, le contenu et le placement des contrôles de l’interface utilisateur dans l’écran **Accueil** et l’écran **Transaction**.

![Vue de l’entité Mise en page de l’écran POS.](../commerce/media/POS-Screen-Layout-View.png)

- **Écran d’accueil** – Dans la plupart des cas, l’écran d’accueil est la page que les utilisateurs voient lorsqu’ils se connectent pour la première fois au POS. L’écran d’accueil peut correspondre à une image de marque et des groupes de boutons qui permettent d’accéder aux opérations de POS. Généralement, les opérations qui ne sont pas spécifiques à la transaction actuelle sont placées sur cet écran.

    ![Écran d’accueil du POS.](../commerce/media/POS-Welcome-Screen.png)

- **Écran de transaction** – L’écran **Transaction** est l’écran principal du POS pour traiter les transactions de vente et les commandes. Le contenu et la mise en page sont configurés à l’aide du concepteur de mise en page de l’écran.

    ![Écran de transaction POS.](../commerce/media/POS-Transaction-Screen.png)

- **Écran d’accueil par défaut** – Certains détaillants préfèrent que les caissiers accèdent directement à l’écran **Transaction** après s’être connectés. Le paramètre **Écran d’accueil par défaut** vous permet de spécifier l’écran par défaut qui s’affiche après la connexion pour chaque mise en page de l’écran.

### <a name="assignment"></a>Affectation

Les mises en page de l’écran peuvent être affectées au magasin, au registre ou à l’utilisateur. L’affectation d’utilisateur remplace les affectations de registre et de magasin, et l’affectation de registre remplace l’affectation de magasin. Dans un scénario unique où tous les utilisateurs utilisent la même mise en page, quel que soit le registre ou le rôle, la mise en page de l’écran peut être paramétrée uniquement au niveau du magasin. Dans les scénarios où des registres ou utilisateurs spécifiques nécessitent des mises en page spécialisées, celles-ci peuvent être affectées.

Selon le niveau auquel les dispositions d’écran sont attribuées, vous devez exécuter les tâches de programme de distribution **1070** (**Configuration des canaux**), **1090** (**Caisses enregistreuses**), et/ou **1060** (**Personnel**) pour synchroniser les dernières configurations de disposition d’écran avec la base de données des canaux.

### <a name="layout-sizes"></a>Tailles de mise en page

La plupart des aspects de l’interface utilisateur du POS sont réactifs, et la mise en page est automatiquement redimensionnée et ajustée selon la taille et l’orientation de l’écran. Toutefois, l’écran **Transaction** du POS doit être configuré pour chaque résolution d’écran prévue.

Au démarrage, l’application POS sélectionne automatiquement la taille la plus proche qui est configurée pour l’appareil. Une mise en page de l’écran peut également contenir des configurations pour les modes Paysage et Portrait, et pour les appareils normaux et compacts. Par conséquent, les utilisateurs peuvent être affectés à une mise en page d’écran unique qui fonctionne avec les différentes tailles et les différents facteurs de forme utilisés dans le magasin.

![Tailles de mise en page du POS.](../commerce/media/POS-Screen-Layout-Sizes.png)

- **Nom** – Vous pouvez entrer un nom significatif pour identifier la taille de l’écran.
- **Type de mise en page** – L’application POS peut afficher son interface utilisateur dans différents modes afin de fournir la meilleure expérience utilisateur sur un appareil donné.

    - **Modern POS – Complet** – Les mises en page complètes sont généralement utilisées pour des écrans plus grands tels que des moniteurs de bureau et des tablettes. Vous pouvez sélectionner les éléments de l’interface utilisateur à inclure, spécifier la taille et l’emplacement de ces éléments et configurer leurs propriétés détaillées. Les mises en page complètes prennent en charge les configurations Portrait et Paysage.
    - **Modern POS – Compact** – Les mises en page compactes sont généralement recommandées pour les téléphones et les petites tablettes. Les possibilités de conception pour les appareils compacts sont limitées. Vous pouvez configurer les colonnes et les champs pour les volets Ticket de caisse et Totaux.

- **Largeur/Hauteur** – Ces valeurs représentent la taille d’écran effective, en pixels, qui est prévue pour la mise en page. N’oubliez pas que certains systèmes d’exploitation utilisent la mise à l’échelle pour les écrans à haute résolution.

> [!TIP]
> Vous pouvez déterminer la taille de mise en page requise pour un écran POS en affichant la résolution dans l’application. Démarrez le POS, puis accédez à **Paramètres \> Informations de session**. POS affiche la mise en page d’écran actuellement chargée, la taille de mise en page et la résolution de la fenêtre d’application.

![Page d’informations sur la session du PDV qui affiche la mise en page d’écran actuellement chargée, la taille de mise en page et la résolution de la fenêtre d’application.](../commerce/media/POS-Session-Information.png)

### <a name="button-grids"></a>Groupes de boutons

Pour chaque taille de mise en page dans une mise en page de l’écran, vous pouvez configurer et affecter des groupes de boutons pour l’écran d’accueil et l’écran **Transaction** du POS. Les groupes de boutons de l’écran d’accueil sont automatiquement alignés de gauche à droite, du plus petit numéro (écran d’accueil 1) au plus grand numéro.

Dans les mises en page complètes du POS, la position des groupes de boutons est spécifiée dans le concepteur de mise en page de l’écran.

Dans les mises en page compactes du POS, les groupes de boutons sont automatiquement alignés de haut en bas, du plus petit numéro (écran de transaction 1) au plus grand numéro. Ils sont accessibles dans le menu **Actions**.

![Groupes de boutons pour la mise en page compacte.](../commerce/media/Compact-View-Button-Grids.png)

> [!NOTE]
> Les tailles des boutons dans le concepteur seront mises à l’échelle pour s’adapter à la taille de la fenêtre, par conséquent, elles peuvent ne pas refléter avec précision les boutons réels rendus dans PDV. Pour simuler au mieux la disposition de la grille des boutons, ajustez les fenêtres du concepteur à la même taille que le PDV.

### <a name="images"></a>Images

Pour chaque taille de mise en page dans une mise en page de l’écran, vous pouvez spécifier des images à inclure dans l’interface utilisateur du POS. Pour les mises en page complètes du POS, une image peut être spécifiée pour l’écran d’accueil. Cette image s’affiche comme premier élément de l’interface utilisateur à gauche. Dans l’écran **Transaction**, des images peuvent être utilisées comme images d’onglet ou comme logo. Les mises en page compactes du POS n’utilisent pas ces images.

### <a name="screen-layout-designer"></a>Concepteur de mise en page de l’écran

Le concepteur de mise en page de l’écran permet de configurer différents aspects de l’écran **Transaction** du POS pour chaque taille de mise en page, dans les modes Portrait et Paysage, et pour les mises en page complètes et compactes. Le concepteur de mise en page de l’écran utilise la technologie de déploiement ClickOnce pour télécharger, installer et lancer la dernière version de l’application chaque fois que les utilisateurs y accèdent. Pensez à vérifier la configuration requise du navigateur pour ClickOnce. Certains navigateurs, tels que Google Chrome, requièrent des extensions.

> [!IMPORTANT]
> Vous devez configurer une mise en page de l’écran pour chaque taille de mise en page définie et utilisée par le POS.

### <a name="full-layout-designer"></a>Concepteur de mise en page complète

Le concepteur de mise en page complète permet aux utilisateurs de déplacer les contrôles de l’interface utilisateur dans l’écran **Transaction** du POS et de configurer les paramètres de ces contrôles.

![Concepteur de mise en page complète du POS (mode Paysage).](../commerce/media/POS-Full-Layout-Designer-Landscape.png)

- **Importer la mise en page/Exporter la mise en page** – Vous pouvez exporter et importer des conceptions de mise en page de l’écran du POS en tant que fichiers XML, afin de pouvoir les réutiliser et les partager facilement dans les environnements. Il est important d’importer les conceptions de mise en page pour les tailles de mise en page correctes. Sinon, les éléments de l’interface utilisateur peuvent ne pas s’afficher correctement à l’écran.
- **Paysage/Portrait** – Si le périphérique POS permet aux utilisateurs de permuter entre les modes Paysage et Portrait, vous devez définir une mise en page de l’écran pour chaque mode. Le POS détecte automatiquement la rotation de l’écran et affiche la mise en page appropriée.
- **Grille de mise en page** – Le concepteur de mise en page du POS utilise une grille de 4 pixels. Les contrôles de l’interface utilisateur « s’affichent » sur la grille pour vous aider à aligner correctement le contenu.
- **Zoom du concepteur** – Vous pouvez effectuer un zoom avant et arrière en mode Concepteur pour mieux voir le contenu sur l’écran du POS. Cette fonction est utile lorsque la résolution de l’écran du POS diffère considérablement de la résolution de l’écran utilisé dans le concepteur.
- **Afficher/masquer la barre de navigation** – Pour les mises en page complètes du POS, vous pouvez choisir si la barre de navigation de gauche est visible sur l’écran **Transaction**. Cette fonction est utile pour les écrans à faible résolution. Pour définir la visibilité, cliquez avec le bouton droit sur la barre de navigation du concepteur, et activez ou désactivez la case à cocher **Toujours visible**. Si la barre de navigation est masquée, les utilisateurs du POS peuvent toujours y accéder via le menu dans le volet supérieur.

    ![Afficher/masquer la barre de navigation.](../commerce/media/Navigation-Bar.PNG)

- **Contrôles du POS** – Le concepteur de mise en page du POS prend en charge les contrôles suivants. Vous pouvez configurer plusieurs contrôles en cliquant avec le bouton droit et en utilisant le menu contextuel.

    ![Contrôles de l’interface utilisateur du POS.](../commerce/media/POS-UI-Controls.png)

    - **Pavé numérique** – Le pavé numérique est le mécanisme principal pour la saisie utilisateur dans l’écran **Transaction** du POS. Vous pouvez configurer le contrôle de manière à ce que le pavé numérique complet soit affiché. Cette option est idéale pour les appareils à écran tactile. Sinon, vous pouvez la configurer pour que seul le champ de saisie soit affiché. Dans ce cas, un clavier physique est utilisé pour la saisie. Les paramètres du pavé numérique sont disponibles uniquement dans les mises en page complètes. Pour les mises en page compactes, le pavé numérique complet est toujours visible sur l’écran **Transaction**.
    - **Volet des totaux** - Vous pouvez configurer le volet des totaux dans une ou deux colonnes pour afficher des valeurs telles que le nombre de lignes, le montant de la remise, les frais, le sous-total et les taxes. Les mises en page compactes ne prennent en charge qu’une seule colonne.
    - **Volet Ticket de caisse** - Le volet Ticket de caisse contient les lignes de vente, les lignes de paiement et les informations de livraison pour les produits et services traités dans le POS. Vous pouvez spécifier les colonnes, les largeurs et le positionnement. Dans les mises en page compactes, vous pouvez également configurer des informations supplémentaires qui s’affichent sur la ligne sous la ligne principale.
    - **Carte du client** – La carte du client affiche les informations sur le client associé à la transaction actuelle. Vous pouvez configurer la carte du client pour masquer ou afficher des informations supplémentaires.
    - **Contrôle de tabulation** - Vous pouvez ajouter le contrôle de tabulation à une mise en page de l’écran, puis placer les autres contrôles tels que le pavé numérique, la carte du client ou les groupes de boutons sur celui-ci. Le contrôle de tabulation est un conteneur qui vous aide à afficher plus de contenu à l’écran. Le contrôle de tabulation est disponible uniquement pour les mises en page complètes.
    - **Image** - Vous pouvez utiliser le contrôle Image pour afficher le logo du magasin ou une autre image de marque dans l’écran **Transaction**. Le contrôle Image est disponible uniquement pour les mises en page complètes.
    - **Produits recommandés** – Si le contrôle Produits recommandés est configuré pour l’environnement, il affiche les suggestions de produits basées sur Machine Learning.
    - **Contrôle personnalisé** – Le contrôle personnalisé agit comme un espace réservé dans la mise en page de l’écran pour vous permettre de réserver de l’espace pour un contenu personnalisé. Le contrôle personnalisé est disponible uniquement pour les mises en page complètes.

### <a name="compact-layout-designer"></a>Concepteur de mise en page compacte

Comme le concepteur de mise en page complète, le concepteur de mise en page compacte vous permet de configurer la mise en page de l’écran du POS pour les téléphones et les petites tablettes. Toutefois, dans ce cas, la mise en page proprement dite est fixe. Vous pouvez configurer les contrôles de la mise en page en cliquant avec le bouton droit et en utilisant le menu contextuel. Toutefois, vous ne pouvez pas utiliser les opérations de glisser-déplacer pour le contenu supplémentaire.

![Concepteur de mise en page compacte.](../commerce/media/Compact-Layout-Designer.png)

### <a name="button-grid-designer"></a>Concepteur du groupe de boutons

Le concepteur du groupe de boutons vous permet de configurer les groupes de boutons qui peuvent être utilisés dans l’écran d’accueil et l’écran **Transaction** du POS pour les mises en page complètes et compactes. Le même groupe de boutons peut être utilisé dans les mises en page et les types de mise en page. Comme le concepteur de mise en page de l’écran, le groupe de boutons utilise la technologie de déploiement ClickOnce pour télécharger, installer et lancer la dernière version de l’application chaque fois que les utilisateurs y accèdent. Pensez à vérifier la configuration requise du navigateur pour ClickOnce. Certains navigateurs, tels que Google Chrome, requièrent des extensions.

![Concepteur du groupe de boutons.](../commerce/media/Button-Grid-Designer.png)

- **Bouton Nouveau** – Cliquez pour ajouter un nouveau bouton au groupe de boutons. Par défaut, les nouveaux boutons s’affichent dans le coin supérieur gauche de la grille. Toutefois, vous pouvez organiser les boutons en les déplaçant dans la mise en page.

    > [!IMPORTANT]
    > Le contenu du groupe de boutons peut se chevaucher. Lorsque vous organisez les boutons, veillez à ce qu’ils ne masquent pas d’autres boutons.

- **Nouvelle configuration** – Cliquez pour définir automatiquement une mise en page du groupe de boutons en spécifiant le nombre de boutons par ligne et colonne.
- **Propriétés du bouton** – Vous pouvez configurer les propriétés du bouton en cliquant avec le bouton droit sur le bouton et en utilisant le menu contextuel.

    > [!IMPORTANT]
    > Certains paramètres de la grille de boutons ne s’appliquent qu’à Enterprise POS, pas à Modern POS ni à Cloud POS.

    ![Propriétés du bouton du groupe de boutons.](../commerce/media/Button-grid-button-properties.png)

    - **Action** – Dans la liste des opérations POS applicables, sélectionnez l’opération concernée lorsque vous cliquez sur le bouton dans le POS.

        Pour la liste des opérations POS prises en charge, voir [Opérations PDV, en ligne et hors connexion](pos-operations.md).

    - **Paramètres d’action** – Certaines opérations du POS utilisent des paramètres supplémentaires lorsqu’elles sont appelées. Par exemple, pour l’opération Ajouter un produit, les utilisateurs peuvent spécifier le produit à ajouter.
    - **Texte du bouton** – Spécifiez le texte qui apparaît sur le bouton dans le POS.
    - **Masquer le texte du bouton** – Utilisez cette case à cocher pour masquer ou afficher le texte du bouton. Le texte du bouton est souvent masqué pour les petits boutons qui affichent uniquement une icône.
    - **Info-bulle** – Spécifiez le texte d’aide supplémentaire qui s’affiche lorsque les utilisateurs placent le curseur de la souris sur le bouton.
    - **Taille des colonnes/Taille des lignes** – Vous pouvez spécifier la hauteur et la largeur du bouton.

        ![Tailles des boutons du POS dans les lignes et les colonnes.](../commerce/media/POS-Button-Sizes-In-Rows-And-Columns.png)

    - **Police personnalisée** – Lorsque vous activez la case à cocher **Activer la police personnalisée pour POS**, vous pouvez spécifier une police autre que la police par défaut du système pour le POS.
    - **Thème personnalisé** – Par défaut, les boutons du POS utilisent la couleur d’accentuation du profil visuel. Lorsque vous activez la case à cocher **Utiliser le thème personnalisé**, vous pouvez spécifier des couleurs supplémentaires.

        > [!NOTE]
        > Modern POS et Cloud POS utilisent uniquement les valeurs **Couleur d’arrière-plan** et **Couleur de la police**.

    - **Image du bouton** – Les boutons peuvent inclure des images ou des icônes. Sélectionnez parmi les images disponibles spécifiées sous **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> PDV \> Images**.

![Exemple de groupe de boutons dans le POS.](../commerce/media/Example-Button-Grid-In-POS.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Installer le concepteur de mise en page du Point de vente au détail (PDV)](install-pos-layout-designer.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]