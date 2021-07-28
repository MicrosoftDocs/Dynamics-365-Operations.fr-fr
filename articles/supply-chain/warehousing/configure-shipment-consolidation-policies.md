---
title: Configurer les stratégies de consolidation de l’expédition
description: Cette rubrique explique comment configurer des stratégies de consolidation de l’expédition par défaut et personnalisées.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: a9215672f4ace591bf7d964c8fbd3ad483bacca5
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6360422"
---
# <a name="configure-shipment-consolidation-policies"></a>Configurer les stratégies de consolidation de l’expédition

[!include [banner](../includes/banner.md)]

Le processus de consolidation de l’expédition qui utilise des stratégies de consolidation permet une consolidation automatisée des expéditions lors du lancement automatique et manuel dans l’entrepôt. Après avoir activé cette fonctionnalité, vous devez configurer vos stratégies initiales. Si aucune stratégie n’est configurée, chaque ligne de vente générera une expédition distincte contenant une seule ligne de chargement.

Les scénarios présentés dans cette rubrique montrent comment configurer des stratégies de consolidation d’expédition par défaut et personnalisées.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>Activer la fonctionnalité Stratégie de consolidation de l’expédition

> [!IMPORTANT]
> Dans le [premier scénario](#scenario-1) décrit dans cette rubrique, vous allez d’abord configurer un entrepôt afin qu’il utilise la fonctionnalité de consolidation de l’expédition antérieure. Vous rendrez ensuite disponibles les stratégies de consolidation de l’expédition. De cette façon, vous pouvez découvrir le fonctionnement du scénario de mise à niveau. Si vous prévoyez d’utiliser un environnement de données de démonstration pour passer par le premier scénario, n’activez pas la fonctionnalité avant de réaliser le scénario.

Avant de pouvoir utiliser la fonctionnalité *Stratégies de consolidation de l’expédition*, vous devez l’activer dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Consolider l’expédition*

## <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Chaque scénario de cette rubrique fait référence aux valeurs et aux enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management. Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique sur **USMF** avant de commencer.

## <a name="scenario-1-configure-default-shipment-consolidation-policies"></a><a name="scenario-1"></a>Scénario 1 : Configurer les stratégies de consolidation des expéditions par défaut

Il existe deux situations dans lesquelles vous devez configurer le nombre minimum de stratégies par défaut après avoir activé la fonctionnalité *Stratégies de consolidation de l’expédition* :

- Quand vous mettez à niveau un environnement qui contient déjà des données.
- Quand vous installez un environnement complètement nouveau.

### <a name="upgrade-an-environment-where-warehouses-are-already-configured-for-cross-order-consolidation"></a>Mettre à niveau un environnement où les entrepôts sont déjà configurés pour la consolidation des commandes croisées

Lorsque vous démarrez cette procédure, la fonctionnalité *Stratégies de consolidation de l’expédition* doit être désactivée pour simuler un environnement dans lequel la fonctionnalité de consolidation des commandes croisées de base était déjà utilisée. Vous utiliserez ensuite la gestion des fonctionnalités pour activer la fonctionnalité, afin de pouvoir apprendre à configurer des stratégies de consolidation des expéditions après la mise à niveau.

Suivez ces étapes pour configurer des stratégies de consolidation des expéditions par défaut dans un environnement où les entrepôts ont déjà été configurés pour la consolidation des commandes croisées.

1. Accédez à **Gestion des entrepôts \> Configuration \> Entrepôt \> Emplacements fixes**.
1. Dans la liste, recherchez et ouvrez l’enregistrement d’entrepôt souhaité (par exemple, l’entrepôt *24* dans les données de démonstration **USMF**).
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans le raccourci **Entrepôt**, définissez l’option **Consolider l’expédition au lancement dans l’entrepôt** sur *Oui*.
1. Répétez les étapes 2 à 4 pour tous les autres entrepôts où la consolidation est requise.
1. Fermez la page.
1. Utilisez [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer la fonctionnalité *Stratégies de consolidation de l’expédition*. Dans l’espace de travail **Gestion des fonctionnalités**, la fonction est nommée *Consolider l’expédition*.
1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**. Vous devrez peut-être actualiser votre navigateur pour voir le nouvel élément de menu **Stratégies de consolidation de l’expédition** après avoir activé la fonctionnalité.
1. Dans le volet Actions, sélectionnez **Créer un paramétrage par défaut** pour créer les stratégies suivantes :

    - Une stratégie **CrossOrder** pour le type de stratégie *Commandes client* (à condition que vous disposiez d’au moins un entrepôt configuré pour utiliser la fonctionnalité de consolidation antérieure)
    - Une stratégie **Par défaut** pour le type de stratégie *Commandes client*
    - Une stratégie **Par défaut** pour le type de stratégie *Sortie de transfert*
    - Une stratégie **CrossOrder** pour le type de stratégie *Sortie de transfert* (à condition que vous disposiez d’au moins un entrepôt configuré pour utiliser la fonctionnalité de consolidation antérieure)

    > [!NOTE]
    > - Les deux stratégies **CrossOrder** prennent en compte le même ensemble de champs que la logique précédente, à l’exception du champ du numéro de commande. (Ce champ est utilisé pour consolider les lignes en expéditions, en fonction de facteurs tels que l’entrepôt, le mode de transport et l’adresse.)
    > - Les deux stratégies **Par défaut** prennent en compte le même ensemble de champs que la logique précédente, y compris le champ du numéro de commande. (Ce champ est utilisé pour consolider les lignes en expéditions, en fonction de facteurs tels que le numéro de commande, l’entrepôt, le mode de transport et l’adresse.)

1. Sélectionnez la stratégie **CrossOrder** pour le type de stratégie *Commandes*, puis, dans le volet Actions, sélectionnez **Modifier la requête**.
1. Dans la boîte de dialogue de l’éditeur de requêtes, notez que les entrepôts où l’option **Consolider l’expédition à la Lancement dans l’entrepôt** est définie sur *Oui* sont répertoriés. Par conséquent, ils sont inclus dans la requête.

### <a name="create-default-policies-for-a-new-environment"></a>Créer des stratégies par défaut pour un nouvel environnement

Suivez ces étapes pour configurer des stratégies de consolidation des expéditions par défaut dans un tout nouvel environnement.

1. Utilisez [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer la fonctionnalité *Stratégies de consolidation de l’expédition*, si ce n’est pas déjà fait. Dans l’espace de travail **Gestion des fonctionnalités**, la fonction est nommée *Consolider l’expédition*.
1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Dans le volet Actions, sélectionnez **Créer un paramétrage par défaut** pour créer les stratégies suivantes :

    - Une stratégie **Par défaut** pour le type de stratégie *Commandes client*
    - Une stratégie **Par défaut** pour le type de stratégie *Sortie de transfert*

    > [!NOTE]
    > Les deux stratégies **Par défaut** prennent en compte le même ensemble de champs que la logique précédente, y compris le champ du numéro de commande. (Ce champ est utilisé pour consolider les lignes en expéditions, en fonction de facteurs tels que le numéro de commande, l’entrepôt, le mode de transport et l’adresse.)

## <a name="scenario-2-configure-custom-shipment-consolidation-policies"></a>Scénario 2 : Configurer les stratégies de consolidation des expéditions personnalisées

Ce scénario montre comment configurer des stratégies de consolidation d’expédition personnalisées. Les stratégies personnalisées peuvent prendre en charge des exigences commerciales complexes où la consolidation des expéditions dépend de plusieurs conditions. Pour chaque exemple de stratégie plus loin dans ce scénario, une brève description de l’analyse de rentabilisation est incluse. Ces exemples de stratégies doivent être configurés dans une séquence qui garantit une évaluation pyramidale des requêtes. (En d’autres termes, les stratégies qui ont le plus de conditions doivent être évaluées comme ayant la plus haute priorité.)

### <a name="turn-on-the-feature-and-prepare-master-data-for-this-scenario"></a>Activer la fonctionnalité et préparer les données de base pour ce scénario

Avant de pouvoir effectuer les exercices de ce scénario, vous devez activer la fonctionnalité et préparer les données de base requises pour effectuer le filtrage, comme décrit dans les sous-sections suivantes. (Ces conditions préalables s’appliquent également aux scénarios répertoriés dans [Exemples de scénarios d’utilisation des stratégies de consolidation de l’expédition](#example-scenarios).)

#### <a name="turn-on-the-feature-and-create-the-default-policies"></a>Activer la fonctionnalité et créer les stratégies par défaut

Utilisez la gestion des fonctionnalités pour activer la fonctionnalité, si ce n’est pas déjà fait, et créez les stratégies de consolidation par défaut décrites dans [Scénario 1](#scenario-1).

#### <a name="create-two-new-product-filter-codes"></a>Créer deux codes de filtre de produit

1. Allez dans **Gestion des entrepôts \> Configuration \> Filtres de produit \> Filtres de produit** et ajoutez deux filtres de produit :

    - Filtre de produit 1 :

        - **Code du filtre :** *Inflammable*
        - **Titre du filtre :** *Code 4*

    - Filtre de produit 2 :

        - **Code du filtre :** *Explosif*
        - **Titre du filtre :** *Code 4*

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Ouvrez le produit ayant le numéro d’article *M9200*. (Le produit que vous sélectionnez doit être activé pour le processus \[WMS\] des entrepôts avancées, et ce produit est pré-activé pour les processus WMS dans les données de démonstration **USMF**.)
1. Dans le raccourci **Entrepôt**, définissez le champ **Code 4** sur *Inflammable*.
1. Fermez la page.
1. Ouvrez le produit ayant le numéro d’article *M9201*. (Ce produit est également pré-activé pour les processus WMS dans les données de démonstration **USMF**.)
1. Dans le raccourci **Entrepôt**, définissez le champ **Code 4** sur *Explosif*.
1. Fermez la page.

#### <a name="create-a-new-transportation-mode-of-delivery"></a>Créer un nouveau mode de livraison

1. Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Mode**.
1. Créez un mode de transport qui sera utilisé dans les requêtes de consolidation et nommez-le *Avion*.
1. Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Transporteurs**.
1. Créez un transporteur possédant les paramètres suivants :

    - **Transporteur :** *Avion*
    - **Nom :** *Avion*
    - **Mode :** *Avion*

1. Dans le raccourcis **Services** du nouveau transporteur, ajoutez une ligne ayant les paramètres suivants :

    - **Service de transporteur :** *Air*
    - **Mode de transport :** *Air*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

    > [!NOTE]
    > Lorsque vous enregistrez le nouveau transporteur, le champ **Mode de livraison** de la nouvelle ligne de la grille **Services** est automatiquement défini sur *Airwa-Air*. Lorsque vous utilisez le mode de livraison *Airwa-Air* pour une commande client, le mode de transport *Avion* sera utilisé pour les expéditions associées.

#### <a name="create-an-order-pool"></a>Créer un regroupement de commandes

1. Allez dans **Ventes et marketing \> Configuration \> Commandes client \> Regroupements de commandes**.
1. Créez un regroupement de commandes qui sera utilisé pour la requête de consolidation. Ce regroupement de commandes doit avoir les paramètres suivants :

    - **Regroupement :** Entrez un entier qui n’est pas déjà utilisé par un autre regroupement.
    - **Nom :** *ShipCons*

1. Allez dans **Ventes et marketing \> Clients \> Tous les clients**.
1. Ouvrez le client qui a un numéro de compte *US-003*.
1. Dans le raccourci **Valeurs par défaut des commandes client**, définissez le champ **Regroupement de commandes client** sur le regroupement de commandes que vous venez de créer.
1. Fermez la page, puis répétez les étapes 4 et 5 pour le client ayant le numéro de compte *US-004*.

### <a name="create-example-policy-1"></a>Créer un exemple de stratégie 1

Dans cet exemple, vous allez créer une stratégie *Client + Mode* qui peut être utilisée pour l’analyse de rentabilisation suivante :

- La stratégie recherchera un compte client spécifique (*US-001*) et un mode de livraison spécifique (*Airwa-Air*).
- La consolidation avec les expéditions en cours est désactivée.
- La consolidation est effectuée par ID de commande. (En d’autres termes, il y aura des expéditions distinctes par commande, entrepôt, etc.)

Suivez ces étapes pour créer la stratégie de consolidation des expéditions pour cette analyse de rentabilisation.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une stratégie qui possède les paramètres suivants :

    - **Nom de la stratégie :** *CustomerMode*
    - **Description de la stratégie :** *Compte client et mode de livraison*

1. Laissez l’option **Consolider avec des expéditions en cours** définie sur *Non*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le raccourci **Champs de consolidation**, dans la liste **Champs restants**, sélectionnez la ligne où **Nom de domaine** est défini sur *Mode de livraison*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Plage**, dans la grille, recherchez la ligne où le champ **Champ** est défini sur *Compte client* et définissez le champ **Critères** pour cette ligne sur *US-001*.
1. Sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants sur la grille :

    - **Table :** *Lignes de commande*
    - **Table dérivée :** *Lignes de commande*
    - **Champ :** *Mode de livraison*
    - **Critères :** *Airwa-Air*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.

> [!NOTE]
> Pour cette analyse de rentabilisation, les lignes de commande pour le client *US-001* qui utilisent le mode de livraison *Airwa-Air* ne seront pas consolidées dans l’ensemble des commandes. Cette stratégie est destinée à être utilisée en premier dans une séquence, dans les cas où les expéditions pour tous les autres modes de livraison sont consolidées pour ce client.

### <a name="create-example-policy-2"></a>Créer un exemple de stratégie 2

Dans cet exemple, vous allez créer une stratégie *Marchandises dangereuses* qui peut être utilisée pour l’analyse de rentabilisation suivante :

- La stratégie recherchera un code de filtre spécifique (*dangereux*) et un mode de livraison spécifique (*Airwa-Air*).
- La consolidation avec les expéditions en cours est activée.
- La consolidation est effectuée dans l’ensemble des commandes. (En d’autres termes, il y aura des expéditions distinctes par compte, entrepôt, etc., mais uniquement au sein du groupe d’articles spécifié dans la requête.)

Suivez ces étapes pour créer la stratégie de consolidation des expéditions pour cette analyse de rentabilisation.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une stratégie qui possède les paramètres suivants :

    - **Nom de la stratégie :** *Type d’élément*
    - **Description de la stratégie :** *Consolider le même type d’article dans l’ensemble des commandes*

1. Définissez l’option **Consolider avec des expéditions en cours** définie sur *Oui*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le raccourci **Champs de consolidation**, dans la liste **Champs restants**, sélectionnez la ligne où **Nom de domaine** est défini sur *Mode de livraison*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Jointures**, développez et sélectionnez **Tables \> Détails du chargement** dans l’arborescence.
1. Sélectionnez **Ajouter une jointure de table**.
1. Dans la grille de relations qui apparaît, recherchez et sélectionnez la ligne où le champ **Relation** est défini sur *Numéro d’article de l’entrepôt (numéro d’article)*, puis sélectionnez **Sélectionner**. 
1. Dans l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants sur la grille :

    - **Table :** *Numéro d’article de l’entrepôt*
    - **Table dérivée :** *Numéro d’article de l’entrepôt*
    - **Champ :** *Code 4*
    - **Critères :** *Inflammable*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.

> [!NOTE]
> Pour cette analyse de rentabilisation, toutes les lignes de commande où les articles ont un code de filtre spécifique (c’est-à-dire le code de filtre où le champ **Code 4** est défini sur *Inflammable*) seront consolidées avec d’autres articles du même type dans toutes les commandes. S’il y a une expédition en cours pour le même compte, entrepôt et groupe d’articles, les nouvelles lignes y seront attachées.

### <a name="create-example-policy-3"></a>Créer un exemple de stratégie 3

Dans cet exemple, vous allez créer une stratégie *Besoins du client* qui peut être utilisée pour l’analyse de rentabilisation suivante :

- La stratégie recherchera un compte client spécifique.
- La consolidation avec les expéditions en cours est activée.
- La consolidation se fait entre les commandes mais est basée sur les demandes des clients. (En d’autres termes, plusieurs commandes seront regroupées en expéditions, en fonction du même numéro de demande client et du même entrepôt.)

Suivez ces étapes pour créer la stratégie de consolidation des expéditions pour cette analyse de rentabilisation.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une stratégie qui possède les paramètres suivants :

    - **Nom de la stratégie :** *CustomerOrderNo*
    - **Description de la stratégie :** *Consolider les lignes en fonction du bon de commande client*

1. Définissez l’option **Consolider avec des expéditions en cours** définie sur *Oui*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le raccourci **Champs de consolidation**, dans la liste **Champs restants**, sélectionnez la ligne où **Nom de domaine** est défini sur *Demande client*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans la liste **Champs restants**, sélectionnez la ligne où le champ **Nom de champ** est défini sur *Mode de livraison*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Plage**, recherchez la ligne où le champ **Champ** est défini sur *Compte client* et définissez le champ **Critères** pour cette ligne sur *US-001*.
1. Sélectionnez **OK** pour fermer la boîte de dialogue.

> [!NOTE]
> Pour cette analyse de rentabilisation, toutes les lignes de commande où les commandes client ont le même numéro de demande client seront regroupées en une seule expédition, quel que soit le numéro de commande client. (Le numéro de demande du client est utilisé comme bon de commande du client \[PO\].) S’il y a une expédition en cours pour le même compte, entrepôt et demande client, les nouvelles lignes y seront attachées. Cette stratégie peut être utilisée si le client envoie des lignes de commande supplémentaires qui ont le même numéro de bon de commande plusieurs fois au cours d’une journée et souhaite que toutes les lignes soient regroupées en une seule expédition. (En d’autres termes, il y aura une feuille de chargement et un bon de livraison.)

### <a name="create-example-policy-4"></a>Créer un exemple de stratégie 4

Dans cet exemple, vous allez créer une stratégie *Clients autorisant la consolidation* qui peut être utilisée pour l’analyse de rentabilisation suivante :

- La stratégie recherchera un regroupement de commandes spécifique pour identifier les clients qui acceptent les expéditions consolidées.
- La consolidation avec les expéditions en cours est désactivée.
- La consolidation est effectuée entre les commandes à l’aide des champs sélectionnés par la stratégie CrossOrder par défaut (pour répliquer la case à cocher **Consolider l’expédition au lancement dans l’entrepôt** antérieure).

- Vous pouvez remplacer la règle sur une commande client en sélectionnant un regroupement de commandes différent.

Suivez ces étapes pour créer la stratégie de consolidation des expéditions pour cette analyse de rentabilisation.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une stratégie qui possède les paramètres suivants :

    - **Nom de la stratégie :** *Regroupement de commandes*
    - **Description de la stratégie :** *Consolider les commandes en fonction du regroupement de commandes*

1. Laissez l’option **Consolider avec des expéditions en cours** définie sur *Non*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le raccourci **Champs de consolidation**, dans la liste **Champs restants**, sélectionnez la ligne où **Nom de domaine** est défini sur *Mode de livraison*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants sur la grille :

    - **Table :** *Commandes client*
    - **Table dérivée :** *Commandes client*
    - **Champ :** *Regroupement*
    - **Critères :** *ShipCons*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.

> [!NOTE]
> Pour cette analyse de rentabilisation, toutes les lignes de commande où les commandes client appartiennent au même regroupement de commandes seront consolidées en une seule expédition parmi les commandes client pour le même compte, entrepôt et mode de livraison de transport. Au lieu du regroupement de commandes, vous pouvez utiliser n’importe quel autre champ pour distinguer un groupe de clients et utiliser l’en-tête de commande client par défaut. Vous pouvez utiliser cette approche si le client, et non l’entrepôt, émet le besoin de consolidation. (Dans la logique de consolidation antérieure, l’entrepôt était à l’origine du besoin de consolidation.)

### <a name="create-example-policy-5"></a>Créer un exemple de stratégie 5

Dans cet exemple, vous allez créer une stratégie *Entrepôts autorisant la consolidation* qui peut être utilisée pour l’analyse de rentabilisation suivante :

- La stratégie recherchera un regroupement de commandes spécifique pour identifier les entrepôts qui peuvent consolider les expéditions.
- La consolidation avec les expéditions en cours est désactivée.
- La consolidation est effectuée entre les commandes à l’aide des champs sélectionnés par la stratégie CrossOrder par défaut (pour répliquer la case à cocher **Consolider l’expédition au lancement dans l’entrepôt** antérieure).

En règle générale, cette analyse de rentabilisation peut être traitée à l’aide des stratégies par défaut que vous avez créées dans le [Scénario 1](#scenario-1). Cependant, vous pouvez également créer manuellement des stratégies similaires en suivant ces étapes.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une stratégie qui possède les paramètres suivants :

    - **Nom de la stratégie :** *Commande croisée*
    - **Description de la stratégie :** *Consolidation des commandes croisées pour des entrepôts spécifiques*

1. Laissez l’option **Consolider avec des expéditions en cours** définie sur *Non*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le raccourci **Champs de consolidation**, dans le champ **Champs restants**, sélectionnez la ligne où **Nom de domaine** est défini sur *Mode de livraison*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Plage**, recherchez la ligne où le champ **Champ** est défini sur *Entrepôt* et définissez le champ **Critères** pour cette ligne sur *61, 63*.
1. Sélectionnez **OK** pour fermer la boîte de dialogue.

### <a name="set-the-order"></a>Définir la commande

Maintenant que vous avez créé toutes vos stratégies, vous devez établir l’ordre dans lequel elles seront appliquées. Pour utiliser une approche pyramidale, où les stratégies qui ont le plus de conditions sont évaluées comme ayant la priorité la plus élevée, procédez comme suit.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Sélectionnez chaque stratégie répertoriée dans la colonne de gauche, puis utilisez les boutons **Déplacer vers le haut** et **Déplacer vers le bas** du volet Actions pour organiser les stratégies dans l’ordre suivant :

    1. CustomerMode
    1. Type d’article
    1. CustomerOrderNo
    1. Regroupement de commandes
    1. Ordre croisé
    1. Valeur par défaut

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a> Exemples de scénarios d’utilisation des stratégies de consolidation de l’expédition

Les scénarios suivants illustrent la façon dont vous pouvez utiliser les stratégies de consolidation de l’expédition créées lors de la lecture de cette rubrique. Chaque scénario vous guide tout au long du processus de consolidation de l’expédition qui utilise des stratégies de consolidation lors du lancement automatique ou manuel dans l’entrepôt :

- Scénario 1 : [Consolider les expéditions lorsqu’elles sont transmises à l’entrepôt à l’aide de la procédure Lancement automatique des commandes client dans l’entrepôt](../warehousing/consolidate-shipments-automatic.md)
- Scénario 2 : [Consolider les expéditions lorsque la stratégie de consolidation de l’expédition est remplacée à partir de la page Lancement dans l’entrepôt](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- Scénario 3 : [Consolider les expéditions à l’aide de page Lancement dans l’entrepôt à partir de l’atelier de planification des chargements](../warehousing/consolidate-shipments-load-planning-workbench.md)
- Scénario 4 : [Consolider les expéditions à l’aide de l’atelier de consolidation d’expédition](../warehousing/consolidate-shipments-manual-workbench.md)
- Scénario 5 : [Consolider les expéditions manuellement à l’aide de la page Consolider les expéditions](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>Ressources supplémentaires

- [Stratégies de consolidation de l’expédition](about-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]