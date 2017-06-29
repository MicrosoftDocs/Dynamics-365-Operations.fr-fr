---
title: "Tenir à jour les ordres prévisionnels"
description: "Cet article fournit des informations sur la gestion des ordres prévisionnels. Il décrit la manière dont vous pouvez mettre à jour le statut des ordres prévisionnels, les confirmer et filtrer les ordres prévisionnels ayant le même statut qu'un ordre prévisionnel sélectionné."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 94f6f28ec4b255930f84a27eb5394503ff59e4c0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="maintain-planned-orders"></a>Tenir à jour les ordres prévisionnels

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur la gestion des ordres prévisionnels. Il décrit la manière dont vous pouvez mettre à jour le statut des ordres prévisionnels, les confirmer et filtrer les ordres prévisionnels ayant le même statut qu'un ordre prévisionnel sélectionné.

Vous pouvez gérer les ordres prévisionnels à partir de l'espace de travail **Planification**, de la liste **Ordre prévisionnel** ou des listes **Ordres de fabrication prévisionnels**, **Commandes fournisseur prévisionnelles** et **Transfert prévisionnel**. Vous pouvez utiliser le champ **Statut** pour aider à suivre la progression. Les valeurs suivantes sont utilisées :

-   Lorsque la planification génère des ordres prévisionnels, leur statut est **Non traité**.
-   Si vous décidez de ne pas confirmer un ordre prévisionnel, vous pouvez lui attribuer le statut **Terminé**.
-   Si vous décidez de confirmer un ordre prévisionnel, vous pouvez lui attribuer le statut **Approuvé**. Ce statut indique que vous approuvez la confirmation de l'ordre prévisionnel, mais que celui-ci n'est pas encore confirmé.

**Remarque :** un ordre prévisionnel approuvé est transféré dans son état actuel vers le calcul de planification suivant. Vous pouvez confirmer les ordres prévisionnels en cliquant sur **Confirmer**. Vous pouvez confirmer les ordres prévisionnels suivants :

-   Ordre prévisionnel sélectionné.
-   Plusieurs ordres prévisionnels.
-   Ordres prévisionnels générés par un éclatement dans la page **Éclatement**. Cliquez sur **Ordres prévisionnels**, sélectionnez l'ordre prévisionnel, puis cliquez sur **Confirmer**.

Après confirmation, l'ordre prévisionnel est déplacé vers la section Commandes du module approprié. **Remarque :** vous pouvez cliquer avec le bouton droit sur un ordre prévisionnel ayant un statut particulier et effectuer un filtrage afin de trouver d'autres ordres prévisionnels avec le même statut. Cette fonctionnalité est utile si, par exemple, vous souhaitez filtrer tous les ordres prévisionnels ayant le statut **Approuvé**, afin de les confirmer.

<a name="see-also"></a>Voir également :
--------

[Plans généraux](master-plans.md)




