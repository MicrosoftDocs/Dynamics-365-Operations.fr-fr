---
title: Personnaliser l'expérience de l'utilisateur
description: Cette rubrique explique comment vous pouvez personnaliser l'application.
author: jasongre
manager: AnnBe
ms.date: 10/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 124609041163bbcaf1b86a6964fa3f56fcd8f755
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2019
ms.locfileid: "2658758"
---
# <a name="personalize-the-user-experience"></a>Personnaliser l'expérience de l'utilisateur

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique explique comment vous pouvez personnaliser l'application.

Il existe trois classes de base de personnalisations.

- Personnalisations qui sont effectuées sur une page de paramétrage. Le thème de couleur et le fuseau horaire sont des exemples.
- Personnalisations associées à l'utilisation de la page. Ces personnalisations sont appelées personnalisations *implicites*. Par exemple, le système garde un suivi de la largeur des colonnes de la grille si vous les ajustez, et de l'état développé ou réduit des organisateurs.
- Personnalisations effectuées par un utilisateur sur l'apparence d'une page en changeant la manière dont un élément apparaît ou agit sur cette page, souvent par le biais d'un mode interactif de personnalisation. Ces personnalisations sont appelées personnalisations *explicites*. Par exemple, l'utilisateur peut ajouter, masquer ou réorganiser les éléments sur la page.

Chaque personnalisation qu'un utilisateur effectue s'applique à cet utilisateur uniquement, indépendamment du type de personnalisation ou de la société avec laquelle l'utilisateur interagit actuellement. Les modifications qu'un utilisateur effectue sur une page n'affectent pas les autres utilisateurs du système.

## <a name="system-wide-options-for-the-current-user"></a>Options au niveau système pour l'utilisateur actuel

La page **Options utilisateur** contient plusieurs paramètres à l'échelle du système pour l'utilisateur actuel. Pour ouvrir la page **Options utilisateur**, sélectionnez le bouton **Paramètres** (symbole d'engrenage) dans la barre de navigation, puis sélectionnez **Options utilisateur**. La page **Options utilisateur** a quatre onglets contenant divers paramètres utilisateur :

- **Visuel** – Permet de sélectionner un thème de couleur et la taille par défaut des éléments sur les pages.
- **Préférences** – Permet de sélectionner des valeurs par défaut qui sont utilisées chaque fois que vous ouvrez le système. Ces valeurs sont notamment la société, la page initiale et le mode affichage/modification par défaut. (Le mode affichage/modification détermine si une page est verrouillée pour l'affichage ou ouverte pour la modification chaque fois que vous l'ouvrez). Cet onglet contient également des options pour la langue, le fuseau horaire et les formats de date/heure et de nombre. Enfin, cet onglet contient plusieurs préférences qui varient d'une version à l'autre.
- **Compte** – Permet d'ajuster votre nom d'utilisateur et d'autres options relatives au compte.
- **Workflow** – Permet de sélectionner les options associées au workflow.

Outre modifier vos paramètres utilisateur, vous pouvez également utiliser la page **Options de l'utilisateur** pour afficher et supprimer vos données et personnalisations d'utilisation. Sélectionnez seulement **Données d'utilisation** sur le volet Actions.

Lorsque vous utilisez l'application, la plupart de vos sélections sont stockées pour faciliter l'utilisation ultérieure du système. Sous l'onglet **Personnalisation**, vous pouvez afficher et gérer les modifications personnelles que vous avez apportées aux pages du système. Sous cet onglet, vous pouvez également réinitialiser les légendes de fonction (autrement dit, les fenêtres contextuelles qui introduisent de nouvelles fonctions du système). Vous êtes ensuite averti de nouveau sur les fonctions précédemment rencontrées.

> [!NOTE]
> Si la fonctionnalité [Vues enregistrées](saved-views.md) est activée, vous pouvez afficher et gérer vos personnalisations en sélectionnant **Personnalisation** dans le volet Actions de la page **Options utilisateur**.

## <a name="implicit-personalizations"></a>Personnalisations implicites

Les personnalisations implicites sont des personnalisations que vous effectuez simplement en interagissant avec des contrôles qui stockent leur état visible actuel.

- **Colonnes de la grille** – Vous pouvez régler la largeur d'une colonne dans la grille en sélectionnant la barre de calibrage à gauche ou à droite de l'en-tête de colonne et en la faisant glisser à gauche ou à droite jusqu'à la largeur souhaitée. L'application enregistre la largeur définie pour une colonne. Ensuite, la prochaine fois que vous ouvrez la page contenant cette grille, la colonne est redimensionnée selon cette largeur.
- **Organisateurs** – Certaines pages ont des sections extensibles appelées *Organisateurs*. L'application enregistre les informations sur les organisateurs que vous avez développés et réduits. Ensuite, la prochaine fois que vous ouvrez la page, les mêmes organisateurs sont développés ou réduits, selon votre dernière interaction avec la page. Dans certains cas, vous pouvez améliorer les performances du système en réduisant un organisateur, car l'application n'a pas besoin de récupérer les informations des organisateurs jusqu'à ce qu'ils soient développés. Comme expliqué plus loin dans cette rubrique, vous pouvez également modifier l'ordre des organisateurs sur une page.
- **Récapitulatifs** – Certaines pages ont un volet **Informations associées** qui affiche des informations en lecture seule associées à l'objet actuel de la page. Chaque section du volet **Informations associées** est appelée un *Récapitulatif*. Vous pouvez développer ou réduire le volet **Informations associées**, et vous pouvez également développer ou réduire des récapitulatifs individuels. L'application stocke ces préférences. Ensuite, la prochaine fois que vous ouvrez la page, le volet **Informations associées** et les récapitulatifs individuels sont développés ou réduits, selon votre dernière interaction avec la page. Dans certains cas, vous pouvez améliorer les performances du système en réduisant un Récapitulatif, car l'application n'a pas besoin de récupérer les informations des Récapitulatifs jusqu'à ce qu'ils soient développés.
- **Volets Actions** – Un *volet Actions* s'affiche en haut de la plupart des pages. Il contient des boutons pour la plupart des actions que vous pouvez exécuter sur la page actuelle. Ces boutons sont souvent organisés dans des onglets. Vous pouvez « épingler » l'ensemble du volet Actions ouvert, ou vous pouvez le faire réduire par défaut. Ensuite, la prochaine fois que vous ouvrez la page, le volet Actions est ouvert ou réduit, selon votre dernière interaction avec la page. Si vous avez épinglé le volet Actions ouvert, le dernier onglet que vous avez utilisé sera affiché.
- **Filtres rapides** – Un *Filtre rapide* s'affiche au-dessus de la plupart des grilles. Il vous permet de filtrer la grille, selon la colonne sélectionnée. L'application enregistre la colonne correspondant au filtre. La prochaine fois que vous ouvrirez la page contenant cette grille, la grille sera filtrée selon la même colonne. Toutefois, vous pouvez sélectionner une colonne différente selon laquelle filtrer la grille.
- **Filtres d'en-tête de colonne** – Lorsque vous filtrez une grille à l'aide des *filtres d'en-tête de colonne*, vous pouvez modifier l'opérateur de filtre si besoin pour rechercher les données souhaitées. Par exemple, vous pouvez modifier l'opérateur de **commence par** en **est exactement**. Chaque fois que vous utilisez un filtre d'en-tête de colonne et changez d'opérateur de filtre, l'application enregistre les modifications. Ensuite, la prochaine fois que vous filtrerez cette colonne, l'opérateur de filtre sera restauré.
- **Volet de navigation** – Vous pouvez ouvrir le *volet de navigation* en sélectionnant le bouton **Développer le volet de navigation** dans la partie supérieure gauche d'une page. (Ce bouton est parfois appelé _bouton **Menu**_, *hamburger*, *menu hamburger* ou *bouton hamburger*.) Vous pouvez épingler le volet de navigation ouvert, ou vous pouvez le garder réduit par défaut. Après avoir épinglé le volet de navigation ouvert, l'application le garde ouvert jusqu'à ce que vous le réduisiez.

## <a name="explicit-personalizations"></a>Personnalisations explicites

Chaque personne et société a sa propre perspective des données qui lui semblent les plus importantes, et les données dont elle n'a pas besoin pour mener à bien ses activités. Vous pouvez personnaliser le mode d'organisation et d'interaction avec vos informations. Vous pouvez également spécifier que certaines informations doivent être masquées. Ces fonctionnalités sont essentielles à une expérience personnelle et productive et sont des exemples de personnalisations explicites. Les personnalisations explicites sont des personnalisations que vous effectuez explicitement, car vous souhaitez modifier l'apparence ou le comportement d'un élément ou d'une page.

### <a name="shortcut-menu-options"></a>Options de menu contextuel

Les menus contextuels permettent de modifier explicitement une page pour mieux l'adapter à vos besoins ou à ceux de votre société. (Un menu contextuel est également appelé *menu par clic droit* ou *menu contextuel*.)

Certaines des modifications les plus courantes et importantes qui peuvent être apportées à une page sont disponibles directement en tant qu'options dans un menu contextuel. Par exemple, à compter de Platform update 17, si vous souhaitez ajouter ou masquer des colonnes dans une grille, cliquez avec le bouton droit sur un en-tête de colonne, puis sélectionnez **Ajouter des colonnes** ou **Masquer cette colonne**.

En outre, les types les plus classiques de personnalisations explicites sont disponibles en cliquant avec le bouton droit sur un élément et en sélectionnant **Personnaliser**. (Notez que tous les éléments sur la page ne peuvent pas être personnalisés). Lorsque vous utilisez cette méthode de personnalisation, la fenêtre des propriétés de l'élément s'affiche.

![Personnalisation des propriétés d'un élément](./media/personalization-element-properties.png)

Vous pouvez utiliser la fenêtre des propriétés pour personnaliser un élément comme suit :

- Modifiez l'étiquette de l'élément.
- Masquez l'élément afin qu'il ne soit pas affiché sur la page. Les données du champ ne sont pas supprimées ou modifiées. Les informations ne s'affichent plus sur la page.
- Ajoutez les informations dans la section récapitulative de l'organisateur (si l'élément se trouve dans un organisateur).
- Ignorez le champ, afin qu'il n'ait jamais le focus lorsque vous appuyez sur la touche tabulation dans la page.
- Empêchez la modification des données du champ (pour n'importe quel enregistrement).

La fenêtre des propriétés peut contenir d'autres fonctionnalités de personnalisation, selon l'élément. Par exemple, la fenêtre des propriétés d'une vignette vous permet de promouvoir cette vignette sur un tableau de bord, et la fenêtre des propriétés d'un tableau de bord vous permet de créer un espace de travail dans ce tableau de bord.

### <a name="the-personalization-toolbar"></a>Barre d'outils de personnalisation

Si vous souhaitez apporter plusieurs modifications à une page, ou des changements qui ne sont pas disponibles par le biais d'autres mécanismes (par ex. si vous souhaitez réorganiser des éléments), vous pouvez utiliser la barre d'outils **Personnalisation**. Pour ouvrir la barre d'outils **Personnalisation**, suivez l'une des étapes suivantes :

- Sélectionnez **Personnaliser cet écran** dans la fenêtre de la propriété d'un élément.
- Sélectionnez **Personnaliser cette page**, dans le groupe **Personnaliser** sous l'onglet **Options**, sur le volet Action de la page.
- Sélectionnez le bouton **Paramètres** (symbole d'engrenage) dans la barre de navigation, puis sélectionnez **Personnaliser**.

[![Barre d'outils de personnalisation](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navigation dans la page

Lorsque la barre d'outils **Personnalisation** est active, la page sous-jacente est en lecture seule (autrement dit, vous ne pouvez pas modifier les données), mais elle est toujours interactive. Spécifiquement, vous pouvez développer ou réduire le volet **Informations associées**, basculer entre les onglets, et développer ou réduire les sections, comme vous effectuez généralement ces actions sur la page. Pour appliquer une modification de personnalisation à une section ou un onglet réductible (par exemple masquer un organisateur), il vous suffit de sélectionner le bouton qui apparaît en regard de cette section ou de l'onglet lorsqu'il est activé au moyen du clavier ou lorsque vous passez le curseur dessus.

#### <a name="personalization-tools"></a>Outils de personnalisation

Les outils suivants sont disponibles dans la barre d'outils **Personnalisation** :

- Utilisez l'outil **Sélectionner** pour sélectionner et modifier les propriétés d'un élément. Pour utiliser cet outil, sélectionnez le bouton **Sélectionner** dans la barre d'outils, puis sélectionnez l'élément souhaité. La fenêtre des propriétés de l'élément s'affiche et vous pouvez modifier les propriétés de cet élément. Vous pouvez répéter le processus pour d'autres éléments qui peuvent être personnalisés sur la page. Notez que certaines propriétés de personnalisation ne soient pas disponibles dans certains scénarios. Par exemple, vous ne pouvez pas verrouiller un champ obligatoire.
- Utilisez l'outil **Masquer** pour masquer un élément sur la page. Pour utiliser cet outil, sélectionnez le bouton **Masquer** dans la barre d'outils, puis sélectionnez l'élément à masquer. Lorsque vous utilisez l'outil **Masquer**, tous les éléments actuellement masqués sont rendus visibles mais affichés dans un conteneur grisé. Vous pouvez ensuite rendre un élément visible en le sélectionnant. Pour afficher l'aspect de la page lorsque les éléments sont masqués, basculez vers un autre outil de personnalisation.

    Vous pouvez masquer les champs obligatoires et les sections contenant des champs obligatoires. Ainsi, vous pouvez créer une expérience simplifiée lorsque des champs obligatoires ne sont pas affichés lorsque leurs valeurs définies par défaut sont renseignées par la logique métier. Les champs obligatoires masqués deviendront temporairement visibles s'ils sont vides lorsqu'un utilisateur essaie d'enregistrer la page.

- Utilisez l'outil **Ajouter un champ** pour ajouter un champ à la page. Si vous utilisez cet outil, vous pouvez ajouter uniquement les champs qui font partie de la définition de page. Pour plus d'informations sur la création de champs qui ne font pas partie de la définition de page actuelle, voir [Champs personnalisés](user-defined-fields.md). Après avoir sélectionné l'outil **Ajouter un champ** sur la barre d'outils, vous devez d'abord sélectionner le groupe ou la zone où vous souhaitez ajouter un champ. Une boîte de dialogue affiche la liste des champs associés au groupe ou à la zone sélectionné. Dans la boîte de dialogue, sélectionnez un ou plusieurs champs à ajouter, puis sélectionnez **Insérer**. Pour supprimer un champ que vous avez précédemment ajouté, répétez le processus, mais effacez la sélection du champ dans la boîte de dialogue.
- Utilisez l'outil **Déplacer** pour déplacer un élément vers un autre emplacement dans le groupe actuel d'éléments. Notez que vous ne pouvez pas déplacer un élément en dehors de son groupe parent. Pour utiliser cet outil, sélectionnez le bouton **Déplacer** dans la barre d'outils, puis sélectionnez l'élément à déplacer. Lorsque vous sélectionnez un élément, l'application détermine les emplacements où l'élément est autorisé à être déplacé. Ces emplacements sont appelés des *zones de déplacement*. Lorsque vous faites glisser l'élément dans le groupe actuel, chaque zone de déplacement est indiquée par une ligne colorée et grasse en regard de la zone où l'élément peut être déplacé.
- Utilisez l'outil **Ignorer** pour supprimer un élément de la séquence de tabulation du clavier de la page. Lorsque vous sélectionnez le bouton **Ignorer** sur la barre d'outils, tous les éléments actuellement ignorés sont affichés dans un conteneur grisé. Vous pouvez supprimer ou ajouter de manière interactive des champs à la séquence de l'onglet.
- Utilisez l'outil **Afficher dans l'en-tête** pour faire apparaître un champ dans la section récapitulative de l'organisateur. Lorsque vous sélectionnez l'outil **Afficher dans l'en-tête** sur la barre d'outils, tous les champs sélectionnés comme champs récapitulatifs sont affichés dans un conteneur grisé. Vous pouvez en mode interactif ajouter des champs au récapitulatif de l'organisateur et en supprimer des champs en sélectionnant les champs.
- Utilisez l'outil **Verrouiller** pour marquer un élément comme modifiable ou non modifiable. Lorsque vous sélectionnez le bouton **Verrouiller** sur la barre d'outils, tous les éléments actuellement non modifiables sont affichés dans un conteneur grisé. Vous pouvez ensuite les rendre modifiables à nouveau. Notez que certains champs sont obligatoires et ne peuvent pas être rendus non modifiables. Un symbole de cadenas apparaît en regard de ces champs.
- Utilisez le bouton **Ajouter une PowerApp** pour incorporer une application créée à l'aide de Microsoft PowerApps dans la page. Pour plus d'informations sur l'incorporation d'une application PowerApps dans une page, voir [Incorporer PowerApps](embed-power-apps.md).
- Utilisez l'outil **Effacer** pour réinitialiser la page à son état installé par défaut. Toutes les personnalisations sur la page actuelle seront effacées. Il n'est pas possible d'annuler l'action. Par conséquent, n'utilisez cet outil que si vous êtes sûr de vouloir réinitialiser la page.
- Utilisez l'outil **Importer** pour charger une personnalisation à partir d'un fichier que vous ou un tiers avez précédemment créé. Lorsque vous importez des personnalisations pour une page, vous pouvez choisir si elles doivent être ajoutées ou si elles doivent remplacer toutes vos personnalisations existantes de la page. Il n'est pas possible d'annuler l'action. Par conséquent, après avoir importé les personnalisations, vous devez effacer ou annuler manuellement les modifications que vous ne souhaitez pas.
- Utilisez l'outil **Exporter** pour enregistrer vos personnalisations de la page dans un fichier. Vous pouvez ensuite partager vos personnalisations avec d'autres utilisateurs. Ces utilisateurs doivent simplement importer le fichier contenant vos personnalisations de la page.
- Sélectionnez le bouton **Fermer** pour fermer la barre d'outils **Personnalisation** et remettre la page dans son état interactif précédent.

Traditionnellement, lorsque la barre d'outils **Personnalisation** est utilisée, vos personnalisations prennent effet dès que vous les effectuez. Toutefois, si la fonctionnalité [Vues enregistrées](saved-views.md) est activée, vous devez explicitement enregistrer les personnalisations dans une vue que vous sélectionnez.

Dans certains cas, lorsque vous sélectionnez un outil, un symbole de cadenas s'affiche en regard d'un élément. Ce symbole indique que vous ne pouvez pas modifier les propriétés de l'élément qui sont associées à l'outil sélectionné, car les modifications de ces propriétés empêchent la page de fonctionner correctement.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Ajout d'une vignette, d'une liste ou d'un lien à un espace de travail

Pour certaines pages qui incluent des listes, la fonctionnalité de personnalisation **Ajouter à l'espace de travail** est disponible au groupe **Personnaliser** sur l'onglet **Options** du volet Actions. Cette fonctionnalité vous permet de transmettre des informations pertinentes de la liste actuelle vers un espace de travail spécifique. Les informations qui apparaissent dans l'espace de travail peuvent être basées sur la liste entière, ou une version filtrée et triée de la liste. Vous pouvez également spécifier si les informations s'affichent dans l'espace de travail sous forme de liste, de vignette récapitulative avec le nombre d'éléments dans la liste, ou encore de lien.

> [!NOTE]
> Si la fonctionnalité [Vues enregistrées](saved-views.md) est activée, le contenu que vous transférez à un espace de travail est directement associé à une vue. La requête de la vue est utilisée pour extraire des données de l'espace de travail, et la vignette ou le lien correspondant dans l'espace de travail ouvre la page dans cette vue, de sorte que la requête et les personnalisations de la vue soient appliquées à celle-ci.

[![Ajouter à l'espace de travail](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Pour ajouter une liste à un espace de travail, triez ou filtrez d'abord la liste sur la page pour afficher les informations comme vous souhaitez les voir apparaître dans l'espace de travail. (Si la fonctionnalité Vues enregistrées est activée, vous ne pouvez pas continuer tant que vous n'enregistrez pas de vue ayant ces conditions.) Sélectionnez **Ajouter à l'espace de travail** ensuite. Sélectionnez un espace de travail, puis, dans le champ **Présentation**, sélectionnez **Liste**. Après avoir sélectionné **Configurer**, une boîte de dialogue s'affiche pour vous permettre de sélectionner les colonnes qui doivent apparaître dans la liste de l'espace de travail. Vous pouvez également spécifier l'étiquette utilisée pour la liste de l'espace de travail.
- Pour ajouter une vignette à un espace de travail, filtrez d'abord la liste sur la page pour afficher les données qui doivent être récapitulées ou auxquelles vous souhaitez avoir un accès rapide. (Si la fonctionnalité Vues enregistrées est activée, vous ne pouvez pas continuer tant que vous n'enregistrez pas de vue ayant ces conditions.) Sélectionnez **Ajouter à l'espace de travail** ensuite. Sélectionnez un espace de travail, puis, dans le champ **Présentation**, sélectionnez **Vignette**. Après avoir sélectionné **Configurer**, une boîte de dialogue s'affiche pour vous permettre de spécifier l'étiquette qui doit être utilisée pour la vignette dans l'espace de travail. Vous pouvez également spécifier si la vignette doit afficher un nombre. Après la vignette ajoutée à l'espace de travail, vous pouvez la sélectionner pour ouvrir la page actuelle dans l'espace de travail. Vous pouvez ensuite afficher la liste filtrée associée à la vignette.
- Pour ajouter un lien à un espace de travail, filtrez d'abord la liste sur la page pour afficher les données qui vous intéressent. (Si la fonctionnalité Vues enregistrées est activée, vous ne pouvez pas continuer tant que vous n'enregistrez pas de vue ayant ces conditions.) Sélectionnez **Ajouter à l'espace de travail** ensuite. Sélectionnez un espace de travail, puis, dans le champ **Présentation**, sélectionnez **Lien**. Après avoir sélectionné **Configurer**, une boîte de dialogue s'affiche pour vous permettre de spécifier l'étiquette qui doit être utilisée pour le lien. Vous pouvez éventuellement spécifier une étiquette pour une nouvelle section contenant ce lien.

Après avoir ajouté une liste, une vignette ou un lien à un espace de travail, vous pouvez ouvrir cet espace de travail et réorganiser les éléments comme vous le souhaitez.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Ajout d'un résumé d'un espace de travail à un tableau de bord

Certains espaces de travail contiennent des vignettes de comptage (c'est-à-dire des vignettes numérotées) que vous pouvez également afficher sur votre tableau de bord. Dans un espace de travail, cliquez avec le bouton droit sur une vignette de comptage, sélectionnez **Personnaliser**, puis, dans la fenêtre des propriétés de la vignette, sélectionnez **Épingler au tableau de bord**. Ensuite, la prochaine fois que vous ouvrirez et actualiserez le tableau de bord sélectionné, le nombre s'affichera en dessous de la vignette de navigation pour cet espace de travail. Vous pouvez sélectionner ce nombre pour accéder directement aux données qu'il représente.

### <a name="personalizing-your-dashboard"></a>Personnalisation de votre tableau de bord

Le tableau de bord est souvent la première page que vous voyez lorsque vous ouvrez l'application. Vous pouvez personnaliser le tableau de bord pour afficher uniquement les vignettes de l'espace de travail que vous souhaitez voir. Vous pouvez également réorganiser les vignettes dans l'ordre d'affichage de votre choix, renommer les vignettes de navigation de votre espace de travail, ou ajouter une nouvelle vignette.

Pour personnaliser le tableau de bord, cliquez avec le bouton droit sur une vignette, puis sélectionnez **Personnaliser** pour ouvrir la fenêtre des propriétés de la vignette.

- Si vous souhaitez masquer ou renommer la vignette sélectionnée, vous pouvez effectuer cette modification directement dans la fenêtre des propriétés.
- Pour réorganiser les vignettes de l'espace de travail, dans la fenêtre des propriétés, sélectionnez **Personnaliser cet écran** pour ouvrir la barre d'outils **Personnalisation**. Vous pouvez ensuite utiliser l'outil **Déplacer** pour réorganiser les vignettes comme vous le souhaitez.
- Pour ajouter une vignette d'espace de travail, dans la fenêtre des propriétés, sélectionnez **Ajouter un espace de travail**. Une nouvelle vignette d'espace de travail est créée en bas du tableau de bord. Vous pouvez renommer cette nouvelle vignette d'espace de travail comme vous le souhaitez. Vous pouvez également ajouter des listes, des vignettes et des liens à l'espace de travail, comme décrit dans la section [Ajout de listes, de vignettes ou de liens aux espaces de travail](#adding-a-tile-list-or-link-to-a-workspace).

## <a name="administration-of-personalizations"></a>Administration des personnalisations

Après avoir personnalisé une page, vous pouvez partager vos personnalisations avec d'autres utilisateurs en exportant la page personnalisée. Vous pouvez ensuite demander aux autres utilisateurs d'ouvrir la page personnalisée et d'importer le fichier de personnalisation que vous avez créé. Sinon, vous pouvez attribuer vos personnalisations à un utilisateur disposant de privilèges d'administrateur. Cet utilisateur peut ensuite appliquer votre fichier de personnalisation à plusieurs utilisateurs en même temps.

Les utilisateurs ayant des privilèges d'administrateur peuvent également gérer les personnalisations pour d'autres utilisateurs sur la page **Personnalisation**.

Pour les clients n'ayant pas activé la fonctionnalité [Vues enregistrées](saved-views.md), cette page contient quatre onglets :

- **Appliquer** – Vous pouvez importer ou sélectionner une personnalisation pour un ou plusieurs utilisateurs. Pour appliquer une personnalisation à un ou plusieurs utilisateurs, sélectionnez d'abord un rôle et des utilisateurs disposant ce rôle. Sélectionnez ensuite une personnalisation existante à appliquer aux utilisateurs sélectionnés, ou importez un fichier de personnalisation. La personnalisation est validée et sera appliquée à tous les utilisateurs sélectionnés la prochaine fois qu'ils ouvriront la page sélectionnée.
- **Effacer** – Vous pouvez effacer toutes les personnalisations d'une page ou d'un espace de travail pour un ou plusieurs utilisateurs. Sélectionnez d'abord une page ou un espace de travail pour afficher la liste des utilisateurs qui l'ont personnalisé. Ensuite, sélectionnez les utilisateurs dont les personnalisations pour cette page ou cet espace de travail doivent être effacées. Enfin, sélectionnez **Effacer**. Toutes les personnalisations que les utilisateurs sélectionnés ont appliqué à la page ou à l'espace de travail sélectionné(e) sont supprimées. Cette action ne peut pas être annulée. Toutefois, si une personnalisation a été enregistrée pour la page ou l'espace de travail, cette personnalisation peut être réimportée.
- **Utilisateurs** : sélectionnez un utilisateur pour afficher une liste des pages personnalisées par celui-ci. Vous pouvez ensuite activer ou désactiver la possibilité que l'utilisateur sélectionné utilise les personnalisations pour des pages spécifiques ou pour l'ensemble du système. Vous pouvez également importer, exporter ou effacer une personnalisation pour l'utilisateur. En outre, vous pouvez réinitialiser les légendes de fonction pour l'utilisateur. Dans ce cas, si l'utilisateur a ignoré précédemment des fenêtres contextuelles qui introduisaient de nouvelles fonctionnalités, elles s'affichent de nouveau la prochaine fois que l'utilisateur rencontre ces fonctionnalités.
- **Système** : vous pouvez désactiver temporairement la personnalisation de l'ensemble des utilisateurs du système. Dans ce cas, toutes les personnalisations sont supprimées pour tous les utilisateurs, et toutes les pages sont rétablies à leur état par défaut. Si vous réactivez la personnalisation ultérieurement, toutes les personnalisations sont réappliquées. Vous pouvez également supprimer définitivement toutes les personnalisations pour l'ensemble des utilisateurs du système. Les personnalisations qui ont été supprimées ne peuvent être restaurées. Par conséquent, avant d'effectuer cette tâche, veillez à exporter les personnalisations que vous souhaitez utiliser ultérieurement.

Pour les clients n'ayant pas activé la fonctionnalité [Vues enregistrées](saved-views.md), la page **Personnalisation** contient cinq onglets :

- **Vues publiées** – Ces vues ont été publiées dans votre organisation. Pour modifier les utilisateurs qui sont ciblés par ces affichages, vous pouvez modifier les rôles de sécurité ou les entités juridiques associés à chaque vue. Vous pouvez également exporter ou supprimer une ou plusieurs vues publiées.
- **Vues non publiées** : ces vues sont des modèles de vues qui ont été importées dans votre système mais n'ont pas encore été publiées. Vous pouvez publier, exporter ou supprimer ces vues.
- **Vues personnelles** : ces vues ont été créées par les utilisateurs dans le système. Vous pouvez publier une vue personnelle dans l'organisation, ou copier une ou plusieurs de ces vues pour d'autres utilisateurs. Vous pouvez également exporter ou supprimer ces vues au besoin.
- **Utilisateurs** : sélectionnez un utilisateur pour afficher une liste des pages personnalisées par celui-ci. Vous pouvez ensuite activer ou désactiver la possibilité que l'utilisateur sélectionné utilise les personnalisations pour des pages spécifiques ou pour l'ensemble du système. Vous pouvez également importer, exporter ou effacer une personnalisation pour l'utilisateur. En outre, vous pouvez réinitialiser les légendes de fonction pour l'utilisateur. Dans ce cas, si l'utilisateur a ignoré précédemment des fenêtres contextuelles qui introduisaient de nouvelles fonctionnalités, elles s'affichent de nouveau la prochaine fois que l'utilisateur rencontre ces fonctionnalités.
- **Système** : vous pouvez désactiver temporairement la personnalisation de l'ensemble des utilisateurs du système. Dans ce cas, toutes les personnalisations sont supprimées pour tous les utilisateurs, et toutes les pages sont rétablies à leur état par défaut. Si vous réactivez la personnalisation ultérieurement, toutes les personnalisations sont réappliquées. Vous pouvez également supprimer définitivement toutes les personnalisations pour l'ensemble des utilisateurs du système. Les personnalisations qui ont été supprimées ne peuvent être restaurées. Par conséquent, avant d'effectuer cette tâche, veillez à exporter les personnalisations que vous souhaitez utiliser ultérieurement.

Les utilisateurs qui ont accès à la page **Personnalisation** peuvent également importer des vues personnelles ou des modèles de vues à l'aide du bouton **Importer les vues** du volet Actions.

## <a name="personalizing-inventory-dimensions"></a>Personnalisation des dimensions de stock

Lorsque vous personnalisez le paramétrage des dimensions de stock sur une page, tenez compte des paramètres qui ont été créés à l'aide de l'option **Afficher les dimensions**. Par exemple, vous utilisez la personnalisation pour masquer une colonne de la dimension de stock Numéro de lot, mais la colonne s'affiche à la prochaine ouverture de la page. Ce comportement se produit car les paramètres **Affichage des dimensions** contrôlent les colonnes de la dimension de stock affichées. Les paramètres **Affichage des dimensions** s'appliquent à toutes les pages et remplacent tout paramétrage personnalisé des champs de la dimension de stock sur des pages individuelles.

Par conséquent, dans l'exemple précédent, si vous ne souhaitez pas afficher la colonne de la dimension de stock Numéro de lot sur une page, vous devez désactiver cette dimension dans le cadre de l'option **Afficher les dimensions** pour cette page.
