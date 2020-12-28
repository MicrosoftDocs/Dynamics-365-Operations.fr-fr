---
title: Réserver le même lot pour une commande client
description: Cet article explique comment paramétrer un produit pour autoriser la réservation du stock par rapport à un lot de stock unique.
author: omulvad
manager: tfehr
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce750745d6f094a296b43827568ee1745179de2d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428301"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a>Réserver le même lot pour une commande client

[!include [banner](../includes/banner.md)]

Cet article explique comment paramétrer un produit pour autoriser la réservation du stock par rapport à un lot de stock unique.

Une réservation de lots identiques vous permet de réserver du stock pour une ligne de commande client par rapport à un lot de stock unique. Par exemple, un client qui commande du papier peint peut demander que toute la commande soit honorée à partir du même lot pour éviter les éventuelles différences entre les rouleaux de papier peint. Pour paramétrer un produit de manière à utiliser la réservation de lots identiques, les paramètres suivants doivent être activés dans les Groupes de modèles d'article, Groupe de dimension de suivi et Groupe de dimension de stockage que vous affectez au produit.

- **Groupes de modèles d'article** – Pour le groupe de modèles d'article, les champs **Même sélection de lot** et **Consolider le besoin** doivent être sélectionnés dans le groupe de champs **Réservation** pour les stratégies de stock.
- **Groupes de dimension de suivi** – Pour le groupe de dimension de suivi, le champ **Plan de couverture par dimension** doit être sélectionné pour le numéro du lot.
- **Groupe de dimension de stockage** – Pour le groupe de dimension de stockage, le champ **Plan de couverture par dimension** doit être sélectionné pour le **Site** et l'**Entrepôt**.

Lorsque vous réservez du stock pour un produit sur une ligne de commande client paramétrée pour la sélection du même lot, le système tente de réserver la quantité commandée dans un seul lot de stock. Il prend également en considération toute demande d'attribut de lot spécifique. Si la quantité ne peut pas être remplie à partir d'un seul lot, la page **Conflit de réservation du même lot** s'affiche. Cette page décrit les problèmes et également les actions que vous pouvez entreprendre pour poursuivre la réservation. Les conditions suivantes peuvent empêcher le lot d'être réservé :

- Pour le code disposition de lot, **Bloquer la réservation** pour les ventes est marqué comme **Bloqué**.
- Le lot a expiré, d'après la date d'expiration et des jours de vente applicables au client. L'article peut toujours être pris en compte pour la réservation si le Groupe de modèles d'article pour l'article est contrôlé par la date FEFO (première date d'expiration, premier sorti) et si la DLUO est sélectionnée dans les critères de prélèvement.
- Le lot a une durée de conservation en jours insuffisante, selon la date d'expiration/DLUO, plus les jours de vente du client.

Pour les éléments associés à un groupe de dimensions de stockage avec l'option **Utiliser des processus de gestion des entrepôts** activée, vous pouvez réserver des numéros de lot spécifiques en utilisant une hiérarchie de réservation avec la dimension d'inventaire de numéro de lot définie au-dessus de la dimension d'emplacement. La page **Réservation de lot** des lignes de commande client et d'ordre de transfert vous permet également de sélectionner et de réserver plusieurs lignes en fonction des numéros de lot disponibles. Pour plus d'informations sur la procédure à suivre si vous utilisez une hiérarchie de réservation dont la dimension de numéro de lot se situe sous l'emplacement, voir [Stratégie flexible de réservation de dimension au niveau de l'entrepôt](../warehousing/flexible-warehouse-level-dimension-reservation.md).
