---
title: Déclarer un ordre de fabrication terminé
description: Cette procédure montre comment déclarer un ordre de fabrication comme terminé.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a35c06874d41ac1209ab38d46227e21708dc03e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838533"
---
# <a name="report-a-production-order-as-finished"></a>Déclarer un ordre de fabrication terminé

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment déclarer un ordre de fabrication comme terminé. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Il s'agit de la sixième des sept procédures expliquant le cycle de vie de l'ordre de fabrication.


## <a name="report-a-production-order-as-finished"></a>Déclarer un ordre de fabrication terminé
1. Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.
    * Sélectionnez un ordre de fabrication ayant le statut Démarré.  
2. Cliquez sur Ordre de fabrication dans le volet Actions.
3. Cliquez sur Déclaration de fin.
    * Dans cette page, vous pouvez confirmer la quantité du produit fini à déclarer terminé.  
4. Cliquez sur l'onglet Général.
5. Définissez la quantité de marchandise sur 18.
6. Définissez la quantité erronée sur 2.
7. Dans le champ Cause de l'erreur, sélectionnez « Matériel ».
8. Activez ou désactivez la case à cocher Tâche de fin.
9. Activez ou désactivez la case à cocher Accepter les erreurs.
10. Cliquez sur OK.

## <a name="verify-the-report-as-finished-journal"></a>Vérifiez le journal Déclarer comme terminé.
1. Cliquez sur Afficher dans le volet Actions.
2. Cliquez sur Déclarer comme terminé.
3. Dans la liste, marquez la ligne sélectionnée.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Le journal Déclarer comme terminé est validé. Si vous souhaitez effectuer des ajustements du journal, vous pouvez créer manuellement un nouveau journal dans lequel vous pouvez apporter des modifications.  

