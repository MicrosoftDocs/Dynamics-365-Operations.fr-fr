---
title: Blocage de commandes
description: "Cette rubrique décrit les blocages sur les commandes à l&quot;aide de Commerce et vente au détail de Dynamics AX."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1cb18e3275b8dcdf0a61531ee056995f6e8fbc8d
ms.lasthandoff: 03/31/2017


---

# <a name="order-holds"></a>Blocage de commandes

Cette rubrique décrit les blocages sur les commandes à l'aide de Commerce et vente au détail de Dynamics AX.

Une commande peut être mise en attente pour diverses raisons. Par exemple, vous pouvez mettre une commande en attente jusqu'à ce que l'adresse du client ou le mode de paiement soit vérifié, ou jusqu'à ce qu'un responsable puisse revoir la limite de crédit du client. Lors du processus de vente, des commandes client doivent parfois être mises en attente. Par exemple, une commande client peut être mise en attente en raison de problèmes avec un paiement client, en raison d'une suspicion de fraude ou parce qu'un responsable doit réviser la commande. Lorsqu'une commande client est mise en attente, un code de blocage de commande est affecté à la commande client pour indiquer le motif du blocage. Les codes de blocage de commande client sont configurés ** Ventes et marketing ** &gt; ** au paramétrage ** &gt; ** des commandes client ** &gt; ** la commande comprend des codes **. Une commande client peut être mise en attente manuellement au moment de la création de la commande ou ultérieurement. En outre, une commande peut être mise en attente automatiquement, en fonction des règles de fraude. Pendant qu'une commande client est en attente, vous devrez peut-être la mettre à jour avec plus d'informations. Sinon, vous souhaitez peut-être contrôler la commande client pendant que vous continuez à travailler dessus. Vous pouvez vérifier une commande client, la vérifiez de retour dans, puis remplacez même l'extraction d'un autre utilisateur à l'aide de l'atelier de blocage de commande (** au détail et commerce ** &gt; ** les clients ** &gt; ** des blocages d'ordre **). Lorsqu'une commande est prête à être terminée, vous devez supprimer le blocage avant de terminer le processus de commande.


