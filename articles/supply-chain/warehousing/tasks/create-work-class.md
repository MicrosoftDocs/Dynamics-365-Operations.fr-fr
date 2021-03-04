---
title: Créer une classe de travail
description: Cette procédure décrit le processus de paramétrage d'une classe de travail.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkClass
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed9b72d891df4d40213d4854da6b09bd9876effa
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428246"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]