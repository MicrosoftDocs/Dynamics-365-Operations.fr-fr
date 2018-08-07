--- 
title: "Créer un plan intersociétés"
description: "Cette procédure indique comment créer un plan intersociétés."
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: da186f7ad74bb607fd6e7220d77c2f414789f29c
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-an-intercompany-plan"></a>Créer un plan intersociétés

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment créer un plan intersociétés. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="set-up-an-intercompany-planning-group"></a>Paramétrer un groupe de planification intersociétés 
1. Accédez à Groupes de planification intersociétés.
    * Planification > Configuration > Groupes de planification intersociétés  
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Nom avec une valeur de « 10 ».
3. Dans la liste, marquez la ligne sélectionnée.
4. Cliquez sur Supprimer.
    * Cette étape est nécessaire pour raccourcir l'exécution de la planification intersociétés.   La planification intersociétés exécute la planification dans toutes les sociétés d'un groupe de planification, en commençant par la séquence de planification la plus faible.  
5. Cliquez sur Oui.
6. Fermez la page.

## <a name="create-an-intercompany-plan"></a>Créer un plan intersociétés
1. Cliquez sur Planification intersociétés.
    * Cela figure dans l'espace de travail Planification.  
2. Dans le champ Groupe de planification intersociétés, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez le groupe de planification intersociétés 10.  
4. Dans le champ Nombre d'itérations de planification intersociétés, entrez « 2 ».
    * Le groupe de planification intersociétés 10 a deux membres. Afin de propager les retards de la société source (USMF) à la société cliente (DEMF), vous devez exécuter deux fois le module intersociétés dans les deux sociétés. La première itération propage la demande et identifie les retards dans la société source (USMF). La deuxième itération propage les retards d'USMF à DEMF.  
5. Dans le champ Première itération, sélectionnez une option.
6. Dans le champ Première itération, sélectionnez « Régénération ».
7. Dans le champ Itérations suivantes, sélectionnez « Régénération ».
8. Entrez un nombre dans le champ Nombre de threads.
    * Représente le nombre de threads parallèles utilisés pour la planification.  
9. Cliquez sur OK.

## <a name="view-the-result-of-the-plan"></a>Afficher le résultat du plan
1. Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Cliquez sur le lien de StaticPlan. Vous devez être dans la société USMF.  
3. Cliquez sur Ordres prévisionnels.


