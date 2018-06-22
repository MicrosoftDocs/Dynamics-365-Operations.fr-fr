---
title: "Personnaliser l'expérience de l'utilisateur"
description: Cette rubrique explique comment vous pouvez personnaliser Microsoft Dynamics 365 for Finance and Operations.
author: TLeforMicrosoft
manager: AnnBe
ms.date: 05/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 862bbf4d1d9b0dc2b6dc418ee766ed4dedef49fe
ms.openlocfilehash: 8ad5bd607f08d4e0b266d86a96a0b7f3e352c4cd
ms.contentlocale: fr-fr
ms.lasthandoff: 05/24/2018

---

# <a name="personalize-the-user-experience"></a>Personnaliser l'expérience de l'utilisateur

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment vous pouvez personnaliser Microsoft Dynamics 365 for Finance and Operations.

Il existe trois classes de base de personnalisations dans Finance and Operations. 
- Personnalisations effectuées sur une page de paramétrage. Le thème de couleur et le fuseau horaire sont des exemples.
- Personnalisations associées à l'utilisation d'une page, appelées personnalisations *implicites*. Par exemple, Finance and Operations garde un suivi de la largeur des colonnes de la grille si vous les ajustez, et de l'état développé ou réduit des organisateurs. 
- Personnalisations effectuées par un utilisateur pour modifier l'apparence d'une page en changeant la manière dont un élément apparaît ou agit sur cette page, souvent par le biais d'un mode interactif de personnalisation. Ces personnalisations sont appelées personnalisations *explicites*. Par exemple, l'utilisateur peut ajouter, masquer ou réorganiser les éléments sur la page.

Chaque personnalisation qu'un utilisateur effectue dans Finance and Operations s'applique à cet utilisateur uniquement, indépendamment du type de personnalisation ou de la société avec laquelle l'utilisateur interagit actuellement. Les modifications qu'un utilisateur effectue sur une page n'affectent pas les autres utilisateurs du système.

## <a name="system-wide-options-for-the-current-user"></a>Options au niveau système pour l'utilisateur actuel
La page **Options utilisateur** contient plusieurs paramètres à l'échelle du système pour l'utilisateur actuel. Pour ouvrir la page **Options utilisateur**, sélectionnez le menu **Paramètres** (symbole d'engrenage) dans la barre de navigation, puis sélectionnez **Options utilisateur**. La page **Options utilisateur** a quatre onglets contenant divers paramètres utilisateur :

- **Visuel** – Permet de sélectionner un thème de couleur et la taille par défaut des éléments sur les pages.
- **Préférences** – Permet de sélectionner des valeurs par défaut qui sont utilisées chaque fois que vous ouvrez Finance and Operations. Ces valeurs sont notamment la société, la page initiale et le mode affichage/modification par défaut. (Le mode affichage/modification détermine si une page est verrouillée pour l'affichage ou ouverte pour la modification chaque fois que vous l'ouvrez). Cet onglet contient également des options pour la langue, le fuseau horaire et le format de date/heure et de nombre. Enfin, cet onglet contient plusieurs préférences qui varient d'une version à l'autre.
- **Compte** – Permet d'ajuster votre nom d'utilisateur et d'autres options relatives au compte.
- **Workflow** – Permet de sélectionner les options associées au workflow.

## <a name="implicit-personalizations"></a>Personnalisations implicites
Les personnalisations implicites sont des personnalisations que vous effectuez simplement en interagissant avec des contrôles qui conservent leur état visible actuel.

- **Colonnes de la grille** – Vous pouvez régler la largeur d'une colonne dans la grille en sélectionnant la barre de calibrage à gauche ou à droite de l'en-tête de colonne et en la faisant glisser à gauche ou à droite jusqu'à la largeur souhaitée. Finance and Operations enregistre la largeur définie pour une colonne. Il redimensionne ensuite la colonne à cette largeur chaque fois que vous ouvrez la page contenant cette grille.
- **Organisateurs** – Certaines pages ont des sections extensibles appelées *Organisateurs*. Finance and Operations enregistre les informations sur les organisateurs que vous avez développés et réduits. Chaque fois que vous revenez à la page, les mêmes organisateurs sont développés ou réduits, selon votre dernière interaction avec la page. Dans certains cas, vous pouvez améliorer les performances du système en réduisant un organisateur, car Finance and Operations n'a pas besoin de récupérer les informations de cet organisateur jusqu'à ce qu'il soit développé. Comme expliqué plus loin dans cette rubrique, vous pouvez également modifier l'ordre des organisateurs sur une page.
- **Récapitulatifs** – Certaines pages ont une section appelée *volet Récapitulatif*. Ce volet contient des informations en lecture seule associées au sujet actuel de la page. Chaque section du volet Récapitulatif est appelée un *Récapitulatif*. Vous pouvez masquer ou afficher l'ensemble du volet Récapitulatif, et vous pouvez également développer ou réduire des récapitulatifs individuels. Finance and Operations enregistre vos préférences. Chaque fois que vous revenez à la page, l'état du volet Récapitulatif et des récapitulatifs individuels est restauré, selon votre dernière interaction avec la page. Dans certains cas, vous pouvez améliorer les performances du système en réduisant un récapitulatif, car Finance and Operations n'a pas besoin de récupérer les informations de ce récapitulatif jusqu'à ce qu'il soit développé.
- **Volets Actions** – Un *volet Actions* s'affiche en haut de la plupart des pages. Il contient des boutons pour la plupart des actions que vous pouvez exécuter sur la page actuelle. Ces boutons sont souvent organisés dans des onglets. Vous pouvez épingler ouvert l'ensemble du volet Actions, ou vous pouvez le faire réduire par défaut. La prochaine fois que vous ouvrirez la page, Finance and Operations restaurera l'état épinglé du volet Actions. Si le volet Actions est épinglé ouvert, Finance and Operations affiche également le dernier onglet d'actions utilisé.
- **Filtres rapides** – Un *Filtre rapide* s'affiche au-dessus de la plupart des grilles. Il vous permet de filtrer la grille, selon la colonne sélectionnée. Finance and Operations enregistre la colonne correspondant au filtre. La prochaine fois que vous ouvrirez la page contenant cette grille, la grille sera filtrée selon la même colonne. Toutefois, vous pouvez filtrer la grille selon une colonne différente.
- **Filtres d'en-tête de colonne** – Lorsque vous filtrez une grille à l'aide des *Filtres d'en-tête de colonne*, vous pouvez modifier l'opérateur de filtre si besoin pour rechercher les données souhaitées. Par exemple, vous pouvez modifier l'opérateur de **commence par** en **est exactement**. Chaque fois que vous utilisez un filtre d'en-tête de colonne et modifiez l'opérateur de filtre, Finance and Operations enregistre les modifications. Il restaurera l'opérateur de filtre la prochaine fois que vous filtrerez cette colonne.
- **Volet de navigation** – Vous pouvez ouvrir le *Volet de navigation* en sélectionnant le bouton **Menu** dans le volet gauche d'une page. (Le bouton **Menu** est parfois appelé *hamburger*, *menu hamburger* ou *bouton hamburger*). Vous pouvez épingler le volet de navigation ouvert, ou vous pouvez le garder réduit par défaut. Après avoir épinglé le volet de navigation ouvert, Finance and Operations le garde ouvert jusqu'à ce que vous le réduisiez.

## <a name="explicit-personalizations"></a>Personnalisations explicites
Chaque personne et société a sa propre perspective des données qui lui semblent les plus importantes, ou les données dont elle n'a pas besoin pour mener à bien ses activités. Dans Finance and Operations, vous pouvez personnaliser le mode d'organisation et d'interaction avec vos informations. Vous pouvez également spécifier que certaines informations doivent être masquées. Ces fonctionnalités sont essentielles à une expérience personnelle et productive et sont des exemples de personnalisations explicites. Les personnalisations explicites sont des personnalisations que vous effectuez explicitement, afin de modifier l'apparence ou le comportement d'un élément ou d'une page.

### <a name="shortcut-menu-options"></a>Options de menu contextuel
Les menus contextuels permettent de modifier explicitement une page pour l'adapter à vos besoins ou à ceux de votre société. (Un menu contextuel est également appelé *menu par clic droit* ou *menu contextuel*.)

Certaines des modifications les plus courantes et importantes qui peuvent être apportées à une page sont disponibles directement en tant qu'options dans un menu contextuel. Par exemple, pour ajouter ou masquer des colonnes dans une grille, cliquez avec le bouton droit sur un en-tête de colonne de la grille, puis sélectionnez **Ajouter des colonnes** ou **Masquer cette colonne**.

En outre, les types les plus classiques de personnalisations explicites sont disponibles en cliquant avec le bouton droit sur un élément et en sélectionnant **Personnaliser**. (Notez que tous les éléments sur la page ne peuvent pas être personnalisés). Lorsque vous utilisez cette méthode de personnalisation, la fenêtre des propriétés de l'élément s'affiche.

[![Personnalisation des propriétés d’un élément](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg)

Vous pouvez utiliser la fenêtre des propriétés pour personnaliser un élément comme suit :

- Modifiez l'étiquette de l'élément.
- Masquez l'élément afin qu'il ne soit pas affiché sur la page. Les données du champ ne sont pas supprimées ou modifiées. Les informations ne s'affichent plus sur la page.
- Ajoutez les informations dans la section récapitulative de l'organisateur (si l'élément se trouve dans un organisateur).
- Ignorez le champ lorsque vous appuyez sur Tab pour naviguer entre les champs sur la page.
- Empêchez la modification des données du champ (pour un enregistrement).

La fenêtre des propriétés peut contenir d'autres fonctionnalités de personnalisation, selon l'élément. Par exemple, la fenêtre des propriétés d'une vignette vous permet de promouvoir cette vignette sur un tableau de bord, et la fenêtre des propriétés d'un tableau de bord vous permet de créer un espace de travail dans ce tableau de bord.

### <a name="the-personalization-toolbar"></a>Barre d'outils de personnalisation
Lorsque vous souhaitez déplacer ou masquer des éléments, ou encore apporter plusieurs modifications à une page, vous pouvez utiliser la barre d'outils **Personnalisation**. Pour ouvrir la barre d'outils **Personnalisation**, sélectionnez **Personnaliser cet écran** dans la fenêtre des propriétés d'un élément. Vous pouvez également sélectionner **Personnaliser cet écran** dans le groupe **Personnaliser** de l'onglet **Options** du volet Actions de chaque page.

[![Barre d'outils de personnalisation](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

Lorsque la barre d'outils **Personnalisation** est ouverte, la page n'est pas interactive. Par conséquent, vous ne pouvez pas entrer des données, ni développer ou réduire les sections. Vous pouvez seulement modifier les éléments qui composent la page.

Les outils suivants sont disponibles dans la barre d'outils **Personnalisation** :

- Utilisez l'outil **Sélectionner** pour sélectionner et modifier les propriétés d'un élément. Sélectionnez l'outil **Sélectionner**, puis sélectionnez l'élément dont vous souhaitez modifier les propriétés. Lorsque vous sélectionnez un élément, la fenêtre des propriétés de l'élément s'affiche pour vous permettre de modifier les propriétés de cet élément. Vous pouvez répéter le processus pour d'autres éléments qui peuvent être personnalisés sur cette page. Toutefois, en raison du mode d'utilisation de certains éléments, Finance and Operations ne vous permet pas modifier certaines de leurs propriétés. Par conséquent, si vous sélectionnez un élément, il se peut que certaines de ses propriétés ne puissent pas être modifiées. Par exemple, vous ne pouvez pas masquer un champ obligatoire.
- Utilisez l'outil **Déplacer** pour déplacer un élément vers un autre emplacement au sein du groupe actuel d'éléments. (Vous ne pouvez pas déplacer un élément en dehors de son groupe parent). Sélectionnez l'outil **Déplacer**, puis sélectionnez l'élément à déplacer. Lorsque vous sélectionnez un élément, Finance and Operations analyse la page pour déterminer où l'élément peut être déplacé. Il crée ensuite une série de « zones de largage ». Lorsque vous faites glisser l'élément dans le groupe actuel, chaque « zone de largage » est indiquée par une ligne colorée et grasse en regard de la zone où l'élément peut être déplacé.
- Utilisez l'outil **Masquer** pour masquer un élément sur la page. Sélectionnez l'outil **Masquer**, puis sélectionnez l'élément à masquer. Lorsque vous sélectionnez l'outil **Masquer**, tous les éléments actuellement masqués sont rendus visibles et affichés dans un conteneur grisé. Vous pouvez ensuite les afficher. Sélectionnez l'outil **Sélectionner** pour voir la manière dont la page s'affiche lorsque les éléments sélectionnés sont masqués.
- Utilisez l'outil **Récapitulatif** pour faire apparaître un élément dans la section récapitulative de l'organisateur. L'outil Récapitulatif s'applique uniquement aux champs contenus dans une section de l'organisateur. Lorsque vous sélectionnez l'outil **Récapitulatif**, tous les champs sélectionnés comme champs récapitulatifs sont affichés dans un conteneur grisé. Vous pouvez en mode interactif ajouter des champs au récapitulatif de l'organisateur et supprimer des champs du récapitulatif de l'organisateur en sélectionnant les champs.
- Utilisez l'outil **Ignorer** pour supprimer un élément de la séquence de tabulation du clavier de la page. Lorsque vous sélectionnez l'outil **Ignorer**, tous les éléments actuellement ignorés sont affichés dans un conteneur grisé. Vous pouvez ensuite les réintégrer dans la séquence de tabulation.
- Utilisez l'outil **Modifier** pour marquer un élément comme modifiable ou non modifiable. Lorsque vous sélectionnez l'outil **Modifier**, tous les éléments actuellement non modifiables sont affichés dans un conteneur grisé. Vous pouvez ensuite les rendre modifiables à nouveau. Notez que certains champs sont obligatoires et ne peuvent pas être rendus non modifiables. Un symbole de cadenas apparaît en regard de ces champs.
- Utilisez le bouton **Insérer** pour afficher la liste des éléments pouvant être insérés sur une page.

    - Sélectionnez l'outil **Champ** sous **Insérer** pour ajouter un champ à la page. Lorsque vous utilisez l'outil **Champ**, vous pouvez ajouter uniquement les champs qui font partie de la définition de page, mais qui ne sont pas actuellement affichés sur la page. Pour plus d'informations sur la création de champs qui ne font pas partie de la définition de page actuelle, voir [Champs personnalisés](user-defined-fields.md). Après avoir sélectionné l'outil **Champ**, vous devez d'abord sélectionner le groupe ou la zone où vous souhaitez ajouter un champ. Une boîte de dialogue affiche la liste des champs associés au groupe ou à la zone sélectionné. Dans la boîte de dialogue, sélectionnez un ou plusieurs champs à ajouter, puis sélectionnez **Insérer**. Pour supprimer un champ que vous avez précédemment ajouté, répétez le processus, mais effacez la sélection du champ dans la boîte de dialogue.
    - Sélectionnez l'outil **PowerApp** sous **Insérer** pour incorporer une application créée à l'aide de Microsoft PowerApps dans la page. Pour plus d'informations sur l'incorporation d'une application PowerApps dans une page, voir [Incorporer PowerApps](embed-power-apps.md).

- Sélectionnez le bouton **Gérer** pour afficher la liste des options de gestion associées à toutes les personnalisations de la page actuelle.

    - Sélectionnez **Effacer** pour réinitialiser la page à son état installé par défaut. Toutes les personnalisations de la page actuelle sont effacées. Il n'est pas possible d'annuler l'action. Par conséquent, n'utilisez cette option que si vous êtes sûr de vouloir réinitialiser la page.
    - Sélectionnez **Importer** pour charger une personnalisation à partir d'un fichier que vous ou un tiers avez précédemment créé pour la page. Toutes vos personnalisations actuelles de la page sont remplacées par les personnalisations du fichier sélectionné.
    - Sélectionnez **Exporter** pour enregistrer vos personnalisations de la page dans un fichier. Vous pouvez partager vos personnalisations avec d'autres utilisateurs. Ces utilisateurs doivent simplement importer le fichier contenant vos personnalisations de la page.

- Sélectionnez le bouton **Fermer** pour fermer la barre d'outils **Personnalisation** et remettre la page dans son état interactif précédent.

Lorsque la barre d'outils **Personnalisation** est utilisée, les opérations d'enregistrement sont implicites. Vos personnalisations prennent effet dès que vous les effectuez, et il n'est pas nécessaire de cliquer sur le bouton **Enregistrer**. Dans certains cas, lorsque vous sélectionnez un outil, un symbole de cadenas s'affiche en regard d'un élément. Ce symbole indique que vous ne pouvez pas modifier les propriétés de l'élément qui sont associées à l'outil sélectionné, car les modifications de ces propriétés empêchent la page de fonctionner correctement.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Ajout d'une vignette, d'une liste ou d'un lien à un espace de travail
Pour certaines pages contenant des listes, une fonctionnalité de personnalisation supplémentaire est disponible. Le bouton **Ajouter à l'espace de travail** dans le groupe **Personnaliser** de l'onglet **Options** du volet Actions vous permet d'afficher les informations de la liste actuelle dans un espace de travail spécifique. Vous pouvez afficher une vue filtrée et triée des informations de l'espace de travail, ou vous pouvez afficher la vue par défaut. Vous pouvez également spécifier si les informations s'affichent dans l'espace de travail sous forme de liste, de vignette récapitulative avec le nombre d'éléments dans la liste, ou encore de lien.

[![Ajouter à l'espace de travail](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Pour ajouter une liste à un espace de travail, triez ou filtrez d'abord la liste sur la page pour afficher les informations comme vous souhaitez les voir apparaître dans l'espace de travail. Sélectionnez ensuite **Ajouter à l'espace de travail**. Sélectionnez un espace de travail, puis, dans le champ **Présentation**, sélectionnez **Liste**. Après avoir sélectionné **Configurer**, une boîte de dialogue s'affiche pour vous permettre de sélectionner les colonnes qui doivent apparaître dans la liste de l'espace de travail. Vous pouvez également spécifier l'étiquette à utiliser pour la liste de l'espace de travail.
- Pour ajouter une vignette à un espace de travail, filtrez d'abord la liste sur la page pour afficher les données que vous souhaitez récapituler ou auxquelles vous souhaitez avoir un accès rapide. Sélectionnez ensuite **Ajouter à l'espace de travail**. Sélectionnez un espace de travail, puis, dans le champ **Présentation**, sélectionnez **Vignette**. Après avoir sélectionné **Configurer**, une boîte de dialogue s'affiche pour vous permettre de spécifier l'étiquette à utiliser pour la vignette dans l'espace de travail. Vous pouvez également spécifier si la vignette doit afficher un nombre. Une fois la vignette ajoutée à l'espace de travail, vous pouvez la sélectionner pour ouvrir la page actuelle à partir de l'espace de travail et afficher la liste filtrée associée à la vignette.
- Pour ajouter un lien à un espace de travail, filtrez d'abord la liste sur la page pour afficher les données qui vous intéressent. Sélectionnez ensuite **Ajouter à l'espace de travail**. Sélectionnez un espace de travail, puis, dans le champ **Présentation**, sélectionnez **Lien**. Après avoir sélectionné **Configurer**, une boîte de dialogue s'affiche pour vous permettre de spécifier l'étiquette à utiliser pour le lien. Vous pouvez éventuellement spécifier une étiquette pour une nouvelle section contenant ce lien.

Une fois que votre liste, vignette ou lien a été ajouté à un espace de travail, vous pouvez ouvrir cet espace de travail et réorganiser les éléments comme vous le souhaitez.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Ajout d'un résumé d'un espace de travail à un tableau de bord
Certains espaces de travail contiennent des vignettes de comptage (c'est-à-dire des vignettes numérotées) que vous pouvez également afficher sur votre tableau de bord. Dans un espace de travail, cliquez avec le bouton droit sur une vignette de comptage, puis sélectionnez **Personnaliser**. Ensuite, dans la fenêtre des propriétés de la vignette, sélectionnez **Épingler au tableau de bord**. La prochaine fois que vous ouvrirez (et actualiserez) le tableau de bord sélectionné, le nombre s'affichera en dessous de la vignette de navigation pour cet espace de travail. Vous pouvez sélectionner ce nombre pour accéder directement aux données qu'il représente.

### <a name="personalizing-your-dashboard"></a>Personnalisation de votre tableau de bord
Le tableau de bord est souvent la première page que vous voyez lorsque vous ouvrez Finance and Operations. Vous pouvez personnaliser le tableau de bord pour afficher uniquement les vignettes de l'espace de travail que vous souhaitez voir. Vous pouvez également réorganiser les vignettes dans l'ordre de votre choix, renommer les vignettes de navigation de votre espace de travail, ou ajouter une vignette entièrement nouvelle.

Pour personnaliser le tableau de bord, cliquez avec le bouton droit sur une vignette, puis sélectionnez **Personnaliser** pour ouvrir la fenêtre des propriétés de la vignette.

- Si vous souhaitez masquer ou renommer la vignette sélectionnée, vous pouvez effectuer cette modification directement dans la fenêtre des propriétés.
- Pour réorganiser les vignettes de l'espace de travail, dans la fenêtre des propriétés, sélectionnez **Personnaliser cet écran** pour ouvrir la barre d'outils **Personnalisation**. Vous pouvez ensuite utiliser l'outil **Déplacer** pour réorganiser les vignettes comme vous le souhaitez.
- Pour créer une vignette d'espace de travail, dans la fenêtre des propriétés, sélectionnez **Ajouter un espace de travail**. Une nouvelle vignette d'espace de travail est créée en bas du tableau de bord. Vous pouvez renommer cette nouvelle vignette d'espace de travail comme vous le souhaitez. Vous pouvez également ajouter des listes, des vignettes et des liens à l'espace de travail, comme décrit dans la section [Ajout de listes, de vignettes ou de liens aux espaces de travail](personalize-user-experience.md#adding-a-tile-list-or-link-to-a-workspace).

## <a name="administration-of-personalization"></a>Administration de la personnalisation
Après avoir personnalisé une page, vous pouvez partager vos personnalisations avec d'autres utilisateurs en exportant la page personnalisée. Vous pouvez ensuite demander aux autres utilisateurs d'ouvrir la page personnalisée et d'importer le fichier de personnalisation que vous avez créé. Sinon, vous pouvez attribuer votre personnalisation à un utilisateur disposant de privilèges d'administrateur. Cet utilisateur peut ensuite appliquer votre fichier de personnalisation à plusieurs utilisateurs en même temps.

Les utilisateurs ayant des droits d'administrateur peuvent également gérer les personnalisations pour d'autres utilisateurs sur la page **Personnalisation**. Cette page contient quatre onglets :

- **Appliquer** – Vous pouvez importer ou sélectionner une personnalisation pour un ou plusieurs utilisateurs. Pour appliquer une personnalisation à un ou plusieurs utilisateurs, sélectionnez d'abord un rôle et des utilisateurs disposant ce rôle. Sélectionnez ensuite une personnalisation existante à appliquer aux utilisateurs sélectionnés, ou importez un fichier de personnalisation. La personnalisation est validée et sera appliquée à tous les utilisateurs sélectionnés la prochaine fois qu'ils ouvriront la page sélectionnée.
- **Effacer** – Vous pouvez effacer toutes les personnalisations d'une page ou d'un espace de travail pour un ou plusieurs utilisateurs. Sélectionnez d'abord une page ou un espace de travail pour afficher la liste des utilisateurs qui l'ont personnalisé. Ensuite, sélectionnez les utilisateurs dont les personnalisations pour cette page ou cet espace de travail doivent être effacées. Enfin, sélectionnez **Effacer**. Toutes les personnalisations que les utilisateurs sélectionnés ont appliqué à la page ou à l'espace de travail sélectionné(e) sont supprimées. Cette action ne peut pas être annulée. Toutefois, si une personnalisation a été enregistrée pour la page ou l'espace de travail, cette personnalisation peut être réimportée.
- **Gérer par utilisateur** – Sélectionnez un utilisateur pour afficher la liste des pages personnalisées par celui-ci. Vous pouvez ensuite activer ou désactiver la possibilité que l'utilisateur sélectionné utilise les personnalisations pour des pages spécifiques ou pour l'ensemble du système. Vous pouvez également importer, exporter ou effacer une personnalisation pour l'utilisateur sélectionné.
- **Système** – Vous pouvez désactiver temporairement toutes les personnalisations pour l'ensemble des utilisateurs du système. Dans ce cas, les personnalisations sont supprimées. Toutes les pages sont simplement réinitialisées à leur état par défaut pour tous les utilisateurs. Si vous réactivez la personnalisation ultérieurement, toutes les personnalisations seront réappliquées. Vous pouvez également supprimer définitivement toutes les personnalisations pour l'ensemble des utilisateurs du système. Il n'existe aucun moyen de récupérer des personnalisations qui ont été supprimées. Par conséquent, avant d'effectuer cette tâche, veillez à exporter les personnalisations que vous souhaitez utiliser ultérieurement.

## <a name="personalization-of-inventory-dimensions"></a>Personnalisation des dimensions de stock

Lorsque vous personnalisez le paramétrage des dimensions de stock sur une page, tenez compte des paramètres qui ont été créés à l'aide de l'option **Afficher les dimensions**. Par exemple, vous utilisez la personnalisation pour masquer une colonne de la dimension de stock Numéro de lot, mais la colonne s'affiche à la prochaine ouverture de la page. Ce comportement se produit car les paramètres **Affichage des dimensions** contrôlent les colonnes de la dimension de stock affichées.

Les paramètres **Affichage des dimensions** s'appliquent à toutes les pages et remplacent tout paramétrage personnalisé des champs de la dimension de stock sur des pages individuelles.

Par conséquent, dans l'exemple précédent, si vous ne souhaitez pas afficher la colonne de la dimension de stock Numéro de lot, vous devez désactiver cette dimension dans le cadre de l'option **Afficher les dimensions** pour la table. Cette modification s'applique non seulement à une page spécifique, mais aussi à l'ensemble des pages.

