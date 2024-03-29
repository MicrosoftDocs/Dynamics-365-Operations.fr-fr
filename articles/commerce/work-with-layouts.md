---
title: Utilisation des dispositions prédéfinies
description: Cet article décrit l’utilisation des dispositions prédéfinies dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: b588df5702657f07e1e790ffba39d2e459901557
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286274"
---
# <a name="work-with-preset-layouts"></a>Utilisation des dispositions prédéfinies

[!include [banner](includes/banner.md)]

Cet article décrit l’utilisation des dispositions prédéfinies dans Microsoft Dynamics 365 Commerce.

Avant d’exécuter les procédures décrites dans cet article, assurez-vous de lire [Dispositions prédéfinies et personnalisées](templates-layouts-overview.md#preset-and-custom-layouts). Pour obtenir une vue d’ensemble générale, voir [Vue d’ensemble des modèles et dispositions](templates-layouts-overview.md).

## <a name="create-a-new-preset-layout"></a>Créer une dispositions prédéfinie

Il existe deux méthodes pour créer une dispositions prédéfinie. Vous pouvez enregistrer une disposition personnalisée existante comme nouvelle disposition prédéfinie, ou créer une disposition prédéfinie créée de toutes pièces.

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a>Créer une disposition prédéfinie à partir d’une disposition personnalisée existante

Pour créer une disposition prédéfinie à partir d’une disposition personnalisée existante; procédez comme suit.

1. Ouvrez une page existante qui n’utilise pas actuellement de disposition prédéfinie, et qui a une structure de module que vous souhaitez réutiliser pour d’autres pages sur votre site.
1. Sélectionnez **Edition** pour consulter la page.
1. Sélectionnez **Enregistrer comme nouvelle disposition**. La boîte de dialogue **Enregistrer comme nouvelle disposition** apparaît.
1. Entrez un nom et une description pour la disposition prédéfinie. Les valeurs entrées sont affichées à d’autres auteurs lorsqu’ils créent des pages dans votre disposition ou passent à celle-ci. Entrez donc des valeurs qui sont utiles pour les auteurs de pages.
1. Cliquez sur **OK**.

La disposition prédéfinie sera désormais disponible lorsque vous créez des pages ou sélectionnez une disposition différente pour une page dans la même hiérarchie de modèle.

> [!TIP]
> Pour afficher rapidement si une page spécifique est actuellement associée à une disposition prédéfinie, sélectionnez la page dans la vue de liste de page, et inspectez les métadonnées de mise en page dans le volet de propriété à droite.

### <a name="create-a-new-preset-layout"></a>Créer une dispositions prédéfinie

Pour créer une disposition prédéfinie de zéro, procédez comme suit.

1. Dans le volet de navigation sur la gauche, sélectionnez **Dispositions**.
1. Sélectionner **Nouvelle disposition**. La boîte de dialogue **Nouvelle disposition** apparaît.
1. Sélectionnez le modèle à utiliser pour une disposition prédéfinie.
1. Entrez un nom et une description pour la disposition prédéfinie. Les valeurs entrées sont affichées à d’autres auteurs lorsqu’ils créent des pages dans votre disposition ou passent à celle-ci. Entrez donc des valeurs qui sont utiles pour les auteurs de pages.
1. Sélectionnez **OK** pour créer une disposition prédéfinie et ouvrir l’éditeur de disposition.
1. Dans l’éditeur de disposition, ajoutez et configurez les modules à l’aide de l’arborescence de contour à gauche et du volet de propriété à droite. (Le processus est semblable à celui pour ajouter et configurer des modules pour un modèle dans l’éditeur de modèle.) L’organisation des modules et de tous les paramètres par défaut verrouillés devient la configuration de module centralisée pour toutes les pages qui utilisent cette disposition prédéfinie.

## <a name="modify-a-preset-layout"></a>Modification d’une disposition prédéfinie

Pour modifier une disposition prédéfinie, procédez comme suit.

1. Dans le volet de navigation sur la gauche, sélectionnez **Dispositions**.
1. Dans l’éditeur de disposition, dans l’arborescence de contour à gauche, sélectionnez le module à modifier. Suivez ensuite l’une des procédures suivantes :

    - Pour déplacer un module vers le haut ou vers le bas à l’intérieur de son parent, sélectionnez le bouton représentant des points de suspension (**...**) pour le module, puis sélectionnez **Déplacer vers le haut** ou **Déplacer vers le bas**.
    - Pour modifier les paramètres par défaut d’un module, utilisez le volet de propriété pour entrer des valeurs par défaut et les verrouiller (facultatif) pour toutes les pages en aval.
    - Pour ajouter de nouveaux modules ou fragments aux modules de conteneur, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Ajouter un module** ou **Ajouter un fragment**.
    - Pour supprimer un module de la disposition, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Supprimer**.

## <a name="change-a-preset-layout-theme"></a>Modification d’un thème de disposition prédéfinie

Une pratique typique consiste à définir un thème par défaut pour toutes les pages qui utilisent une disposition prédéfinie.

Pour définir ou modifier le thème pour toutes les pages enfants qui utilisent une disposition prédéfinie, procédez comme suit.

1. Dans l’éditeur de disposition, dans l’arborescence de contour à gauche, sélectionnez le module de conteneur de page. (Généralement, ce module est le deuxième nœud et est appelé **Page par défaut**.)
1. Dans le volet de propriété de droite, dans le champ **Thème**, sélectionnez un thème.

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a>Enregistrer, archiver, afficher un aperçu et publier une disposition prédéfinie

Pour enregistrer et archiver dans votre disposition prédéfinie, procédez comme suit.

1. Sélectionnez **Enregistrer** en haut de l’éditeur de disposition. Les modifications enregistrées n’affectent pas les pages en aval tant qu’elles ne sont pas archivées.
1. Sélectionnez **Terminer la modification**. Vos modifications sont désormais découvrables pour les workflows en aval.

Pour afficher les modifications en aperçu, ouvrez une page existante qui utilise la disposition prédéfinie ou créez une page à partir de la disposition.

Après avoir prévisualisé les modifications de votre disposition prédéfinie, suivez l’une de ces étapes pour publier la disposition sur votre site en direct :

1. Accédez à **Dispositions**, sélectionnez la disposition, puis sélectionnez **Publier**.
1. Sélectionnez le nom de la disposition pour ouvrir l’éditeur de disposition, puis cliquez sur **Publier**.
1. Publiez une page qui référence la disposition non publiée. La disposition est automatiquement publiée.

> [!WARNING]
> Les dispositions prédéfinies peuvent être référencées par plusieurs pages. Lorsque vous publiez une disposition prédéfinie, notez que vous pouvez affecter la disposition de plusieurs pages.

## <a name="rename-a-preset-layout"></a>Renommer une disposition prédéfinie

Pour renommer une disposition prédéfinie dans le générateur de site, procédez comme suit.

1. Dans le volet de navigation de gauche, sélectionnez **Dispositions**.
1. Sélectionnez le nom de disposition que vous souhaitez renommer.
1. Sélectionnez **Modifier** pour commencer à modifier la disposition.
1. Dans le volet des propriétés de la disposition, sélectionnez le symbole du stylo à côté du nom de la disposition.
1. Modifiez le nom de la disposition, le cas échéant.
1. Sélectionnez la coche pour confirmer le changement de nom.
1. Sélectionnez **Terminer la modification**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des modèles et dispositions](templates-layouts-overview.md)

[Utiliser des modèles](work-with-templates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
