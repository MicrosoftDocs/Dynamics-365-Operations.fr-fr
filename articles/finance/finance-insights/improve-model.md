---
title: Améliorer le modèle de prévision (version préliminaire)
description: Cette rubrique décrit les fonctionnalités que vous pouvez utiliser pour améliorer les performances des modèles de prédiction.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 74005d17e2524b922b0fab1aab5350b85dfad771
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355674"
---
# <a name="improve-the-prediction-model-preview"></a>Améliorer le modèle de prévision (version préliminaire)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique décrit les fonctionnalités que vous pouvez utiliser pour améliorer les performances des modèles de prédiction. Vous commencez à améliorer votre modèle dans l’espace de travail **Prédictions de paiement client** dans Microsoft Dynamics 365 Finance. Les étapes d’amélioration sont ensuite terminées dans AI Builder.

## <a name="select-historical-outcomes"></a>Sélectionnez les résultats historiques

Vous sélectionnez d’abord un ou plusieurs des trois résultats possibles pour les factures : **À temps**, **En retard**, et **Très tard**. Les trois résultats doivent être sélectionnés. Si vous désactivez la sélection de l’un des résultats, les factures seront filtrées du processus de formation et la précision de la prédiction sera réduite.

[![Confirmer les résultats.](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Si votre organisation ne requiert que deux résultats, modifiez les seuils **En retard** et **Très tard** à 0 (zéro) jour. De cette façon, vous réduisez efficacement la prédiction à un état binaire de **À temps** ou **En retard**.

## <a name="select-fields"></a>Sélectionner des champs

Lorsque vous sélectionnez des champs à inclure dans le modèle, sachez que la liste comprend tous les champs disponibles dans la table Microsoft Dataverse mappée aux données dans le lac de données Azure. Certains de ces champs devraient **ne pas** être sélectionnés. Les champs qui ne doivent pas être sélectionnés appartiennent à l’une des trois catégories suivantes :

- Le champ est obligatoire pour la table Dataverse, mais il n’y a pas de données de sauvegarde pour elle dans le lac de données.
- Le champ est un ID et n’a donc pas de sens pour une fonctionnalité de Machine Learning.
- Le champ représente des informations qui ne seront pas disponibles pendant la prédiction.

Les sections suivantes présentent les champs disponibles pour la facture et les entités client, et répertorient les champs qui doivent **ne pas** être sélectionné pour la formation. La catégorie spécifiée pour chacun de ces champs fait référence aux catégories de la liste précédente.
 
### <a name="invoice-dataverse-table"></a>Table Dataverse de facturation

L’illustration suivante présente les champs disponibles pour la table de facturation.

[![Champs disponibles pour la table de facturation.](./media/available-fields.png)](./media/available-fields.png)

Les champs suivants ne doivent pas être sélectionnés pour la formation :

- **Compte de facturation** (catégorie 2)
- **Est fermé** (catégorie 3) – Ce champ est utilisé pour filtrer les factures pour la formation (fermée) et la prédiction (non clôturée).
- **Nom** (catégorie 1)
- **ID source** (catégorie 2)
- **enregistrement source** (catégorie 2)
- **Table source** (catégorie 2)

### <a name="customer-dataverse-table"></a>Table Dataverse des clients

L’illustration suivante présente les champs disponibles pour la table client.

[![Champs disponibles pour la table client.](./media/related-entities.png)](./media/related-entities.png)

Le champ suivant ne doit pas être sélectionné pour la formation :

- **Clé unique de ligne** (catégorie 2)

## <a name="filters"></a>Filtres

Vous pouvez filtrer les factures utilisées pour la formation en définissant des critères de filtrage pour les champs de la facture ou dans les tables client. Par exemple, vous pouvez définir un seuil pour inclure uniquement les factures dont le total est égal ou supérieur à un montant spécifique. Vous pouvez également exclure les factures associées aux clients d’un groupe de clients spécifique.

Pour plus d’informations sur le filtrage de vos données, consultez [Créer un modèle de prédiction](https://docs.microsoft.com/ai-builder/prediction-create-model#filter-your-data).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
