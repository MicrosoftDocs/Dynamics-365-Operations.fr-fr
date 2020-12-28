---
title: Expédier des commandes depuis un autre magasin à l'aide de la fonction Facturer l'envoi
description: Cette rubrique décrit la fonction Facturer l'envoi.
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 0bbebcc7b2ab89bf2f5db7294acfca1d8a5ad96e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412259"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a>Expédier des commandes depuis un autre magasin à l'aide de la fonction Facturer l'envoi

[!include [banner](includes/banner.md)]

Avec la fonction Facturer l'envoi de Commerce, les commandes client peuvent être passées dans un magasin et expédiées depuis un autre magasin.

Les commandes client du point de vente (PDV) prennent en charge les plusieurs options d'exécution. Parmi les options d'exécution de commande notons :

- Prélèvement dans le même magasin à une date différente.
- Prélèvement dans un autre magasin à la même date ou à une date différente.
- Expédition depuis l'entrepôt d'expédition affecté par défaut au magasin, et livraison à une date spécifique.

La fonction Facturer l'envoi utilise les opérations du PDV suivantes : Expédier tous les produits et Expédier les produits sélectionnés. Cela permet au commis de magasin de sélectionner l'emplacement d'« expédition » à partir duquel la commande ou la ligne de commande peut être honorée. Par défaut, l'emplacement d'« expédition » est l'entrepôt d'expédition associé au magasin. Toutefois, le commis de magasin peut modifier cet emplacement et sélectionner n'importe quel magasin défini dans le groupe de localisateurs de magasin affecté au magasin.

La capacité de sélectionner des adresses d'« expédition » reste inchangée.

Les méthodes d'expédition qui peuvent être utilisées pour honorer la ligne de commande sont basées sur la configuration de modes de livraison valides pour les produits et les adresses. Du fait que les règles sur les modes de livraison valides sont tenues à jour uniquement dans Siège, un client du PDV effectue un appel en temps réel pour extraire les modes de livraison valides pour une ligne d'expédition.
