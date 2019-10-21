---
title: Retourner des articles pour plusieurs commandes et factures client
description: Cette rubrique décrit la fonctionnalité d'activation des retours pour plusieurs commandes et factures client dans Dynamics 365 Retail.
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
ms.openlocfilehash: 25a1081e5f903076e23089c41dda7437f8a70124
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017987"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Retourner des articles pour plusieurs commandes et factures client

[!include [banner](includes/banner.md)]


Il est possible d'effectuer des retours pour plusieurs commandes et factures client. 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a>Configurer Retail pour prendre en charge les retours pour plusieurs commandes et factures client

1. Accédez à **Paramètres des ventes au détail \> Commandes client**.
1. Activez le paramètre **Activer les retours pour plusieurs commandes**. 

## <a name="process-returns"></a>Traiter les retours

Une fois que le paramètre est activé et que les modifications sont synchronisées avec les magasins, le caissier du magasin peut sélectionner plusieurs commandes d'un client pour les retourner.

Lorsque les commandes sont sélectionnées, la liste de tous les produits retournables pour toutes les factures des commandes s'affiche. Le caissier peut ensuite sélectionner les produits à retourner. Un ordre de retour unique sera créé pour tous les produits sélectionnés.
