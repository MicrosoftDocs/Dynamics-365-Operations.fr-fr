---
title: Utiliser des modules
description: Cette rubrique décrit quand et comment utiliser des modules dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: da430857801d8007244c04aadd325e99c0b882c5
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2020
ms.locfileid: "3646013"
---
# <a name="work-with-modules"></a>Utiliser des modules

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique décrit quand et comment utiliser des modules dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Les modules sont des blocs élémentaires logiques qui constituent la structure de la page, et ils ont différentes fins et étendues. Certains modules sont des conteneurs de haut niveau, et leur seul objectif est de garder à jour et d’organiser les autres modules (modules enfants). D’autres modules, tels qu’un module de placement d’une image simple, à un objet très spécifique. D’autres modules, tels qu’un module de carrousel, se situe entre ces deux catégories.

Par défaut, votre site Dynamics 365 Commerce inclut une bibliothèque de modules du kit de démarrage qui vous permet de réaliser la plupart des scénarios de base de commerce électronique. Vous devez pouvoir construire un site de bout en bout de commerce électronique juste à l’aide de ces modules. Toutefois, vous pouvez également souhaiter personnaliser ces modules ou générer de nouveaux modules, personnalisés pour les besoins spécifiques. Si vous souhaitez générer les modules personnalisés, un kit de développement logiciel (SDK) de conception de module est disponible pour créer une bibliothèque de modules personnalisée.

## <a name="container-modules-and-slots"></a>Modules et emplacement de conteneur

Comme précédemment évoqué, certains modules sont conçus pour mettre à jour les modules enfants. Ces modules sont appelés *conteneurs*, et ils permettent des hiérarchies de modules imbriqués. Les modules de conteneur incluent des *emplacements*. Les emplacements sont utilisés pour gérer la disposition et l’objectif des modules enfants dans le conteneur. Un exemple est un module de conteneur de page de base (module de niveau supérieur pour toute page) qui définit plusieurs emplacements importantes :

- Un emplacement d’en-tête
- Emplacement de sous-en-tête
- Emplacement principal
- Un emplacement de pied de page
- Emplacement de sous-pied de page

Le développeur du module définit ces emplacements, et détermine quels modules enfants et combien de modules enfants peuvent être placés directement à l’intérieur de celui-ci. Par exemple, l’emplacement d’en-tête ne peut prendre en charge qu’un module de type **Module d’en-tête**, alors que l’emplacement du corps peut prendre en charge un nombre illimité de modules de tous types (sauf d’autres modules de conteneur de page).

Dans les outils de création, les auteurs de page ne doivent pas savoir à l’avance quels modules peuvent et ne peuvent pas être placés dans chaque emplacement. Lorsque des auteurs de page sélectionnent un emplacement puis essayent de sélectionner un module à ajouter à celui-ci, ils peuvent afficher une vue filtrée des types de modules pris en charge pour cet emplacement.

## <a name="content-modules"></a>Modules de contenu

Les modules de contenus contiennent des éléments de contenu et multimédias, tels que le texte (par exemple, des titres, des paragraphes, ainsi que des liens) ou des références d’actifs (par exemple, des images, des vidéos, et des PDF). Les types de modules de contenu typiques incluent les modules de bloc de contenu, de bloc de texte et de bannière promotionnelle. Les modules de ces trois types peuvent contenir du texte ou du multimédia, et ils n’exigent pas de module enfant pour rendre un événement visible dans une page.

La plupart des activités de création de page et de contenu standard et quotidiennes impliquent des modules de contenu, principalement car ces modules définissent le contenu réel qui s’affiche dans leurs modules parents de conteneur. De nombreux modules de contenu sont disponibles, et ces modules sont généralement les dernières pièces que vous ajoutez à la hiérarchie d’une page de modules imbriqués.

L’illustration ci-dessous indique comment les modules sont imbriqués dans des emplacements parents des modules de conteneur.

![Imbrication de modules](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Ajouter ou supprimer des modules

Les procédures suivantes expliquent comment ajouter, supprimer des modules.

### <a name="add-a-module"></a>Ajouter un module

Pour ajouter un module à un emplacement ou à un conteneur sur une page, procédez comme suit.

1. Dans le volet de contour à gauche ou directement dans le canevas principal, sélectionnez un conteneur ou un emplacement auquel un module enfant peut être ajouté.

    > [!NOTE]
    > Le concepteur de module définit la liste des types de modules qui peuvent être ajoutés à un emplacement spécifique du module. Les auteurs de modèles peuvent ensuite affiner les options autorisées de module pour assurer un optimisation de moteur de recherche (SEO) cohérente et un rendement de création pour toutes les pages qui sont créées à partir d’un modèle spécifique. Lors de l’ajout d’un module à un emplacement, la boîte de dialogue **Ajouter un module** est automatiquement filtrée afin d’afficher uniquement les modules pris en charge dans le conteneur ou l’emplacement sélectionné. Cette liste des modules autorisés est déterminée par le modèle de la page ou la définition du module de conteneur.

1. Si vous utilisez le volet de contour, sélectionnez les points de suspension (**...**) à côté du nom du module, puis sélectionnez **Ajouter un module**. Si vous utilisez les contrôles directement dans le canevas, sélectionnez le symbole plus (**+**) dans un emplacement vide ou adjacent au module actuellement sélectionné, puis sélectionnez **Ajouter un module**.

    > [!NOTE]
    > Si le conteneur ou l’emplacement ne prend pas en charge de nouveaux modules enfants, l’option **Ajouter un module** n’est pas disponible.

1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez un module à ajouter à votre page.

    > [!TIP]
    > **Bloc de contenu** est un bon type de module pour les débutants.

1. Sélectionnez **OK** pour ajouter le module sélectionné au conteneur ou à l’emplacement sélectionné sur la page.

### <a name="remove-a-module"></a>Supprimer un module

Pour supprimer un module d’un emplacement ou d’un conteneur sur une page, procédez comme suit.

1. Dans le volet de contour à gauche, sélectionnez le bouton représentant des points de suspension (**...**) en regard du nom du module à supprimer, puis sélectionnez le symbole de corbeille. Sinon, dans le canevas principal, vous pouvez sélectionner le symbole de corbeille dans la barre d’outils d’un module sélectionné.
1. Lorsque vous êtes invité à confirmer la suppression du module, sélectionnez **OK**.

## <a name="move-a-module-to-a-new-position"></a>Déplacer un module vers une nouvelle position

Pour déplacer un module vers une nouvelle position sur votre page, appliquez l’une des méthodes suivantes.

### <a name="move-a-module-using-the-outline-pane"></a>Déplacer un module à l’aide du volet de contour

Pour déplacer un module à l’aide du volet de contour, procédez comme suit.

1. Sélectionnez et maintenez le module que vous souhaitez déplacer dans le volet de contour, puis faites glisser le module vers une nouvelle position dans le contour. La ligne bleue dans le contour et sur le canevas indique où le module peut être placé.
1. Relâchez le module pour le déposer dans la nouvelle position.

### <a name="move-a-module-directly-within-the-canvas"></a>Déplacer un module directement dans le canevas

Pour déplacer un module directement dans le canevas, procédez comme suit.

1. Sélectionnez le module à déplacer dans le canevas. 
1. Sélectionnez une flèche pointant vers le haut ou vers le bas dans la barre d’outils du module, puis faites glisser la flèche vers une nouvelle position sur la page. La ligne bleue sur le canevas et dans le contour indique où le module peut être placé. Si un module ne peut pas être déplacé vers le haut ou vers le bas, ce symbole de flèche sera grisé. 
1. Relâchez le module pour le déposer dans la nouvelle position.

### <a name="move-a-module-using-the-ellipsis-menu"></a>Déplacer un module à l’aide du menu de points de suspension

Pour déplacer un module à l’aide du menu de points de suspension, procédez comme suit.

1. Sélectionnez un module dans le contour ou sur le canevas.
1. Sélectionnez les points de suspension (**...**) à côté du nom du module dans le volet de contour ou dans la barre d’outils du module sur le canevas.
1. Si le module peut être déplacé vers le haut ou vers le bas dans le conteneur ou l’emplacement, vous verrez des options pour **Déplacer vers le haut** ou **Déplacer vers le bas**. Sélectionnez l’option de déplacement souhaitée pour déplacer le module vers le haut ou vers le bas par rapport à ses frères et sœurs.

## <a name="configure-modules"></a>Configuration des modules

Les procédures suivantes expliquent comment configurer des modules de contenu et de conteneur.

### <a name="configure-a-content-module"></a>Configuration d’un module de contenu

Pour configurer un module de contenu sur une page, procédez comme suit.

1. Dans le volet de contour à gauche, développez l’arborescence et sélectionnez un type de module de contenu (par exemple, **Bloc de contenu**). Sinon, vous pouvez sélectionner le module dans le canevas principal.
1. Dans le volet des propriétés du module sur la droite, entrez les propriétés des contrôles de module souhaités.
1. Sur la barre de commande, sélectionnez **Enregistrer**. Le canevas d’aperçu est également actualisé.

### <a name="edit-module-text-properties"></a>Modifier les propriétés du texte du module

Les propriétés du texte du module qui ne sont pas en lecture seule peuvent être modifiées directement dans le canevas.

Pour modifier les propriétés du texte du module, procédez comme suit.

1. Sélectionnez le contrôle de texte dans le canevas, puis placez votre curseur à l’endroit où vous souhaitez modifier le texte.
1. Entrez le contenu du texte.
1. Sélectionnez n’importe où en dehors du contenu du texte pour continuer à modifier d’autres contenus.

### <a name="inline-image-selection"></a>Sélection d’images en ligne

Les images du module qui ne sont pas en lecture seule peuvent être modifiées directement dans le canevas.

Pour choisir une image pour un module de contenu, procédez comme suit.

1. Dans le canevas, double-cliquez sur l’image. Cela fera apparaître la fenêtre du sélecteur de média.
1. Recherchez et sélectionnez une nouvelle image à utiliser, puis sélectionnez **OK**. La nouvelle image est maintenant affichée dans le canevas.

### <a name="configure-a-container-module"></a>Configurer un module de conteneur

Pour configurer un module de conteneur sur une page, procédez comme suit.

1. Sélectionnez un module de conteneur sur la page (par exemple, un module de carrousel ou de conteneur fluide).
1. Dans le volet de propriétés de droite, développez les contrôles imbriqués en sélectionnant les en-têtes, puis définissez toutes les valeurs requises de contrôle.
1. Dans le volet de contour à gauche, sélectionnez le bouton représentant des points de suspension en regard du nom du conteneur ou des emplacements à l’intérieur du conteneur, puis sélectionnez **Ajouter un module**. Ajoutez ensuite les modules enfants au conteneur sélectionné. Pour plus d’informations, voir la section [Utiliser les modules](#add-a-module) plus haut dans cette rubrique.
1. Si plusieurs modules enfants existent en tant que jumeaux dans un conteneur parent, vous pouvez changer l’ordre d’affichage du conteneur parent. Sélectionnez le bouton représentant des points de suspension d’un module, puis utilisez les boutons de flèche vers le bas ou vers le haut.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des modèles et dispositions](templates-layouts-overview.md)

[Utiliser des modèles](work-with-templates.md)

[Utilisation des mises en page prédéfinies](work-with-layouts.md)

[Utiliser des fragments](work-with-fragments.md)

[Ajouter un module de conteneur à une page](add-container-module.md)

[Utilisation de groupes de publication](publish-groups.md)

