---
title: Blocage de commandes
description: "Cette rubrique décrit les blocages sur les commandes à l&quot;aide de Commerce et vente au détail de Dynamics AX."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5e18a488fed92de3278b438af67ae72fdbe229b4
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="order-holds"></a>Blocage de commandes

[!include[banner](includes/banner.md)]


Cette rubrique décrit les blocages sur les commandes à l'aide de Commerce et vente au détail de Dynamics AX.

Une commande peut être mise en attente pour diverses raisons. Par exemple, vous pouvez mettre une commande en attente jusqu'à ce que l'adresse du client ou le mode de paiement soit vérifié, ou jusqu'à ce qu'un responsable puisse revoir la limite de crédit du client. Lors du processus de vente, des commandes client doivent parfois être mises en attente. Par exemple, une commande client peut être mise en attente en raison de problèmes avec un paiement client, en raison d'une suspicion de fraude ou parce qu'un responsable doit réviser la commande. Lorsqu'une commande client est mise en attente, un code de blocage de commande est affecté à la commande client pour indiquer le motif du blocage. Les codes de blocage de commande client sont configurés dans **Ventes et marketing** &gt; **Paramétrage** &gt; **Commandes client** &gt; **Codes de blocage de commande**. Une commande client peut être mise en attente manuellement au moment de la création de la commande ou ultérieurement. En outre, une commande peut être mise en attente automatiquement, en fonction des règles de fraude. Pendant qu'une commande client est en attente, vous devrez peut-être la mettre à jour avec plus d'informations. Sinon, vous souhaitez peut-être contrôler la commande client pendant que vous continuez à travailler dessus. Vous pouvez extraire une commande client, la réenregistrer, et même, remplacer l'extraction d'un autre utilisateur à l'aide de l'atelier de fin de blocage des commandes (**Commerce et vente au détail** &gt; **Clients** &gt; **Blocages de commande**). Lorsqu'une commande est prête à être terminée, vous devez supprimer le blocage avant de terminer le processus de commande.




