---
title: Groupes de gestion des remises
description: Cette rubrique décrit la configuration des groupes de gestion des remises. Les groupes de gestion des remises peuvent être utilisés lors des calculs de remise et peuvent être associés à un enregistrement principal.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1f9deeedef504d1b2d0ba3431902c50bc65d62ba
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572695"
---
# <a name="rebate-management-groups"></a>Groupes de gestion des remises

[!include [banner](../includes/banner.md)]

Les calculs de gestion des remise peuvent être déterminés par des groupes. Il est possible de créer des groupes de gestion des remises pour les clients, les fournisseurs et les articles. Ils peuvent être joints à un enregistrement principal.

## <a name="rebate-management-customer-groups"></a>Groupes de clients pour la gestion des remises

Le calcul pour un groupe de clients est souvent créé pour une chaîne d’entreprises, comme une chaîne de supermarchés ou une entreprise franchisée. Ce type de calcul est généralement lié à une remise.

Une déduction est souvent calculée sans tenir compte de la personne à qui la commande admissible a été vendue. Il existe cependant des exceptions. Par exemple, un titulaire de licence peut créer un système de déduction dans lequel le groupe de clients A recevra 4 pour cent, mais le groupe de clients B ne recevra que 3 pour cent.

### <a name="set-up-customer-groups"></a>Paramétrer les groupes de clients

Pour utiliser les groupes de clients pour la gestion des remises, accédez à **Gestion des remises \> Configuration des groupes de gestion des remises \> Groupes de clients**. Vous pouvez utiliser les boutons du volet Actions pour ajouter et supprimer des groupes selon vos besoins. Pour chaque groupe, définissez les champs suivants :

- **Groupe de gestion des remises** : entrez un nom unique pour le groupe.
- **Description** : entrez une description du groupe pour fournir plus d’informations sur la façon dont il doit être utilisé.

### <a name="manage-customer-group-assignments"></a>Gérer les affectations des groupes de clients

Chaque client peut appartenir à n’importe quel nombre de groupes de gestion des remises. Pour afficher et affecter les membres du groupe, vous pouvez partir de la liste des groupes ou de la liste des clients.

Pour afficher, ajouter ou supprimer des clients d’un groupe sélectionné, procédez comme suit :

1. Accédez à **Gestion des remises \> Configuration des groupes de gestion des remises \> Groupes de clients**.
1. Sélectionnez le groupe à gérer.
1. Dans le volet Action, sélectionnez **Clients**. La page **Groupes de gestion des remises** apparaît et affiche une liste de clients qui sont déjà membres du groupe sélectionné.
1. Pour ajouter un nouveau client au groupe, sélectionnez **Nouveau** dans le volet Actions pour ajouter une ligne à la grille. Définissez ensuite le champ suivant pour la nouvelle ligne :

    - **Compte client** : sélectionnez l’ID de compte client.

1. Pour supprimer un client du groupe, sélectionnez le client, puis sélectionnez **Supprimer** dans le volet Actions.

Pour afficher, ajouter ou supprimer des affectations de groupe pour un client sélectionné, procédez comme suit :

1. Allez dans **Comptabilité client \> Clients \> Tous les clients**.
1. Sélectionnez le client concerné.
1. Dans le volet Actions, sous l’onglet **Client**, dans le groupe **Gestion des remises**, sélectionnez **Groupes de gestion des remises**. La page **Groupes de gestion des remises** apparaît et affiche une liste des groupes auxquels appartient déjà le client.
1. Pour ajouter le client à un nouveau groupe, sélectionnez **Nouveau** dans le volet Actions pour ajouter une ligne à la grille. Définissez ensuite le champ suivant pour la nouvelle ligne :

    - **Groupe de gestion des remises** : sélectionnez le groupe auquel ajouter le client.

1. Pour supprimer un client d’un groupe, sélectionnez le groupe, puis sélectionnez **Supprimer** dans le volet Actions.

## <a name="rebate-management-vendor-groups"></a>Groupes de fournisseurs pour la gestion des remises

Le calcul pour un groupe de fournisseurs est souvent créé pour un groupe de points de livraison. Ce type de calcul est généralement lié à une remise.

### <a name="set-up-vendor-groups"></a>Configuration des groupes de fournisseurs

Pour utiliser les groupes de fournisseurs pour la gestion des remises, accédez à **Gestion des remises \> Configuration des groupes de gestion des remises \> Groupes de fournisseurs**. Vous pouvez utiliser les boutons du volet Actions pour ajouter et supprimer des groupes selon vos besoins. Pour chaque groupe, définissez les champs suivants :

- **Groupe de gestion des remises** : entrez un nom unique pour le groupe.
- **Description** : entrez une description du groupe pour fournir plus d’informations sur la façon dont il doit être utilisé.

### <a name="manage-vendor-group-assignments"></a>Gérer les affectations des groupes de fournisseurs

Chaque fournisseur peut appartenir à n’importe quel nombre de groupes de gestion des remises. Pour afficher et affecter les membres du groupe, vous pouvez partir de la liste des groupes ou de la liste des fournisseurs.

Pour afficher, ajouter ou supprimer des fournisseurs d’un groupe sélectionné, procédez comme suit :

1. Accédez à **Gestion des remises \> Configuration des groupes de gestion des remises \> Groupes de fournisseurs**.
1. Sélectionnez le groupe à gérer.
1. Dans la volet Actions, sélectionnez **Fournisseurs**. La page **Groupes de gestion des remises** apparaît et affiche une liste de fournisseurs qui sont déjà membres du groupe sélectionné.
1. Pour ajouter un nouveau fournisseur au groupe, sélectionnez **Nouveau** dans le volet Actions pour ajouter une ligne à la grille. Définissez ensuite le champ suivant pour la nouvelle ligne :

    - **Compte fournisseur** : sélectionnez l’ID de compte fournisseur.

1. Pour supprimer un fournisseur du groupe, sélectionnez le fournisseur, puis sélectionnez **Supprimer** dans le volet Actions.

Pour afficher, ajouter ou supprimer des affectations de groupe pour un fournisseur sélectionné, procédez comme suit :

1. Accédez à **Comptabilité fournisseur \> Fournisseurs \> Tous les fournisseurs**.
1. Sélectionnez le fournisseur concerné.
1. Dans le volet Actions, sous l’onglet **Fournisseur**, dans le groupe **Gestion des remises**, sélectionnez **Groupes de gestion des remises**. La page **Groupes de gestion des remises** apparaît et affiche une liste des groupes auxquels appartient déjà le fournisseur.
1. Pour ajouter le fournisseur à un nouveau groupe, sélectionnez **Nouveau** dans le volet Actions pour ajouter une ligne à la grille. Définissez ensuite le champ suivant pour la nouvelle ligne :

    - **Groupe de gestion des remises** : sélectionnez le groupe auquel ajouter le fournisseur.

1. Pour supprimer un fournisseur d’un groupe, sélectionnez le groupe, puis sélectionnez **Supprimer** dans le volet Actions.

## <a name="item-rebate-groups"></a>Groupes de remises d’article

En regroupant les articles, vous bénéficiez d’une plus grande flexibilité lors du calcul des remises et des déductions. Cette approche est souvent plus efficace pour mettre en place des remises et des déductions pour les clients et les fournisseurs.

### <a name="set-up-item-groups"></a>Paramétrer des groupes d’articles

Pour utiliser les groupes d’articles pour la gestion des remises, accédez à **Gestion des remises \> Configuration des groupes de gestion des remises \> Groupes d’articles**. Vous pouvez utiliser les boutons du volet Actions pour ajouter et supprimer des groupes selon vos besoins. Pour chaque groupe, définissez les champs suivants :

- **Groupe de gestion des remises** : entrez un nom unique pour le groupe.
- **Description** : entrez une description du groupe pour fournir plus d’informations sur la façon dont il doit être utilisé.

### <a name="manage-item-group-assignments"></a>Gérer les affectations des groupes d’articles

Chaque article peut appartenir à n’importe quel nombre de groupes de gestion des remises. Pour afficher et affecter les membres du groupe, vous pouvez partir de la liste des groupes ou de la liste des articles. Vous pouvez également ajouter des articles en fonction de votre hiérarchie de catégories.

Pour afficher, ajouter ou supprimer des articles d’un groupe sélectionné, procédez comme suit :

1. Accédez à **Gestion des remises \> Configuration des groupes de gestion des remises \> Groupes d’articles**.
1. Sélectionnez le groupe à gérer.
1. Dans le volet Actions, sélectionnez **Articles**. La page **Groupes de gestion des remises** apparaît et affiche une liste d’articles qui sont déjà membres du groupe sélectionné.
1. Pour ajouter un nouvel article au groupe, sélectionnez **Nouveau** dans le volet Actions pour ajouter une ligne à la grille. Définissez ensuite le champ suivant pour la nouvelle ligne :

    - **Compte article** : sélectionnez l’ID de compte article.

1. Pour supprimer un article du groupe, sélectionnez l’article, puis sélectionnez **Supprimer** dans le volet Actions.

Pour afficher, ajouter ou supprimer des affectations de groupe pour un article sélectionné, procédez comme suit :

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez l’article concerné.
1. Dans le volet Actions, sous l’onglet **Produit**, dans le groupe **Gestion des remises**, sélectionnez **Groupes de gestion des remises**. La page **Groupes de gestion des remises** apparaît et affiche une liste des groupes auxquels appartient déjà l’article.
1. Pour ajouter l’article à un nouveau groupe, sélectionnez **Nouveau** dans le volet Actions pour ajouter une ligne à la grille. Définissez ensuite le champ suivant pour la nouvelle ligne :

    - **Groupe de gestion des remises** : sélectionnez le groupe auquel ajouter l’article.

1. Pour supprimer un article d’un groupe, sélectionnez le groupe, puis sélectionnez **Supprimer** dans le volet Actions.

Pour ajouter des articles à un groupe en fonction de votre hiérarchie de catégories, procédez comme suit :

1. Accédez à **Gestion des remises \> Configuration des groupes de gestion des remises \> Groupes d’articles**.
1. Sélectionnez le groupe à gérer.
1. Dans le volet Actions, sélectionnez **Ajouter des articles**.
1. Dans la boîte de dialogue **Ajouter des articles**, dans le champ **Hiérarchie des catégories**, sélectionnez une catégorie de niveau supérieur.
1. La hiérarchie des articles s’ouvre dans le volet gauche. Sélectionnez le niveau de hiérarchie que vous recherchez. 
1. Les articles de la hiérarchie et du niveau de hiérarchie sélectionnés sont désormais répertoriés dans le volet droit. Procédez comme suit pour utiliser le volet :

    - Activez la case à cocher pour chaque article à ajouter.
    - Cochez la case de l’en-tête de la grille pour sélectionner tous les éléments répertoriés.
    - Sélectionnez le bouton **Afficher la sélection** pour filtrer la grille afin qu’elle n’affiche que les articles que vous avez sélectionnés jusqu’à présent. Sélectionnez à nouveau le bouton pour revenir à la liste complète.

1. Sélectionnez **OK** pour appliquer votre sélection d’articles au groupe sélectionné.
