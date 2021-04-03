---
title: Créer des types de sollicitation et des critères d’attribution pour les demandes de devis
description: Ce guide montre comment créer un type de sollicitation et l’associer à une méthode d’attribution de score.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cf196711799b78d7f4106b6693127d7f356b1d4e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262211"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>Créer des types de sollicitation et des critères d’attribution pour les demandes de devis

[!include [banner](../../includes/banner.md)]

Ce guide montre comment créer un type de sollicitation et l’associer à une méthode d’attribution de score. Il montre également comment utiliser le type de sollicitation sur un appel d’offre qui définit ensuite la méthode d’attribution de score par défaut. Ces tâches sont généralement effectuées par un responsable des achats. Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Vous devez avoir une méthode d’attribution de score disponible avant de commencer.


## <a name="create-a-solicitation-type"></a>Créer un type de sollicitation
1. Allez dans Approvisionnements > Paramétrage > Appel d’offre > Type de sollicitation.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Méthode d’attribution de score, choisissez la méthode d’attribution de score que vous voulez utiliser pour ce type de sollicitation.
6. Cliquez sur Enregistrer.
7. Fermez la page.

## <a name="use-the-solicitation-type"></a>Utiliser le type de sollicitation
1. Accédez à Approvisionnements > Demandes de devis > Toutes les demandes de devis
2. Cliquez sur Nouveau.
3. Dans le champ Type de sollicitation, choisissez le type de sollicitation que vous venez de créer. 
    *   
4. Cliquez sur OK.
5. Cliquez sur Critères d’attribution de score.
    * Les critères d’attribution de score qui sont montrés sont ceux de la méthode d’attribution de score associée au type de sollicitation. Vous pouvez choisir d’ajouter ou de supprimer des critères sur cette page. Il est également possible d’ajouter de nouveaux critères en les copiant à partir d’autres méthodes d’attribution de score.  
6. Cliquez sur Copier les critères.
7. Entrez ou sélectionnez une valeur dans le champ Méthode d’attribution de score.
8. Cliquez sur OK.
9. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]