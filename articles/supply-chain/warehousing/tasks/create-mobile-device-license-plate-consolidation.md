---
title: Créer une option de menu d'appareil mobile pour la consolidation de contenants
description: Cette procédure décrit comment créer une option de menu d'appareil mobile pour le travail de consolidation de contenants.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cc610a16f4b0e574b5d5e7f8fc9ecf1e12534645
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847301"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a>Créer une option de menu d'appareil mobile pour la consolidation de contenants

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment créer une option de menu d'appareil mobile pour le travail de consolidation de contenants. Cela permet aux magasiniers de consolider les articles d'un contenant avec les articles d'un autre contenant dans le même emplacement. Par exemple, ils peuvent utiliser cette procédure si les étapes intermédiaires suivantes sont les mêmes sur les deux ordres d'exécution, de sorte que le travail ne doit être exécuté qu'une seule fois pour les articles fusionnés. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF. La tâche est généralement effectuée par un responsable d'entrepôt. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.

1. Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile.
2. Cliquez sur Nouveau.
3. Saisissez une valeur dans le champ Nom de l'option de menu.
4. Tapez une valeur dans le champ Titre.
5. Dans le champ Mode, sélectionnez « Indirect ».
6. Dans le champ Code d'activité, sélectionnez « Consolider les contenants ».

