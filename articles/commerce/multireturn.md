---
title: Retourner des articles pour plusieurs commandes et factures client
description: Cette rubrique décrit la fonctionnalité d'activation des retours pour plusieurs commandes et factures client dans Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c5f17424f0837344030f9ce2d2d037cde08c4e49
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004456"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Retourner des articles pour plusieurs commandes et factures client

[!include [banner](includes/banner.md)]


Il est possible d'effectuer des retours pour plusieurs commandes et factures client. 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a>Configurer Commerce pour prendre en charge les retours pour plusieurs commandes et factures client

1. Accédez à **Paramètres commerciaux \> Commandes client**.
1. Activez le paramètre **Activer les retours pour plusieurs commandes**. 

## <a name="process-returns"></a>Traiter les retours

Une fois que le paramètre est activé et que les modifications sont synchronisées avec les magasins, le caissier du magasin peut sélectionner plusieurs commandes d'un client pour les retourner.

Lorsque les commandes sont sélectionnées, la liste de tous les produits retournables pour toutes les factures des commandes s'affiche. Le caissier peut ensuite sélectionner les produits à retourner. Un ordre de retour unique sera créé pour tous les produits sélectionnés.
