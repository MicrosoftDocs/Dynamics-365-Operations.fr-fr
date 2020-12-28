---
title: Marquage du stock avec optimisation de la planification
description: Cette rubrique fournit des informations sur les options disponibles pour marquer le stock dans les commandes confirmées lorsque vous utilisez l’optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 99a52c03e519384955d68d7101a7b73b7e9a7af6
ms.sourcegitcommit: fe21a3a98dcf6fe4eb9351941493f2c0443d8696
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2020
ms.locfileid: "4672185"
---
# <a name="inventory-marking-with-planning-optimization"></a>Marquage du stock avec optimisation de la planification

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des informations sur les options disponibles pour marquer le stock dans les commandes confirmées lorsque vous utilisez l’optimisation de la planification.

Le *Marquage* est utilisé pour relier l'offre et la demande. Il ressemble à l'*origine des besoins*, qui indique comment la planification prévoit de couvrir la demande. Du point de vue de la planification, la principale différence est que le marquage est plus permanent que l'origine des besoins.

Le marquage a été introduit pour prendre en charge des scénarios de coûts spéciaux pour le premier entré, premier sorti (FIFO) et le dernier entré, premier sorti (LIFO). Cependant, il est maintenant également utilisé pour certains scénarios sans coût. Le marquage entre l'offre et la demande est facultatif et presque permanent. Le marquage peut être supprimé manuellement par un utilisateur, ou il peut être supprimé en exécutant une explosion de ligne de commande client où l'option **Supprimer le marquage** est sélectionnée.

L'origine des besoins est contrôlé par la planification pendant la couverture pour lier la demande à l'offre requise. L'origine des besoins peut être mis à jour pour chaque cycle de planification afin d'optimiser l'approvisionnement nécessaire pour couvrir la demande. Lorsque la planification met à jour les informations d'origine des besoins, elle respecte tout marquage existant.

L'origine des besoins commence par inclure le marquage pertinent, les réservations disponibles et les réservations sur commande, dans l'ordre suivant :

1. Marquage entre demande et offre
1. Réservations disponibles
1. Réservation sur commande

Lorsque vous confirmez une commande planifiée, la boîte de dialogue **Confirmation** fournit un champ **Mettre à jour le marquage** que vous utilisez pour définir les options de marquage des commandes créées lors de la confirmation. Vous devez sélectionner l’une des valeurs suivantes :

- **Non** – Aucun marquage de stock n'est appliqué.
- **Standard** – Le marquage du stock est mis à jour en fonction de l'origine des demandes. Un ordre de besoins (demande) est marqué par rapport à un ordre d'exécution de commande (offre). S'il reste une quantité sur l'ordre d'exécution, elle n'est pas marquée et les informations de référence sont laissées vides. Par exemple, si une commande client de 100 unités est liée à une commande d'achat de 150 unités, les informations de référence ne seront affectées qu'à la commande client.
- **Développé** - L'ordre de besoins (demande) et l'ordre d'exécution de commande (offre) sont marqués, indépendamment de la quantité restant dans l'ordre d'exécution de commande. Par exemple, si une commande client de 100 unités est liée à une commande d'achat de 150 unités, les informations de référence ne seront affectées qu'à la commande client et à la commande fournisseur.
