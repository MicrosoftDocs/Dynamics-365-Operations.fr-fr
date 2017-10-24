--- 
title: "Paramétrer des stratégies pour les hiérarchies de catégories d'approvisionnement"
description: "Cette procédure permet de définir des règles pour commander des produits dans une catégorie."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 50764f99be04d27e04047824f870e724336cb452
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>Paramétrer des stratégies pour les hiérarchies de catégories d'approvisionnement

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure permet de définir des règles pour commander des produits dans une catégorie. Les règles sont définies pour une politique d'achat spécifique. La règle d'accès à la catégorie détermine à quelles catégories d'approvisionnement les utilisateurs ont accès lorsqu'ils créent une demande. Lorsqu'une demande est créée, la règle d'accès aux catégories et la politique d'achat à appliquer est déterminée en fonction de l'entité juridique et l'unité opérationnelle auxquelles l'employé appartient. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF. Cette tâche est généralement effectuée par un responsable des achats.


## <a name="find-the-procurement-policy"></a>Rechercher la stratégie d'approvisionnement
1. Allez dans Approvisionnements > Paramétrage > Stratégies > Politiques d'achat.
2. Cliquez sur le lien de la stratégie d'approvisionnement USMF.
    * Il s'agit de la stratégie à laquelle vous devez ajouter la règle. Il doit s'agir d'une stratégie Active.  

## <a name="create-a-category-access-rule"></a>Création d'une règle d'accès à la catégorie
1. Sélectionnez la règle de stratégie d'accès à la catégorie.
    * Le bouton Créer une règle de stratégie est estompé parce qu'il y a déjà une règle de stratégie active pour l'accès à la catégorie. Vérifiez les champs Date d'effet et Date d'expiration pour déterminer de quelle règle il s'agit, puis sélectionnez-la et cliquez sur Supprimer la règle de stratégie. Si le bouton Créer une règle de stratégie est disponible, vous n'avez rien à faire.  
2. Cliquez sur Créer une règle de stratégie.
3. Entrez une date et une heure dans le champ Date d'effet.
    * La durée ne doit pas chevaucher une autre règle qui est déjà active.  
    * Choisissez une catégorie à la laquelle la règle s'appliquera. Notez la catégorie dont il s'agit, vous en aurez besoin plus tard. Lorsque vous sélectionnez une catégorie, sa ou ses catégories parentes sont également ajoutées à la liste Catégories sélectionnées.  
    * Pour appliquer la règle à toutes les sous-catégories de la catégorie sélectionnée, cochez la case Inclure les sous-catégories.  
4. Cliquez sur Ajouter.
    * Si vous définissez l'option Inclure la règle parent sur Oui, la règle de stratégie que vous définissez pour une catégorie parente est également affectée à ses catégories enfants si aucune règle de stratégie n'a été définie pour les catégories enfants.  
5. Cliquez sur OK.

## <a name="create-a-category-policy-rule"></a>Création d'une règle de stratégie de catégorie.
1. Sélectionner la règle de stratégie de catégorie
    * Si le bouton Créer une règle de stratégie est estompé, choisissez la règle de stratégie active, puis cliquez sur Supprimer la règle de stratégie.  
2. Cliquez sur Créer une règle de stratégie.
3. Entrez une date et une heure dans le champ Date d'effet.
4. Cliquez sur Ajouter.
5. Choisissez la même catégorie que celle utilisée pour la règle d'accès à la catégorie.
6. Dans le champ Sélection de fournisseur, sélectionnez une option.
    * Choisissez une règle pour contrôler le genre de fournisseur qui peut être choisi pour la catégorie quand des demandes sont créées.  
7. Cliquez sur Fermer.
    * Les règles de stratégie que vous avez définies concernaient des demandes de type Consommation. Pour définir des stratégies pour des demandes de type Réapprovisionnement, vous devez créer une règle pour le type de règle de stratégie appelé « Règle de stratégie d'accès à la catégorie de réapprovisionnement ».  


