---
title: Retourner des articles pour plusieurs commandes et factures client
description: Cette rubrique décrit la fonctionnalité d’activation des retours pour plusieurs commandes et factures client dans Dynamics 365 Commerce.
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4a64794a0e04516441fab628d441640e4d154b8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796889"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Retourner des articles pour plusieurs commandes et factures client

[!include [banner](includes/banner.md)]


Cet article décrit deux fonctionnalités qui optimisent les retours de commandes client sur plusieurs factures. 

## <a name="enable-refunds-over-multiple-captures"></a>Activer les remboursements sur plusieurs captures

Cette fonctionnalité permet plusieurs remboursements liés à la même commande client. 

1. Accédez à l’espace de travail **Gestion des fonctionnalités** et recherchez **Activer les remboursements sur plusieurs captures**.
2. Sélectionnez **Activer les remboursements sur plusieurs commandes**, puis cliquez sur **Activer**. 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Activer le calcul de taxe correct pour les retours avec une quantité partielle

Cette fonctionnalité garantit que lorsqu’une commande est retournée à l’aide de plusieurs factures, les taxes seront finalement égales au montant des taxes initialement facturées. 

1. Accédez à l’espace de travail **Gestion des fonctionnalités** et recherchez **Activer le calcul de taxe correct pour les retours avec une quantité partielle**.
2. Sélectionnez **Activer le calcul de taxe correct pour les retours avec une quantité partielle**, puis cliquez sur **Activer**. 


## <a name="process-returns"></a>Traiter les retours

Une fois ces fonctionnalités activées et les modifications synchronisées avec les magasins, le caissier du magasin peut sélectionner plusieurs commandes d’un client pour les retourner.

Lorsque les commandes sont sélectionnées, la liste de tous les produits retournables pour toutes les factures des commandes s’affiche. Le caissier peut ensuite sélectionner les produits à retourner. Un ordre de retour unique sera créé pour tous les produits sélectionnés.

Si l’ordre est retourné intégralement, le montant des taxes restitué au client sera égal au montant des taxes initialement facturées.



[!INCLUDE[footer-include](../includes/footer-banner.md)]