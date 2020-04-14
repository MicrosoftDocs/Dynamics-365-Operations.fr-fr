---
title: Créer une classe de travail
description: Cette procédure décrit le processus de paramétrage d'une classe de travail.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6afbd9f54ef9046da10d0abc24ed545b5735a069
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146098"
---
# <a name="create-a-work-class"></a>Créer une classe de travail

[!include [banner](../../includes/banner.md)]

Cette procédure décrit le processus de paramétrage d'une classe de travail. Les classes de travail sont utilisées pour diriger et/ou limiter le type de lignes de commande de travail qu'un employé de l'entrepôt peut traiter sur un périphérique portable. Les lignes qu'un employé peut traiter sont déterminées à partir des classes de travail sur les éléments du menu du périphérique portable auquel l'employé de l'entrepôt a accès et de la classe de travail spécifiée sur les lignes de travail. Les classes de travail peuvent également être utilisées pour valider l'emplacement de rangement d'une ligne de commande de travail. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Cette procédure est destinée au gestionnaire d'entrepôts.

1. Accédez à Gestion des entrepôts > Configuration > Travail > Classes de travail.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ ID classe de travail.
4. Dans le champ Description, entrez une valeur.
5. Sélectionnez une option dans le champ Type d'ordre d'exécution.
6. Cliquez sur Nouveau.
7. Dans le champ Emplacement, tapez une valeur.
    * Si vous sélectionnez un type d'emplacement, ceci définit une restriction quant au lieu dans lequel les articles peuvent être mis une fois qu'ils ont été prélevés. Ce paramètre est utilisé lors de tentatives d'une directive d'emplacement pour résoudre l'emplacement, ou si un employé de l'entrepôt fournit manuellement l'emplacement pour l'élément du menu du périphérique portable.  
8. Fermez la page.

