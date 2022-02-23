---
title: Créer un catalogue d'approvisionnement
description: Cette rubrique illustre la création d'un catalogue d'approvisionnement.
author: RichardLuan
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eaf8b8d8b369aa704344d6984a0f111af6e4285b
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016475"
---
# <a name="create-a-procurement-catalog"></a>Créer un catalogue d'approvisionnement

[!include [banner](../../includes/banner.md)]

Cette rubrique illustre la création d'un catalogue d'approvisionnement. Cette tâche est généralement effectuée par un professionnel de l'approvisionnement. Vous apprendrez également comment les employés peuvent utiliser le catalogue quand ils créent une demande. Avant que vous puissiez créer un catalogue, il doit y avoir une hiérarchie des catégories d'approvisionnement dans votre système. La hiérarchie est héritée par le nouveau catalogue, avec tous les produits qui sont dans la hiérarchie. Vous pouvez utiliser ce guide dans les données de démonstration de la société USMF où la hiérarchie des catégories d'approvisionnement est disponible, ainsi que les exemples utilisés dans les étapes de procédure.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Assurez-vous qu'une hiérarchie des catégories d'approvisionnement existe
1. Accédez au **Volet de navigation > Modules > Approvisionnements > Catégories d'approvisionnement**. Une hiérarchie de catégories d'approvisionnement est disponible dans la société fictive USMF et les produits ont été ajoutés à la catégorie **Équipements de bureau/Ordinateurs**. Si vous exécutez cette procédure en tant que guide des tâches, vous devrez peut-être déverrouiller le guide pour parcourir la catégorie. Si une hiérarchie n'est pas disponible, vous devez la créer en cliquant sur **Nouveau**. Ceci peut seulement être fait une fois.  
2. Fermez la page.

## <a name="create-a-catalog"></a>Création d'un catalogue
1. Accédez au **Volet de navigation > Modules > Approvisionnements > Catalogues > Catalogues d'approvisionnement**.
2. Sélectionnez **Nouveau catalogue d'approvisionnement** pour ouvrir la boîte de dialogue.
3. Tapez une valeur dans le champ **Nom**.
4. Cliquez sur **OK**.
5. Dans l'arborescence, développez **CATÉGORIES D'APPROVISIONNEMENT DE L'ENTREPRISE**.
6. Dans l'arborescence, développez **ORDINATEURS DE BUREAU**.
7. Dans l'arborescence, sélectionnez **Ordinateurs**.

  - Les produits du catalogue d'approvisionnement sont affichés dans la liste. Si vous voulez ajouter un produit à la catégorie vous devez le faire sur la page **Hiérarchie des catégories d'approvisionnement** ou sur la page **Détails de l'article**.  
  - Le type de mise à jour de **défaut** détermine si de nouveaux produits nouveaux qui ont été ajoutés à la hiérarchie des catégories d'approvisionnement sont immédiatement visibles dans le catalogue. Si le type de mise à jour est défini sur **Dynamique**, les changements sont visibles immédiatement. Si le type de mise à jour est **Statique**, les nouveaux produits sont seulement visibles pour les utilisateurs employant le catalogue une fois qu'il a été republié. L'action **Publier** est disponible sur le volet Action en haut de la page. Si des produits sont supprimés de la hiérarchie des catégories d'approvisionnement, le changement est immédiatement visible, indépendamment de la valeur du champ Type de mise à jour **par défaut**.  

8. Dans le volet Actions, sélectionnez **Navigation de catégorie** et assurez-vous que **Activer** est sélectionné.
9. Sélectionner **Activer le catalogue**.
10. Fermez la page.

## <a name="make-the-catalog-visible"></a>Rendre le contrôle visible
1. Accédez au **Volet de navigation > Modules > Approvisionnements > Paramétrage > Stratégies > Stratégies d'achat**.
2. Sélectionnez **Choisissez Stratégie d'approvisionnement USMF**. Vous devez choisir la politique d'achat pour l'entité juridique pour laquelle le collaborateur associé à votre profil utilisateur est autorisé à commander des produits. Dans les données de démonstration de la société fictive USMF, l'utilisateur Admin est relié à la collaboratrice appelée **Julia Funderburk**, et elle commande des produits dans USMF par défaut.  
3. Sélectionnez le catalogue que vous venez de créer.
4. Cliquez sur **OK**.

## <a name="use-the-catalog"></a>Utiliser le catalogue
1. Allez dans le **volet de navigation > Modules > Approvisionnement > Demandes d'achat > Toutes les demandes d'achat**.
2. Sélectionnez **Nouveau**.
3. Tapez une valeur dans le champ **Nom**.
4. Cliquez sur **OK**.
5. Sélectionnez **Ajouter les produits**.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Vous pouvez utiliser la hiérarchie de catégorie du côté gauche ou le filtre en haut de la liste pour filtrer les produits.  
7. Sélectionnez **Ajouter aux lignes**.
8. Cliquez sur **OK**.

