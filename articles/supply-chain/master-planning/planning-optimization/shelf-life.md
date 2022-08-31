---
title: Planification générale pour les produits à durée de conservation limitée
description: Cet article décrit comment configurer et utiliser les fonctionnalités de planification qui prennent en compte la durée de conservation des produits périssables.
author: t-benebo
ms.date: 08/10/2022
ms.topic: article
ms.search.form: ReqPlanSched, CustTable, EcoResProductDetailsExtended, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 95c905cbcc3c057dbccf2b7d6e894b1e99ddfba5
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337147"
---
# <a name="master-planning-for-products-with-limited-shelf-life"></a>Planification générale pour les produits à durée de conservation limitée

[!include [banner](../../includes/banner.md)]

La durée de conservation est la durée pendant laquelle un produit peut être stocké jusqu’à ce qu’il ne puisse plus être utilisé ou vendu. Pour les produits qui ont une durée de conservation limitée, vous utiliserez probablement une stratégie d’entrepôt premier expiré, premier sorti (FEFO), qui donne la priorité à la consommation et à la vente des articles en fonction de leur durée de conservation restante. Cette stratégie d’entrepôsage est pertinente pour les aliments, les médicaments et d’autres biens qui se caractérisent par une courte durée de stockage. Selon FEFO, les articles dans l’entrepôt sont stockés comme des marchandises sur une étagère de supermarché : les produits qui ont une longue durée de conservation sont placés en arrière sur les étagères, de sorte que les produits qui ont une durée de conservation restante plus courte sont expédiés en premier.

## <a name="using-shelf-life-in-master-planning"></a>Utilisation des durées de conservation dans la planification principale

Cette section explique comment la planification générale suggère l’approvisionnement pour les articles à durée de conservation.

Lorsque vous exécutez un plan directeur, il génère des ordres planifiés suggérés (approvisionnement) qui répondront à votre demande et minimiseront également les retards. Si votre plan comprend des articles dont la durée de conservation est limitée, les calculs de planification deviennent plus complexes, car le plan doit non seulement minimiser les retards, mais également utiliser l’approvisionnement existant avant son expiration. Le plan doit essayer d’utiliser l’approvisionnement le plus proche de sa date d’expiration avant l’approvisionnement qui expire plus tard. Par conséquent, le plan directeur vise à atteindre les objectifs suivants, dans cet ordre :

1. Minimiser la somme des retards.
1. Maximiser la somme de l’approvisionnement FEFO.
1. Minimiser le réapprovisionnement des stocks.

Dans certains cas, il peut y avoir un conflit entre les deux premiers objectifs, et un choix doit être fait : voulez-vous retarder une expédition ou voulez-vous utiliser un approvisionnement qui expire plus tard au lieu d’un approvisionnement qui expire plus tôt ? Pour résoudre ce conflit lors de la planification générale, le système donne la priorité à la minimisation des retards plutôt qu’à l’utilisation de l’approvisionnement bientôt périmé. En général, ce type de conflit se produit lorsqu’il peut y avoir des retards et une couverture par période. Par conséquent, nous vous recommandons d’utiliser une période de couverture plus courte que la durée de conservation d’un article. D’autres types de couverture (comme l’exigence) sont peu susceptibles de rencontrer ce type de conflit.

## <a name="set-up-shelf-life"></a>Configurer la durée de conservation

### <a name="configure-each-master-plan-to-consider-shelf-life"></a>Configurez chaque plan directeur pour tenir compte de la durée de conservation

Par défaut, les plans directeurs ne tiennent pas compte de la durée de conservation. Utilisez la procédure suivante pour activer les calculs de durée de conservation pour chaque plan directeur qui les requiert.

1. Accédez à **Planification directrice \> paramétrage \> plans \> Plans généraux**.
1. Sélectionnez un plan directeur dans le volet liste ou créez-en un nouveau.
1. Dans FastTab **Général**, définissez l’option **Utiliser les dates de durée de conservation** sur *Oui*.

### <a name="configure-tracking-dimension-groups-to-track-the-batch-dimension"></a>Configurez les groupes de dimensions de suivi pour suivre la dimension par lot

La durée de conservation d’un article ne peut être suivie que si cet article est suivi au niveau de la dimension de lot. En d’autres termes, la référence du lot et les dates requises doivent être enregistrées à la réception ou à la fabrication, et à chaque transaction d’inventaire de l’article. Pour gérer cette option, configurez un ou plusieurs groupes de dimensions de suivi pour effectuer le suivi requis, puis affectez les éléments pertinents à ces groupes selon les besoins.

Utilisez la procédure suivante pour configurer un groupe de dimension de suivi afin de suivre la dimension de lot.

1. Aller à **Gestion des informations produit \> Configurer \> Dimensions et groupes de variantes \> Groupes de dimensions de suivi**.
1. Suivez l’une des procédures suivantes :

    - Dans le volet Actions, sélectionnez **Nouveau** pour créer un nouveau groupe de dimension de suivi. Entrez un nom et une description dans le volet Actions, puis sélectionnez **Sauvegarder**.
    - Dans le volet de liste, sélectionnez le groupe de dimensions de suivi existant que vous souhaitez configurer pour suivre la dimension de lot.

1. Dans FastTab **dimension de suivi**, sur la ligne **Numéro de lot**, cochez les cases dans les colonnes **Actif** et **Inventaire physique**.

### <a name="set-up-shelf-life-for-a-product"></a>Configurer la durée de conservation d'un produit

Utilisez la procédure suivante pour configurer la durée de conservation d’un produit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Créez ou ouvrez le produit que vous souhaitez configurer.
1. Pour utiliser les paramètres de durée de conservation, sur FastTab **Général**, définissez le champ **Groupe de dimensions de suivi** sur un groupe de dimension de suivi configuré pour suivre la dimension de lot. Vous ne pouvez définir ce champ que lorsque vous créez un produit pour la première fois. Vous ne pouvez pas modifier la valeur des produits existants.
1. Dans FastTab **Gérer les inventaires**, définissez les champs suivants :

    - **Période d’avis de rayon en jours** – Précisez la période (en jours) à laquelle vérifier un lot de ce produit pour s’assurer qu’il est propre à la consommation ou à la revente. La valeur de ce champ est ajoutée à la valeur de la *date de fabrication* d’un lot pour déterminer sa *date d’avis de rayon*. Vous pouvez configurer le système pour générer des ordres de qualité lorsqu’un lot approche de sa date limite de vente.
    - **Durée de conservation en jours** – Spécifiez le nombre de jours avant l’expiration d’un lot de ce produit. Cette valeur est ajoutée à la *date de fabrication* pour déterminer la *date d’expiration*. Le lot est considéré comme inutilisable après cette date.
    - **Période de consommation recommandée en jours** – Précisez la période (en jours) après laquelle un lot de ce produit est réputé encore commercialisable mais ne peut plus conserver certaines de ses propriétés d’origine. Cette valeur est ajoutée à la *date de fabrication* pour déterminer la *date de consommation recommandée*. Vous pouvez exécuter des rapports pour identifier l’inventaire qui a dépassé sa date de péremption. 

### <a name="set-a-sellable-days-rule-for-each-customer"></a>Définissez une règle de jours vendables pour chaque client

La fonctionnalité *Jours vendables* garantit que les produits d’un lot qui expirera bientôt ne seront pas envoyés aux clients. De plus, il garantit que lorsque les produits sont envoyés à un client, il restera encore un nombre suffisant de jours vendables après la livraison.

Pour utiliser la fonctionnalité de jours vendables, vous devez définir le nombre de jours vendables qui s’applique à chaque produit (ou groupe de produits) pour chaque client. Vous devez terminer manuellement ce processus, car il n’y a pas d’entité de données pour cela.

Utilisez la procédure suivante pour configurer les jours vendables pour chaque produit pour chaque client.

1. Allez dans **Ventes et marketing \> Clients \> Tous les clients**.
1. Trouvez et sélectionnez le client que vous voulez configurer.
1. Dans le volet Actions, dans l’onglet **Vendre**, dans le groupe **Configurer**, sélectionnez **Vendre \> Jours vendables**.
1. Sur la page **Jours vendables pour le client**, la grille répertorie les règles de jours vendables existantes pour chaque produit ou groupe de produits. Utilisez les boutons du volet Actions pour ajouter ou modifier des lignes dans la grille, selon vos besoins. Un **Filtre** est fourni pour vous aider à trouver des lignes existantes.
1. Pour chaque ligne, définissez les champs suivants :

    - **Code d'article** - Sélectionnez l’une des valeurs suivantes pour spécifier l’étendue des articles qui seront affectés :

        - *Table* - la ligne s’applique à un article spécifique.
        - *Groupe* – La ligne s’applique à un groupe d’articles spécifiques.
        - *Tous* – La ligne s’applique à tous les articles.

    - **Relation d’article** - Si vous définissez le champ **Code d'article** sur *Table*, sélectionnez un article spécifique. Si vous définissez le champ **Code d'article** sur *Groupe*, sélectionnez un groupe d'article. Si vous définissez le champ **Code d'article** sur *Tout*, ce champ n'est pas disponible.
    - **Jours vendables** – Entrez le nombre minimum de jours dont le client doit disposer pour vendre les produits correspondants avant l’expiration du lot. La valeur des jours vendables est basée sur la date de réception demandée (ou la date de réception confirmée, si elle est définie) pour les produits correspondants sur la commande client.
    - *(Autres dimensions du produit)* – Pour limiter davantage l'étendue d’une ligne, spécifiez d’autres valeurs de dimension (telles que **Taille** et **Couleur**) comme demandé. Pour contrôler les dimensions affichées dans la grille, sélectionnez **Afficher les dimensions** dans le volet Actions.

### <a name="set-up-all-relevant-products-so-that-they-are-fefo-date-controlled"></a>Configurez tous les produits pertinents afin qu’ils soient contrôlés par date FEFO

Pour que les jours vendables fonctionnent, chaque article concerné doit appartenir à un groupe de modèles d’articles où la case **FEFO à date contrôlée** est cochée.

Utilisez la procédure suivante pour configurer un groupe de modèles d’articles afin qu’il prenne en charge la fonctionnalité des jours vendables.

1. Allez dans **Gestion des stocks \> Paramétrage \> Stock \> Groupes de modèles d’article**.
1. Sélectionnez un groupe existant dans le volet liste ou créez un nouveau groupe en sélectionnant **Nouveau** dans le volet Actions.
1. Dans le FastTab **Stratégies de stock**, cochez la case **FEFO dates contrôlées**.
1. Définissez les autres champs du groupe selon vos besoins.

Utilisez la procédure suivante pour afficher ou définir le groupe de modèles d’article auquel appartient un produit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Ouvrez le produit que vous souhaitez inspecter ou modifier.
1. Dans **Général**, définissez le champ **Groupe de modèles d’article** à un groupe où la case **FEFO à date contrôlée** est cochée.

## <a name="example-1-simple-fefo-10-day-period-zero-days-of-lead-time"></a>Exemple 1 : FEFO simple, période de 10 jours, zéro jour de prospect

Cet exemple montre un exemple de base de durée de conservation, où l’indexation entre les commandes d’approvisionnement et la demande est effectuée pour satisfaire les objectifs suivants du système :

- Minimiser la somme des retards.
- Maximiser la somme de l’approvisionnement FEFO.
- Minimiser le réapprovisionnement des stocks.

Le système dispose des paramètres d’article et de plan directeur suivants :

- Période de **Code de couverture (stratégie de réapprovisionnement) :** 
- **Période de couverture :** 10 jours (égal à la durée de conservation)
- **Durée de conservation (jours)** 10 jours
- **Jours vendables:** 0 jour
- **Délai de prospect :** 0 jour
- **Jours négatifs :** 0 jour
- **Type d’ordre planifié (paramètres d’ordre par défaut de l’article) :** Bon de commande

Les commandes client suivantes pour l’article existent dans le système :

- **SO1:** Quantité (qté) = 2, date de livraison demandée = aujourd’hui + 1 jour
- **SO2 :** Qté = 1, date de livraison demandée = aujourd’hui + 4 jours
- **SO3 :** Qté = 1, date de livraison demandée = aujourd’hui + 5 jours

Toutes ces commandes client créent une demande pour l’article.

L’offre suivante existe pour l’article :

- **Inventaire disponible :** Qté = 1, date d’expiration = aujourd’hui + 5 jours
- **Bon de commande 1 (PO1) :** Date de réception = aujourd’hui + 2 jours, qté = 1, date d’expiration = aujourd’hui + 4 jours

Le système crée une liste d’approvisionnement qui peut couvrir cette demande, et il trie la liste par date d’expiration (en utilisant FEFO).

La planification générale crée l’indexation requise entre l’offre et la demande. Il crée également toute demande requise en fonction de la liste d’approvisionnement (en utilisant FEFO) et prend en compte la date de disponibilité.

- SO1 peut être exécuté par la quantité en stock, mais il ne peut pas être exécuté par PO1, car la date de disponibilité pour PO1 est d'un jour plus tard que SO1 l’exige. Par conséquent, SO1 génère une demande pour une unité de bien.
- SO2 peut être couvert par PO1, car PO1 arrivera à l’heure demandée et la date d’expiration sera toujours valide. Par conséquent, le besoin en SO2 est entièrement couvert par l’OP1.
- SO3 n’est pas couvert, car les ressources ne sont pas disponibles. Par conséquent, SO3 génère une demande pour une unité de bien.

Pour couvrir tous les besoins restants, le système doit créer la commande d’achat prévisionnelle suivante :

- **PPO1 :** Date de réception = aujourd’hui, qté = 2, date d’expiration = aujourd’hui + 10 jours

Le tableau suivant résume le résultat.

| Demande | Origine des besoins |
|---|---|
| **SO1 :** Date de livraison = aujourd’hui + 1 jour, qté = 2 | <p>**Disponible :** Qté = 1, date d’expiration = aujourd’hui + 5 jours</p><p>**PPO1 :** Date de réception = aujourd’hui, qté = 1, date d’expiration = aujourd’hui + 10 jours</p> |
| **SO2 :** Date de livraison = aujourd’hui + 4 jours, qté = 1 | **PO1 :** Date de réception = aujourd’hui + 2 jours, 1 qté, date d’expiration = aujourd’hui + 4 jours |
| **SO3 :** Date de livraison = aujourd’hui + 5 jours, qté = 1 | **PPO1 :** Date de réception = aujourd’hui, qté = 2, date d’expiration = aujourd’hui + 10 jours |

L’illustration suivante présente la chronologie pour cet exemple.

![Exemple 1 : FEFO simple, période de 10 jours, zéro jour de prospect](media/fefo-example-1.png "Exemple 1 : FEFO simple, période de 10 jours, zéro jour de prospect")

## <a name="example-2-simple-fefo-requirement-three-days-of-lead-time"></a>Exemple 2 : FEFO simple, requête, trois jours de prospect

Cet exemple montre comment la tentative du système de minimiser les retards peut parfois provoquer une surcharge.

Le système dispose des paramètres d’article et de plan directeur suivants :

- Exigence du **Code de couverture (stratégie de réapprovisionnement) :**
- **Durée de conservation (jours)** 10 jours
- **Jours vendables:** 0 jour
- **Délai de prospect :** Établi par les accords commerciaux suivants avec les fournisseurs :

    - **Accord commercial 1 :** si qté = 1, délai de prospect = 4
    - **Accord commercial 2:** si qté = 2, délai de prospect = 3

- **Jours négatifs :** 0 jour
- **Type d’ordre planifié (paramètres d’ordre par défaut de l’article) :** Bon de commande

Les lignes de commande client suivantes existent dans le système :

- **SO1 :** Qté = 2, date de livraison demandée = aujourd’hui + 3 jours

Cette demande est couverte par l’offre existante et une commande confirmée :

- **Inventaire disponible :** Disponible = aujourd'hui, qté = 1, date d’expiration = aujourd’hui + 2 jours
- **PO1 :** Date de réception = aujourd’hui + 3 jours, qté = 1, date d’expiration = aujourd’hui + 4 jours

SO1 ne peut pas être satisfait par le stock disponible, car la date d’expiration du stock est antérieure à la date d’expédition. PO1 peut couvrir le besoin de SO1 avec une quantité de 1 seulement. Par conséquent, SO1 génère une demande pour une unité de bien. Pour couvrir ce besoin, le système crée une commande d’achat prévisionnelle (PPO1).

Le système a deux accords commerciaux (un pour qté = 1, délai de prospect = 4 jours, et un pour qté = 2, délai de prspect = 3 jours). Par conséquent, le système essaie de minimiser les retards en créant un bon de commande prévisionnel (PPO1) qui respecte le deuxième accord commercial. Le résultat est une livraison excédentaire (qté = 2, date d’expiration = aujourd’hui + 10 jours).

Le tableau suivant résume le résultat.

| Demande | Origine des besoins |
|---|---|
| **SO1 :** Date de livraison = aujourd’hui + 3 jours, qté = 2 | <p>**PO1 :** Date de réception = aujourd’hui + 3 jours, qté = 1, date d’expiration = aujourd’hui + 4 jours</p><p>**PPO1 :** Date de réception = aujourd’hui + 3 jours, qté = 1, date d’expiration = aujourd’hui + 10 jours</p> |

L’illustration suivante présente la chronologie pour cet exemple.

![Exemple 2 : FEFO simple, requête, trois jours de prospect](media/fefo-example-2.png "Exemple 2 : FEFO simple, requête, trois jours de prospect")

## <a name="example-3-simple-fefo-requirement-three-days-of-lead-time-five-sellable-days"></a>Exemple 3 : FEFO simple, requête, trois jours de délai de prospect, cinq jours vendables

Cet exemple montre comment fonctionne la durée de conservation lorsque des jours vendables sont ajoutés pour un article.

Le système dispose des paramètres d’article et de plan directeur suivants :

- Exigence du **Code de couverture (stratégie de réapprovisionnement) :**
- **Durée de conservation (jours)** 10 jours
- **Jours vendables:** 5 jours
- **Délai de prospect :** 5 jours
- **Jours négatifs :** 0 jour
- **Type d’ordre planifié (paramètres d’ordre par défaut de l’article) :** Bon de commande

Les commandes client suivantes existent dans le système :

- **SO1 :** Qté = 2, date de livraison demandée = aujourd’hui + 2 jours
- **SO2 :** Qté = 1, date de livraison demandée = aujourd’hui + 3 jours
- **SO3 :** Qté = 1, date de livraison demandée = aujourd’hui + 5 jours

Cette demande peut être couverte par l’offre existante et une commande fournisseur confirmée :

- **Inventaire disponible :** Disponible = aujourd'hui, qté = 1, date d’expiration = aujourd’hui + 6 jours
- **PO1 :** Date de réception = aujourd’hui + 2 jours, qté = 3, date d’expiration = aujourd’hui + 10 jours

Le système crée une liste de candidats à l’origine des besoins, en fonction de la liste d’approvisionnement (FEFO) et des dates de disponibilité. Par conséquent, SO1 ne peut pas être satisfait par le stock disponible, car ce stock expire avant la fin des jours vendables requis par le client (date de réception demandée + 5 jours). PO1 peut couvrir la demande de SO1 avec deux unités et la demande de SO2 avec une unité. Par conséquent, seul SO3 a encore une demande non couverte pour une unité de bien. Pour couvrir cette demande, le système crée la commande d’achat prévisionnelle suivante :

- **PP01 :** Date de réception = aujourd’hui + 5 jours, qté = 1, date d’expiration = aujourd’hui + 10 jours

Le tableau suivant résume le résultat.

| Demande | Origine des besoins |
|---|---|
| **SO1 :** Date de livraison = aujourd’hui + 2 jours, qté = 2 | **PO1 :** Date de réception = aujourd’hui + 2 jours, qté = 2, date d’expiration = aujourd’hui + 10 jours |
| **SO2 :** Date de livraison = aujourd’hui + 3 jours, qté = 1 | **PO1 :** Date de réception = aujourd’hui + 2 jours, qté = 1, date d’expiration = aujourd’hui + 10 jours |
| **SO3 :** Date de livraison = aujourd’hui + 5 jours, qté = 1 | **PPO1 :** Date de réception = aujourd’hui + 5 jours, qté = 1, date d’expiration = aujourd’hui + 10 jours |

L’illustration suivante présente la chronologie pour cet exemple.

![Exemple 3 : FEFO simple, demande, trois jours de délai de prospect, cinq jours vendables.](media/fefo-example-3.png "Exemple 3 : FEFO simple, requête, trois jours de délai de prospect, cinq jours vendables")

## <a name="example-4-simple-fefo-period-lead-time-depends-on-the-quantity"></a>Exemple 4 : FEFO simple, période, délai de prospect dépend de la quantité

Cet exemple montre comment la tentative du système de minimiser les retards peut parfois provoquer une surcharge.

Le système dispose des paramètres d’article et de plan directeur suivants :

- Période de **Code de couverture (stratégie de réapprovisionnement) :**
- **Période de couverture :** 10 jours (égal à la durée de conservation)
- **Durée de conservation (jours)** 10 jours
- **Jours vendables:** 0 jour
- **Délai de prospect :** Établi par les accords commerciaux suivants avec les fournisseurs :

    - **Accord commercial 1 :** si qté = 1, délai de prospect = 5
    - **Accord commercial 2 :** si qté = 2, délai de prospect = 0

- **Jours négatifs :** 0 jour
- **Type d’ordre planifié (paramètres d’ordre par défaut de l’article) :** Bon de commande

Les commandes client suivantes existent dans le système :

- **SO1 :** Qté = 1, date de livraison demandée = aujourd’hui
- **SO2 :** Qté = 1, date de livraison demandée = aujourd’hui + 6 jours

Cette demande peut être partiellement couverte par l’approvisionnement existant des bons de commande confirmés suivants :

- **PO1 :** Date de réception = aujourd’hui + 1 jour, qté = 1, date d’expiration = aujourd’hui + 2 jours
- **PO2 :** Date de réception = aujourd’hui + 3 jours, qté = 1, date d’expiration = aujourd’hui + 7 jours

Le système a deux accords commerciaux (un pour qté = 1, délai de prospect = 5 jours, et un pour qté = 2, délai de prospect = 0 jour). Par conséquent, le système essaie de minimiser les retards en créant le bon de commande prévisionnel qui respecte le deuxième accord commercial.

- **PP01 :** Date de réception = aujourd’hui, qté = 2, date d’expiration = aujourd’hui + 10 jours

SO1 sera couvert par une unité de PPO1. SO2 sera couvert par PO2, car PO2 expire plus tôt que PPO1.

Le tableau suivant résume le résultat.

| Demande | Origine des besoins |
|---|---|
| **SO1 :** Date de livraison = aujourd’hui, qté = 1 | **PPO1 :** Date de réception = aujourd’hui, qté = 1, date d’expiration = aujourd’hui + 10 jours |
| **SO2 :** Date de livraison = aujourd’hui + 6 jours, qté = 1 | **PO2 :** Date de réception = aujourd’hui + 3 jours, qté = 1, date d’expiration = aujourd’hui + 7 jours |

> [!NOTE]
> PO1 n’est pas utilisé, car il arrivera trop tard pour S01 et expirera avant la livraison de S02. PPO1 a sur-commandé d’une unité pour permettre au délai de prospect d’être de 0 (zéro), selon l’accord commercial 2.

L’illustration suivante présente la chronologie pour cet exemple.

![Exemple 4 : FEFO simple, période, délai de prospect dépend de la quantité.](media/fefo-example-4.png "Exemple 4 : FEFO simple, période, délai de prospect dépend de la quantité")

## <a name="example-5-simple-fefo-requirement-10-negative-days"></a>Exemple 5 : FEFO simple, demande, 10 jours négatifs

<!-- KFM: This is more of a negative days example than a shelf life example. We should point out more explicitly how shelf life affects this situation (or maybe otherwise remove this example). -->

Cet exemple montre comment fonctionne la durée de conservation lorsqu'un grand nombre de jours vendables sont ajoutés pour un article. Les jours négatifs représente le nombre de jours que vous pouvez attendre avant de commander un réapprovisionnement d'un article qui a un stock négatif. Le système ne crée pas d’approvisionnement tant que le nombre de jours négatifs n’est pas dépassé.

Le système dispose des paramètres d’article et de plan directeur suivants :

- Exigence du **Code de couverture (stratégie de réapprovisionnement) :**
- **Délai de prospect :** 0 jour
- **Jours négatifs :** 10 jours
- **Type d’ordre planifié (paramètres d’ordre par défaut de l’article) :** Bon de commande

Les lignes de commande client suivantes existent dans le système :

- **SO1 :** Qté = 1, date de livraison demandée = aujourd’hui

Cette demande peut être partiellement couverte par l’approvisionnement existant des bons de commande confirmés suivants :

- **PO1 :** Date de réception = aujourd’hui + 3 jours, qté = 1, date d’expiration = aujourd’hui + 5 jours

Étant donné que le système est configuré pour autoriser 10 jours négatifs, il couvre la demande de SO1 en utilisant PO1, même si le résultat sera un retard de trois jours car SO1 crée un stock négatif jusqu’à ce que PO1 arrive. Aucun bon de commande prévisionnel n’est créé, même si le délai est de 0 (zéro) et que la création d’un bon de commande prévisionnel réduirait les délais.

Le tableau suivant résume le résultat.

| Demande | Origine des besoins |
|---|---|
| **SO1 :** Date de livraison = aujourd’hui, qté = 1 | **PO1 :** Date de réception = aujourd’hui + 3 jours, qté = 1, date d’expiration = aujourd’hui + 5 jours |

L’illustration suivante présente la chronologie pour cet exemple.

![Exemple 5 : FEFO simple, demande, 10 jours négatifs.](media/fefo-example-5.png "Exemple 5 : FEFO simple, demande, 10 jours négatifs")

## <a name="example-6-simple-fefo-requirement-five-negative-days"></a>Exemple 6 : FEFO simple, demande, cinq jours négatifs.

Cet exemple montre comment fonctionne la durée de conservation lorsque le nombre de jours négatifs pour un article est inférieur à sa période de durée de conservation.

Le système dispose des paramètres d’article et de plan directeur suivants :

- Exigence du **Code de couverture (stratégie de réapprovisionnement) :**
- **Jours vendables:** 0 jour
- **Délai de prospect :** 0 jour
- **Jours négatifs :** 5 jours
- **Type d’ordre planifié (paramètres d’ordre par défaut de l’article) :** Bon de commande

Les lignes de commande client suivantes existent dans le système :

- **SO1 :** Qté = 2, date de livraison demandée = aujourd’hui

Cette demande peut être couverte par l’approvisionnement existant des bons de commande confirmés suivants :

- **PO1 :** Date de réception = aujourd’hui, qté = 1, date d’expiration = aujourd’hui + 1 jour
- **PO2 :** Date de réception = aujourd’hui + 2 jours, qté = 1, date d’expiration = aujourd’hui + 3 jours

Cependant, le système doit respecter la restriction selon laquelle les articles expédiés ne peuvent pas être expirés au moment de l’expédition. Par conséquent, PO2 et PO1 ne peuvent pas être utilisés tous les deux pour SO1, car PO1 expire avant l’arrivée de PO2. Le système crée la commande d’achat prévisionnelle suivante pour achever de couvrir la demande pour SO1 :

- **PPO1 :** Date de réception = aujourd’hui, qté = 1, date d’expiration = aujourd’hui + 10 jours

Le système peut profiter des cinq jours négatifs et utiliser PO2 et PPO1 pour couvrir SO1. Cependant, cette approche entraînera un retard de livraison jusqu’à l’arrivée de PO2, et PO1 expirera entre-temps. Par conséquent, le système couvre SO1 en utilisant PPO1 et PO1.

Le tableau suivant résume le résultat.

| Demande | Origine des besoins |
|---|---|
| **SO1 :** Date de livraison = aujourd’hui, qté = 2 | <p>**PO1 :** Date de réception = aujourd’hui, qté = 1, date d’expiration = aujourd’hui + 1 jour</p><p>**PPO1 :** Date de réception = aujourd’hui, qté = 1, date d’expiration = aujourd’hui + 10 jours</p> |

L’illustration suivante présente la chronologie pour cet exemple.

![Exemple 6 : FEFO simple, demande, cinq jours négatifs.](media/fefo-example-6.png "Exemple 6 : FEFO simple, demande, cinq jours négatifs.")
