--- 
title: Reclassifier des immobilisations
description: "Pour reclassifier une immobilisation, vous devez la transférer à un nouveau groupe d'immobilisations ou lui affecter un nouveau numéro d'immobilisation au sein du même groupe."
author: saraschi2
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fda4d71b050edde2752536985b18ebcad203d078
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="reclassify-fixed-assets"></a>Reclassifier des immobilisations

[!include[task guide banner](../../includes/task-guide-banner.md)]

Pour reclassifier une immobilisation, vous devez la transférer à un nouveau groupe d'immobilisations ou lui affecter un nouveau numéro d'immobilisation au sein du même groupe. 

Lorsqu'une immobilisation est reclassifiée :

• Tous les modèles de valeur de l'immobilisation existante sont créés pour la nouvelle immobilisation. Les informations paramétrées pour l'immobilisation originale sont copiées vers la nouvelle immobilisation. Le statut des modèles de valeur de l'immobilisation originale est Clôturé. 

• Les nouveaux modèles de valeur des nouvelles immobilisations indiquent la date de reclassification dans le champ Date d'acquisition. La date dans le champ Date d'exécution de l'amortissement est copiée à partir des informations originales relatives à l'actif. Si l'amortissement a déjà commencé, le champ Date du dernier amortissement affiche la date de la reclassification. 

• Les transactions d'immobilisation existantes relatives à l'immobilisation originale sont annulées et regénérées pour la nouvelle immobilisation.

1. Allez dans Immobilisations > Tâches périodiques > Reclassement.
2. Dans le champ Groupe d'immobilisations, sélectionnez le groupe à reclasser.
3. Dans le champ Numéro d'immobilisation, sélectionnez l'immobilisation à reclasser.
4. Dans le champ Nouveau groupe d'immobilisations, sélectionnez un groupe vers lequel transférer l'immobilisation.
    * Si le nouveau groupe d'immobilisations est associé à une souche de numéros, le champ Nouveau numéro d'immobilisation est mis à jour avec le numéro de la nouvelle souche de numéros du groupe d'immobilisations. Sinon, le champ Nouveau numéro d'immobilisation est mis à jour avec le numéro de la nouvelle souche de numéros configuré dans la page Paramètres d'immobilisation. Si une souche de numéros n'est pas configurée dans la page Paramètres d'immobilisation, entrez un nombre dans le champ Nouveau numéro d'immobilisation.  
5. Dans le champ Date de reclassification, entrez une date.
6. Dans le champ Souche de N° documents, entrez ou sélectionnez une valeur.
7. Cliquez sur OK.


