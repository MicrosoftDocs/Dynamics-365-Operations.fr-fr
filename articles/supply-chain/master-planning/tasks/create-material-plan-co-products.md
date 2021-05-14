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
ms.openlocfilehash: b51e4b4d00da2babb5128d8c4c22139b0c1853d4
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920727"
---
# <a name="create-a-material-plan-for-co-products"></a>Créer un plan de matériaux pour des coproduits

[!include [banner](../../includes/banner.md)]

Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules. La société fictive de démonstration utilisée pour créer cette procédure est USP2.

## <a name="create-requirement-for-a-co-product"></a>Créer une demande pour un coproduit

1. Accédez à **Ventes et marketing \> Espaces de travail \> Traitement et recherche de commande client**.
1. Sélectionnez **Nouveau**.
1. Sélectionnez **Commandes client**.
1. Dans le champ **Compte client**, saisissez une valeur.
    * Exemple : US-001  
1. Cliquez sur **OK**.
1. Dans le champ **Numéro d’article**, tapez une valeur.
    * Exemple : P6003  
1. Entrez un nombre dans le champ **Quantité**.
    * Exemple : 50000  
1. Sélectionnez **Enregistrer**.

## <a name="create-a-material-plan-for-co-products"></a>Créer un plan matières pour des coproduits

1. Fermez la page.
1. Fermez la page.
1. Sélectionnez **Planification**.
1. Dans le champ **Régime**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
    * Exemple : Programme  
1. Sélectionnez **Exécuter**.
1. Développez ou réduisez la section **Enregistrements à inclure**.
1. Sélectionnez **Filtrer**.
1. Dans la liste, sélectionnez la ligne pour **Champ** = *Numéro d’article*.
1. Tapez une valeur dans le champ **Critères**.
    * Exemple : P6003  
1. Cliquez sur **OK**.
1. Cliquez sur **OK**.
1. Sélectionnez **Ordres prévisionnels**.
1. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez su le champ **Numéro d’article** avec une valeur de « P6000 ».
    * Filtrez par élément de formule ayant comme coproduit de l’article pour lequel vous avez créé une commande client.  
1. Dans la liste, marquer la ligne sélectionnée.
    * Sélectionnez n’importe quelle ligne renvoyée par le filtre.  
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Développez la section **Origine des besoins**.
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
    * L’ordre prévisionnel est chevillé à la commande client du coproduit.  
1. Fermez la page.

## <a name="create-a-second-requirement-for-a-co-product"></a>Créer une deuxième demande pour un coproduit

1. Accédez à **Ventes et marketing \> Espaces de travail \> Traitement et recherche de commande client**.
1. Sélectionnez **Nouveau**.
1. Sélectionnez **Commandes client**.
1. Dans le champ **Compte client**, saisissez une valeur.
    * Exemple : US-001  
1. Cliquez sur **OK**.
1. Dans le champ **Numéro d’article**, tapez une valeur.
    * Exemple : P6003  
1. Entrez un nombre dans le champ **Quantité**.
    * Exemple : 50000  
1. Sélectionnez **Enregistrer**.

## <a name="create-a-second-material-plan-for-co-products"></a>Créer un deuxième plan matières pour des co-produits

1. Dans le champ **Régime**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
2. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
    * Exemple : Programme  
3. Sélectionnez **Exécuter**.
4. Développez ou réduisez la section **Enregistrements à inclure**.
5. Sélectionnez **Filtrer**.
6. Dans la liste, sélectionnez la ligne pour **Champ** = *Numéro d’article*.
7. Tapez une valeur dans le champ *Critères*.
    * Exemple : P6003  
8. Cliquez sur **OK**.
9. Cliquez sur **OK**.
10. Sélectionnez **Ordres prévisionnels**.
11. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez su le champ **Numéro d’article** avec une valeur de « P6000 ».
    * Filtrez par élément de formule ayant comme coproduit de l’article pour lequel vous avez créé une commande client.  
12. Dans la liste, marquer la ligne sélectionnée.
    * Sélectionnez n’importe quelle ligne renvoyée par le filtre.  
13. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
14. Développez ou réduisez la section **Origine des besoins**.
15. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
    * L’ordre prévisionnel est chevillé à la commande client du coproduit.  
16. Fermez la page.
17. Sélectionnez **Planification**.
18. Accédez à **Planification \> Paramétrage \> Paramètres de planification**.
19. Sélectionnez *Non* dans le champ **Désactiver tous les processus de planification**.
20. Fermez la page.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]