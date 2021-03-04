---
title: Améliorer le modèle de prévision (version préliminaire)
description: Cette rubrique décrit les fonctionnalités que vous pouvez utiliser pour améliorer les performances des modèles de prédiction.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 23c9062dcc13951792306c955b54cae6f656fec5
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646077"
---
# <a name="improve-the-prediction-model-preview"></a>Améliorer le modèle de prévision (version préliminaire)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique décrit les fonctionnalités que vous pouvez utiliser pour améliorer les performances des modèles de prédiction. Vous commencez à améliorer votre modèle dans l’espace de travail **Prédictions de paiement client** dans Microsoft Dynamics 365 Finance. Les étapes d’amélioration sont ensuite terminées dans AI Builder.

## <a name="select-historical-outcomes"></a>Sélectionnez les résultats historiques

Vous sélectionnez d’abord un ou plusieurs des trois résultats possibles pour les factures : **À temps**, **En retard**, et **Très tard**. Les trois résultats doivent être sélectionnés. Si vous désactivez la sélection de l’un des résultats, les factures seront filtrées du processus de formation et la précision de la prédiction sera réduite.

[![Confirmer les résultats](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Si votre organisation ne requiert que deux résultats, modifiez les seuils **En retard** et **Très tard** à 0 (zéro) jour. De cette façon, vous réduisez efficacement la prédiction à un état binaire de **À temps** ou **En retard**.

## <a name="select-fields"></a>Sélectionner des champs

Lorsque vous sélectionnez des champs à inclure dans le modèle, sachez que la liste comprend tous les champs disponibles dans l’entité Common Data Service mappée aux données dans le lac de données Azure. Certains de ces champs devraient **ne pas** être sélectionnés. Les champs qui ne doivent pas être sélectionnés appartiennent à l’une des trois catégories suivantes :

- Le champ est obligatoire pour l’entité Common Data Service, mais il n’y a pas de données de sauvegarde pour elle dans le lac de données.
- Le champ est un ID et n’a donc pas de sens pour une fonctionnalité de Machine Learning.
- Le champ représente des informations qui ne seront pas disponibles pendant la prédiction.

Les sections suivantes présentent les champs disponibles pour la facture et les entités client, et répertorient les champs qui doivent **ne pas** être sélectionné pour la formation. La catégorie spécifiée pour chacun de ces champs fait référence aux catégories de la liste précédente.
 
### <a name="invoice-common-data-model-entity"></a>Entité Common Data Model de facture

L’illustration suivante présente les champs disponibles pour l’entité de facture.

[![Champs disponibles pour l’entité de facturation](./media/available-fields.png)](./media/available-fields.png)

Les champs suivants ne doivent pas être sélectionnés pour la formation :

- **Compte de facturation** (catégorie 2)
- **Est fermé** (catégorie 3) – Ce champ est utilisé pour filtrer les factures pour la formation (fermée) et la prédiction (non clôturée).
- **Nom** (catégorie 1)
- **ID source** (catégorie 2)
- **enregistrement source** (catégorie 2)
- **Table source** (catégorie 2)

### <a name="customer-common-data-model-entity"></a>Entité Common Data Model client

L’illustration suivante présente les champs disponibles pour l’entité client.

[![Champs disponibles pour l’entité client](./media/related-entities.png)](./media/related-entities.png)

Le champ suivant ne doit pas être sélectionné pour la formation :

- **Clé unique de ligne** (catégorie 2)

## <a name="filters"></a>Filtres

Les filtres ne prennent actuellement pas en charge le scénario de prédicteur de paiement client. Par conséquent, sélectionnez **Passer cette étape** et passez à la page de résumé.

[![Modèle de mise au point avec filtres](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)

#### <a name="privacy-notice"></a>Avis de confidentialité
Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]