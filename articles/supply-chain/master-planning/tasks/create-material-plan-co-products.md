--- 
title: "Créer un plan matières pour des coproduits"
description: "Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
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
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-material-plan-for-co-products"></a>Créer un plan matières pour des coproduits

[!include [task guide banner](../../includes/task-guide-banner.md)]

Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules. La société fictive de démonstration utilisée pour créer cette procédure est USP2.


## <a name="create-requirement-for-a-co-product"></a>Créer une demande pour un coproduit
1. Allez dans le Tableau de bord par défaut.
2. Cliquez sur Traitement et recherche de commande client.
3. Cliquez sur Nouveau.
4. Cliquez sur Commande client.
5. Tapez une valeur dans le champ Compte client.
    * Exemple : US-001  
6. Cliquez sur OK.
7. Tapez une valeur dans le champ Numéro d'article.
    * Exemple : P6003  
8. Dans le champ Quantité, entrer un numéro.
    * Exemple : 50000  
9. Cliquez sur Enregistrer.

## <a name="create-a-material-plan-for-co-products"></a>Créer un plan matières pour des coproduits
1. Cliquez sur Planification.
2. Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Exemple : Programme  
4. Cliquez sur Exécuter.
5. Développez ou réduisez la section Enregistrements à inclure.
6. Cliquez sur Filtre.
7. Dans la liste, sélectionnez la ligne pour Champ = Numéro d'article.
8. Tapez une valeur dans le champ Critères.
    * Exemple : P6003  
9. Cliquez sur OK.
10. Cliquez sur OK.
11. Cliquez sur Ordres prévisionnels.
12. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez su le champ Numéro d'article avec une valeur de « P6000 ».
    * Filtrez par élément de formule ayant comme coproduit de l'article pour lequel vous avez créé une commande client.  
13. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez n'importe quelle ligne renvoyée par le filtre.  
14. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
15. Développez ou réduisez la section Origine des besoins.
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * L'ordre prévisionnel est chevillé à la commande client du coproduit.  
17. Fermez la page.


