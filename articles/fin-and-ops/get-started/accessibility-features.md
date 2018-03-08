---
title: "Fonctions d'accessibilité"
description: "Cette rubrique décrit les fonctionnalités conçues pour aider les utilisateurs ayant divers handicaps à utiliser Dynamics 365 for Finance and Operations, Enterprise Edition, Dynamics 365 for Retail et Dynamics 365 for Talent."
author: TLeforMicrosoft
manager: AnnBe
ms.date: 01/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a523ff097eedf9a4a2cb0341b3be9d05abfa09fa
ms.openlocfilehash: 42b4f670dee95c073ce8dcca16afef83bbf78ff8
ms.contentlocale: fr-fr
ms.lasthandoff: 01/23/2018

---

# <a name="accessibility-features"></a>Fonctions d'accessibilité

[!include[banner](../includes/banner.md)]

Cette rubrique décrit les fonctionnalités conçues pour aider les utilisateurs ayant divers handicaps à utiliser Dynamics 365 for Finance and Operations, Enterprise Edition, Dynamics 365 for Retail et Dynamics 365 for Talent. Par exemple, il existe des fonctionnalités pour les personnes qui utilisent des technologies d'assistance visuelle telles que Microsoft Windows Narrator.

## <a name="windows-narrator-and-keyboard-only-access"></a>Windows Narrator et accès par clavier uniquement

Chaque champ et contrôle comporte une étiquette et une description des raccourcis applicables. Un lecteur d'écran peut lire l'étiquette et la description.

## <a name="shortcuts-for-the-most-frequently-performed-actions"></a>Raccourcis pour les actions les plus fréquemment exécutées

Pour la plupart des utilisateurs, l'utilisation quotidienne du système implique beaucoup de saisies de données et d'interactions du clavier. Pour améliorer l'expérience de l'utilisateur, nous avons créé des raccourcis pour vous aider à « naviguer » dans l'écran et des raccourcis pour des actions spécialisées. Pour plus d'informations, voir [Raccourcis clavier](shortcut-keys.md).

## <a name="navigation-search"></a>Recherche de navigation

Toute page accessible à l'aide du menu du volet de navigation, c'est-à-dire le volet le plus à gauche, est également accessible à partir de la zone de **Recherche**. Appuyez sur Alt+G pour activer la zone de **Recherche**, puis tapez le nom ou la description de la page.

![« Compte bancaire » saisi dans la zone de recherche](media/6d08b0be32808221023e2aa92d69fd70.png)

Pour plus d'informations, voir [Recherche lors de la navigation](navigation-search.md).

> [!NOTE]
> Vous pouvez accéder directement aux pages de niveau supérieur uniquement. Les pages secondaires se basent sur les informations ou le contexte de leur page parente.

## <a name="action-search-for-keyboard-only-users-or-for-heads-down-data-entry"></a>Recherche d'actions pour les utilisateurs qui utilisent le clavier uniquement ou pour la saisie de données

Chaque action disponible sur une page est accessible à partir d'un clavier, via la séquence de tabulations. Les informations sur la séquence de tabulations sont fournies plus loin dans cette rubrique. Pour exécuter des actions plus directement, vous pouvez utiliser la fonctionnalité de recherche d'actions.

### <a name="example"></a>Exemple

Vous souhaitez exécuter l'action **Journal de notification par e-mail** qui s'affiche dans le groupe **Notification par e-mail** de l'onglet **Commande client** du volet Actions.

![Action Journal de notification par e-mail du volet Actions](media/f0d78399e7fafcd85ded1cd1e3d34f3c.jpg)

Une option consiste à utiliser le clavier. Appuyez sur Ctrl+F6 pour activer le volet Actions, puis appuyez sur Tab à plusieurs reprises pour parcourir les onglets et actions, jusqu'à ce que l'action **Journal de notification par e-mail** soit active.

Toutefois, vous pouvez également exécuter l'action plus directement. À partir de n'importe quel emplacement sur la page, appuyez sur Ctrl+Apostrophe (') pour afficher la zone de recherche d'actions.

![Zone de recherche d'actions](media/80f7e8c5ac412fdf2c8a12f7728f135a.jpg)

Dans la zone de recherche, tapez des mots qui décrivent l'action. L'action devient accessible, et vous pouvez l'exécuter directement. Par exemple, en tapant **e-mail**, **notific** (mot partiel) ou **journal**, vous pouvez « accéder » à la fonctionnalité Journal de notification par e-mail.

![« E-mail » saisi dans la zone de recherche](media/image4.png) ![« Notific » saisi dans la zone de recherche](media/image5.png) ![« Journal » saisi dans la zone de recherche](media/image6.png)

Lorsque vous avez terminé, vous pouvez appuyer à nouveau sur Ctrl+Apostrophe pour activer le champ que vous utilisiez avant d'exécuter la recherche d'actions.

Pour plus d'informations, voir [Recherche d'actions](action-search.md).

## <a name="tab-sequence"></a>Séquence de tabulations

Lors de l'utilisation quotidienne du système, certains champs sont obligatoires pour exécuter des tâches courantes. Par conséquent, la séquence de tabulations « est optimisée » par défaut. Les taquets de tabulation sont définis uniquement sur les champs qui sont essentiels pour les scénarios courants.

Toutefois, il se peut que certains champs que vous utilisez souvent pour exécuter des tâches ne soient pas inclus dans la séquence de tabulations par défaut. Dans ce cas, si vous utilisez Windows Narrator, vous pouvez utiliser les actions du clavier de Windows Narrator pour accéder à ces champs et inspecter leur contenu. Vous pouvez également activer l'option **Séquence des tabulations améliorées** sur la page **Options**. Cette option permet à tous les champs modifiables et en lecture seule de faire partie de la séquence de tabulations. Vous pouvez ensuite utiliser la personnalisation de page pour créer une séquence de tabulations personnalisée et omettre les champs qui ne doivent pas faire partie de la séquence de tabulations. Pour plus d'informations sur la personnalisation, voir [Personnaliser l'expérience de l'utilisateur](personalize-user-experience.md).

![Option Séquence des tabulations améliorées](media/8c0f12bbb3f26032997ef0ba95d89b6a.png)

## <a name="form-patterns"></a>Modèles d'écran

Presque 90 % des pages du produit sont basées sur un petit ensemble de modèles. Ces modèles sont appelés *modèles d'écran*. Chaque modèle d'écran permet de fournir les actions les plus souvent exécutées sur la page. Un modèle d'écran permet de garantir la familiarité et la facilité de compréhension, car les actions et les données fréquemment utilisées sont toujours présentées au même emplacement sur différentes pages. En raison du nombre limité de modèles d'écran, les utilisateurs peuvent facilement se familiariser avec le système, quel que soit le nombre de pages qu'il contient, et peuvent l'utiliser en toute confiance une fois qu'ils reconnaissent les modèles d'écran.

Pour en savoir plus sur les modèles d'écran, voir [Styles et modèles d'écran](../../dev-itpro/user-interface/form-styles-patterns.md).

## <a name="responsive-layout"></a>Mise en page réactive

Le produit est conçu pour fonctionner sur différents appareils et facteurs de forme, des plus petits écrans aux grands écrans qui ont la résolution la plus élevée. Notre moteur de mise en page réactive permet aux utilisateurs d'effectuer un zoom à un niveau d'agrandissement de 200 % (ou, dans certains scénarios, de plus de 200 %).

## <a name="guidance-to-help-developers-and-customers-incorporate-accessible-thinking-in-their-customizations"></a>Conseils pour aider les développeurs et les clients à incorporer une réflexion accessible dans leurs personnalisations

Pour en savoir plus sur les pratiques recommandées de Microsoft pour activer l'accessibilité, voir [Accessibilité dans les écrans, les produits et les contrôles](../../dev-itpro/user-interface/enable-accessibility.md).

