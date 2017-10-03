--- 
title: "Créer un catalogue d'approvisionnement"
description: "Ce guide vous indique comment créer un catalogue d'approvisionnement."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 19d053a0bdbdcc764b3361fe5a326e8c68cdc682
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-procurement-catalog"></a>Créer un catalogue d'approvisionnement

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce guide vous indique comment créer un catalogue d'approvisionnement. Cette tâche est généralement effectuée par un professionnel de l'approvisionnement. Vous apprendrez également comment les employés peuvent utiliser le catalogue quand ils créent une demande. Avant que vous puissiez créer un catalogue, il doit y avoir une hiérarchie des catégories d'approvisionnement dans votre système. La hiérarchie est héritée par le nouveau catalogue, avec tous les produits qui sont dans la hiérarchie. Vous pouvez utiliser ce guide dans les données de démonstration de la société USMF où la hiérarchie des catégories d'approvisionnement est disponible, ainsi que les exemples utilisés dans les étapes de procédure.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Assurez-vous qu'une hiérarchie des catégories d'approvisionnement existe
1. Accédez à Approvisionnements > Catégories d'approvisionnement.
    * Une hiérarchie de catégories d'approvisionnement est disponible dans la société fictive USMF et les produits ont été ajoutés à la catégorie Équipements de bureau/Ordinateurs. Si vous exécutez cette procédure en tant que guide des tâches, vous devrez peut-être déverrouiller le guide pour parcourir la catégorie. Si une hiérarchie n'est pas disponible, vous devez la créer en cliquant sur Nouveau. Ceci peut seulement être fait une fois.  
2. Fermez la page.

## <a name="create-a-catalog"></a>Création d'un catalogue
1. Allez dans Approvisionnements > Catalogues > Catalogues d'approvisionnement.
2. Cliquez sur Nouveau catalogue d'approvisionnement pour ouvrir la boîte de dialogue.
3. Tapez une valeur dans le champ Nom.
4. Cliquez sur OK.
5. Dans l'arborescence, développez « CATÉGORIES D'APPROVISIONNEMENT DE L'ENTREPRISE ».
6. Dans l'arborescence, développez ORDINATEURS DE BUREAU.
7. Dans l'arborescence, sélectionnez Ordinateurs.
    * Les produits du catalogue d'approvisionnement sont affichés dans la liste. Si vous voulez ajouter un produit à la catégorie vous devez le faire sur la page Hiérarchie des catégories d'approvisionnement ou sur la page Détails de l'article.  
    * Le type de mise à jour de défaut détermine si de nouveaux produits nouveaux qui ont été ajoutés à la hiérarchie des catégories d'approvisionnement sont immédiatement visibles dans le catalogue. Si le type de mise à jour est défini sur Dynamique, les changements sont visibles immédiatement. Si le type de mise à jour est Statique, les nouveaux produits sont seulement visibles pour les utilisateurs employant le catalogue une fois qu'il a été republié. L'action Publier est disponible sur le volet Action en haut de la page. Si des produits sont supprimés de la hiérarchie des catégories d'approvisionnement, le changement est immédiatement visible, indépendamment de la valeur du champ Type de mise à jour par défaut.  
8. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
9. Cliquez sur Masquer.
10. Dans le volet Action, cliquez sur Navigation de catégorie.
11. Cliquez sur Désactiver.
12. Dans le volet Action, cliquez sur Navigation de catégorie.
13. Cliquez sur Activer.
14. Cliquez sur Activer le catalogue.
15. Fermez la page.

## <a name="make-the-catalog-visible"></a>Rendre le contrôle visible
1. Allez dans Approvisionnements > Paramétrage > Stratégies > Politiques d'achat.
2. Choisissez Stratégie d'approvisionnement USMF.
    * Vous devez choisir la politique d'achat pour l'entité juridique pour laquelle le collaborateur associé à votre profil utilisateur est autorisé à commander des produits. Dans les données de démonstration de la société fictive USMF, l'utilisateur Admin est relié à la collaboratrice appelée Julia Funderburk, et elle commande des produits dans USMF par défaut.  
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Sélectionnez le catalogue que vous venez de créer.
5. Cliquez sur OK.
6. Fermez la page.
7. Fermez la page.

## <a name="use-the-catalog"></a>Utiliser le catalogue
1. Allez dans Approvisionnement > Demandes d'achat > Toutes les demandes d'achat.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Cliquez sur OK.
5. Cliquez sur Ajouter des produits.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Vous pouvez utiliser la hiérarchie de catégorie du côté gauche ou le filtre en haut de la liste pour filtrer les produits.  
7. Cliquez sur Ajouter aux lignes.
8. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
9. Cliquez sur Ajouter aux lignes.
10. Cliquez sur OK.

