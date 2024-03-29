---
title: Vue d’ensemble du cycle de vie de l’ordre de fabrication
description: Lors de la création d’un ordre de fabrication, une demande de lancement de fabrication d’un article est effectuée. L’ordre de fabrication contient des informations sur l’article à fabriquer, la quantité à fabriquer, ainsi que la date de fin de fabrication prévue. Il inclut également des informations sur les matières à consommer et quel processus suivre pour produire l’article.
author: johanhoffmann
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19741"
- intro-internal
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4c3632d644070f064ec70d3dd7c0d480927eafe
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982875"
---
# <a name="production-order-lifecycle-overview"></a>Vue d’ensemble du cycle de vie de l’ordre de fabrication

[!include [banner](../includes/banner.md)]

Lors de la création d’un ordre de fabrication, une demande de lancement de fabrication d’un article est effectuée. L’ordre de fabrication contient des informations sur l’article à fabriquer, la quantité à fabriquer, ainsi que la date de fin de fabrication prévue. Il inclut également des informations sur les matières à consommer et quel processus suivre pour produire l’article.

Un ordre de fabrication traverse les stades du cycle de vie de la production. Lorsqu’un ordre est créé, le statut **Créé** lui est affecté. Lorsqu’un ordre est terminé, le statut **Terminé** lui est affecté. Le paramétrage de chaque stade permet à un utilisateur de configurer chaque étape. Ce paramétrage peut être paramétré pour un seul utilisateur ou pour tous les utilisateurs.

Les nomenclatures de production et la gamme de production sont les entités principales de l’ordre de fabrication. Elles sont copiées dans l’ordre de fabrication selon l’article sélectionné et la quantité qui vont être produits. La nomenclature de production et la gamme peuvent être modifiées avant le début de l’ordre de fabrication.

Un ordre de fabrication peut être créé dans les scénarios suivants :

-   Créé par l’exécution de planification principale selon les besoins en matériel.
-   Créé directement à partir d’une ligne de commande client ou lorsqu’un ordre de fabrication de niveau supérieur est créé et estimé (approvisionnement invariable).
-   Créé manuellement.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]