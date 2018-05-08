--- 
title: "Créer des critères de sélection de prix de vente"
description: "Cette procédure indique comment créer un critère de sélection de prix de vente pour les modèles de prix de vente basés sur des attributs."
author: YuyuScheller
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 59f6a4131f6a27c0089a1259e3f849f91a47bc87
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-sales-price-selection-criteria"></a>Créer des critères de sélection de prix de vente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment créer un critère de sélection de prix de vente pour les modèles de prix de vente basés sur des attributs. Cette procédure nécessite qu'au moins un modèle de prix de vente soit disponible. Cet exemple utilise le modèle de prix du modèle de prix de vente de la solution Haut-parleur dans les données de démonstration de la société fictive USMF. Généralement, un responsable de produit utilise cette procédure.


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Ajouter un nouveau critère pour un modèle de prix de vente existant
1. Cliquez sur Définition du modèle de variante de produit.
2. Cliquez sur Modèles de configuration de produit.
3. Dans la liste, sélectionnez la ligne du modèle de produit de la solution Haut-parleur, mais ne cliquez pas sur le lien du nom du modèle.
4. Dans le volet Actions, cliquez sur Modèle.
5. Cliquez sur Critères de modèle de prix.
6. Cliquez sur Nouveau.
7. Dans le champ Nom, tapez « Groupe de clients 10 ».
    * Le nom du critère de modèle de prix permet d'identifier les critères de sélection sous-jacents.  
8. Dans le champ Modèle de prix, entrez ou sélectionnez une valeur.
9. Dans le champ Type de commande, sélectionnez Commande client.
    * Le type de commande détermine les champs de base de données disponibles pour la requête de sélection.  
10. Dans le champ Début de validité, entrez une date.
11. Dans le champ Expiration, entrez une date.
12. Cliquez sur Enregistrer.

## <a name="create-the-query-for-the-selection-criteria"></a>Créer la requête pour les critères de sélection
1. Cliquez sur Modifier.
2. Dans le champ Table, sélectionnez Clients. 
3. Dans le champ Champ, sélectionnez un groupe de clients.
    * Dans cet exemple, nous utilisons un groupe de clients spécifique pour les critères de sélection.  
4. Dans le champ Critères, sélectionnez Groupe de clients 10. 
5. Cliquez sur OK.


