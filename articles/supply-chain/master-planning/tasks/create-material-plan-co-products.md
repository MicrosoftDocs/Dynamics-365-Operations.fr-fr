---
title: Créer un plan de matériaux pour des coproduits
description: Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d910b89330865b0bcf3f6cd05b761506f339a45f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841669"
---
# <a name="create-a-material-plan-for-co-products"></a>Créer un plan de matériaux pour des coproduits

[!include [banner](../../includes/banner.md)]

Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules. La société fictive de démonstration utilisée pour créer cette procédure est USP2.


## <a name="create-requirement-for-a-co-product"></a>Créer une demande pour un coproduit
1. Allez dans le Tableau de bord par défaut.
2. Cliquez sur Traitement et recherche de commande client.
3. Cliquez sur Nouveau.
4. Cliquez sur Commande client.
5. Tapez une valeur dans le champ Compte client.
    * Exemple : US-001  
6. Cliquez sur OK.
7. Tapez une valeur dans le champ Numéro d’article.
    * Exemple : P6003  
8. Dans le champ Quantité, entrer un numéro.
    * Exemple : 50000  
9. Cliquez sur Enregistrer.

## <a name="create-a-material-plan-for-co-products"></a>Créer un plan matières pour des coproduits
1. Fermez la page.
2. Fermez la page.
3. Cliquez sur Planification.
4. Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Exemple : Programme  
6. Cliquez sur Exécuter.
7. Développez ou réduisez la section Enregistrements à inclure.
8. Cliquez sur Filtre.
9. Dans la liste, sélectionnez la ligne pour Champ = Numéro d’article.
10. Tapez une valeur dans le champ Critères.
    * Exemple : P6003  
11. Cliquez sur OK.
12. Cliquez sur OK.
13. Cliquez sur Ordres prévisionnels.
14. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez su le champ Numéro d’article avec une valeur de « P6000 ».
    * Filtrez par élément de formule ayant comme coproduit de l’article pour lequel vous avez créé une commande client.  
15. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez n’importe quelle ligne renvoyée par le filtre.  
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
17. Développez ou réduisez la section Origine des besoins.
18. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * L’ordre prévisionnel est chevillé à la commande client du coproduit.  
19. Fermez la page.

## <a name="create-requirement-for-a-co-product"></a>Créer une demande pour un coproduit
1. Allez dans le Tableau de bord par défaut.
2. Cliquez sur Traitement et recherche de commande client.
3. Cliquez sur Nouveau.
4. Cliquez sur Commande client.
5. Tapez une valeur dans le champ Compte client.
    * Exemple : US-001  
6. Cliquez sur OK.
7. Tapez une valeur dans le champ Numéro d’article.
    * Exemple : P6003  
8. Dans le champ Quantité, entrer un numéro.
    * Exemple : 50000  
9. Cliquez sur Enregistrer.

## <a name="create-a-material-plan-for-co-products"></a>Créer un plan matières pour des coproduits
1. Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Exemple : Programme  
3. Cliquez sur Exécuter.
4. Développez ou réduisez la section Enregistrements à inclure.
5. Cliquez sur Filtre.
6. Dans la liste, sélectionnez la ligne pour Champ = Numéro d’article.
7. Tapez une valeur dans le champ Critères.
    * Exemple : P6003  
8. Cliquez sur OK.
9. Cliquez sur OK.
10. Cliquez sur Ordres prévisionnels.
11. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez su le champ Numéro d’article avec une valeur de « P6000 ».
    * Filtrez par élément de formule ayant comme coproduit de l’article pour lequel vous avez créé une commande client.  
12. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez n’importe quelle ligne renvoyée par le filtre.  
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
14. Développez ou réduisez la section Origine des besoins.
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * L’ordre prévisionnel est chevillé à la commande client du coproduit.  
16. Fermez la page.
17. Cliquez sur Planification.
18. Accédez à Planification > Paramétrage > Paramètres de planification.
19. Sélectionnez Non dans le champ Désactiver tous les processus de planification.
20. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]