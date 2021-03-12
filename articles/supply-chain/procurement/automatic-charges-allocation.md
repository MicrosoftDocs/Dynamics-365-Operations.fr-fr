---
title: Répartition automatique des frais
description: La fonction de frais dans Microsoft Dynamics 365 Supply Chain Management vous aide à répartir automatiquement des frais sur les bons de commande ou les commandes client.
author: dasani-madipalli
manager: tfehr
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8067285237127bd43e8ff24166a15506cc0426f4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983165"
---
# <a name="automatic-allocation-of-charges"></a>Répartition automatique des frais

[!include [banner](../includes/banner.md)]

En fonction du client avec lequel vous travaillez ou de l'article que vous vendez, vous pouvez appliquer des frais supplémentaires spécifiques. La fonction de *frais* dans Microsoft Dynamics 365 Supply Chain Management vous aide à répartir automatiquement des frais sur les bons de commande ou les commandes client.

Les frais automatiques, ou frais auto, sont appliqués automatiquement lorsque vous créez une commande client ou fournisseur. Vous pouvez définir des frais auto pour des fournisseurs, clients, groupes de fournisseurs, articles spécifiques. Vous pouvez également définir des frais auto qui s'appliquent à tous les fournisseurs, clients ou articles.

## <a name="set-up-charges-codes"></a>Paramétrer des codes frais

Pour attribuer des frais, vous devez d'abord définir des codes de frais.

1. Utilisez l’une des procédures suivantes :

    - Pour les commandes fournisseur : accédez à **Comptabilité fournisseur \> Paramétrage des frais \> Code frais**.
    - Pour les commandes client : accédez à **Comptabilité client \> Paramétrage des frais \> Code frais**.

1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un code frais.
1. Dans l’en-tête du nouvel enregistrement, définissez les champs suivants :

    - **Code frais** - Entrez un code pour les frais.
    - **Description** - Entrez une description des frais.
    - **Groupe de taxe d'article** - Sélectionnez un groupe de taxe d'article, le cas échéant.
    - **Au prorata** - Définissez cette option sur *Oui* si vous souhaitez répartir vos frais au prorata. Cette option est disponible uniquement pour les commandes client.
    - **Montant maximal** - Entrez le montant maximal autorisé pour le code frais. Ce champ est utilisé pour valider les frais pour les factures fournisseur. Il n'est disponible que pour les commandes fournisseur.

        > [!NOTE]
        > Pour activer la fonctionnalité de validation des frais des commandes fournisseur, accédez à **Comptabilité fournisseur \> Paramétrage \> Paramètres de la comptabilité fournisseur**. Sur le FastTab **Contrôle de la facture**, dans la section **Contrôle de la facture**, définissez l'option **Activer le contrôle de rapprochement de factures** sur *Oui*.

1. Le FastTab **Validation** comprend les sections **Débit** et **Crédit**. Définissez les champs suivants, en fonction de la comptabilité dans laquelle vous souhaitez valider les frais :

    - **Type** - Sélectionnez le type de compte sur lequel vous validez (*Général*, *Client*, ou *Article*).
    - **Validation** - Sélectionnez le type de validations à créer (comme *Frais de courtier* ou *Règlement client*).
    - **Compte** - Sélectionnez le compte pour lequel valider les frais.

1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="create-charge-groups"></a>Créer des groupes de frais

Les groupes de frais attribuent automatiquement des frais spécifiques à un groupe de clients ou de fournisseurs. Les sous-sections suivantes décrivent comment créer et affecter ces groupes de frais.

### <a name="charge-groups-for-purchase-orders"></a>Groupes de frais pour les commandes fournisseur

Pour créer des groupes de frais pour les commandes fournisseur, procédez comme suit.

1. Accédez à **Comptabilité fournisseur \> Paramétrage des frais \> Groupe de frais fournisseur**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille, puis définissez les champs suivants :

    - **Groupe de frais** - Saisissez le nom du groupe de frais.
    - **Description** - Entrez une description du groupe de frais.

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Accédez à **Comptabilité fournisseur \> Fournisseurs \> Tous les fournisseurs**, et ouvrez un fournisseur existant ou créez un nouveau fournisseur.
1. Sur le FastTab **Valeurs par défaut des commandes fournisseur**, dans la section **Commande fournisseur**, définissez le champ **Groupe de frais** sur le groupe de frais que vous venez de créer.

### <a name="charge-groups-for-sales-orders"></a>Groupes de frais pour les commandes client

Pour créer des groupes de frais pour les commandes client, procédez comme suit.

1. Accédez à **Comptabilité client \> Paramétrage des frais \> Groupes de frais client**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille, puis définissez les champs suivants :

    - **Groupe de frais** - Saisissez le nom du groupe de frais.
    - **Description** - Entrez une description du groupe de frais.

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Accédez à **Comptabilité client \> Clients \> Tous les clients**, et ouvrez un client existant ou créez un nouveau client.
1. Sur le FastTab **Valeurs par défaut des commandes fournisseur**, dans la section **Commande client**, définissez le champ **Groupe de frais** sur le groupe de frais que vous venez de créer.

## <a name="define-auto-charges"></a>Définition de frais automatiques

Une fois vos codes de frais configurés, suivez ces étapes pour définir les frais automatiques.

1. Utilisez l’une des procédures suivantes :

    - Pour les commandes client : accédez à **Approvisionnements \> Paramétrage \> Frais \> Frais automatiques**.
    - Pour les commandes client : accédez à **Comptabilité client \> Paramétrage \> Paramétrage des frais \> Frais automatiques**.

1. Dans le volet de liste, dans le champ **Niveau**, sélectionnez le niveau auquel s'applique vos frais automatiques :

    - *Principal* – Permet d'appliquer les frais à l'en-tête de commande.
    - *Ligne* – Permet d'appliquer les frais aux lignes de commande.

1. Sélectionnez des frais automatiques existants pour les modifier ou sélectionnez **Nouveaux** pour définir de nouveaux fais automatiques.
1. Dans la liste **Code de compte**, sélectionnez l'une des valeurs suivantes pour spécifier l'étendue des comptes qui seront affectés :

    - *Table* – Permet d'affecter les frais à un client ou à un fournisseur donné.
    - *Groupe* – Permet d'affecter les frais à un groupe de frais divers.
    - *Tous* – Permet d'affecter les frais à tous les clients ou fournisseurs.

1. Dans le champ **Relation client** ou **Relation fournisseur**, sélectionnez un client ou fournisseur spécifique, si vous définissez le champ **Code compte** sur *Table*. Si vous définissez le champ **Code de compte** sur *Groupe*, sélectionnez un groupe de frais client ou fournisseur.
1. Dans le champ **Code article**, sélectionnez l'une des valeurs suivantes pour spécifier l'étendue des articles qui seront affectés. Vous pouvez sélectionner un code article uniquement lorsque vous définissez des frais automatiques au niveau de la ligne.

    - *Table* – Permet d'affecter les frais à un article donné.
    - *Groupe* – Permet d'affecter les frais à un groupe de frais des articles.
    - *Tous* – Permet d'affecter les frais à tous les articles.

1. Dans le champ **Relation d'article**, sélectionnez un article spécifique, si vous définissez le champ **Code article** sur *Table*. Si vous définissez le champ **Code article** sur *Groupe*, sélectionnez un groupe de frais des articles.
1. **Pour les commandes client uniquement :** dans le champ **Code de mode de livraison**, sélectionnez l'une des valeurs suivantes pour spécifier l'étendue des modes de livraison qui seront concernés :

    - *Table* – Permet d'affecter des frais à un mode de livraison spécifique.
    - *Groupe* – Permet d'affecter des frais à un groupe de modes de livraison.
    - *Tous* – Permet d'affecter des frais à tous les modes de livraison.

1. **Pour les commandes client uniquement :** Dans le champ **Groupe mode de livraison**, sélectionnez un mode de livraison spécifique si vous définissez le champ **Code Mode de livraison** sur *Table*. Si vous définissez le champ **Code Mode de livraison** sur *Groupe*, sélectionnez un groupe de modes de livraison.
1. Sur le FastTab **Lignes**, définissez les frais et les taux de frais qui seront utilisés pour l'application des frais automatiques. Vous pouvez utiliser la barre d'outils de ce FastTab pour ajouter autant de lignes que vous le souhaitez. Pour chaque ligne, définissez les champs suivants :

    - **Devise** - Sélectionnez la devise à utiliser pour calculer les frais.
    - **Code frais** - Sélectionnez le code des frais.
    - **Catégorie** - Sélectionnez l’une des valeurs suivantes :

        - *Fixes* – Les frais sont entrés comme montant fixe dans la ligne. Les frais fixes peuvent porter sur l'en-tête de commande et sur les lignes de commande.
        - *Pcs* – Les frais sont basés sur l'unité. Ces frais peuvent être utilisés uniquement sur les lignes de commande. Ils apparaîtront lorsque vous calculerez le total de la commande.
        - *Pourcentage* – Les frais sont entrés sous forme de pourcentage sur la ligne. Les frais sous forme de pourcentage peuvent porter sur l'en-tête de commande et sur les lignes de commande.
        - *Pourcentage intersociétés* – Les frais sont entrés dans la ligne sous forme de pourcentage pour les commandes intersociétés. Les frais définis comme pourcentage intersociétés peuvent être utilisés uniquement sur les lignes de commande.
        - *Externes* – Les frais sont calculés par un service tiers associé à un ou plusieurs transporteurs.

    - **Valeur des frais** - Entrez la valeur des frais, en fonction de la catégorie que vous avez sélectionnée.
    - **Code devise des frais** - Spécifiez une devise pour les frais si vous souhaitez utiliser une devise autre que la devise que vous avez spécifiée dans le champ **Devise**. Il est possible d'utiliser une devise différente uniquement si le champ **Type de débit** ou **Type de crédit** est défini comme *Compte général* ou *Article* pour le code frais sélectionné.
    - **Montant de départ** - Spécifiez un montant de départ pour l'application des frais automatiques. Dans ce contexte, le montant fait référence au total de la commande.
    - **Montant d'arrivée** - Spécifiez un montant de fin pour l'application des frais automatiques. Dans ce contexte, le montant fait référence au total de la commande.
    - **Groupe de taxe** - Spécifiez un groupe de taxe.
    - **Site** et **Entrepôt** - Spécifiez un site et un entrepôt si les frais doivent être appliqués uniquement pour un site et un entrepôt spécifiques.
    - **Conserver** - Activez cette case à cocher pour conserver les transactions de frais une fois la facturation terminée, de manière à ce que les frais soient appliqués à chaque fois que vous créez une facture pour le compte client sélectionné.

1. **Pour les commandes client uniquement:** Si vous souhaitez calculer des frais progressifs, consultez [Frais progressifs sur les commandes client](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/about-tiered-charges-on-sales-orders) pour information.

## <a name="allocate-charges-from-the-header-to-a-line"></a>Répartir des frais de l'en-tête sur une ligne

La procédure suivante montre comment répartir des frais au niveau de l'en-tête sur une ligne. Avant de commencer cette procédure, vous devriez déjà avoir des frais au niveau de l'en-tête du type *Montant fixe* et une commande où ces frais sont appliqués. En outre, la commande doit déjà inclure au moins une ligne.

1. Ouvrez la commande fournisseur ou l'autorisation de débiter.
1. Dans le volet Action, procédez comme suit :

    - Pour les commandes fournisseur : Sous l'onglet **Achat**, dans le groupe **Frais**, sélectionnez **Répartir les frais**.
    - Pour les commandes client : Sous l'onglet **Vendre**, dans le groupe **Frais**, sélectionnez **Répartir les frais**.

1. Dans la boîte de dialogue **Répartir des frais sur des lignes de commande**, définissez les champs suivants :

    - **Répartition des frais** - Sélectionnez l'une des valeurs suivantes pour spécifier la manière dont les frais doivent être répartis :

        - *Montant net* - Répartissez les frais en fonction du montant de chaque ligne par rapport au montant net total.
        - *Quantité* - Répartissez les frais en fonction du nombre d'unités pour chaque ligne par rapport au nombre total d'unités.
        - *Par ligne* – Répartissez les frais de façon équitable entre le nombre total de lignes.

    - **Répartir les frais sur les lignes** - Sélectionnez une valeur pour spécifier si les frais doivent être répartis sur toutes les lignes, sur les lignes positives uniquement ou sur les lignes négatives uniquement.
    - **Tout répartir** - Activez cette case à cocher pour répartir des frais sur les lignes de commande même si le code frais a un type de débit autre que *Article*.
    - **Reçues** - Activez cette case à cocher pour répartir les frais uniquement sur les lignes de commande reçues.
    - **Stockées** - Activez cette case à cocher pour répartir les frais uniquement sur les lignes de commande inventoriées.
    - **Afficher les sélections et effacer les lignes spécifiques** - Cochez cette case pour exclure des lignes spécifiques de cette répartition. Lorsque vous cochez cette case, la grille **Choisir les lignes à exclure de la répartition** est ouverte. Cette grille inclut uniquement les lignes qui correspondent aux critères définis par les paramètres **Répartir les frais sur les lignes** et **Stockées**. Par exemple, si vous définissez le champ **Répartir les frais sur les lignes** sur *Lignes positives*, puis cochez la case **Stockées**, la grille affiche uniquement les lignes qui sont positives et inventoriées. De plus, la grille filtre automatiquement toutes les lignes pour lesquelles la quantité totale a déjà été reçue. Pendant que la grille est ouverte, décochez la case **Inclure** pour chaque ligne à exclure de la répartition. 

        > [!IMPORTANT]
        > Lorsque vous utilisez la grille **Choisir les lignes à exclure de la répartition**, veillez à laisser la grille ouverte jusqu'à ce que vous sélectionniez **Répartir**. Si vous fermez la grille avant de sélectionner **Répartir**, vos paramètres dans la grille seront perdus. Par conséquent, les frais seront répartis en fonction des critères que vous aviez définis précédemment.

1. Sélectionnez **Répartir** pour appliquer vos paramètres et fermer la boîte de dialogue.
