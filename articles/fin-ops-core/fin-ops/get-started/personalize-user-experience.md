---
title: Personnaliser l’expérience de l’utilisateur
description: Cette rubrique explique comment vous pouvez personnaliser l’application.
author: jasongre
ms.date: 01/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 840a68d506664043c9affb67e801429e0594f0bd
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075420"
---
# <a name="personalize-the-user-experience"></a>Personnaliser l’expérience de l’utilisateur

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Cette rubrique explique comment personnaliser l’application et couvre les sujets suivants : 

- **Options à l’échelle du système** – Ces options de personnalisation sont paramétrer sur une page de configuration et sont disponibles pour tous les utilisateurs. Le thème de couleur et le fuseau horaire sont des exemples. 
- **Accès de personnalisation restreint** – À ce niveau d’accès, les actions des utilisateurs associées à l’utilisation typique de la page sont automatiquement enregistrées par l’application et restaurées la prochaine fois que vous visitez la page. Par exemple, l’application stocke la largeur des colonnes de la grille si vous les ajustez, et de l’état développé ou réduit des raccourcis. 
- **Accès à la personnalisation complète** – À ce niveau d’accès, les utilisateurs ont accès à toutes les fonctionnalités de personnalisation de l’application. En particulier, ils ont accès à la barre d’outils **Personnalisation**. 
- **Partager des personnalisations** – Les utilisateurs disposant d’un accès complet à la personnalisation peuvent exporter leurs personnalisations de page et les partager avec d’autres utilisateurs.
- **Administration des personnalisations** – Les utilisateurs privilégiés peuvent accéder à la page d’administration **Personnalisation** pour gérer toutes les personnalisations au niveau de l’organisation. 

## <a name="system-wide-options-for-the-current-user"></a>Options au niveau système pour l’utilisateur actuel

La page **Options utilisateur** contient plusieurs paramètres à l’échelle du système pour l’utilisateur actuel. Ces options sont disponibles pour tous les utilisateurs, même les utilisateurs qui n’ont pas eu accès à la personnalisation. Pour ouvrir la page **Options utilisateur**, sélectionnez le bouton **Paramètres** dans la barre de navigation, puis sélectionnez **Options utilisateur**. La page **Options utilisateur** a quatre onglets contenant divers paramètres utilisateur :

- **Visuel** – Permet de sélectionner un thème de couleur et la taille par défaut des éléments sur les pages.
- **Préférences** – Permet de sélectionner des valeurs par défaut qui sont utilisées chaque fois que vous ouvrez le système. Ces valeurs sont notamment la société par défaut, la page initiale et le mode affichage/modification par défaut. (Le mode affichage/modification détermine si une page est verrouillée pour l’affichage ou ouverte pour la modification chaque fois que vous l’ouvrez). Cet onglet contient également des options pour la langue, le fuseau horaire et les formats de date/heure et de nombre. Enfin, cet onglet contient plusieurs préférences qui varient d’une version à l’autre.
- **Compte** – Affichez ou ajustez votre nom d’utilisateur et d’autres options relatives au compte.
- **Workflow** – Permet de sélectionner les options associées au workflow.

Outre modifier vos paramètres utilisateur, vous pouvez également afficher et supprimer vos données et personnalisations d’utilisation à partir de la page **Options utilisateur**. Pour voir vos données d’utilisation, sélectionnez **Données d’utilisation** sur le volet Actions. Sous l’onglet **Personnalisation**, vous pouvez afficher et gérer les modifications personnelles que vous avez apportées aux pages du système. Sous cet onglet, vous pouvez également réinitialiser les légendes de fonction (autrement dit, les fenêtres contextuelles qui introduisent de nouvelles fonctions du système). Vous êtes ensuite averti de nouveau sur les fonctions précédemment rencontrées.

> [!NOTE]
> Si la fonctionnalité [Vues enregistrées](saved-views.md) est activée, vous pouvez afficher et gérer vos personnalisations en sélectionnant **Personnalisation** dans le volet Actions de la page **Options utilisateur**.

## <a name="restricted-personalization-access-formerly-implicit-personalizations"></a>Accès de personnalisation restreint (anciennement personnalisations implicites)

Au niveau **Accès de personnalisation restreint**, les actions des utilisateurs associées à l’utilisation typique de la page sont automatiquement enregistrées par l’application et restaurées la prochaine fois que vous visitez la page. Aucune action d’enregistrement explicite n’est requise. 

Voici une liste des actions qui relèvent d’une utilisation de page typique et sont couvertes par un accès de personnalisation restreint : 

- **Largeurs des colonnes de la grille** : réglez la largeur d’une colonne dans une grille en sélectionnant la barre de dimensionnement située à gauche ou à droite de l’en-tête de la colonne, et en la faisant glisser vers la gauche ou vers la droite jusqu’à atteindre la largeur souhaitée. L’application enregistre la largeur définie pour une colonne. Ensuite, la prochaine fois que vous ouvrez cette page, la colonne sera redimensionnée selon cette largeur.
- **Pied de page de la grille et totaux des colonne** – *(Uniquement disponible si la nouvelle commande de grille est activée)* Vous pouvez décider si un total doit s’afficher en bas des colonnes numériques dans une grille et si le pied de page de la grille doit être visible. L’application ces préférences et les applique à la prochaine ouverture de la page. Pour plus d’informations, voir [Capacités de grille](grid-capabilities.md). 
- **Raccourcis** – Certaines pages ont des sections extensibles appelées *Raccourcis*. L’application enregistre les informations sur les raccourcis que vous avez développés ou réduits. La prochaine fois que vous ouvrez la page, les mêmes raccourcis sont développés ou réduits, selon votre dernière interaction avec la page. Dans certains cas, vous pouvez améliorer les performances du système en réduisant un raccourci, car l’application n’a pas besoin de récupérer les informations des raccourcis jusqu’à ce qu’ils soient développés. Comme expliqué plus loin dans cette rubrique, vous pouvez également modifier l’ordre des raccourcis sur une page.
- **Récapitulatifs** – Certaines pages ont un volet **Informations associées** qui affiche des informations en lecture seule associées à l’objet actuel de la page. Chaque section du volet **Informations associées** est appelée un *Récapitulatif*. Vous pouvez développer ou réduire le volet **Informations associées**, et vous pouvez également développer ou réduire des récapitulatifs individuels. L’application stocke ces préférences. La prochaine fois que vous ouvrez la page, le volet **Informations associées** et les récapitulatifs individuels sont développés ou réduits, selon votre dernière interaction avec la page. Dans certains cas, vous pouvez améliorer les performances du système en réduisant un volet **Informations associées** ou un Récapitulatif, car l’application n’a pas besoin de récupérer les informations des Récapitulatifs jusqu’à ce qu’ils soient développés.
- **Volets Actions** – Un *volet Actions* s’affiche en haut de la plupart des pages. Il contient des boutons pour la plupart des actions que vous pouvez exécuter sur la page actuelle. Ces boutons sont souvent organisés dans des onglets. Vous pouvez *épingler* l’ensemble du volet Actions ouvert, ou vous pouvez le faire réduire par défaut. La prochaine fois que vous ouvrez la page, le volet Actions est ouvert ou réduit, selon votre dernière interaction avec la page. Si vous avez épinglé le volet Actions ouvert, le dernier onglet que vous avez utilisé sera affiché.
- **Filtres rapides** – Un *Filtre rapide* s’affiche au-dessus de la plupart des grilles. Il vous permet de filtrer la grille, selon la seule colonne sélectionnée. L’application enregistre la colonne correspondant au filtre. La prochaine fois que vous ouvrirez la page, la grille utilisera cette même colonne pour le filtrage par défaut. Toutefois, vous pouvez toujours sélectionner une colonne différente selon laquelle filtrer la grille.
- **Filtres d’en-tête de colonne** – Lorsque vous filtrez une grille à l’aide des *filtres d’en-tête de colonne*, vous pouvez modifier l’opérateur de filtre si besoin pour rechercher les données souhaitées. Par exemple, vous pouvez modifier l’opérateur de **commence par** en **est exactement**. Chaque fois que vous utilisez un filtre d’en-tête de colonne et changez d’opérateur de filtre, l’application enregistre les modifications. Ensuite, la prochaine fois que vous filtrerez cette colonne, l’opérateur de filtre sera restauré.
- **Volet de navigation** – Vous pouvez ouvrir le *volet de navigation* en sélectionnant le bouton **Développer le volet de navigation** dans la partie supérieure gauche d’une page. (Ce bouton est parfois appelé _bouton **Menu**_, *hamburger*, *menu hamburger* ou *bouton hamburger*.) Vous pouvez épingler le volet de navigation ouvert, ou vous pouvez le garder réduit par défaut. Après avoir épinglé le volet de navigation ouvert, l’application le garde ouvert jusqu’à ce que vous le réduisiez.

## <a name="full-personalization-access-formerly-explicit-personalizations"></a>Accès de personnalisation complet (anciennement personnalisations explicites)

Au niveau d’accès **Accès à la personnalisation complète**, les utilisateurs ont accès à toutes les fonctionnalités de personnalisation de l’application. Étant donné que différentes personnes et entreprises ont des besoins différents lorsqu’elles interagissent avec l’application, en particulier en termes de champs utilisés, la personnalisation fournit des outils qui permettent aux utilisateurs et aux organisations d’adapter la façon dont les informations sont classées et interagies dans l’application. Ces fonctionnalités sont essentielles pour fournir des expériences simplifiées et optimisées dans l’application, adaptées à vous et à votre organisation. 

Si la fonctionnalité [Vues enregistrées](saved-views.md) est activée, un enregistrement explicite est requis pour conserver ces modifications dans l’expérience utilisateur pour une vue spécifique. Quand la fonctionnalité **Vues enregistrées** est désactivée, ces modifications sont automatiquement enregistrées.

Les sections suivantes couvrent l’étendue des capacités de personnalisation disponibles pour les utilisateurs au niveau **accès complet à la personnalisation**. Voici quelques-unes de ces capacités :

- Options de menu contextuel
- Barre d’outils **Personnalisation**
- Ajout de vignettes, de listes et de liens aux espaces de travail
- Ajout d’un résumé d’un espace de travail à un tableau de bord
- Personnalisation de tableau de bord

### <a name="shortcut-menu-options"></a>Options de menu contextuel

Les menus contextuels permettent de modifier l’interface d’une page pour mieux l’adapter à vos besoins ou à ceux de votre organisation. (Un menu contextuel est également appelé *menu par clic droit* ou un *menu contextuel*.)

Certaines des modifications les plus courantes et importantes qui peuvent être apportées à une page sont disponibles directement en tant qu’options dans un menu contextuel. Par exemple, si vous souhaitez ajouter ou masquer des colonnes dans une grille, cliquez avec le bouton droit sur un en-tête de colonne, puis sélectionnez **Insérer une colonne** ou **Masquer cette colonne**.

En outre, les types les plus classiques de personnalisations sont disponibles en cliquant avec le bouton droit sur un élément et en sélectionnant **Personnaliser**. (Notez que tous les éléments sur la page ne peuvent pas être personnalisés). Lorsque vous utilisez cette méthode de personnalisation, la *fenêtre des propriétés* de l’élément s’affiche.

![Personnalisation des propriétés d’un élément.](./media/cli-element-property-window.png)

Vous pouvez utiliser la fenêtre des propriétés pour personnaliser un élément comme suit :

- Modifiez l’étiquette de l’élément.
- Masquez l’élément afin qu’il ne soit pas affiché sur la page. Les données du champ ne sont pas supprimées ou modifiées. Les informations ne s’affichent simplement plus sur la page.
- Ajoutez les informations dans la section récapitulative du raccourci (si l’élément se trouve dans un raccourci).
- Ignorez le champ, afin qu’il n’ait jamais le focus lorsque vous appuyez sur la touche tabulation dans la page.
- Empêchez la modification des données du champ (pour n’importe quel enregistrement).
- Désignez un champ qui sera requis pour la saisie des données. Si aucune valeur n’a été entrée dans ce champ, il apparaît avec une bordure rouge et un astérisque pour indiquer cet état. Cette option n’est disponible qu’à partir de la version 10.0.11 lorsque les fonctionnalités [Vues enregistrées](saved-views.md) et **Désigner des champs selon les besoins à l’aide de la personnalisation** sont activées.

La fenêtre des propriétés peut contenir d’autres fonctionnalités de personnalisation, selon l’élément. Par exemple, la fenêtre des propriétés d’une vignette vous permet de promouvoir cette vignette sur un tableau de bord, et les fenêtres des propriétés pour les éléments du tableau de bord par défaut vous permet de créer un espace de travail dans un nouveau tableau de bord personnalisé.

### <a name="personalization-toolbar"></a>Barre d’outils de personnalisation

Si vous souhaitez apporter plusieurs modifications à une page, ou des changements qui ne sont pas disponibles par le biais d’autres mécanismes (par ex. si vous souhaitez réorganiser des éléments), vous pouvez utiliser la barre d’outils **Personnalisation**. Pour ouvrir la barre d’outils **Personnalisation**, suivez l’une des étapes suivantes :

- Sélectionner **Ctrl+Maj+P** à partir de n’importe quel élément de la page.
- Sélectionnez **Personnaliser cette page** dans la fenêtre des propriétés d’un élément.
- Sélectionnez **Personnaliser cette page**, dans le groupe **Personnaliser** sous l’onglet **Options**, sur le volet Action de la page.
- Sélectionnez le bouton **Paramètres** (symbole d’engrenage) dans la barre de navigation, puis sélectionnez **Personnaliser**.

[![Barre d’outils de personnalisation.](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navigation dans la page

Lorsque la barre d’outils **Personnalisation** est active, la page sous-jacente est en lecture seule (autrement dit, vous ne pouvez pas modifier les données), mais elle est toujours interactive. Spécifiquement, vous pouvez développer ou réduire le volet **Informations associées**, basculer entre les onglets, et développer ou réduire les sections, comme vous effectuez généralement ces actions sur la page. Pour appliquer une modification de personnalisation à une section ou un onglet réductible (par exemple masquer un raccourci), il vous suffit de sélectionner le bouton qui apparaît en regard de cette section ou de l’onglet lorsqu’il est activé au moyen du clavier ou lorsque vous passez le curseur dessus.

#### <a name="personalization-tools"></a>Outils de personnalisation

Les outils suivants sont disponibles dans la barre d’outils **Personnalisation** :

- Utilisez l’outil **Sélectionner** pour sélectionner et modifier les propriétés d’un élément. Pour utiliser cet outil, sélectionnez le bouton **Sélectionner** dans la barre d’outils, puis sélectionnez l’élément souhaité. La fenêtre des propriétés de l’élément s’affiche où vous pouvez modifier les propriétés de cet élément. Vous pouvez répéter le processus pour d’autres éléments qui peuvent être personnalisés sur la page. Notez que certaines propriétés de personnalisation ne soient pas disponibles dans certains scénarios. Par exemple, vous ne pouvez pas verrouiller un champ obligatoire.
- Utilisez l’outil **Masquer** pour masquer un élément sur la page. Pour utiliser cet outil, sélectionnez le bouton **Masquer** dans la barre d’outils, puis sélectionnez l’élément à masquer. Lorsque vous utilisez l’outil **Masquer**, tous les éléments actuellement masqués sont rendus visibles mais ils sont affichés dans un conteneur grisé. Vous pouvez ensuite rendre un élément visible en le sélectionnant. Pour afficher l’aspect de la page lorsque les éléments sont masqués, basculez vers un autre outil de personnalisation ou fermez la barre d’outils de personnalisation.
- Utilisez l’outil **Ajouter des champs** pour ajouter des champs à la page. Si vous utilisez cet outil, vous pouvez ajouter uniquement les champs qui font partie de la définition de page. Pour plus d’informations sur la création de champs qui ne font pas partie de la définition de page actuelle, voir [Créer et utiliser les champs personnalisés](user-defined-fields.md). Après avoir sélectionné l’outil **Ajouter des champs** sur la barre d’outils, vous devez d’abord sélectionner la grille ou la section où vous souhaitez ajouter un champ. Une boîte de dialogue affiche la liste des champs associés à la grille ou à la section sélectionnée. Dans la boîte de dialogue, sélectionnez un ou plusieurs champs à ajouter à partir de la liste **Champs recommandés** ou **Tous les champs**. Après avoir choisi les champs souhaités, sélectionnez **Mettre à jour**. Pour supprimer un champ que vous avez précédemment ajouté, répétez le processus, mais effacez la sélection du champ dans la boîte de dialogue.

    La liste **Champs recommandés** affiche les champs qui ont été précédemment ajoutés par d’autres utilisateurs de votre organisation. Cette liste de champs est mise à jour en fonction de la fréquence de récurrence du **Traitement par lot de recommandation**. Une expérience similaire existe lors de l’ajout de nouveaux champs de filtre à l’aide du volet Filtre sur une page.

- Utilisez l’outil **Déplacer** pour déplacer un élément vers un autre emplacement dans le groupe actuel d’éléments. Notez que vous ne pouvez pas déplacer un élément en dehors de son groupe parent. Pour utiliser cet outil, sélectionnez le bouton **Déplacer** dans la barre d’outils, puis sélectionnez l’élément à déplacer. Lorsque vous sélectionnez un élément, l’application détermine les emplacements où l’élément est autorisé à être déplacé. Ces emplacements sont appelés des *zones de déplacement*. Lorsque vous faites glisser l’élément dans le groupe actuel, chaque zone de déplacement est indiquée par une ligne colorée et grasse en regard de la zone où l’élément peut être déplacé.
- Utilisez l’outil **Ignorer** pour supprimer un élément de la séquence de tabulation du clavier de la page. Lorsque vous sélectionnez le bouton **Ignorer** sur la barre d’outils, tous les éléments actuellement ignorés sont affichés dans un conteneur grisé. Vous pouvez supprimer ou ajouter de manière interactive des champs à la séquence de l’onglet.
- Utilisez l’outil **Afficher dans l’en-tête** pour faire apparaître un champ dans la section récapitulative de le raccourci. Lorsque vous sélectionnez l’outil **Afficher dans l’en-tête** sur la barre d’outils, tous les champs sélectionnés comme champs récapitulatifs sont affichés dans un conteneur grisé. Vous pouvez en mode interactif ajouter des champs au récapitulatif de le raccourci et supprimer des champs du récapitulatif en sélectionnant les champs.
- Utilisez l’outil **Obligatoire** pour désigner un élément comme obligatoire pour la saisie de données. Lorsque vous sélectionnez le bouton **Obligatoire** sur la barre d’outils, tous les éléments qui ont été personnalisés pour être requis sont affichés dans un conteneur grisé. Vous pouvez ensuite les rendre à nouveau non obligatoire. Cette option est disponible dans la version 10.0.12 et les versions ultérieures lorsque la fonctionnalité **Désigner des champs selon les besoins à l’aide de la personnalisation** est activée.
- Utilisez l’outil **Verrouiller** pour marquer un élément comme modifiable ou non modifiable. Lorsque vous sélectionnez le bouton **Verrouiller** sur la barre d’outils, tous les éléments actuellement non modifiables sont affichés dans un conteneur grisé. Vous pouvez ensuite les rendre modifiables à nouveau. Notez que certains champs sont obligatoires et ne peuvent pas être rendus non modifiables. Un symbole de cadenas apparaît en regard de ces champs.
- Utilisez l’outil **Ajouter une application à partir de Power Apps** pour intégrer une application créée à l’aide de Microsoft Power Apps dans la page. Pour des informations détaillées sur l’intégration d’une application à partir de Power Apps dans une page, voir [Intégrer les applications à partir de Power Apps](embed-power-apps.md). Cette option n’est disponible que si la fonctionnalité [Vues enregistrées](saved-views.md) est désactivée.
- Utilisez le bouton **Ajouter une application** pour intégrer une application, soit une application créée à partir de Microsoft Power Apps, soit une application tierce, dans la page. Cette option n’est disponible que si la fonctionnalité [Vues enregistrées](saved-views.md) est activée. 
- Utilisez l’outil **Effacer** pour réinitialiser la page à son état installé par défaut. Toutes les personnalisations sur la page actuelle seront effacées. Cette action ne peut pas être annulée. Par conséquent, n’utilisez cet outil que si vous êtes sûr de vouloir réinitialiser la page. Quand la fonctionnalité **Vues enregistrées** est activée, cet outil efface les personnalisations de la vue actuelle.
- Utilisez l’outil **Importer** pour charger une personnalisation à partir d’un fichier que vous ou un tiers avez précédemment créé. 

    - Quand la fonctionnalité **Vues enregistrées** est désactivée, vous pouvez choisir d’ajouter ou de remplacer vos personnalisations existantes par les personnalisations qui sont importées pour la page. Cette action ne peut pas être annulée. Par conséquent, après avoir importé les personnalisations, vous devez effacer ou annuler manuellement les modifications que vous ne souhaitez pas.
    - Quand la fonctionnalité **Vues enregistrées** est activée, les personnalisations importées deviendront une vue sur la page. Si la vue existe déjà, vous aurez la possibilité d’ignorer l’importation, de remplacer la vue actuelle qui porte le même nom ou de renommer la vue importée.

- Utilisez l’outil **Exporter** pour enregistrer vos personnalisations de la page dans un fichier. Vous pouvez ensuite partager vos personnalisations avec d’autres utilisateurs. Ces utilisateurs doivent simplement importer le fichier contenant vos personnalisations de la page. Quand la fonctionnalité **Vues enregistrées** est activée, cet outil enregistre votre vue actuelle dans un fichier pour le partage.
- Sélectionnez le bouton **Fermer** pour fermer la barre d’outils **Personnalisation** et remettre la page dans son état interactif précédent.

Traditionnellement, lorsque la barre d’outils **Personnalisation** est utilisée, vos personnalisations prennent effet dès que vous les effectuez. Toutefois, si la fonctionnalité [Vues enregistrées](saved-views.md) est activée, vous devez explicitement enregistrer les personnalisations dans une vue que vous sélectionnez.

Dans certains cas, lorsque vous sélectionnez un outil, un symbole de cadenas s’affiche en regard d’un élément. Ce symbole indique que vous ne pouvez pas modifier les propriétés de l’élément qui sont associées à l’outil sélectionné, car les modifications de ces propriétés empêchent la page de fonctionner correctement.

### <a name="adding-tiles-lists-and-links-to-a-workspace"></a>Ajout de vignettes, de listes et de liens à un espace de travail

Pour certaines pages qui incluent des listes, la fonctionnalité de personnalisation **Ajouter à l’espace de travail** est disponible au groupe **Personnaliser** sur l’onglet **Options** du volet Actions. Cette fonctionnalité vous permet de transmettre des informations pertinentes de la liste actuelle vers un espace de travail spécifique. Les informations qui apparaissent dans l’espace de travail peuvent être basées sur la liste entière, ou une version filtrée et triée de la liste. Vous pouvez également spécifier si les informations s’affichent dans l’espace de travail sous forme de liste, de vignette récapitulative avec le nombre d’éléments dans la liste, ou encore de lien.

> [!NOTE]
> Si la fonctionnalité [Vues enregistrées](saved-views.md) est activée, le contenu que vous transférez à un espace de travail est directement associé à une vue. La requête de la vue est utilisée pour extraire des données de l’espace de travail, et la vignette ou le lien correspondant dans l’espace de travail ouvre la page dans cette vue, de sorte que la requête et les personnalisations de la vue soient appliquées à celle-ci. Si la vue est mise à jour, les éléments de l’espace de travail correspondants seront ajustés à la nouvelle définition de vue.

[![Ajouter à l’espace de travail.](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Pour ajouter une liste à un espace de travail, triez ou filtrez d’abord la liste sur la page pour afficher les informations comme vous souhaitez les voir apparaître dans l’espace de travail. (Si la fonctionnalité **Vues enregistrées** est activée, vous ne pouvez pas continuer tant que vous n’enregistrez pas de vue ayant ces conditions.) Sélectionnez **Ajouter à l’espace de travail** ensuite. Sélectionnez un espace de travail, puis, dans le champ **Présentation**, sélectionnez **Liste**. Après avoir sélectionné **Configurer**, une boîte de dialogue s’affiche pour vous permettre de sélectionner les colonnes qui doivent apparaître dans la liste de l’espace de travail. Vous pouvez également spécifier l’étiquette utilisée pour la liste de l’espace de travail.
- Pour ajouter une vignette à un espace de travail, filtrez d’abord la liste sur la page pour afficher les données qui doivent être récapitulées ou auxquelles vous souhaitez avoir un accès rapide. (Si la fonctionnalité **Vues enregistrées** est activée, vous ne pouvez pas continuer tant que vous n’enregistrez pas de vue ayant ces conditions.) Sélectionnez **Ajouter à l’espace de travail** ensuite. Sélectionnez un espace de travail, puis, dans le champ **Présentation**, sélectionnez **Vignette**. Après avoir sélectionné **Configurer**, une boîte de dialogue s’affiche pour vous permettre de spécifier l’étiquette qui doit être utilisée pour la vignette dans l’espace de travail. Vous pouvez également spécifier si la vignette doit afficher un nombre. Après la vignette ajoutée à l’espace de travail, vous pouvez la sélectionner pour ouvrir la page actuelle dans l’espace de travail. Vous pouvez ensuite afficher la liste filtrée associée à la vignette.
- Pour ajouter un lien à un espace de travail, filtrez d’abord la liste sur la page pour afficher les données qui vous intéressent. (Si la fonctionnalité **Vues enregistrées** est activée, vous ne pouvez pas continuer tant que vous n’enregistrez pas de vue ayant ces conditions.) Sélectionnez **Ajouter à l’espace de travail** ensuite. Sélectionnez un espace de travail, puis, dans le champ **Présentation**, sélectionnez **Lien**. Après avoir sélectionné **Configurer**, une boîte de dialogue s’affiche pour vous permettre de spécifier l’étiquette qui doit être utilisée pour le lien. Vous pouvez éventuellement spécifier une étiquette pour la section où ce lien peut être placé. Si cette section n’existe pas, une nouvelle section sera créée.

> [!NOTE]
> À partir de la version 10.0.25, lorsque vous configurez votre liste, vignette ou lien, vous devrez peut-être également sélectionner les vues de l’espace de travail auxquelles vous souhaitez ajouter l’élément si la fonctionnalité **Prise en charge des vues enregistrées pour les espaces de travail (version préliminaire)** est activée. Les vues d’espace de travail disponibles s’affichent dans la section **Options de l’espace de travail** de chaque boîte de dialogue **Configurer**. 

Après avoir ajouté une liste, une vignette ou un lien à un espace de travail, vous pouvez ouvrir cet espace de travail et réorganiser les éléments comme vous le souhaitez.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Ajout d’un résumé d’un espace de travail à un tableau de bord

Certains espaces de travail contiennent des vignettes de comptage (c’est-à-dire des vignettes numérotées) que vous pouvez également afficher sur votre tableau de bord. Dans un espace de travail, cliquez avec le bouton droit sur une vignette de comptage, sélectionnez **Personnaliser**, puis, dans la fenêtre des propriétés de la vignette, sélectionnez **Épingler au tableau de bord**. La prochaine fois que vous ouvrirez et actualiserez le tableau de bord sélectionné, le nombre s’affichera en dessous de la vignette de navigation pour cet espace de travail. Vous pouvez sélectionner ce nombre pour accéder directement aux données qu’il représente.

### <a name="personalizing-your-dashboard"></a>Personnalisation de votre tableau de bord

Le tableau de bord est souvent la première page que vous voyez lorsque vous ouvrez l’application. Il peut être personnalisé comme n’importe quelle autre page du système, en utilisant les mêmes mécanismes que ceux décrits plus haut dans cette rubrique. 

> [!WARNING]
> Actuellement, lorsque vous masquez du contenu sur le tableau de bord, il est important de cibler directement une vignette, pas l’espace qui l’entoure. Si vous masquez le groupe à l’aide d’une vignette, des résultats inattendus peuvent survenir si d’autres vignettes sont ajoutées ultérieurement ou si le système est basculé dans une langue différente.

Une fonctionnalité de personnalisation unique disponible sur le tableau de bord est la possibilité d’ajouter des vignettes. 

- Si la fonctionnalité **Applications pleine page** est désactivée, vous ajoutez une nouvelle vignette en cliquant avec le bouton droit sur un élément du tableau de bord, puis en sélectionnant **Ajouter un espace de travail**. Une nouvelle vignette d’espace de travail est créée en bas du tableau de bord. Vous pouvez renommer cette nouvelle vignette d’espace de travail comme vous le souhaitez. Vous pouvez également ajouter des listes, des vignettes et des liens à l’espace de travail, comme décrit dans la section [Ajout de listes, de vignettes ou de liens vers un espace de travail](personalize-user-experience.md#adding-tiles-lists-and-links-to-a-workspace).
- Si la fonctionnalité **Applications pleine page** est activée, vous ajoutez une nouvelle vignette en cliquant avec le bouton droit sur un élément du tableau de bord, puis en sélectionnant **Ajouter une application**. Dans la boîte de dialogue, indiquez si vous souhaitez ajouter une vignette pour un nouvel espace de travail ou une vignette dont le contenu est Power Apps ou un site web. Suivez ensuite les étapes pour configurer l’option que vous avez sélectionnée. Une nouvelle vignette est créée en bas du tableau de bord. Pour plus d’informations sur l’ajout, la modification, la suppression et le partage de ces applications intégrées, consultez [Intégrer des applications de canevas à partir de Power Apps](embed-power-apps.md) et [Intégrer des applications tierces](embed-website.md).

## <a name="sharing-personalizations"></a>Partage des personnalisations

Après avoir personnalisé une page, vous pouvez utiliser plusieurs méthodes pour partager vos personnalisations avec d’autres utilisateurs. Dans la liste suivante, les méthodes sont classées dans l’ordre allant du plus recommandé au moins recommandé.

1. Publiez des vues pour les utilisateurs.
2. Copiez les vues ou les personnalisations pour les utilisateurs.
3. Exportez et importez des vues ou des personnalisations.

### <a name="publish-views-to-users"></a>Publier des vues pour les utilisateurs

Si la fonctionnalité [Vues enregistrées](saved-views.md) est activée et si la page prend en charge les vues, la meilleure façon de partager des personnalisations avec d’autres utilisateurs est de publier la vue auprès des utilisateurs qui ont un ou plusieurs rôles de sécurité. Pour plus d’informations, voir [Publication de vues](saved-views.md#publishing-views).

### <a name="copy-views-or-personalizations-to-users"></a>Copier les vues ou les personnalisations pour les utilisateurs

Si la fonctionnalité [Vues enregistrées](saved-views.md) est désactivée, ou si la page ne prend pas en charge les vues, la méthode recommandée pour partager les personnalisations est de les copier entre les utilisateurs. Cette méthode n’est disponible que pour les utilisateurs privilégiés (par exemple, les administrateurs système). Cependant, les administrateurs peuvent rechercher la personnalisation d’un utilisateur spécifique dans le système (y compris la vue personnelle de l’utilisateur si les vues enregistrées sont activées) et copier la configuration vers d’autres utilisateurs.

Si les vues enregistrées sont activées, procédez comme suit pour copier les personnalisations.

1. Accédez à **Administration système \> Paramétrage \> Personnalisation**.
2. Suivez ces étapes pour copier des vues personnelles :

    1. Sélectionnez **Vues personnelles**.
    2. Sélectionnez les vues souhaitées dans la liste.
    3. Sélectionnez **Copier pour les utilisateurs**.
    4. Sélectionnez les utilisateurs auxquels distribuer les vues.

    Suivez ces étapes pour copier des personnalisations sur des pages qui ne prennent pas en charge les vues :

    1. Sélectionnez **Paramètres utilisateur**.
    2. Sélectionnez l’utilisateur qui possède la personnalisation que vous souhaitez distribuer.
    3. Sélectionnez **Gérer toutes les personnalisations**.
    4. Sélectionnez les personnalisations souhaitées dans la liste.
    5. Sélectionnez **Copier pour les utilisateurs**.
    6. Sélectionnez les utilisateurs auxquels distribuer les personnalisations.

Si les vues enregistrées ne sont pas activées, procédez comme suit pour copier une personnalisation.

1. Accédez à **Administration système \> Paramétrage \> Personnalisation**.
2. Sélectionnez **Appliquer**.
3. Sélectionnez les utilisateurs auxquels distribuer la personnalisation.
4. Sélectionnez **Sélectionner la personnalisation existante**.
5. Recherchez et sélectionnez la personnalisation (unique) qui vous intéresse.
6. Cliquez sur **OK**.

### <a name="export-and-import-views-or-personalizations"></a>Exporter et importer des vues ou des personnalisations

Une autre façon de partager des personnalisations consiste à exporter et à importer. Les utilisateurs individuels, ou un administrateur agissant en leur nom, peuvent utiliser cette méthode pour exporter leurs personnalisations ou vues, puis donner le fichier exporté à d’autres utilisateurs afin de l’importer. Les utilisateurs peuvent également donner leurs personnalisations exportées à un utilisateur qui dispose de privilèges d’administrateur, et cet utilisateur peut ensuite utiliser la page d’administration **Personnalisation** pour appliquer le fichier de personnalisation à plusieurs utilisateurs en même temps.

> [!IMPORTANT]
> Du fait que les personnalisations persistent à travers les mises à jour, la réimportation de toutes les personnalisations après une mise à jour de service ou à tout autre moment est inutile et fortement déconseillée.

#### <a name="export"></a>Exporter

En général, vous pouvez exporter l’une de vos propres vues ou personnalisations en ouvrant la page appropriée, en ouvrant la barre d’outils **Personnalisation**, puis en sélectionnant **Exporter**. Pour plus d’informations sur la barre d’outils, consultez la section précédente [Barre d’outils de personnalisation](#personalization-toolbar) dans cette rubrique. Sinon, si les [vues enregistrées](saved-views.md) sont activés, vous pouvez aller dans **Paramètres \> Options utilisateur \> Personnalisation** pour afficher la liste de toutes vos personnalisations dans le système. À partir de là, vous pouvez sélectionner les vues ou les personnalisations à exporter, puis sélectionner **Exporter**.

En outre, les administrateurs peuvent exporter les personnalisations d’autres utilisateurs en suivant ces étapes.

1. Accédez à **Administration système \> Paramétrage \> Personnalisation**.
2. Sous l’onglet **Utilisateurs**, sélectionnez l’utilisateur souhaité.
3. Recherchez et sélectionnez la vue ou la personnalisation qui vous intéresse.
4. Sélectionnez **Exporter**.

#### <a name="import"></a>IMPORTER

Pour importer une vue ou une personnalisation, vous pouvez simplement ouvrir la barre d’outils **Personnalisation** et sélectionner **Importer**. De plus, les administrateurs peuvent importer un fichier et le donner immédiatement à un ou plusieurs utilisateurs.

Si les vues enregistrées sont activées, procédez comme suit :

1. Accédez à **Administration système \> Paramétrage \> Personnalisation**.
2. Dans la volet Actions, sélectionnez **Importer les vues \> Vues utilisateur**.
3. Sélectionnez le mode d’importation :

    - **Sélectionner des utilisateurs spécifiques** – Attribuer la vue ou la personnalisation aux utilisateurs sélectionnés.
    - **Importer tel quel** – Importer la vue ou la personnalisation vers le même utilisateur qui l’a exportée.

4. Sélectionnez **Parcourir**, puis recherchez et sélectionnez la personnalisation à importer.
5. Sélectionnez **Suivant**.
6. Si vous avez sélectionné **Sélectionner des utilisateurs spécifiques** à l’étape 3, sélectionnez les utilisateurs vers lesquels importer la personnalisation.
7. Sélectionnez **Importer**.
8. Résolvez les conflits au besoin.

Si les vues enregistrées ne sont pas activées, procédez comme suit :

1. Accédez à **Administration système \> Paramétrage \> Personnalisation**.
2. Sélectionnez **Appliquer**.
3. Sélectionnez les utilisateurs auxquels distribuer la personnalisation.
4. Sélectionnez **Importer des personnalisations à partir d’un fichier**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez la personnalisation à importer.
6. Cliquez sur **OK**.

## <a name="administration-of-personalizations"></a>Administration des personnalisations

La page **Personnalisation** est le nœud central de la gestion des personnalisations au niveau de l’organisation. Le contenu et les fonctionnalités de cette page varient selon que la fonctionnalité **Vues enregistrées** a été activée.

Pour les clients qui ont activé la fonctionnalité **Vues enregistrées**, consultez la section « Gestion globale des vues » dans la rubrique [Vues enregistrées](saved-views.md).

Pour les clients n’ayant pas encore activé la fonctionnalité [Vues enregistrées](saved-views.md), cette page contient quatre onglets :

- **Appliquer** – Vous pouvez importer ou sélectionner une personnalisation pour un ou plusieurs utilisateurs. Pour appliquer une personnalisation à un ou plusieurs utilisateurs, sélectionnez d’abord un rôle et des utilisateurs disposant ce rôle. Sélectionnez ensuite une personnalisation existante à appliquer aux utilisateurs sélectionnés, ou importez un fichier de personnalisation. La personnalisation est validée et sera appliquée à tous les utilisateurs sélectionnés la prochaine fois qu’ils ouvriront la page sélectionnée.
- **Effacer** – Vous pouvez effacer toutes les personnalisations d’une page ou d’un espace de travail pour un ou plusieurs utilisateurs. Sélectionnez d’abord une page ou un espace de travail pour afficher la liste des utilisateurs qui l’ont personnalisé. Ensuite, sélectionnez les utilisateurs dont les personnalisations pour cette page ou cet espace de travail doivent être effacées. Enfin, sélectionnez **Effacer**. Toutes les personnalisations que les utilisateurs sélectionnés ont appliquées à la page ou à l’espace de travail sélectionné(e) sont supprimées. Cette action ne peut pas être annulée. Toutefois, si une personnalisation a été enregistrée pour la page ou l’espace de travail, cette personnalisation peut être réimportée.
- **Utilisateurs** : sélectionnez un utilisateur pour afficher une liste des pages personnalisées par celui-ci. Vous pouvez ensuite activer ou désactiver la possibilité que l’utilisateur sélectionné utilise les personnalisations pour des pages spécifiques ou pour l’ensemble du système. Vous pouvez également importer, exporter ou effacer une personnalisation pour l’utilisateur. En outre, vous pouvez réinitialiser les légendes de fonction pour l’utilisateur. Dans ce cas, si l’utilisateur a ignoré précédemment des fenêtres contextuelles qui introduisaient de nouvelles fonctionnalités, elles s’affichent de nouveau la prochaine fois que l’utilisateur rencontre ces fonctionnalités.
- **Système** : vous pouvez désactiver temporairement la personnalisation de l’ensemble des utilisateurs du système. Dans ce cas, toutes les personnalisations sont supprimées pour tous les utilisateurs, et toutes les pages sont rétablies à leur état par défaut. Si vous réactivez la personnalisation ultérieurement, toutes les personnalisations sont réappliquées. Vous pouvez également supprimer définitivement toutes les personnalisations pour l’ensemble des utilisateurs du système. Les personnalisations qui ont été supprimées ne peuvent être restaurées. Par conséquent, avant d’effectuer cette tâche, veillez à exporter les personnalisations que vous souhaitez utiliser ultérieurement.

## <a name="personalizing-inventory-dimensions"></a>Personnalisation des dimensions de stock

Lorsque vous personnalisez le paramétrage des dimensions de stock sur une page, tenez compte des paramètres qui ont été créés à l’aide de l’option **Afficher les dimensions**. Par exemple, vous utilisez la personnalisation pour masquer une colonne de la dimension de stock Numéro de lot, mais la colonne s’affiche à la prochaine ouverture de la page. Ce comportement se produit car les paramètres **Affichage des dimensions** contrôlent les colonnes de la dimension de stock affichées. Les paramètres **Affichage des dimensions** s’appliquent à toutes les pages et remplacent tout paramétrage personnalisé des champs de la dimension de stock sur des pages individuelles.

Par conséquent, dans l’exemple précédent, si vous ne souhaitez pas afficher la colonne de la dimension de stock Numéro de lot sur une page, vous devez désactiver cette dimension dans le cadre de l’option **Afficher les dimensions** pour cette page.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
