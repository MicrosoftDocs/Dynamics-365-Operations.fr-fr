---
title: FR-00004 Valider le journal de création et de contestation des lettres de change
description: Cette procédure vous guide au cours des étapes des contestation d'une lettre de change impayée.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustBillOfExchange, CustOpenTrans
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ad05c406b526ced1c61efefc4dfaf999b0e30cc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175129"
---
# <a name="fr-00004-post-protest-draw-bill-of-exchange-journal"></a>FR-00004 Valider le journal de création et de contestation des lettres de change

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous guide au cours des étapes des contestation d'une lettre de change impayée.

Cette procédure a été créée à l'aide des données fictives de la société FRSI. 

Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en France.

Pour effectuer cette procédure, vous devez avoir le rôle de commis à la comptabilité client.



1. Accédez à Comptabilité client > Paiements > Lettre de change > Journal des lettres de change impayées.
2. Cliquez sur Nouveau.
3. Dans la liste, marquez la ligne sélectionnée.
4. Saisissez ou sélectionnez une valeur dans le champ Nom.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez « LitigeEAR »  
6. Cliquez sur Lignes.
7. Dans la liste, marquez la ligne sélectionnée.
8. Dans le champ Compte, spécifiez les valeurs « FR_SI_0001 ».
9. Cliquez sur Régler les transactions.
10. Dans la liste, marquez la ligne sélectionnée.
    * Marquer le journal de création de lettres de change le plus récemment validé  
11. Cochez la case Marquer.
12. Cliquez sur OK.
13. Cliquez sur Valider.
14. Accédez à Comptabilité client > Recherches et états > Paiements > Journal des lettres de change.
    * Vérifiez que le statut du journal récemment validé est Impayés. Si c'est le cas, le processus est terminé.  
