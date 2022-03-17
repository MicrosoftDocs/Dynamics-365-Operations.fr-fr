---
title: Activer la gestion cohérente du mode de livraison dans les canaux de commerce électronique
description: Cette rubrique décrit comment activer la gestion cohérente du mode de livraison pour résoudre les problèmes éventuels liés aux flux de frais dans les canaux de commerce électronique Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 4cecd70dacd72572afc8e6cb65530bf2be4cc93d
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349949"
---
# <a name="enable-consistent-delivery-mode-handling-in-e-commerce-channels"></a>Activer la gestion cohérente du mode de livraison dans les canaux de commerce électronique 

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment activer la gestion cohérente du mode de livraison pour résoudre les problèmes éventuels liés aux flux de frais dans les canaux de commerce électronique Microsoft Dynamics 365 Commerce.

Dans Dynamics 365 Commerce, les frais non calculés au prorata au niveau de l’en-tête ne sont pas appliqués par défaut dans les canaux de commerce électronique. Ce comportement peut entraîner l’un ou l’autre des problèmes suivants dans les canaux de commerce électronique :

- Les frais non calculés au prorata au niveau de l’en-tête n’apparaissent pas.
- Les frais pour les modes de livraison ne sont pas cohérents entre le mode de livraison sélectionné et le récapitulatif de la commande de paiement.

Pour résoudre ces problèmes, vous devez activer la fonctionnalité **Activer la gestion cohérente du mode de livraison dans le canal**. Cette fonctionnalité garantit que les frais non calculés au prorata au niveau de l’en-tête apparaissent dans les canaux de commerce électronique et que les informations de livraison des commandes client sont traitées de manière cohérente par le même flux de travail de demande.

## <a name="turn-on-the-enable-consistent-delivery-mode-handling-in-channel-feature"></a>Activer la fonctionnalité Activer la gestion cohérente du mode de livraison dans le canal

Pour activer la fonctionnalité **Activer la gestion cohérente du mode de livraison dans le canal** dans Commerce Headquarters, procédez comme suit.

1. Ouvrez l’espace de travail **Gestion des fonctionnalités** (**Administration du système \> Espaces de travail \> Gestion des fonctionnalités**).
1. Dans la liste des fonctionnalités disponibles, recherchez et sélectionnez **Activer la gestion cohérente du mode de livraison dans le canal**.
1. Dans le volet droit, sélectionnez **Activer maintenant**.
