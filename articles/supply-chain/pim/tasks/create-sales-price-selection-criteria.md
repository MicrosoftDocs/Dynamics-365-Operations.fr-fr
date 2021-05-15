---
title: Créer des critères de sélection de prix de vente
description: Cette procédure indique comment créer un critère de sélection de prix de vente pour les modèles de prix de vente basés sur des attributs.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920529"
---
# <a name="create-sales-price-selection-criteria"></a>Créer des critères de sélection de prix de vente

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment créer un critère de sélection de prix de vente pour les modèles de prix de vente basés sur des attributs. Cette procédure nécessite qu’au moins un modèle de prix de vente soit disponible. Cet exemple utilise le modèle de prix du modèle de prix de vente de la solution Haut-parleur dans les données de démonstration de la société fictive USMF. Généralement, un responsable de produit utilise cette procédure.

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Ajouter un nouveau critère pour un modèle de prix de vente existant

1. Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.
1. Dans la liste, sélectionnez la ligne du modèle de produit de la solution Haut-parleur, mais ne cliquez pas sur le lien du nom du modèle.
1. Dans le volet Actions, sélectionnez **Modèle**.
1. Sélectionnez **Critères de modèle de prix**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Nom**, tapez « Groupe de clients 10 ».
    * Le nom du critère de modèle de prix permet d’identifier les critères de sélection sous-jacents.  
1. Dans le champ **Modèle de prix**, entrez ou sélectionnez une valeur.
1. Dans le champ **Type de commande**, sélectionnez *Commande client*.
    * Le type de commande détermine les champs de base de données disponibles pour la requête de sélection.  
1. Dans le champ **Début de validité**, entrez une date.
1. Dans le champ **Expiration**, entrez une date.
1. Sélectionnez **Enregistrer**.

## <a name="create-the-query-for-the-selection-criteria"></a>Créer la requête pour les critères de sélection

1. Sélectionnez **Modifier**.
2. Dans le champ **Table**, sélectionnez *Clients*.
3. Dans le champ **Champ**, sélectionnez *Groupe de clients*.
    * Dans cet exemple, nous utilisons un groupe de clients spécifique pour les critères de sélection.  
4. Dans le champ **Critères**, sélectionnez *Groupe de clients 10*.
5. Cliquez sur **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]