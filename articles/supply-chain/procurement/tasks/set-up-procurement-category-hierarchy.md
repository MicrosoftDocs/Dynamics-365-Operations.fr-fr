--- 
title: "Paramétrage d'une hiérarchie des catégories d'approvisionnement"
description: "Cette procédure vous indique comment créer de nouveaux nœuds dans une hiérarchie des catégories d'approvisionnement et comment configurer une catégorie d'approvisionnement à utiliser dans processus d'approvisionnement."
author: mkirknel
manager: AnnBe
ms.date: 11/06/2017
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
ms.sourcegitcommit: 6ad5c8552a6989e9093d0b1325754bc0f6d19372
ms.openlocfilehash: 4541d029c9c3be3ee42332e5d8ff183dd503f13e
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-a-procurement-category-hierarchy"></a>Paramétrage d'une hiérarchie des catégories d'approvisionnement

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous indique comment créer de nouveaux nœuds dans une hiérarchie des catégories d'approvisionnement et comment configurer une catégorie d'approvisionnement à utiliser dans processus d'approvisionnement. Ces tâches sont généralement effectuées par un responsable des achats. Avant de démarrer cette procédure, il doit y avoir une hiérarchie de catégories de type Approvisionnement. Si vous utilisez une société de données de démonstration, vous pouvez exécuter cette procédure à l'aide de la société USMF.


## <a name="add-a-new-procurement-category"></a>Ajouter une catégorie d'approvisionnement
1. Accédez à Approvisionnements > Catégories d'approvisionnement.
2. Cliquez sur Modifier la hiérarchie de la catégorie.
    * La hiérarchie des catégories d'approvisionnement actuelle s'affiche à la gauche de la page. Vous êtes sur le point de modifier la hiérarchie.  
3. Cliquez sur Nouveau nœud de catégorie.
    * Le système sélectionne le nœud supérieur par défaut. Si vous exécutez cette procédure en tant que guide des tâches, vous pouvez cliquer sur le bouton Déverrouiller et sélectionner un autre nœud parent dans lequel insérer votre nouveau nœud. Une fois que c'est fait, verrouillez à nouveau le guide de tâches, puis cliquez sur Nouveau nœud de catégorie.  
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Description, entrez une valeur.
6. Dans le champ Nom convivial, saisissez une valeur.
    * Le nom convivial est facultatif. Il sera affiché dans les recherches de catégories avec le nom de la catégorie.  
7. Cliquez sur Enregistrer.

## <a name="add-products-to-your-new-procurement-category"></a>Ajouter des produits à une nouvelle catégorie d'approvisionnement
1. Accédez à Approvisionnements > Catégories d'approvisionnement.
    * Sélectionnez le nœud que vous venez d'ajouter. Si vous exécutez cette procédure en tant que guide des tâches, vous devrez peut-être déverrouiller le guide des tâches pour sélectionner le nœud.  
2. Activez ou désactivez l'extension de la section Produits.
3. Cliquez sur Ajouter pour associer des produits à la catégorie d'approvisionnement.
4. Sélectionnez les produits à ajouter à la catégorie d'approvisionnement.
5. Cliquez sur la flèche pour sélectionner le produit.
6. Sélectionnez d'autres produits à ajouter à la catégorie d'approvisionnement.
7. Cliquez sur la flèche pour sélectionner le produit.
8. Cliquez sur OK.

## <a name="add-approved-and-preferred-vendors"></a>Ajouter des fournisseurs approuvés et préférés
1. Activez ou désactivez l'extension de la section Fournisseurs.
2. Cliquez sur Ajouter.
    * Vous pouvez ajouter un fournisseur à une catégorie d'approvisionnement et spécifier si un fournisseur est préféré ou simplement approuvé dans la catégorie. Lorsque vous supprimez un fournisseur d'une catégorie, les transactions d'historique avec le fournisseur de la catégorie ne sont pas supprimées.   
3. Localisez le fournisseur à ajouter à la catégorie d'approvisionnement.
4. Cliquez sur la flèche pour sélectionner le fournisseur.
5. Cliquez sur OK.
6. Sélectionnez la ligne fournisseur que vous souhaitez modifier.
7. Dans le champ Statut du fournisseur, sélectionnez une option.
    * Le paramètre de sélection du fournisseur dans la règle Stratégie de catégorie régit si les fournisseurs préférés ou approuvés ou si tous les fournisseurs sont disponibles sur les demandes d'achat.   

## <a name="add-additional-information-to-the-category"></a>Ajouter des informations supplémentaires à la catégorie
1. Activez ou désactivez l'extension de la section Groupes de critères d'évaluation du fournisseur.
    * Cet onglet permet de définir les critères de classement des fournisseurs dans la catégorie d'approvisionnement. Pour ce faire, cliquez sur Ajouter, puis sélectionnez un groupe d'évaluation des fournisseurs qui contient les critères vous souhaitez.  
2. Activez ou désactivez l'extension de la section Questionnaires.
    * Cet onglet permet d'ajouter des questionnaires qui apparaîtront sur la demande, à la condition que vous définissiez le type d'activité sur « Demande ». Le demandeur doit ensuite remplir un questionnaire avant d'envoyer une demande pour le ou les produits spécifiques dans la catégorie d'approvisionnement.  
3. Activez ou désactivez l'extension de la section Groupes de taxe d'article.
4. Dans le champ Groupes de taxe d'article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Permet de sélectionner un groupe de taxe.
6. Activez ou désactivez l'extension de la section Page des catégories.
    * Les pages Catégorie sont créées dans la page Hiérarchie de catégories. Elles contiennent des 'informations sur la catégorie d'approvisionnement, comme le type de produits dans une catégorie, des images de produits dans une catégorie ou des annonces, telles que les remises disponibles dans une catégorie. Les informations dans une page de catégorie sont affichées sur les demandes d'achat.  
7. Fermez la page.


