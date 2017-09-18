--- 
title: " Configurations de paramètres pour des relevés de vente au détail"
description: "Cette procédure illustre les configurations de paramètres des ventes au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: ba3b528f8739e4e84ffdbeea5d0af5817f2d9c10
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="parameter-configurations-for-retail-statements"></a> Configurations de paramètres pour des relevés de vente au détail

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure illustre les configurations de paramètres des ventes au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Commerce et vente au détail > Configuration du siège > Paramètres > Paramètres des ventes au détail.
2. Cliquer sur l'onglet Validation.
    * Sélectionnez « oui » si vous souhaitez valider les montants de remise exceptionnelle spécifiquement.  
    * Sélectionnez le « Standard » pour utiliser des comptes par défaut, ou sélectionnez « Périodique » si vous souhaitez définir le compte à utiliser pour chaque remise exceptionnelle.  
    * Sélectionnez « Récapitulatif » si les lignes de stock doivent être agrégées dès lors que cela est possible.  
    * Sélectionnez « Oui » si les factures et les paiements doivent être automatiquement réglées dans le cadre du processus de validation de relevé.  
    * Sélectionnez « Oui » si les transactions de mise en coffre-fort doivent être agrégées.  
    * Sélectionnez « Oui » si les transactions de remise en banque doivent être agrégées.  
    * Sélectionnez « Oui » pour activer l'agrégation pour la validation de relevé.  
    * Sélectionnez « Oui » pour créer et traiter les commandes en parallèle lorsque les relevés sont validés.  
    * Spécifiez le nombre maximum de commandes à traiter dans chaque tâche de traitement par lots.  
3. Cliquez sur Enregistrer.

