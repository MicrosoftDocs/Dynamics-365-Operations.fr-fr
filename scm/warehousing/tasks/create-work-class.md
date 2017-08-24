--- 
title: "Créer une classe de travail"
description: "Cette procédure décrit le processus de paramétrage d'une classe de travail."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 50b8ee1825391d7e5977f758628b559d006a334e
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-work-class"></a>Créer une classe de travail

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


