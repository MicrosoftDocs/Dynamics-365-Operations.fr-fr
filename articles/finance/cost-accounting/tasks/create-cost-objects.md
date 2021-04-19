---
title: Créer des objets de coût
description: Cette procédure indique comment créer des objets de coût en important la dimension financière Centre de coût dans le contrôle de gestion via un connecteur de données.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1219cb15ecec7c156579c5cf7c3a3511a141e00b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810052"
---
# <a name="create-cost-objects"></a>Créer des objets de coût 

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment créer des objets de coût en important la dimension financière Centre de coût dans le contrôle de gestion via un connecteur de données. La société fictive USMF a été utilisée pour créer cette procédure. 


## <a name="create-new-cost-objects"></a>Créer des objets de coût
1. Accédez à Contrôle de gestion > Dimensions > Dimensions d’objet de coût.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Connecteur de données pour les membres de la dimension, entrez ou sélectionnez une valeur.
5. Dans le champ Description, entrez une valeur.
6. Cliquez sur Enregistrer.

## <a name="configure-the-data-connector"></a>Configurer le connecteur de données
1. Cliquez sur Configurer le fournisseur du membre de dimension.
    * Sélectionnez CostCenter pour importer la dimension CostCenter dans le contrôle de gestion.  
2. Dans le champ Nom de dimension, sélectionnez Centre de coût.
3. Cliquez sur OK.

## <a name="import-cost-centers"></a>Importer les centres de coût
1. Cliquez sur Importer les membres de la dimension.
2. Cliquez sur OK.

## <a name="view-the-imported-cost-centers"></a>Afficher les centres de coût importés
1. Cliquez sur Afficher les membres de la dimension.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]