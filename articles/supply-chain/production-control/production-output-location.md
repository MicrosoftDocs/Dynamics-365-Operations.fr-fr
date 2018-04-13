---
title: Emplacement de la sortie de production
description: "Cette rubrique décrit la hiérarchie utilisée pour identifier l'emplacement de sortie de production."
author: johanhoffmann
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e53c8e96579dba3b47bef0c00e55b8fa786fc55c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="production-output-location"></a>Emplacement de la sortie de production

[!INCLUDE [banner](../includes/banner.md)]

Cette rubrique décrit la hiérarchie utilisée pour identifier l'emplacement de sortie de production.

L'emplacement de sortie de production est l'emplacement où un produit fini est d'abord stocké après avoir été produit. Généralement, cet emplacement est près du processus de production qui produit le produit fini. L'emplacement de sortie de production est utilisé comme stockage intermédiaire pour le matériel avant qu'il soit déplacé dans la zone d'expédition, à un emplacement de stockage, à un emplacement d'entrée en production pour un processus de production en aval, et ainsi de suite. 

Un emplacement de sortie de production par défaut est paramétré lorsque des produits finis sont signalés sur un ordre de fabrication ou un lot de commandes. La hiérarchie suivante est utilisée pour identifier cet emplacement de sortie :

1. Utilisez l'emplacement de sortie qui est défini dans l'en-tête de l'ordre de fabrication ou du lot de commandes.
2. Si aucun emplacement n'est trouvé là, utilisez l'emplacement de sortie défini sur la ressource utilisée par la dernière opération définie dans la gamme de production.
3. Si aucun emplacement n'est trouvé là, utilisez l'emplacement de sortie défini sur le groupe de ressources utilisé par la ressource pour la dernière opération définie dans la gamme de production.
4. Si aucun entrepôt n'est trouvé là, utilisez l'emplacement de sortie défini dans l'entrepôt qui est défini pour l'ordre de fabrication.

Un emplacement de sortie de production par défaut est défini uniquement pour les produits qui sont paramétrés à l'aide des processus d'entrepôt avancés. Lorsque ce type d'article est déclaré terminé, le type de travail en entrepôt **Rangement des produits finis** ou **Rangement des coproduits et des sous-produits** est créé. Ce type de travail utilise l'emplacement de sortie de production comme emplacement de prélèvement. L'emplacement de rangement est déterminé par les instructions sur l'emplacement.

