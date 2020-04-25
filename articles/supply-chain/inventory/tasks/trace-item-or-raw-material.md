---
title: Suivre un article ou une matière première
description: Cette procédure illustre comment utiliser le suivi d'article pour identifier où les articles ou les matières premières ont été ou sont utilisés.
author: pjacobse
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c39d34773a2b36cbf9477e4bdda8e45491d9c03
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213904"
---
# <a name="trace-an-item-or-raw-material"></a>Suivre un article ou une matière première

[!include [banner](../../includes/banner.md)]

Cette procédure illustre comment utiliser le suivi d'article pour identifier où les articles ou les matières premières ont été ou sont utilisés. Avec cette procédure, vous pouvez identifier un article, le suivre jusqu'à la source, puis le suivre à nouveau en avant via la production et la vente du produit fini. Le processus peut être utilisé pour étudier les clients concernés, les commandes client affectées, et plus. La société fictive USP2 sert d'exemple dans cette procédure.


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a>Suivre un article vers l'arrière à l'aide d'un numéro de lot connu
1. Dans le **Volet de navigation**, accédez à **Modules > Gestion des stocks > Recherches et états > Dimensions de suivi > Suivi d'article**.
2. Dans le champ **Numéro d'article**, sélectionnez « P9100 ».
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Dans le champ **En avant ou En arrière**, sélectionnez « En arrière ».
5. Dans le champ **Numéro de lot**, sélectionnez « as-12-344-01 ».
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Cliquez sur **OK**.

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a>Identifier un article, le suivre vers lavant, puis effectuer une analyse

Le nœud supérieur de l'arborescence représente la quantité disponible de l'article et du lot sélectionné. Vous devez développer les nœuds de l'arborescence pour rechercher l'article sur lequel doit être exécuté le suivi en avant.   
1. Dans l'arborescence, développez les nœuds décrits ci-dessous, puis sélectionnez le dernier nœud.
    
    Développez : « P9100/1/10/as-12-344-01 ● 2 barils ● 7,00 gallons\P9100 ● Prélevé ● Commande client 000072 ● 22/12/2015 ● -1 baril ● -4,00 gallons ● Site=1, Entrepôt=10, Numéro de lot=as-12-344-01\P9100 ● Production B-000050 ● 9/12/2015 ● 7 barils ● 27,00 gallons ● Site=1, Entrepôt=10, Numéro de lot=as-12-344-01 ● Co-produits : P9101 » puis sélectionnez le nœud.     
2. Dans l'arborescence, développez le nœud décrit ci-dessous, puis sélectionnez ce nœud.
    
    À partir du nœud que vous venez de sélectionner, développez « M9103 ● Ligne de production B-000050 ● 12/9/2015 ● -80 kg ● Taille=70, Couleur=OK,Site=1, Entrepôt=10, Numéro de lot=App01 », puis sélectionnez ce nœud.  
3. Cliquez sur **Suivi à partir du nœud**.
4. Cliquez sur **Suivant**.
5. Dans le **volet Actions**, cliquez sur **Suivi**.
    
    Il existe plusieurs options de suivi qui fournissent des informations sur les clients concernés par l'article que vous suivez, et sur les commandes client liées à l'article qui ont été ou non expédiées.   
6. Cliquez sur **Clients**.
7. Fermez la page.
8. Dans le **volet Actions**, cliquez sur **Suivi**.
9. Cliquez sur **Commandes client non expédiées**.
10. Fermez la page.

