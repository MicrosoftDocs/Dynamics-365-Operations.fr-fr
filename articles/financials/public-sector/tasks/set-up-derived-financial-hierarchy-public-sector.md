--- 
title: "Paramétrer une hiérarchie financière dérivée dans le secteur public"
description: "Pour répondre aux exigences des principales classifications comptables applicables au niveau gouvernemental, les organisations du secteur public peuvent utiliser des hiérarchies financières dérivées afin de recueillir et d'analyser des données de transaction validées pour des numéros de compte principal, des numéros de compte complet et des valeurs de dimension financière spécifiques."
author: twheeloc
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole, LedgerDerivedFinHierarchyLegalEntities, LedgerDerivedFinHierarchies
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1677d92119704ff2540f706512b383eeaa065ed9
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-a-derived-financial-hierarchy-in-the-public-sector"></a>Paramétrer une hiérarchie financière dérivée dans le secteur public

[!include [task guide banner](../../includes/task-guide-banner.md)]

Pour répondre aux exigences des principales classifications comptables applicables au niveau gouvernemental, les organisations du secteur public peuvent utiliser des hiérarchies financières dérivées afin de recueillir et d'analyser des données de transaction validées pour des numéros de compte principal, des numéros de compte complet et des valeurs de dimension financière spécifiques. Cette procédure a été créée à l'aide des données de la société fictive PSUS dans la partition du secteur public.


## <a name="create-a-category-hierarchy"></a>Créer une hiérarchie de catégories
1. Accédez à Gestion des informations sur les produits > Paramétrage > Catégories et d'attributs > Hiérarchies de catégories.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Créer.
6. Cliquez sur Nouveau nœud de catégorie.
7. Tapez une valeur dans le champ Nom.
8. Dans le champ Code, tapez une valeur.
9. Cliquez sur Nouveau nœud de catégorie.
10. Tapez une valeur dans le champ Nom.
11. Dans le champ Code, tapez une valeur.
    * (Facultatif) Ajoutez des nœuds enfants supplémentaires, ou définissez des options supplémentaires pour les nœuds que vous avez créés.  
12. Cliquez sur Enregistrer.

## <a name="assign-the-derived-financial-hierarchy-category-type"></a>Affecter le type de catégorie Hiérarchie financière dérivée
1. Accédez à Gestion des informations sur les produits > Paramétrage > Catégories et attributs > Associations de rôles de hiérarchie de catégories.
2. Cliquez sur Nouveau.
3. Dans le champ Type de hiérarchie de catégories, sélectionnez « Hiérarchie financière dérivée ».
4. Dans le champ Hiérarchie de catégories, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquez sur la hiérarchie de catégories à associer au type Hiérarchie financière dérivée.
6. Cliquez sur Enregistrer.

## <a name="associate-the-derived-financial-hierarchy-with-a-legal-entity"></a>Associer la hiérarchie financière dérivée à une entité juridique
1. Accédez à Comptabilité > Plan de comptes > Dimensions > Associer des hiérarchies financières.
2. Cliquez sur Nouveau.
3. Dans le champ Entité juridique, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, sélectionnez l'entité juridique à associer à la hiérarchie financière dérivée.
5. Dans le champ Hiérarchie financière dérivée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, sélectionnez la hiérarchie financière dérivée à associer à l'entité juridique.
7. Cliquez sur Enregistrer.

## <a name="create-filter-rules-for-the-derived-financial-hierarchy"></a>Créer des règles de filtre pour la hiérarchie financière dérivée
1. Accédez à Comptabilité > Plan de comptes > Dimensions > Hiérarchies financières dérivées.
2. Dans le champ Hiérarchie financière dérivée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, cliquez sur la hiérarchie pour laquelle créer des règles de filtre.
4. Dans l'arborescence, sélectionnez un nœud enfant.
5. Cliquez sur Modifier le filtre.
    * Cliquez sur Ajouter de nouveaux critères pour commencer à ajouter des règles au filtre. Après avoir ajouté tous les critères, cliquez sur Activer le filtre.  


