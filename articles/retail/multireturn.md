---
title: Retourner des articles pour plusieurs commandes et factures client
description: Cette rubrique décrit la fonctionnalité d'activation des retours pour plusieurs commandes et factures client dans Microsoft Dynamics 365 for Retail.
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
ms.openlocfilehash: c201311028b11121d626e93859a2b98497c047d1
ms.sourcegitcommit: bacec397ee48ac583596be156c87ead474ee07df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "777224"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Retourner des articles pour plusieurs commandes et factures client

[!include [banner](includes/banner.md)]


Dans Dynamics 365 for Finance and Operations version 10.0, les retours peuvent être effectués pour plusieurs commandes et factures, alors que dans les versions antérieures à la version 10,0, les retours ne pouvaient être traités que pour une seule facture à la fois. 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a>Configurer Retail pour prendre en charge les retours pour plusieurs commandes et factures client

1. Accédez à **Paramètres Retail \> Commandes client**.
1. Activez le paramètre **Activer les retours pour plusieurs commandes**. 

## <a name="process-returns"></a>Traiter les retours

Une fois que le paramètre est activé et que les modifications sont synchronisées avec les magasins, le caissier du magasin peut sélectionner plusieurs commandes d'un client pour les retourner.

Lorsque les commandes sont sélectionnées, la liste de tous les produits retournables pour toutes les factures des commandes s'affiche. Le caissier peut ensuite sélectionner les produits à retourner. Un ordre de retour unique sera créé pour tous les produits sélectionnés.
