---
title: Actifs et postes techniques
description: Cette rubrique décrit les postes techniques et les actifs dans Gestion des actifs. Gestion des actifs est un module avancé de gestion des actifs et des tâches de maintenance dans Microsoft Dynamics 365 for Finance and Operations.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 351e27dfbbd5227a9642f14a48afe194c447a0f3
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783278"
---
# <a name="functional-locations-and-assets"></a>Actifs et postes techniques

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Cette rubrique décrit les postes techniques et les actifs dans Gestion des actifs. Gestion des actifs est un module avancé de gestion des actifs et des tâches de maintenance dans Microsoft Dynamics 365 for Finance and Operations.

## <a name="overview"></a>Présentation

Gestion des actifs est intégré de façon transparente à plusieurs modules de Finance and Operations. L'illustration suivante présente les interfaces avec d'autres modules.

![Figure 1](media/01-overview-image.png)

Gestion des actifs vous permet de gérer et d'exécuter plus efficacement toutes les tâches relatives à la gestion et à la maintenance de nombreux types d'équipements de votre société. Cet équipement inclut les machines, l'équipement de production et les véhicules. Gestion des actifs prend également en charge les solutions de nombreux secteurs.

L'illustration suivante présente une vue d'ensemble de la fonctionnalité principale couverte par Gestion des actifs.

![Figure 2](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>Actifs et postes techniques

Les postes techniques permettent de gérer des actifs à des postes. Cette gestion inclut le suivi des coûts d'actif à des postes techniques. Les postes techniques sont structurés hiérarchiquement, et les postes peuvent avoir des sous-postes. La structure des postes techniques est statique. Autrement dit, les postes ne peuvent pas changer d'emplacement. Les actifs peuvent être installés à des postes techniques et, au besoin, être installés à d'autres postes techniques ultérieurement.

Les coûts d'actifs suivent toujours le poste de l'actif. En d'autres termes, si vous installez un actif à un nouveau poste technique, l'actif utilise automatiquement les dimensions financières associées au nouveau poste technique. Par conséquent, les coûts d'actif sont toujours liés au poste technique sur lequel l'actif est actuellement installé. Ce traitement automatique des dimensions financières garantit le suivi complet des coûts lorsque votre société fait le projet de contrôler et de générer des états sur les postes techniques.

La façon dont vous établissez votre hiérarchie des postes techniques dépend des exigences de votre société pour la maintenance de l'équipement interne ou l'entretien de l'équipement du client. La figure suivante présente un exemple des postes techniques basés sur des emplacements géographiques.

![Figure 3](media/03-overview-image.png)

La figure suivante présente un exemple des postes techniques basés sur les clients.

![Figure 4](media/04-overview-image.png)
