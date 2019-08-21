---
title: Actifs et ordres de travail
description: Cette rubrique décrit les actifs et les ordres de travail dans le module Gestion des actifs.
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
ms.openlocfilehash: 5bd55988578be2b0287b399549f17642bfb1693b
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783260"
---
# <a name="assets-and-work-orders"></a>Actifs et ordres de travail

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Cette rubrique décrit les actifs et les ordres de travail dans le module Gestion des actifs. Les actifs et les ordres de travail sont les parties centrales du module Gestion des actifs. Un *actif* est une machine ou une pièce de machine qui nécessite une maintenance et un service continus. Les actifs peuvent être créés dans une structure hiérarchique, et ils peuvent être associés à des postes techniques. Les tâches de maintenance peuvent être planifiées à tous les niveaux de la structure de l'actif.

Diverses données, telles que les informations sur le produit et la spécification de l'actif, ainsi que les plans de maintenance requis sont paramétrés sur chaque actif. L'illustration suivante donne une vue d'ensemble des données d'actif et de l'affiliation des actifs aux types de tâche. Le texte en rouge est utilisé pour les exemples illustrant l'héritage et les dépendances.

![Figure 1](media/05-overview-image.png)

Chaque ordre de travail a un type d'ordre de travail, comme la maintenance préventive, la maintenance corrective ou l'inspection. L'ordre de travail contient une ou plusieurs tâches d'ordre de travail. Chaque tâche d'ordre de travail définit une tâche qui doit être réalisée sur un actif et un type de tâche associé. La révision à 10 000 km, 50 000 km et 1 an et l'inspection de sécurité sont des exemples de types de tâche associés. Un ordre de travail peut être associé à plusieurs actifs.

L'illustration suivante donne une vue d'ensemble des principales données d'un ordre de travail.

![Figure 2](media/06-overview-image.png)

Un ordre de travail peut être associé à un autre ordre de travail, et les types de tâche peuvent contenir les tâches suivantes qui créent un ordre de travail. En général, il n'existe aucune dépendance entre les ordre de travail. Par conséquent, ils peuvent modifier leur état du cycle de vie et peuvent être planifiés indépendamment les uns des autres.

Il est possible de créer des ordres de travail de différentes manières qui sont associés à la maintenance corrective, préventive ou réactive. Vous pouvez également créer des ordres de travail manuellement. L'illustration suivante donne une vue d'ensemble du processus de création automatique ou manuelle des ordres de travail.

![Figure 3](media/07-overview-image.png)

Plusieurs étapes doivent être effectuées lorsque vous souhaitez planifier et exécuter une tâche de maintenance sur un ordre de travail. L'illustration suivante donne une vue d'ensemble du traitement d'un ordre de travail.

![Figure 4](media/08-overview-image.png)

> [!NOTE]
> En général, lorsque vous travaillez dans Microsoft Dynamics 365 for Finance and Operations et le module **Gestion des actifs**, vous sélectionnez **Nouveau** pour créer un enregistrement, vous sélectionnez **Modifier** pour mettre à jour un enregistrement existant et vous sélectionnez **Enregistrer** pour enregistrer des données nouvelles ou modifiées.
