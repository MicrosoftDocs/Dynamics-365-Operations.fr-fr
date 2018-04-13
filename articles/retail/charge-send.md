---
title: "Expédier une commande depuis un autre magasin"
description: "Cette rubrique décrit la fonction Facturer l'envoi."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 797058bdbbdb63a08eb35034ffe3c913307f38df
ms.openlocfilehash: 41434614b01f9a00f2b8a56765ecb90ee07e3d90
ms.contentlocale: fr-fr
ms.lasthandoff: 03/05/2018

---

# <a name="ship-an-order-from-a-different-store"></a>Expédier une commande depuis un autre magasin

[!INCLUDE [banner](includes/banner.md)]

Avec la fonction Facturer l'envoi de Dynamics 365 for Retail, les commandes client peuvent être passées dans un magasin et expédiées depuis un autre magasin. Les commandes client du point de vente (PDV) prennent en charge les plusieurs options d'exécution. Parmi les options d'exécution de commande notons :
-   Prélèvement dans le même magasin à une date différente.
-   Prélèvement dans un autre magasin à la même date ou à une date différente.
-   Expédition depuis l'entrepôt d'expédition affecté par défaut au magasin, et livraison à une date spécifique.

La fonction Facturer l'envoi utilise les opérations du PDV suivantes : Expédier tous les produits et Expédier les produits sélectionnés. Cela permet au commis de magasin de sélectionner l'emplacement d'« expédition » à partir duquel la commande ou la ligne de commande peut être honorée. Par défaut, l'emplacement d'« expédition » est l'entrepôt d'expédition associé au magasin. Toutefois, le commis de magasin peut modifier cet emplacement et sélectionner n'importe quel magasin défini dans le groupe de localisateurs de magasin affecté au magasin. 

La capacité de sélectionner des adresses d'« expédition » reste inchangée. 

Les méthodes d'expédition qui peuvent être utilisées pour honorer la ligne de commande sont basées sur la configuration de modes de livraison valides pour les produits et les adresses. Du fait que les règles sur les modes de livraison valides sont tenues à jour uniquement dans Retail Siège, un client du PDV effectue un appel en temps réel pour extraire les modes de livraison valides pour une ligne d'expédition. 


