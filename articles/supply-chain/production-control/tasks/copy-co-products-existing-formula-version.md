---
title: Copier les coproduits à partir d’une version de formule existante
description: Cette procédure vous indique comment copier des coproduits à partir d’une version de formule existante vers une autre version de formule pour un produit lancé.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cbcf2abc37441f9ff23e2b180c261831dfb79369
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829280"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a>Copier les coproduits à partir d’une version de formule existante

[!include [banner](../../includes/banner.md)]

Cette procédure vous indique comment copier des coproduits à partir d’une version de formule existante vers une autre version de formule pour un produit lancé. Condition préalable : au moins une version de formule doit être associée à des coproduits. Pour créer cette procédure, la société fictive de démonstration USP2 est utilisée.


## <a name="find-a-released-product"></a>Rechercher un produit lancé
1. Allez dans Produits lancés.
2. Cliquez sur Afficher les filtres.
    * Vous êtes sur le point d’ajouter le champ Type de production dans la boîte de dialogue de filtre.  
3. Cliquez sur Ajouter un champ de filtre pour ajouter le champ Type de production.
    * Dans l’étape suivante, vous devez entrer manuellement une formule dans le champ Type de production avant de sélectionner Appliquer. Cela définit le filtre sur la liste des produits lancés.  
4. Entrez manuellement la formule dans le champ Type de production.
5. Cliquez sur Appliquer.

## <a name="select-a-released-product"></a>Sélectionner un produit lancé
1. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
2. Cliquez sur Versions de formule.
    * Dans le volet Action d’ingénierie, cliquez sur Versions de formule.  

## <a name="copy-co-products"></a>Copier des coproduits
1. Dans le volet Actions, cliquez Version de formule.
2. Cliquez sur Co-produits.
3. Cliquez sur Copier.
4. Entrez ou sélectionnez une valeur dans le champ Numéro d’article.
5. Dans le champ Version de formule, saisissez ou sélectionnez une valeur.
6. Cliquez sur OK.
7. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]