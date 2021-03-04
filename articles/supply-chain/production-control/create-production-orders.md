---
title: Vue d'ensemble du cycle de vie de l'ordre de fabrication
description: Lors de la création d'un ordre de fabrication, une demande de lancement de fabrication d'un article est effectuée. L'ordre de fabrication contient des informations sur l'article à fabriquer, la quantité à fabriquer, ainsi que la date de fin de fabrication prévue. Il inclut également des informations sur les matières à consommer et quel processus suivre pour produire l'article.
author: johanhoffmann
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80031737ab0d0c4ab1e4dbd5646ad91f1a010cd5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428033"
---
# <a name="production-order-lifecycle-overview"></a>Vue d'ensemble du cycle de vie de l'ordre de fabrication

[!include [banner](../includes/banner.md)]

Lors de la création d'un ordre de fabrication, une demande de lancement de fabrication d'un article est effectuée. L'ordre de fabrication contient des informations sur l'article à fabriquer, la quantité à fabriquer, ainsi que la date de fin de fabrication prévue. Il inclut également des informations sur les matières à consommer et quel processus suivre pour produire l'article.

Un ordre de fabrication traverse les stades du cycle de vie de la production. Lorsqu'un ordre est créé, le statut **Créé** lui est affecté. Lorsqu'un ordre est terminé, le statut **Terminé** lui est affecté. Le paramétrage de chaque stade permet à un utilisateur de configurer chaque étape. Ce paramétrage peut être paramétré pour un seul utilisateur ou pour tous les utilisateurs.

Les nomenclatures de production et la gamme de production sont les entités principales de l'ordre de fabrication. Elles sont copiées dans l'ordre de fabrication selon l'article sélectionné et la quantité qui vont être produits. La nomenclature de production et la gamme peuvent être modifiées avant le début de l'ordre de fabrication.

Un ordre de fabrication peut être créé dans les scénarios suivants :

-   Créé par l'exécution de planification principale selon les besoins en matériel.
-   Créé directement à partir d'une ligne de commande client ou lorsqu'un ordre de fabrication de niveau supérieur est créé et estimé (approvisionnement invariable).
-   Créé manuellement.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]