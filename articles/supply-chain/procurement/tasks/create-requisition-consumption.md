---
title: Créer une demande de consommation
description: Cette rubrique décrit le processus de création d'une demande.
author: mkirknel
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2948282d8b40f7d34ffbae072a195cf954ab6e2
ms.sourcegitcommit: 81e6eaa2178fda7f7d086ad978f4c891bc4ec10a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2019
ms.locfileid: "1738902"
---
# <a name="create-a-requisition-for-consumption"></a>Créer une demande de consommation

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique décrit le processus de création d'une demande. Elle vous indique les différentes manières de rechercher des produits dans votre catalogue d'approvisionnement et comment ajouter un produit qui n'est pas dans votre catalogue. Avant de démarrer cette procédure, vous devez avoir un paramétrage de stratégie d'achat avec Consommation comme type de demande par défaut. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données. La procédure peut uniquement être réalisée par un profil utilisateur qui est paramétré en tant que collaborateur. Cette tâche serait normalement réalisée par un employé. Le rôle de sécurité **Employé** vous permettra d'effectuer les tâches, ou si vous utilisez USMF, vous pouvez vous connecter en tant qu'**Alicia**.


## <a name="create-a-new-requisition"></a>Créer une nouvelle demande
1. Allez dans le **volet de navigation > Modules > Approvisionnement > Demandes d'achat > Demandes d'achat préparées par moi**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom**, entrez un nom pour la demande.
4. Dans le champ **Date demandée**, entrez une date. Par défaut, la date demandée et la date comptable sont copiées dans les lignes de demandes d'achats. Elles peuvent être modifiées au niveau de la ligne. La date demandée correspond à la date de livraison demandée.  
5. Dans le champ **Date comptable**, entrez une date. La date comptable permet d'enregistrer l'écriture comptable dans la comptabilité et de contrôler la disponibilité des fonds budgétaires.  
6. Cliquez sur **OK**.
7. Dans le champ **Motif**, sélectionnez une option dans le menu déroulant. Par défaut, le motif de justification de la demande sélectionné apparaît pour les lignes de demande d'achat, mais vous pouvez le modifier au niveau de la ligne.  
8. Sélectionnez la raison.
9. Dans le champ **Détails**, entrez une justification plus descriptive de la demande.

## <a name="add-a-line-to-the-requisition"></a>Ajouter une ligne à la demande
1. Sélectionnez **Ajouter la ligne**. Il existe deux manières d'ajouter des lignes à la demande d'achat. Si vous connaissez déjà le numéro de produit ou si vous savez déjà que vous demandez un produit qui n'est pas dans le catalogue de produits, vous pouvez ajouter la ligne directement à l'aide de **Ajouter la ligne**. L'autre manière consiste à utiliser **Ajouter des produits** pour pouvoir utiliser la recherche et le filtrage pour trouver des articles du catalogue de produits.    
2. Sélectionnez la ligne que vous venez de créer.
    - Le demandeur est le collaborateur qui a effectué la demande.   
    - Par défaut, la personne préparant la demande est le collaborateur qui l'a demandée. Vous devez disposer de l'autorisation de préparer une ligne de demande au nom d'un autre employé. Si vous disposez de telles autorisations, alors les autres employés apparaîtront dans cette recherche.  
3. Dans le champ **Numéro d'article**, tapez une valeur. Les articles disponibles sont limités par la stratégie d'accès à la catégorie et le catalogue d'approvisionnement pour l'entité juridique d'achat.   
4. Entrez un nombre dans le champ **Quantité**.

## <a name="add-more-products-to-the-requisition"></a>Ajouter des produits à la demande
1. Sélectionnez **Ajouter les produits**. Il s'agit de l'option qui permet de rechercher des produits dans le catalogue de produits.    
2. Dans le champ de nœud **Trouver la catégorie d'approvisionnement**, entrez la première partie du nom de la catégorie que vous recherchez, puis sélectionnez **Entrée**. Par exemple, entrez `comput`.  
3. Utilisez le raccourci **InvokeDefaultButton**.
4. Utilisez le **filtre** pour filtrer la liste des produits dans la catégorie sélectionnée.
5. Sélectionnez la carte du produit à ajouter à la demande d'achat.
6. Sélectionnez **Ajouter aux lignes**.
7. Entrez un nombre dans le champ **Quantité**.
8. Dans le champ de nœud **Trouver la catégorie d'approvisionnement**, tapez la première partie du nom de la catégorie que vous recherchez, puis sélectionnez **Entrée**. Pour cet exemple, entrez `High` (codes-barres de mise en valeur).  
9. Utilisez le raccourci **InvokeDefaultButton**.
10. Sélectionnez **Ajouter les produits non listés** pour ajouter un produit qui n'est pas répertorié dans le catalogue d'approvisionnement.
11. Dans le champ **Nom du produit**, saisissez une valeur.
12. Dans le champ **Unité**, tapez une valeur.
13. Cliquez sur **OK**.
14. Dans le champ **Description de l'article**, ajoutez une description du produit.
15. Entrez un nombre dans le champ **Quantité**.
16. Entrez un nombre dans le champ **Prix unitaire**. Si vous connaissez le prix pour un fournisseur spécifique (que vous sélectionnez dans le champ Compte fournisseur), alors ce prix peut être saisi.   
17. Dans le champ **Compte fournisseur**, ouvrez la liste déroulante pour sélectionner une option. Les fournisseurs disponibles dans ce champ dépendent des stratégies d'achat et du statut du fournisseur pour la catégorie d'approvisionnement actuelle. Au lieu de sélectionner un fournisseur ici, vous pouvez sélectionner **Suggérer un fournisseur**.    
18. Dans la liste, sélectionnez le fournisseur que vous souhaitez utiliser.
19. Dans le champ **Numéro d'article externe**, tapez une valeur. Il s'agit d'un numéro de référence pour le produit qui est connu du fournisseur. Par exemple, il peut s'agir du numéro d'article du produit dans le propre catalogue fournisseur.  
20. Cliquez sur **OK**.

## <a name="distribute-amounts"></a>Répartir les montants
1. Sélectionnez **Finances**.
2. Sélectionnez **Répartir les montants**. Ce processus vous indique comment répartir le coût pour la première ligne entre 2 comptes. Cela peut également être effectué ultérieurement lorsque la demande est en cours de révision.  
3. Sélectionnez **Fractionner** pour créer une ligne de répartition.
4. Dans le champ **Compte général**, sélectionnez le premier centre de coût qui doit participer au coût.
5. Sélectionnez l'autre ligne de répartition.
6. Dans le champ Compte général, spécifiez l'autre centre de coût.
7. Sélectionnez **Répartir en valeurs égales**.
8. Fermez la page.

## <a name="view-line-details"></a>Afficher les détails de ligne
1. Activez ou désactivez l'extension de la section **Détails de ligne**.

## <a name="submit-the-requisition"></a>Envoyer la demande
1. Sélectionnez **Workflow** pour ouvrir la boîte de dialogue.
2. Sélectionnez **Soumettre**.
3. Fermez la page.
4. Dans le champ **Commentaire**, tapez une note pour l'approbateur de la demande.
5. Sélectionnez **Soumettre**.
6. Fermez la page.
7. Actualisez la page.

