---
title: "Personnaliser l'expérience de l'utilisateur"
description: Cette rubrique explique comment vous pouvez personnaliser Microsoft Dynamics 365 for Finance and Operations.
author: RobinARH
manager: AnnBe
ms.date: 08/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dbc80ff756a5286a98489f1f1403959d9b18ebe6
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="personalize-the-user-experience"></a>Personnaliser l'expérience de l'utilisateur

[!include[banner](../includes/banner.md)]


Cette rubrique explique comment vous pouvez personnaliser Microsoft Dynamics 365 for Finance and Operations.

Il existe plusieurs types de personnalisations dans Microsoft Dynamics 365 for Finance and Operations. Certaines personnalisations sont des sélections effectuées dans la liste des options dans une page de paramétrage. Certaines personnalisations sont implicites, par exemple, Finance and Operations garde un suivi des largeurs des colonnes de la grille si vous les ajustez, et l'état développé/réduit des organisateurs. D'autres personnalisations sont explicites. Pour les personnalisations explicites, vous entrez en mode interactif de personnalisation et modifiez l'apparence de la page en gérant directement la manière dont les éléments apparaissent ou agissent sur la page. 

Toutes les personnalisations, de n'importe quel type, qu'un utilisateur effectue dans Finance and Operations sont pour cet utilisateur uniquement, indépendamment de la société avec laquelle l'utilisateur interagit. Les modifications qu'un utilisateur effectue sur une page n'affectent pas les autres utilisateurs dans le système.

## <a name="systemwide-options-for-the-current-user"></a>Options au niveau système pour l'utilisateur actuel
Dans la barre de navigation, vous trouverez une image d'engrenages appelée bouton de menu **Paramètres**. Si vous ouvrez le menu **Paramètres**, un certain nombre de choix apparaissent. Si vous sélectionnez **Options**, la page **Options** de l'utilisateur s'ouvre. Quatre onglets d'option sont disponibles : 

-   **Visuel** : permet de choisir un thème de couleur et la taille par défaut des éléments dans vos pages.
-   **Préférences** : vous permet de choisir des valeurs par défaut pour chaque ouverture de Finance and Operations, notamment la société, la page initiale, et le mode affichage/modification par défaut (qui détermine si une page est verrouillée pour l'affichage ou ouverte pour la modification à chaque fois que vous l'ouvrez). Vous trouverez également la langue, le fuseau horaire, la date, l'heure, et les options de format de numéro. Enfin, cette page contient de nombreuses préférences diverses qui varieront d'une version à l'autre.
-   **Compte** : permet de fournir votre ID utilisateur et d'autres options relatives au compte.
-   **Workflow** : permet de sélectionner des options relatives au workflow.

## <a name="implicit-personalizations"></a>Personnalisations implicites
Les personnalisations implicites sont les personnalisations que vous effectuez simplement en utilisant certains contrôles qui conservent leur état actuel visible. 

**Colonnes de la grille** : vous pouvez régler la largeur d'une colonne dans la liste en sélectionnant la barre de calibrage à gauche ou à droite de l'en-tête de colonne et en la glissant à gauche ou à droite jusqu'à la largeur souhaitée. Finance and Operations enregistre la largeur que vous voulez et affiche cette colonne avec cette largeur à chaque fois que vous ouvrez la page de cette liste. 

**Organisateurs** : certaines pages ont des sections extensibles appelées Organisateurs. Finance and Operations enregistre les organisateurs que vous avez développés, ainsi que les organisateurs que vous avez réduits. Chaque fois que vous revenez à la page, ces mêmes organisateurs sont développés ou réduits comme la dernière fois que vous les avez utilisés. Dans cet article, nous expliquerons comment modifier l'ordre des sections de l'organisateur. Dans certains cas, la réduction d'un organisateur peut améliorer les performances car Finance and Operations n'a pas besoin de récupérer les informations de cet organisateur jusqu'à ce qu'il soit développé. 

**Récapitulatif** : certaines pages ont une section appelée volet Récapitulatif. Ce volet contient des informations en lecture seule associées au sujet actuel de la page. Chaque section dans le volet Récapitulatif est appelée un Récapitulatif. Vous pouvez développer ou réduire un Récapitulatif et Finance and Operations enregistrera votre préférence. Dans certains cas, la réduction d'un Récapitulatif peut améliorer les performances car Finance and Operations n'a pas besoin de récupérer les informations de ce Récapitulatif jusqu'à ce qu'il soit développé.

## <a name="explicit-personalizations-using-the-personalization-toolbar"></a>Personnalisations explicites à l'aide de la barre d'outils de personnalisation
Chaque personne et société a un point de vue différent sur les données qui sont les plus importantes pour elle, ou sur les données qui ne sont pas nécessaires pour son travail. La capacité de personnaliser la manière de classer vos informations, d'interagir avec elles, ou même de les masquer est essentiel pour faire de Finance and Operations un outil personnel et productif. 

Les personnalisations explicites sont les personnalisations que vous effectuez explicitement afin de modifier l'apparence ou le comportement d'un élément ou d'une page, en choisissant un menu de personnalisation. Le type le plus classique de personnalisation explicite est celui dans lequel vous cliquez avec le bouton droit sur un élément et sélectionnez **Personnaliser**. (Note que tous les éléments sur la page peuvent être personnalisés.) Lorsque vous sélectionnez cette méthode de personnalisation, vous verrez la fenêtre de la propriété de l'élément. 

[![Personnalisation des propriétés d’un élément](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg) 

Vous personnaliserez un élément sur la page de cette manière si vous souhaitez simplement modifier le nom de l'élément, masquer l'élément pour qu'il ne s'affiche dans la page (cela ne modifie aucune donnée, mais simplement ne vous montre plus les informations), inclure les informations dans la section de synthèse de l'organisateur (si l'élément est dans un organisateur), ignorer le champ en tabulant, ou faire en sorte que les données ne puissent pas être modifiées par le marquage « Ne pas modifier ». 

Lorsque vous voulez déplacer ou masquer les éléments ou effectuer plusieurs modifications, vous pouvez utiliser la barre d'outils de personnalisation, disponible dans la fenêtre de propriété des éléments en choisissant **Personnaliser cet écran**. La barre d'outils de personnalisation est également disponible dans le volet Actions de l'écran, sous le groupe Personnaliser de l'onglet **Options**. Sélectionnez **Personnaliser cet écran** et vous pourrez voir la barre d'outils de personnalisation. 

[![Barre d'outils Personnalisation](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

La barre d'outils de personnalisation contient de nombreuses actions de personnalisation. Choisissez l'outil **Sélectionner** lorsque vous souhaitez sélectionner et modifier les propriétés de plusieurs éléments, un par un. D'abord, cliquez sur l'outil Sélectionner, puis cliquez sur l'élément dont vous voulez modifier les propriétés. Lorsque vous sélectionnez un élément, la fenêtre de propriété de l'élément s'ouvre et vous pouvez modifier les propriétés de cet élément. Vous pouvez répéter le processus pour d'autres éléments dans l'écran qui sont personnalisables. Dans certains cas, vous sélectionnerez un élément et verrez que certaines propriétés ne sont pas modifiables. Cela signifie que selon la manière dont l'élément actuel est utilisé, Finance and Operations ne peut vous permettre pas modifier cette propriété. Par exemple, vous ne pouvez pas masquer un champ obligatoire. 

Choisissez l'outil **Déplacer** lorsque vous souhaitez sélectionner et déplacer un élément dans un autre emplacement au sein du groupe actuel d'éléments. (Vous ne pouvez pas déplacer un élément en dehors de son groupe parent). D'abord, cliquez sur l'outil Déplacer, puis cliquez sur l'élément que vous voulez déplacer. Lorsque vous cliquez sur l'élément que vous souhaitez déplacer, Finance and Operations analyse l'écran pour savoir où cet élément peut être déplacé et crée une série de « zones de largage » indiquées par une ligne colorée et grasse en regard de la région où l'élément peut être déposé pendant que vous faites glisser l'élément dans le groupe actuel. 

Choisissez l'outil **Masquer** pour sélectionner et masquer un élément. Pour masquer un élément, choisissez simplement l'outil Masquer et cliquez sur l'élément que vous voulez masquer. Lorsque vous sélectionnez l'outil Masquer, tous les éléments actuellement masqués sont rendus visibles et affichés dans un conteneur grisé afin de pouvoir choisir l'élément à afficher. Choisissez l'outil Sélectionner pour voir la manière dont la page s'affichera avec les éléments sélectionnés masqués. Choisissez l'outil **Récapitulatif** lorsque vous souhaitez qu'un champ numérique ou de chaîne s'affiche dans la zone récapitulative de l'organisateur. L'outil Récapitulatif s'applique uniquement aux champs contenus dans une section de l'organisateur. Lorsque vous sélectionnez l'outil Récapitulatif, Finance and Operations affiche tous les champs qui ont été sélectionnés comme champs récapitulatifs en les entourant d'un conteneur grisé. Vous pouvez en mode interactif ajouter et supprimer des champs d'un récapitulatif de l'organisateur en cliquant sur le champ. 

Choisissez l'outil **Ignorer** pour supprimer un élément de la séquence de tabulation du clavier de la page. Lorsque vous sélectionnez l'outil Ignorer, tous les éléments actuellement ignorés seront affichés dans un conteneur grisé afin de pouvoir les choisir de nouveau pour les intégrer à la séquence de tabulation en sélectionnant un élément ignoré. 

Choisissez l'outil **Modifier** si vous souhaitez marquer un élément comme Modifiable ou Non modifiable. Lorsque vous sélectionnez l'outil Modifier, tous les éléments actuellement non modifiables sont affichés dans un conteneur grisé afin de pouvoir choisir l'élément à rendre modifiable. Notez que certains champs sont obligatoires et ne peuvent pas être rendus non modifiables. Ces champs apparaissent accompagnés d'une icône de cadenas. 

Choisissez l'outil **Ajouter** pour ajouter un champ à la page. Avec l'outil ajouter, vous ne pouvez pas créer de champ, mais vous pouvez ajouter les champs qui font partie de la définition de page actuelle, mais non affiché dans la page. Lorsque vous sélectionnez l'outil Ajouter, vous devez d'abord sélectionner le groupe ou la zone où vous voulez ajouter un champ. Une boîte de dialogue affiche la liste des champs liés à la section sélectionnée. Dans cette boîte de dialogue, vous pouvez sélectionner un ou plusieurs champs à ajouter et cliquer sur Insérer. Si vous souhaitez plus tard supprimer un champ que vous avez précédemment ajouté, répétez le processus, mais effacez simplement le champ que vous avez précédemment ajouté. 

Choisissez le bouton **Gérer** pour afficher une liste des options de gestion relatives à toutes les personnalisations de la page actuelle. 

Choisissez **Effacer** pour réinitialiser la page dans son état installé par défaut. Toutes les personnalisations sur la page actuelle seront effacées. Il n'existe pas d'action annuler, donc n'utilisez cette option que si vous êtes certain que vous souhaitiez réinitialiser la page. 

Choisissez **Importer** pour utiliser une personnalisation à partir d'un fichier de personnalisation que vous ou un tiers avez précédemment créé pour cette page. L'importation d'une personnalisation effacera toutes les personnalisations que vous avez effectuées dans la page entière et utilisera à la place toutes les personnalisations du fichier sélectionné. Si vous souhaitez enregistrer ou partager une personnalisation, sélectionnez l'option **Exporter** pour enregistrer les personnalisations vers un fichier. 

Choisissez le bouton **Fermer** pour fermer la barre d'outils et remettre la page dans son état interactif précédent. 

Avec la barre d'outils de personnalisation, l'enregistrement est implicite. Vos personnalisations prennent effet immédiatement à mesure que vous les faites et il n'y a pas besoin de cliquer sur un bouton **Enregistrer**. Dans certains cas, vous verrez une icône de cadenas en regard d'un élément lorsque vous sélectionnez un outil. Cela signifie que pour que la page fonctionne correctement, vous ne pouvez pas modifier les propriétés liées à l'outil sélectionné. Lorsque la barre d'outils de personnalisation est ouverte, la page devient non-interactive. Vous ne pouvez pas entrer des données ni développer ou réduire les sections.

## <a name="explicit-personalization-adding-a-tile-or-list-to-a-workspace"></a>Personnalisation explicite : ajout d'une vignette ou d'une liste à un espace de travail
Certaines pages avec des listes disposeront d'une fonctionnalité de personnalisation supplémentaire accessible dans le volet Actions, sous le groupe Personnaliser de l'onglet Options. Sélectionnez **Ajouter à l'espace de travail** pour ouvrir la liste déroulante qui indique la capacité à afficher les informations dans la liste actuelle (filtrée et triée ou par défaut) d'un espace de travail sous la forme d'une liste ou d'une vignette de synthèse (indiquant le nombre d'articles dans la liste). 

[![Ajouter à l'espace de travail](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png) 

Pour ajouter une liste à un espace de travail, triez ou filtrez d'abord la liste avec les informations que vous voulez afficher dans votre espace de travail, puis sélectionnez la boîte de dialogue Ajouter à l'espace de travail. Ensuite, sélectionnez l'espace de travail désiré et sélectionnez **Liste** dans la liste déroulante de présentation. Lorsque vous sélectionnez **Liste** une boîte de dialogue s'ouvre vous permettant de choisir les colonnes que vous voudriez afficher dans la liste, et le nom de la liste tel qu'il apparaîtra dans l'espace de travail. 

Pour ajouter une vignette à un espace de travail, filtrez d'abord la liste pour représenter les données que vous souhaitez récapituler (ou auxquelles vous souhaitez avoir un accès rapide). Cliquez ensuite sur la boîte de dialogue Ajouter à l'espace de travail. Ensuite, sélectionnez l'espace de travail désiré et sélectionnez **Vignette** dans la liste déroulante de présentation. Lorsque vous sélectionnez **Vignette**, une boîte de dialogue s'ouvre pour vous permettre de fournir un nom de vignette et de décider si la vignette indique un compte. Lorsqu'elle est placée dans un espace de travail, la vignette vous permet d'ouvrir la page actuelle de l'espace de travail, et d'afficher la liste des informations relatives à la vignette. 

Lorsque votre liste ou vignette est ajoutée à un espace de travail, vous pouvez ensuite ouvrir cet espace de travail et trier à nouveau la liste ou la vignette au sein du groupe où elle a été placée.

## <a name="explicit-personalization-adding-a-summary-from-a-workspace-to-a-dashboard"></a>Personnalisation explicite : ajout d'un récapitulatif provenant d'un espace de travail à un tableau de bord
Certains espaces de travail contiennent des vignettes de comptage (vignettes numérotées) que vous voudriez également afficher sur votre tableau de bord. Dans un espace de travail, cliquez avec le bouton droit sur une vignette de comptage et la sélectionnez **Personnaliser**. Sélectionnez **Épingler au tableau de bord**. La prochaine fois que vous accéderez (et actualiserez) le tableau de bord sélectionné, vous verrez ce comptage en dessous de la vignette de navigation de cet espace de travail dans le tableau de bord.

## <a name="explicit-personalization-personalizing-your-dashboard"></a>Personnalisation explicite : personnalisation de votre tableau de bord
Le tableau de bord est souvent la première page que vous voyez lorsque vous ouvrez Finance and Operations. Vous pouvez personnaliser le tableau de bord pour renommer les vignettes de votre espace de travail, pour afficher uniquement les vignettes que vous voulez voir, renommer les vignettes ou réorganiser les vignettes dans l'ordre que vous préfèrerez. Pour personnaliser le tableau de bord, sélectionnez une vignette et cliquez avec le bouton droit pour ouvrir un menu contextuel. Dans le menu contextuel, sélectionnez **Personnaliser**. Si vous voulez masquer, renommer ou ignorer la vignette sélectionnée, vous pouvez effectuer cette modification directement dans la fenêtre de propriété qui est apparue. Si vous voulez réorganiser des vignettes, sélectionnez **Personnaliser cet écran** dans la fenêtre de propriété pour ouvrir la barre d'outils de personnalisation. Vous pouvez ensuite utiliser l'outil Déplacer pour réorganiser les vignettes.

## <a name="administration-of-personalization"></a>Administration de la personnalisation
Après avoir personnalisé une page, vous pouvez partager vos personnalisations avec d'autres utilisateurs en exportant la page personnalisée. Vous pouvez ensuite demander aux autres utilisateurs d'accéder à la page spécifiée et d'importer le fichier de personnalisation que vous avez créé.

Les utilisateurs ayant des droits d'administrateur peuvent également gérer les personnalisations pour d'autres utilisateurs sur la page **Personnalisation**. Cette page contient quatre onglets : 

- **Système** - Vous pouvez désactiver temporairement ou arrêter toutes les personnalisations dans le système. Dans ce cas, vous ne supprimez pas les personnalisations. Au lieu de cela, vous réinitialisez juste toutes les pages à leur état par défaut. Si vous réautorisez la personnalisation par la suite, toutes les personnalisations seront réappliquées aux pages de chaque utilisateur. Vous pouvez également supprimer toutes les personnalisations de tous les utilisateurs. Notez que lorsque vous supprimez les personnalisations, il n'existe aucun moyen de les réactiver automatiquement à partir du système. Par conséquent, avant d'effectuer cette étape, veillez à exporter toutes les personnalisations que vous souhaiterez peut-être importer ultérieurement.
- **Utilisateurs** – Vous pouvez spécifier si chaque utilisateur peut appliquer la personnalisation implicite ou la personnalisation explicite. Vous pouvez également spécifier si chaque utilisateur peut exécuter la personnalisation implicite ou explicite dans une page spécifique. Enfin, vous pouvez importer, exporter ou supprimer une personnalisation pour chaque utilisateur.
- **Importer** – Vous pouvez importer une personnalisation pour un ou plusieurs utilisateurs. Utilisez cet onglet après avoir créé une personnalisation sur une page ou un espace de travail, puis exporté cette personnalisation en tant que fichier de personnalisation. Pour importer votre fichier de personnalisation et l'appliquer à un ou plusieurs utilisateurs, sélectionnez les utilisateurs individuels dans la liste de tous les utilisateurs, ou filtrez-les par rôle spécifique, puis sélectionnez les utilisateurs dans ce rôle. Après avoir sélectionné les utilisateurs qui utiliseront votre personnalisation, cliquez sur **Importer**, puis sélectionnez votre fichier de personnalisation. La personnalisation est validée et appliquée à tous les utilisateurs sélectionnés la prochaine fois qu'il ouvre la page sélectionnée.
- **Effacer** – Vous pouvez effacer les personnalisations de page ou d'espace de travail pour un ou plusieurs utilisateurs. Premièrement, sélectionnez la page ou l'espace de travail dont les personnalisations doivent être effacées. Ensuite, sélectionnez les utilisateurs individuels dans la liste de tous les utilisateurs, ou filtrez-les par rôle spécifique, puis sélectionnez les utilisateurs de ce rôle. Après avoir sélectionné une page ou l'espace de travail et des utilisateurs, cliquez sur **Effacer**. Toutes les personnalisations que les utilisateurs sélectionnés ont appliqué à la page ou à l'espace de travail sélectionné(e) sont effacées. Cette action ne peut pas être annulée. Toutefois, si la page ou l'espace de travail a une personnalisation enregistrée, cette personnalisation peut être réimportée.

## <a name="personalization-of-inventory-dimensions"></a>Personnalisation des dimensions de stock

Lorsque vous personnalisez le paramétrage des dimensions de stock sur une page, tenez compte des paramètres qui ont été créés à l'aide de l'option **Afficher les dimensions**. Par exemple, si vous utilisez la personnalisation pour masquer une colonne pour la dimension de stock Numéro de lot et que la colonne s'affiche à la prochaine ouverture de la page, il se peut que les paramètres d'affichage de la dimension contrôlent l'affichage des colonnes de la dimension de stock. 

Les paramètres d'affichage de la dimension s'appliquent à toutes les pages et ces paramètres remplacent tout paramétrage personnalisé des champs de la dimension de stock sur des pages individuelles. 

Pour l'exemple avec la dimension de stock Numéro de lot, cette dimension doit être désactivée dans le cadre de l'option **Afficher les dimensions** pour que la table n'affiche pas cette colonne. Cette modification ne s'applique pas à une page spécifique mais à l'ensemble des pages.

