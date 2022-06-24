---
title: Descriptif du plan budgétaire
description: Cet article explique comment inclure une description et un récapitulatif des recettes dans un plan budgétaire.
author: v-kiarnd
ms.date: 06/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-kiarnd
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b557257c1a05fc924179a2d19b6ae0f766e3dcee
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898225"
---
# <a name="budget-plan-narrative"></a>Descriptif du plan budgétaire

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Lorsque vous prévoyez de valider des livres ou des documents budgétaires, il est parfois nécessaire d’inclure une description et/ou un résumé des revenus dans un plan budgétaire. Ces informations peuvent inclure une description du plan budgétaire ou une liste d’hypothèses, de mesures de performance, d’informations sur les revenus ou de modifications proposées des services qui ont conduit à des montants sur des lignes budgétaires spécifiques. Cette fonctionnalité vous permettra d’utiliser un éditeur HTML pour contrôler les planificateurs budgétaires afin de documenter les considérations liées à la création du plan.

Vous pouvez utiliser le contrôle pour écrire un nouveau contenu ou coller du contenu qui a été écrit et formaté dans un autre éditeur de texte, tel que Microsoft Word. La zone narrative vous permet également de modifier les polices et la mise en forme du texte. Des fonctionnalités supplémentaires, telles qu’un correcteur orthographique, peuvent être activées.
 
Le contenu ajouté à ces deux sections peut être imprimé séparément dans un rapport descriptif du plan budgétaire.
 
## <a name="setting-up-the-budget-plan-narrative"></a>Mise en place du récit du plan budgétaire

Effectuez les étapes suivantes pour activer la zone narrative du plan budgétaire et utiliser l’éditeur HTML le plus récent disponible dans le produit.
1.  Activez le **Récit du plan budgétaire** sous Gestion des fonctionnalités. Vous pouvez également activer le **Nouveau contrôle de l’éditeur HTML** dans l’espace de travail **Gestion des fonctionnalités** pour utiliser un éditeur plus récent.
2.  Dans le **Module de planification budgétaire**, sélectionnez un plan budgétaire. 
3.  Sélectionnez **En-tête** pour ouvrir la vue **En-tête** et permettre l’accès à la section **Descriptif du plan budgétaire**. Les champs de cette section ne sont généralement pas visibles dans la vue **Ligne**.
4.  Élargissez la section **Récit du plan budgétaire** et ajoutez des descriptions ou des informations sur les revenus à inclure dans le plan budgétaire.

Aucune autorisation complémentaire n’est requise pour modifier le descriptif du plan budgétaire.

## <a name="include-budget-plan-narrative-fields-when-you-copy-budget-plans"></a>Inclure les champs descriptifs du plan budgétaire lorsque vous copiez les plans budgétaires

Suivez ces étapes pour permettre la copie de la description du plan budgétaire et du récapitulatif des recettes dans les nouveaux plans budgétaires.

1. Assurez-vous que la fonctionnalité **Descriptif du plan budgétaire** est activée dans la gestion des fonctionnalités, comme décrit dans la section précédente.
2. Dans la gestion des fonctionnalités, activez la fonctionnalité **Inclure la description du plan budgétaire lors de la copie des plans budgétaires**. Cette fonctionnalité ajoute une section **Descriptif du plan budgétaire** et deux indicateurs utilisés pour la copie du plan budgétaire : **Inclure la description du budget** et **Inclure le récapitulatif des recettes**.
3. Vous pouvez définir les nouveaux indicateurs depuis les pages suivantes :

    - **Plans budgétaires :**

        1. Accédez à **Budgétisation \> Plans budgetaires**.
        2. Sélectionnez le plan budgétaire à copier.
        3. Dans le volet Actions, sous l’onglet **Plan budgétaire**, dans le groupe **Nouveau**, sélectionnez **Copie de**.

        La boîte de dialogue **Copier un plan budgétaire** qui apparaît inclut les nouveaux indicateurs.

    - **Générer un plan budgétaire à partir d’un plan budgétaire :**

        - Accédez à **Budgétisation \> Périodique \> Générer un plan budgétaire à partir d’un plan budgétaire**.

        La page inclut les nouveaux indicateurs. Cependant, les indicateurs ne sont disponibles que lorsque le champ **Action** est défini sur **Créer un plan budgétaire**.

4. Sélectionnez les champs descriptifs à copier dans le nouveau plan. Vous pouvez effectuer cette étape à partir de la page **Plans budgétaires** ou de la page **Générer un plan budgétaire à partir d’un plan budgétaire**.

Une fois le plan budgétaire copié, les champs descriptifs du plan budgétaire sélectionné seront copiés dans le nouveau plan.
