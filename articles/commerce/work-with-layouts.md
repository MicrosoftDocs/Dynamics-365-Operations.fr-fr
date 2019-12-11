---
title: Utilisation des mises en page prédéfinies
description: Cette rubrique décrit l'utilisation des dispositions prédéfinies dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/01/2019
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
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1f2c0638caa7e4f6f831e592e3f7e3f5ab7d1d81
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697817"
---
# <a name="work-with-preset-layouts"></a>Utilisation des mises en page prédéfinies

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique décrit l'utilisation des dispositions prédéfinies dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Avant d'exécuter les procédures décrites dans cette rubrique, assurez-vous de lire [Dispositions prédéfinies et personnalisées](templates-layouts-overview.md#preset-and-custom-layouts). Pour obtenir une vue d'ensemble générale, voir [Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md).

## <a name="create-a-new-preset-layout"></a>Créer une dispositions prédéfinie

Il existe deux méthodes pour créer une dispositions prédéfinie. Vous pouvez enregistrer une disposition personnalisée existante comme nouvelle disposition prédéfinie, ou créer une disposition prédéfinie créée de toutes pièces.

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a>Créer une disposition prédéfinie à partir d'une disposition personnalisée existante

Pour créer une disposition prédéfinie à partir d'une disposition personnalisée existante; procédez comme suit.

1. Ouvrez une page existante qui n'utilise pas actuellement de disposition prédéfinie, et qui a une structure de module que vous souhaitez réutiliser pour d'autres pages sur votre site.
1. Sélectionnez **Caisse**.
1. Sélectionnez **Enregistrer comme nouvelle disposition**. La boîte de dialogue **Enregistrer comme nouvelle disposition** apparaît.
1. Entrez un nom et une description pour la disposition prédéfinie. Les valeurs entrées sont affichées à d'autres auteurs lorsqu'ils créent des pages dans votre disposition ou passent à celle-ci. Entrez donc des valeurs qui sont utiles pour les auteurs de pages.
1. Cliquez sur **OK**.

La disposition prédéfinie sera désormais disponible lorsque vous créez des pages ou sélectionnez une disposition différente pour une page dans la même hiérarchie de modèle.

> [!TIP]
> Pour afficher rapidement si une page spécifique est actuellement associée à une disposition prédéfinie, sélectionnez la page dans la vue de liste de page, et inspectez les métadonnées de mise en page dans le volet de propriété à droite.

### <a name="create-a-new-preset-layout"></a>Créer une dispositions prédéfinie

Pour créer une disposition prédéfinie de zéro, procédez comme suit.

1. Dans le volet de navigation sur la gauche, sélectionnez **Dispositions**.
1. Sélectionner **Nouvelle disposition**. La boîte de dialogue **Nouvelle disposition** apparaît.
1. Sélectionnez le modèle à utiliser pour une disposition prédéfinie.
1. Entrez un nom et une description pour la disposition prédéfinie. Les valeurs entrées sont affichées à d'autres auteurs lorsqu'ils créent des pages dans votre disposition ou passent à celle-ci. Entrez donc des valeurs qui sont utiles pour les auteurs de pages.
1. Sélectionnez **OK** pour créer une disposition prédéfinie et ouvrir l'éditeur de disposition.
1. Dans l'éditeur de disposition, ajoutez et configurez les modules à l'aide de l'arborescence de contour à gauche et du volet de propriété à droite. (Le processus est semblable à celui pour ajouter et configurer des modules pour un modèle dans l'éditeur de modèle.) L'organisation des modules et de tous les paramètres par défaut verrouillés devient la configuration de module centralisée pour toutes les pages qui utilisent cette disposition prédéfinie.

## <a name="modify-a-preset-layout"></a>Modification d'une disposition prédéfinie

Pour modifier une disposition prédéfinie, procédez comme suit.

1. Dans le volet de navigation sur la gauche, sélectionnez **Dispositions**.
1. Dans l'éditeur de disposition, dans l'arborescence de contour à gauche, sélectionnez le module à modifier. Suivez ensuite l'une des procédures suivantes :

    - Pour déplacer un module vers le haut ou vers le bas à l'intérieur de son parent, sélectionnez le bouton représentant des points de suspension (**...**) pour le module, puis sélectionnez **Déplacer vers le haut** ou **Déplacer vers le bas**.
    - Pour modifier les paramètres par défaut d'un module, utilisez le volet de propriété pour entrer des valeurs par défaut et les verrouiller (facultatif) pour toutes les pages en aval.
    - Pour ajouter de nouveaux modules ou fragments aux modules de conteneur, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Ajouter un module** ou **Ajouter un fragment**.
    - Pour supprimer un module de la disposition, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Supprimer**.

## <a name="change-a-preset-layout-theme"></a>Modification d'un thème de disposition prédéfinie

Une pratique typique consiste à définir un thème par défaut pour toutes les pages qui utilisent une disposition prédéfinie.

Pour définir ou modifier le thème pour toutes les pages enfants qui utilisent une disposition prédéfinie, procédez comme suit.

1. Dans l'éditeur de disposition, dans l'arborescence de contour à gauche, sélectionnez le module de conteneur de page. (Généralement, ce module est le deuxième nœud et est appelé **Page par défaut**.)
1. Dans le volet de propriété de droite, dans le champ **Thème**, sélectionnez un thème.

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a>Enregistrer, archiver, afficher un aperçu et publier une disposition prédéfinie

Pour enregistrer et archiver dans votre disposition prédéfinie, procédez comme suit.

1. Sélectionnez **Enregistrer** en haut de l'éditeur de disposition. Les modifications enregistrées n'affectent pas les pages en aval tant qu'elles ne sont pas archivées.
1. Sélectionnez **Archiver**. Vos modifications sont désormais découvrables pour les workflows en aval.

Pour afficher les modifications en aperçu, ouvrez une page existante qui utilise la disposition prédéfinie ou créez une page à partir de la disposition.

Après avoir prévisualisé les modifications de votre disposition prédéfinie, suivez l'une de ces étapes pour publier la disposition sur votre site en direct :

* Accédez à **Dispositions**, sélectionnez la disposition, puis sélectionnez **Publier**.
* Dans l'éditeur de disposition, sélectionnez **Publier**.
* Publiez une page qui référence la disposition non publiée. La disposition est automatiquement publiée.

> [!WARNING]
> Les dispositions prédéfinies peuvent être référencées par plusieurs pages. Lorsque vous publiez une disposition prédéfinie, notez que vous pouvez affecter la disposition de plusieurs pages.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md)

[Utiliser des modèles](work-with-templates.md)
