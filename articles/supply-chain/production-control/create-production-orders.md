---
title: "Créer des ordres de fabrication"
description: "Lors de la création d'un ordre de fabrication, une demande de lancement de fabrication d'un article est effectuée. L'ordre de fabrication contient des informations sur l'article à fabriquer, la quantité à fabriquer, ainsi que la date de fin de fabrication prévue. Il inclut également des informations sur les matières à consommer et quel processus suivre pour produire l'article."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 58213d4d6e8c29ab6605eb7aa5c6cb9ca6ba4a10
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="create-production-orders"></a>Créer des ordres de fabrication

[!include [banner](../includes/banner.md)]

Lors de la création d'un ordre de fabrication, une demande de lancement de fabrication d'un article est effectuée. L'ordre de fabrication contient des informations sur l'article à fabriquer, la quantité à fabriquer, ainsi que la date de fin de fabrication prévue. Il inclut également des informations sur les matières à consommer et quel processus suivre pour produire l'article.

Un ordre de fabrication traverse les stades du cycle de vie de la production. Lorsqu'un ordre est créé, le statut **Créé** lui est affecté. Lorsqu'un ordre est terminé, le statut **Terminé** lui est affecté. Le paramétrage de chaque stade permet à un utilisateur de configurer chaque étape. Ce paramétrage peut être paramétré pour un seul utilisateur ou pour tous les utilisateurs.

Les nomenclatures de production et la gamme de production sont les entités principales de l'ordre de fabrication. Elles sont copiées dans l'ordre de fabrication selon l'article sélectionné et la quantité qui vont être produits. La nomenclature de production et la gamme peuvent être modifiées avant le début de l'ordre de fabrication.

Un ordre de fabrication peut être créé dans les scénarios suivants :

-   Créé par l'exécution de planification principale selon les besoins en matériel.
-   Créé directement à partir d'une ligne de commande client ou lorsqu'un ordre de fabrication de niveau supérieur est créé et estimé (approvisionnement invariable).
-   Créé manuellement.





