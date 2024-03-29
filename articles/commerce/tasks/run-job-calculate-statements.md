---
title: Configurer et exécuter la tâche de calcul des déclarations
description: Cette procédure décrit la configuration et l’exécution de traitements par lots récurrents pour créer et calculer des relevés pour un magasin ou un groupe de magasins sélectionné.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ecbc35cabced37a51ecedcd3f37bff2f23c093e184607b0c4d57ae9e70ae2c75
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751517"
---
# <a name="configure-and-run-job-to-calculate-statements"></a>Configurer et exécuter la tâche de calcul des déclarations

[!include [banner](../includes/banner.md)]

Cette procédure décrit la configuration et l’exécution de traitements par lots récurrents pour créer et calculer des relevés pour un magasin ou un groupe de magasins sélectionné. Cette procédure utilise la société USRT dans les données de démonstration.

1. Accédez à Tous les espaces de travail > Finances du magasin.
2. Cliquez sur Calcul des relevés.
    * Sélectionnez un magasin spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.  
    * Cliquez sur la flèche pour ajouter votre sélection.  
3. Cliquez sur l’onglet Exécuter à l’arrière-plan.
4. Sous Traitement par lots, sélectionnez « Oui ».
5. Cliquez sur Répétition.
6. Entrez une date dans le champ Date de début.
7. Dans le champ Heure de début, saisissez une heure.
8. Sélectionnez l’option Pas de date de fin.
9. Dans le champ PatternUnit, saisissez « Jours ».
10. Entrez un numéro dans le champ Par.
11. Cliquez sur OK.
12. Cliquez sur OK.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]