---
title: Plans de livraison
description: Les plans de livraison vous permettent de suivre la quantité sur la ligne de commande lorsque vous effectuez plusieurs livraisons pour une seule commande client, un devis de vente ou une commande fournisseur.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dfc9467e6c7df70ce749f531bab447513ea3349e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998576"
---
# <a name="delivery-schedules"></a>Plans de livraison

[!include [banner](../includes/banner.md)]

Les plans de livraison vous permettent de suivre la quantité sur la ligne de commande lorsque vous effectuez plusieurs livraisons pour une seule commande client, un devis de vente ou une commande fournisseur.

Utilisez un plan de livraison lorsque la quantité totale d'une ligne de commande ou de devis doit être livrée dans le cadre de plusieurs expéditions. Les expéditions individuelles sont représentées par des lignes de livraison. Deux lignes de livraison ou plus constituent un calendrier de livraison. Les lignes de livraison peuvent avoir des dates de livraison, des quantités, des modes de livraison et des dimensions de stockage différents (telles qu'un site ou un entrepôt).  

**Exemple d'un plan de livraison**

|                                   |                                          |
|-----------------------------------|------------------------------------------|
| Commande totale (ligne de commande d'origine) | 600 chaises                               |
| Calendrier de livraison demandé       | 100 chaises par mois                     |
| Délai de livraison demandé | 6 mois, le premier jour de chaque mois |

Dans ce scénario, le client demande une livraison de 600 chaises en lots de 100 chaises sur une période de six mois. Pour assurer le suivi des exigences de livraison, vous créez un plan de livraison. Dans la page Plan de livraison, vous créez six lignes de livraison distinctes. Chaque ligne de livraison contient 100 chaises et indique la date de livraison de celles-ci. Dans ce cas, chaque ligne est décalée sur le premier du mois pendant six mois consécutifs.  

Lorsque vous créez un plan de livraison, le type de la ligne de commande d'origine passe automatiquement à **Ligne de commande avec livraisons multiples**. Une ligne de ce type est appelée une ligne commerciale et est marquée par une icône. La ligne de livraison est marquée par une icône différente. Si vous modifiez une quantité sur une ligne de livraison, la ligne commerciale est mise à jour en fonction de la quantité totale du plan de livraison. Si un accord commercial a défini une remise totale pour la commande, le calendrier de livraison garantit que votre commande est éligible pour cette remise, même si la commande est fractionnée en plusieurs livraisons.  

Les commandes contenant un plan de livraison sont traitées par rapport aux lignes de livraison. Le traitement inclut la validation des bons de livraison, des accusés de réception de marchandises et des factures.  

Les impressions des commandes et des devis contenant un plan de livraison affichent uniquement les lignes de livraison. Elles n'affichent pas les lignes d'origine (lignes commerciales). **Remarque :** en outre, seules les lignes de livraison sont affichées lorsque vous exécutez les actions suivantes :

-   Valider
-   Copier des pages
-   Parcourir les pages de listes et les états

Lorsque vous confirmez des devis de vente, les commandes client générées affichent l'ensemble du plan de livraison, même les lignes de commande contenant plusieurs livraisons. En outre, l'ensemble du plan de livraison s'affiche sur toutes les pages principales (commandes client, devis de vente et commandes fournisseur).



