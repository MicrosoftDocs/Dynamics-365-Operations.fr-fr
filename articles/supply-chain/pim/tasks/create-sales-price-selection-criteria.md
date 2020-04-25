---
title: Créer des critères de sélection de prix de vente
description: Cette procédure indique comment créer un critère de sélection de prix de vente pour les modèles de prix de vente basés sur des attributs.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6d1385a83da5b6448a9c753d7469979796043b60
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203770"
---
# <a name="create-sales-price-selection-criteria"></a>Créer des critères de sélection de prix de vente

[!include [banner](../../includes/banner.md)]

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

