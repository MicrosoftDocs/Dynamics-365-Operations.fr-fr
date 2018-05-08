--- 
title: "Paramétrer un index de carburant du transporteur"
description: "Ce guide indique comment créer une région de l'index de carburant, un index de carburant et un index de carburant du transporteur."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 81f3244ff42cf13cd93ac10656c47f8a9204ef99
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-a-carrier-fuel-index"></a>Paramétrer un index de carburant du transporteur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide indique comment créer une région de l'index de carburant, un index de carburant et un index de carburant du transporteur. La région d'index de carburant spécifie à quelle région l'index doit s'appliquer, et l'index de carburant spécifie un prix du carburant pour une période spécifique. Pour refléter la modification des prix du carburant au fil du temps, vous pouvez associer une région à plusieurs index de carburant à un transporteur.  Ces tâches sont normalement effectuées par un coordinateur de transport. Vous pouvez utiliser cette procédure dans les données de démonstration de la société fictive USMF ou utiliser vos propres données.


## <a name="create-a-fuel-index-region"></a>Créer la région de l'index de carburant
1. Allez dans Gestion du transport > Configuration > Index de carburant > Régions de l'index de carburant.
    * Vous devez tout d'abord créer différentes régions, dans lesquelles vous allez traiter et calculer différents suppléments de carburant.  
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Région.
4. Tapez une valeur dans le champ Nom.
5. Cliquez sur Enregistrer.

## <a name="create-a-fuel-index"></a>Créer un index de carburant
1. Allez dans Gestion du transport > Configuration > Index de carburant > Index de carburant.
    * Pour les régions que vous avez paramétrées, vous devez entrer les prix actuels pour le carburant.  
2. Cliquez sur Nouveau.
3. Dans le champ Région, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Entrez un nombre dans le champ Prix par litre.
6. Entrez une date et une heure dans le champ Date et heure de début effectives.
7. Cliquez sur Enregistrer.

## <a name="create-a-carrier-fuel-index"></a>Créer un index de carburant du transporteur
1. Allez dans Gestion du transport > Configuration > Index de carburant > Index de carburant du transporteur.
2. Cliquez sur Nouveau.
3. Saisissez une valeur dans le champ Index de carburant du transporteur.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Nouveau.
6. Entrez une date et une heure dans le champ Date et heure de début effectives.
7. Entrez un nombre dans le champ PPG de départ.
    * Dans cet exemple, vous pouvez définir le champ PPG de départ sur 1,95.  
8. Entrez un nombre dans le champ PPG de fin.
    * Dans cet exemple, vous pouvez définir le champ PPG de fin sur 2.  
9. Entrez un nombre dans le champ Pourcentage.
    * Dans cet exemple, vous pouvez définir le pourcentage sur 3.  
10. Dans le champ Devise, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
12. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
13. Cliquez sur Enregistrer.


