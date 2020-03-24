---
title: Utiliser des fragments
description: Cette rubrique décrit le pourquoi, quand et comment utiliser des fragments dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f29046ded47ed9c49a2cc841aa7c1f6492b49aec
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124357"
---
# <a name="work-with-fragments"></a>Utiliser des fragments 


[!include [banner](includes/banner.md)]

Cette rubrique décrit le pourquoi, quand et comment utiliser des fragments dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Les fragments permettent une expérience de création centralisée pour les configurations du module qui doivent être réutilisées dans tout votre site. Par exemple, les en-têtes, les pieds de page, et les bannières sont souvent configurés comme fragments, car ils sont partagés entre la plupart des pages. Vous pouvez imaginer les fragments comme des pages web miniatures pouvant être insérées dans d'autres pages sur votre site. Les fragments ont leur propre cycle de vie. En d'autres termes, ils sont créés, référencés, mis à jour et supprimés comme des entités indépendantes dans les outils de création.

Une fois les fragments configurés, ils peuvent être utilisés chaque fois que des modules peuvent être utilisés dans votre structure de site. Les fragments peuvent être référencés dans les pages, dans les dispositions, dans les modèles, et dans d'autres fragments.

> [!NOTE]
> Les fragments peuvent être imbriqués jusqu'à sept niveaux de profondeur à l'intérieur d'autres fragments.

Par exemple, si vous souhaitez promouvoir un événement saisonnier entre de nombreux pages de notre site, vous pouvez utiliser un fragment. La première étape du processus de création d'un fragment est de sélectionner le type du module à partir duquel démarrer. Par exemple, vous pouvez créer le fragment à partir d'un module de bannière.

> [!NOTE]
> Les fragments peuvent être établis à partir de n'importe quel type de module.

Vous pouvez ensuite configurer le fragment de bannière avec votre contenu promotionnel spécifique. Vous pouvez également le localiser au besoin. Le nouveau fragment de bannière autonome peut ensuite être utilisé comme module préconfiguré dans tout votre site. Vous pouvez facilement l'ajouter aux modèles, à des pages spécifiques, ou à d'autres fragments qui peuvent contenir des modules de bannière.

Tous les emplacements où le fragment est ajouté sont des références au fragment central de bannière que vous avez créé. Si vous sortez des modifications dans le fragment, ces modifications sont immédiatement répercutées à tous les emplacements où le fragment est mentionné dans le site. Par conséquent, les fragments sont un moyen puissant et efficace de réutiliser et de gérer centralement des configurations de module dans un site. En les utilisant efficacement, vous pouvez augmenter de façon importante l'agilité et minimiser le coût associé à la gestion du contenu du site.

L'illustration ci-dessous indique comment des fragments peuvent être utilisés pour centraliser la création de configurations de module partagées dans un site de commerce électronique.

![Une illustration affichant comment des fragments peuvent être utilisés pour centraliser la création de configurations de module partagées dans un site de commerce électronique](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a>Créer un fragment

Vous pouvez créer un fragment ou enregistrer une configuration de module existante comme fragment.

### <a name="save-an-existing-module-configuration-as-a-fragment"></a>Enregistrez une configuration de module existante comme fragment

Pour convertir un module précédemment configuré en un fragment réutilisable, procédez comme suit.

1. Ouvrez une page ou un modèle contenant le module que vous souhaitez convertir en un fragment.
1. Dans le volet de contour à gauche, sélectionnez le bouton des points de suspension (**...**) à côté du nom du module. 
1. Sélectionnez **Partager en tant que fragment**. 
1. Une boîte de dialogue s'affiche. Entrez un nom et les métadonnées du fragment.
1. Sélectionnez **OK** pour enregistrer la configuration du module comme fragment qui peut être ajouté à d'autres pages.

L'image suivante montre comment enregistrer une configuration de module en tant que fragment.

![Capture d'écran montrant comment enregistrer une configuration de module en tant que fragment](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a>Créer un fragment

Pour créer un fragment, procédez comme suit.

1. Dans le volet de navigation sur la gauche, sélectionnez **Fragments**.
1. Sélectionnez **Nouveau fragment de page**. Une boîte de dialogue apparaît qui indique tous les types de modules disponibles. Comme mentionné précédemment, les fragments peuvent être créés à partir de n'importe quel type de module.
1. Sélectionnez un type de module pour votre fragment.

L'image suivante montre où créer un fragment.

![Capture d'écran montrant où créer un fragment](./media/fragment-nav-menu.png)

> [!TIP]
> En sélectionnant un type de module de conteneur générique, vous obtenez la plus grande flexibilité lorsque vous devrez mettre à jour et configurer votre fragment ultérieurement.

## <a name="add-remove-or-edit-fragments-on-a-page"></a>Ajouter, supprimer ou modifier des fragments sur une page

Les procédures suivantes expliquent comment ajouter, supprimer, et modifier des fragments.

### <a name="add-a-fragment"></a>Ajouter un fragment

Pour ajouter un fragment à une page, procédez comme suit.

1. Dans le volet de contour à gauche, sélectionnez un conteneur ou un emplacement auquel les modules enfants peuvent être ajoutés.
1. Sélectionnez le bouton représentant des points de suspension en regard du nom du conteneur ou de l'emplacement, et sélectionnez **Ajouter un fragment**. Une boîte de dialogue s'affiche.

    ![Capture d'écran montrant comment ajouter un fragment existant à un emplacement ou un conteneur](./media/add-fragment.png)
 
    > [!NOTE]
    > Si le conteneur ou l'emplacement ne prend pas en charge de nouveaux modules enfants, l'option **Ajouter un fragment** n'est pas disponible.
    
1. Dans la boîte de dialogue, recherchez et sélectionnez un fragment à ajouter. Si aucun fragment disponible n'est répertorié, vous pouvez d'abord peut-être créer un fragment d'un type de module que le conteneur ou l'emplacement sélectionné prend en charge.
1. Sélectionnez le fragment que vous voulez ajouter au conteneur ou à l'emplacement sélectionné sur la page.

    ![Capture d'écran de la fenêtre modale du sélecteur de fragments](./media/fragment-picker.png)

> [!NOTE]
> Les modules autorisés dans un conteneur ou un emplacement sont définis par le modèle de la page ou les propres définitions des modules.

### <a name="remove-a-fragment"></a>Suppression d'un fragment

Pour supprimer un fragment d'un emplacement ou d'un conteneur sur une page, procédez comme suit.

1. Dans le volet de contour à gauche, sélectionnez le bouton représentant des points de suspension en regard du nom du fragment à supprimer, puis sélectionnez le bouton de corbeille.
1. Lorsque vous êtes invité à confirmer la suppression du fragment, sélectionnez **OK**.

> [!NOTE]
> Lorsque vous supprimez un fragment d'une page, vous en supprimez immédiatement la référence sur cette page. Vous ne supprimez **pas** le fragment de votre site. Pour supprimer des fragments de votre site, vous devez utiliser l'interface utilisateur (UI) de l'inspecteur de fragment. Vous pouvez supprimer des fragments d'un site que si ils ne sont actuellement référencés par des pages, modèles, ou d'autres fragments.

### <a name="edit-a-fragment"></a>Modifier un fragment

Pour modifier des fragments, vous devez utiliser l'interface utilisateur de l'éditeur de fragment. Cette restriction est faite exprès. Elle permet de garantir que les auteurs ne confondent pas le processus de modifier les modules pour une page spécifique avec le processus de modification des fragments qui peuvent être partagés entre plusieurs de pages.

Pour modifier un fragment, procédez comme suit.

1. Dans le volet de navigation sur la gauche, sélectionnez **Fragments**.
1. Sous **Fragments**, sélectionnez le fragment à modifier.
1. Modifiez les propriétés et la structure du module du fragment comme vous le souhaitez. Le processus est semblable au processus de modification des modules sont modifiés dans la vue d'éditeur de page.

Vous pouvez également modifier un fragment en le sélectionnant dans une page, dans un modèle, ou un fragment parent, puis en sélectionnant **Modifier le fragment** dans le volet de propriétés à droite.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md)

[Utiliser des modèles](work-with-templates.md)

[Utilisation des mises en page prédéfinies](work-with-layouts.md)

[Utilisation de groupes de publication](publish-groups.md)
