---
title: Description et niveau de service
description: Cette rubrique explique le niveau de service et la description dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7dd577c930c6cc17da6baee30d3558656de01a09
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569821"
---
# <a name="service-level-and-description"></a>Description et niveau de service

[!include [banner](../../includes/banner.md)]

 

Lorsque vous créez un ordre de travail, vous pouvez définir les niveaux de service pour celui-ci et y ajouter une description générale. Vous pouvez créer des niveaux de service de l'ordre de travail sur la page **Niveaux de service de l'ordre de travail** et les descriptions sur la page **Description de l'ordre de travail**.

## <a name="create-a-service-level"></a>Créer un niveau de service

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Niveau de service**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Niveau de service**, entrez le niveau de service (par exemple, un numéro).
4. Dans le champ **Nom**, entrez un nom.

    Dans l'organisateur **Ordres de travail**, vous pouvez définir les dates et heures de début et de fin prévues. Les champs de cet organisateur définissent la période au cours de laquelle les ordres de travail doivent être démarrés et terminés. Ils sont utilisés pour les ordres de travail créés manuellement et les ordres de travail créés selon les demandes de maintenance. 

5. Dans le champ **Jour de début**, entrez un nombre de jours pour définir la période au cours de laquelle l'ordre de travail doit commencer. Le nombre de jours est calculé depuis la date de création de l'ordre de travail. Par exemple, si l'ordre de travail doit commencer à sa création, entrez **0**. Si l'ordre de travail doit commencer sous une semaine après sa création, entrez **7**.
6. Pour définir une heure de début pour l'ordre de travail, en plus d'une date de début, définissez l'option **Définir l'heure de début** sur **Oui**. Puis saisissez l'heure de début dans le champ **Heure de début**. Si vous définissez l'option sur **Non**, l'heure actuelle de la journée est utilisée.
7. Dans le champ **Jour de fin**, entrez un nombre de jours pour définir la période au cours de laquelle l'ordre de travail doit se terminer. Le nombre de jours est calculé depuis la date de début de l'ordre de travail. Par exemple, si l'ordre de travail se termine au cours d'une semaine à compter de sa date de début, entrez **7**.
8. Pour définir une heure de fin pour l'ordre de travail, en plus d'une date de fin, définissez l'option **Définir l'heure de fin** sur **Oui**. Puis saisissez l'heure de fin dans le champ **Heure de fin**. Si vous définissez l'option sur **Non**, l'heure actuelle de la journée est utilisée.
9. Sélectionnez **Enregistrer**.

![Page Niveau de service des ordres de travail](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a>Créer une description

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Descriptions**.
2. Sélectionnez **Nouveau**.
3. Entrez la description dans le champ **Description**.
4. Sélectionnez **Enregistrer**.
