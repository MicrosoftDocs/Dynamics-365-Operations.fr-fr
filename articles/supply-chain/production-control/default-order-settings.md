---
title: Paramètres de commande par défaut pour les dimensions et les variantes de produit
description: Les paramètres de commande par défaut définissent le site et l'entrepôt d'où les articles seront originaires ou stockés, les quantités minimales, maximales, multiples et standard qui seront utilisées pour le commerce ou la gestion des stocks, les délais, l'indicateur de fin, et la méthode de promesse de commande.
author: roxanadiaconu
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 46b1efb274c9f54f27c26884dc18fc4a317786be
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211571"
---
# <a name="default-order-settings-for-dimensions-and-product-variants"></a>Paramètres de commande par défaut pour les dimensions et les variantes de produits

[!include [banner](../includes/banner.md)]

Les paramètres de commande par défaut dans Dynamics 365 Supply Chain Management définissent le site et l'entrepôt d'où les articles seront originaires ou stockés, les quantités minimales, maximales, multiples et standard qui seront utilisées pour le commerce ou la gestion des stocks, les délais, l'indicateur de fin, et la méthode de promesse de commande. Les paramètres de commande par défaut sont utilisés lors de la création de commandes fournisseur, de commandes client, d'ordres de transfert, de journaux de stock, et par la planification pour générer des ordres prévisionnels. Les paramètres de commande par défaut peuvent être spécifiques à l'article, au site, à une variante de produit, ou à une dimension de produit.

Vous pouvez définir les paramètres de commande par défaut sur la page **Paramètres de commande par défaut**. Pour ouvrir cette page, accédez à **Gestion des informations sur les produits** &gt; **Produits** &gt; **Produits lancés** &gt; **Sélectionnez un produit lancé** &gt; sur le Volet d'action **Plan** ou **Gérer le stock** Paramètres de &gt; **la commande** &gt; **Paramètres de commande par défaut**.

## <a name="default-order-settings"></a>Paramètres de commande par défaut
Il existe trois types de paramètres de commande par défaut pour les achats, les ventes, et le stock. Les paramètres de commande par défaut pour les achats sont utilisés lors de la création de :

-   Lignes de commande fournisseur
-   Lignes de contrat d'achat
-   Lignes d'appel d'offre
-   Lignes de demande d'achat
-   Lignes de réapprovisionnement avec consignation
-   Commandes fournisseur prévisionnelles

Les paramètres de commande par défaut pour les ventes sont utilisés lors de la création de :

-   Lignes de commande client
-   Lignes de contrat de vente
-   Lignes de devis de vente
-   Lignes d'ordre de retour et lignes de remplacement d'article
-   Lignes de prévision de la demande

Les paramètres de commande client par défaut s'appliquent également lors de la création de :

-   Demandes d'articles du projet
-   Demandes d'articles dans une commande de service

Les paramètres de commande par défaut pour le stock sont utilisés lors de la création de :

-   Journaux de stock
-   Ordres de transfert
-   Ordres de transfert prévisionnels

Les paramètres de commande de stock par défaut s'appliquent également lors de la création de :

-   Ordres de contrôle
-   Ordres de qualité
-   Ordres de fabrication
-   Lignes de nomenclature
-   Ordres de fabrication prévisionnels

## <a name="full-definition-of-a-released-product"></a>Définition complète d'un produit lancé
Lors de la création d'une transaction, vous devez spécifier la définition complète d'un produit lancé sur la ligne afin que Supply Chain Management tente d'identifier les paramètres de commande par défaut. La définition complète du produit lancé signifie que le numéro d'article et les dimensions de produit actives, telles que la configuration, la taille, le style et la couleur, sont spécifiés dans la transaction. Par exemple, si vous créez manuellement une ligne de commande fournisseur d'une variante de produit lancé, vous devez spécifier toutes les dimensions de produit requises avant que le site, l'entrepôt, les quantités, et le délai s'affichent par défaut sur la ligne de commande. 

Tous les paramètres de commande par défaut s'appliquent lors de la création d'une commande ou de lignes de journal. Les quantités et les délais s'affichent uniquement par défaut lorsqu'il y a lieu. Par exemple, lors du comptage d'une ligne de journal, seul le site et l'entrepôt s'affichent par défaut lorsque la ligne est créée. Évidemment, aucune utilisation de valeur par défaut ni aucun vérification de multiples ou de minima ne sont effectuées lors de la création de la ligne ou lors de la validation du journal. 

Le système tente toujours de trouver un site ou un entrepôt par défaut lorsqu'une commande ou une ligne de journal est créée. Le site n'est pas toujours affiché par défaut dans les paramètres de commande. Par exemple, lors de la création d'une commande client ou fournisseur, le site de l'en-tête de commande est utilisé automatiquement sur les lignes de commande. Lors de la création d'une ligne de nomenclature, le site de l'en-tête de la nomenclature est utilisé. Une fois le site déterminé, il sera utilisé pour rechercher tous les paramètres de commande spécifiques au site qui peuvent être utilisés par défaut pour l'entrepôt. 

Le type de commande par défaut, les achats, et les délais de stock peuvent être remplacés par des règles de couverture de l'article sur la page **Couverture de l'article**. Bien que les paramètres de commande par défaut ne permettent pas de faire la distinction entre le délai de production et le délai de transfert, les règles de couverture de l'article le permettent. Toutefois, le paramétrage de couverture de l'article est uniquement utilisé par la production lors de la création d'ordres de production et d'ordres de transfert prévisionnels et ne s'appliquera pas lors de la création manuelle d'ordres de production et d'ordres de transfert. 

## <a name="default-order-settings-rules"></a>Règles de paramètrage de commande par défaut
Vous pouvez définir les paramètres de commande par défaut générales et autant de règles de paramètrage de commande par défaut qui s'appliquent uniquement dans certaines conditions, telles qu'un site ou une combinaison de dimension de produit ou de dimensions de produits spécifiques. Vous ne pouvez pas définir des paramètres de commande spécifiques à l'entrepôt.

### <a name="rank-in-default-order-settings"></a>Classer les paramètres de commande par défaut

Les règles de paramètrage de commande par défaut sont classées. Plus le classement est élevé, plus la règle est importante, ce qui signifie qu'elle a une priorité supérieure et est utilisée avant les règles avec des classements inférieurs. Les paramètres de commande généraux par défaut ont le classement zéro, qui ne peut pas être modifié. Il ne peut y avoir qu'une seule règle avec le classement zéro. Les règles peuvent avoir le même classement, à condition que les dimensions auxquelles elles s'appliquent diffèrent. Cela est utile pour modéliser des paramètres de commande spécifiques au site. Lorsqu'une règle de paramétrage de commande par défaut est créée, les valeurs des valeurs de commande, de l'indicateur de fin, etc. sont hérités de la règle avec le classement zéro, mais peuvent être remplacées.

### <a name="default-order-settings-for-released-products"></a>Paramètres de commande par défaut pour les produits lancés

Pour les produits lancés distincts, vous pouvez définir des paramètres de commande généraux ou des paramètres de commande spécifiques au site. Les paramètres de commande généraux ont toujours le classement zéro. Si vous paramétrez de nouveaux paramètres de commandes client, fournisseur et de stock ensemble simultanément, nous vous recommandons d'utiliser la **Vue Détails** sur la page **Paramètres de commande par défaut**. Pour passer à la vue Détails, accédez au volet d'actions **Options** &gt; **Options de page** &gt; **Changer de vue** &gt; **Vue Détails**.

### <a name="site-specific-order-settings"></a>Paramètres de commande spécifiques au site

Pour créer des paramètres de commande spécifiques au site, cliquez sur **Nouveau**. Dans **Vue Détails**, renseignez le site dans le champ **Paramètres applicables pour** &gt; **Site**. Dans **Vue Grille**, renseignez le site dans la colonne **Site**. La nouvelle règle obtient automatiquement une nouvelle valeur de classement, supérieure à zéro. Vous pouvez créer autant de règle spécifiques au site que nécessaires et vous pouvez affecter à toutes les règles spécifiques au site le même classement, afin de modéliser qu'elles sont également importantes. 

Si vous vous trouvez dans **Vue Détails**, vous ne pouvez pas obtenir une vue d'ensemble des règles créées pour l'article. Basculez le bouton **Afficher/Masquer la liste** pour afficher les informations de vue d'ensemble. Lorsqu'une ligne de commande de tout type est créée et qu'aucun site n'est fourni, Supply Chain Management recherche une règle sans site spécifié. Ceci peut aider à déterminer un site par défaut sur la ligne de commande. Ce site est ensuite utilisé pour rechercher une règle spécifique au site, dans laquelle un entrepôt par défaut peut avoir été défini. Cet entrepôt est appliqué à la ligne de commande.

### <a name="specific-order-settings-for-product-dimension"></a>Paramètres de commande spécifiques à la dimension de produit

Vous pouvez définir des règles de paramètrage de commande pour une dimension de produit active ou une combinaison de dimensions de produits active. Si un champ de dimension de produit est laissé vide, la règle s'applique à toutes les valeurs de la dimension de produit. 

Considérez l'exemple de produit suivant.

|                                                     |                                         |
|-----------------------------------------------------|-----------------------------------------|
| **Nom du produit**                                    | Capteur photoélectrique                    |
| **Numéro d'article**                                     | XW56                                    |
| **Configuration** (utilisée pour modéliser le type de lumière) | Lumière rouge C1-Visible, lumière infrarouge C2-Infrared |
| **Style** (utilisé pour modéliser la révision d'ingénierie)  | R1, R2, R3                              |

Pour cet exemple, supposons que le produit est approvisionné et pas produit. Supposons également que la configuration C1 est plus communément utilisée, avec des délais plus courts. 

Créez les paramètres de commande par défaut suivants pour modéliser ce scénario.

| Rang | site ; | Configuration | Style | Achats - Remplacer les paramètres par défaut | Délai d'achat | Achats - Arrêtés | Ventes - Remplacer les paramètres par défaut | Ventes - Arrêtées |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C1            |       | Oui                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Lorsqu'une ligne de commande fournisseur ou une commande fournisseur prévisionnelle est créée pour XW56, Configuration C1, indépendamment de la révision ou du site auquel la ligne est affectée, le délai sera considéré de 2. Supposons que toutes les révisions à part R3 sont arrêtées.

Vous pouvez créer les régles de paramétrage de commande par défaut suivantes.

| Rang | site ; | Configuration | Style | Achats - Remplacer les paramètres par défaut | Délai d'achat | Achats - Arrêtés | Ventes - Remplacer les paramètres par défaut | Ventes - Arrêtées |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 20   |      |               | R2    | Oui                                  |                    | Oui                | Oui                               | Oui             |
| 20   |      |               | R1    | Oui                                  |                    | Oui                | Oui                               | Oui             |
| 10   |      | C1            |       | Oui                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Les deux règles pour arrêter les anciennes révisions ont le même classement, ce qui signifie qu'elles sont également importantes. Chacun d'elles ont un classement supérieur à la règle de la configuration C1, ce qui signifie qu'elles ont priorité sur la règle de la configuration C1. 

Cet exemple décrit le besoin de classement. Si une commande fournisseur est créée pour la configuration C1 et la révision R2, en l'absence de classement, les deux règles définies pour R2 et C1 serait ambiguës. Pour résoudre l'ambiguïté, Supply Chain Management recherche parmi les règles définies dans l'ordre de classement décroissant et applique la première règle applicable. Dans l'exemple actuel, lorsqu'une ligne de commande fournisseur est créée pour la configuration C1 et la révision R2, l'utilisateur reçoit un message d'avertissement que l'article est en attente et qu'il est provoqué par la valeur de révision. Si la règle de la configuration a un classement supérieur à celui de la révision, la création d'une ligne de commande fournisseur pour la configuration C1 et la révision R2 aurait réussi et aucun message « article en attente » n'aurait été envoyé à l'utilisateur. 

Prenons les régles de paramétrage de commande par défaut suivantes.

| Rang | site ; | Configuration | Style | Site par défaut | Entrepôt par défaut | Achats - Remplacer les dimensions de stockage par défaut | Entrepôt d'achat |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Oui                                            | 22                 |
| 10   |      | C1            |  R2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

Le système parcourt l'ensemble de règles deux fois pour déterminer le site et l'entrepôt. Lorsqu'une ligne de commande fournisseur est créée pour la configuration C1, le style R2, le site est déterminé sur la règle avec le classement 10. Puis le système recherche une règle pour le site 2 afin de déterminer un entrepôt. La règle 20 est détectée car elle a un classement supérieur, l'entrepôt sur la ligne de commande fournisseur est de 22, et non de 21. 

En général, les règles spécifiques et les règles des dimensions qui sont plus importantes que d'autres dimensions ont les classements les plus élevés, tandis que les règles plus génériques ont des classements inférieurs. 

La règle avec le classement zéro sert de filet de sécurité. Si aucune autre règle n'est détectée, les paramètres de commande par défaut de la règle zéro sont utilisés. 

Du fait que le numéro du classement est important, dans le volet d'actions **Paramètres de commande par défaut**, des fonctions permettent de déplacer une règle vers le haut ou vers le bas du classement et pour renuméroter les règles, afin qu'elles soient toujours par incréments de 10. 

Le nombre de règles créées pour un produit lancé peut être important. Afin de mieux comprendre ce que chaque règle remplace et pourquoi elles sont nécessaires, nous vous recommandons d'utiliser la **Vue Grille** sur la page **Paramètres de commande par défaut**. Vous pouvez activer la vue de la grille en accédant au volet d'actions **Options** &gt; **Options de page** &gt; **Changer de vue** &gt; **Vue Grille**. Le nombre de colonnes affichées dans la grille peut être très significatif, en particulier pour les onglets de ventes et de stock. Pour limiter le nombre de colonnes affichées dans la grille, des groupes de colonnes peuvent être masqués ou affichés à l'aide des boutons du menu **Paramètres de commande par défaut** &gt; **Affichage des colonnes**.

### <a name="specific-order-settings-for-released-product-variant"></a>Paramètres de commande spécifiques à une variante de produit lancé

Si le système de règles des paramètres de commande par défaut est trop encombrant, il est possible de définir simplement les paramètres de commande par défaut pour chaque variante de produit. Les exemples suivants illustrent la recherche de produit et des scénarios décrits ci-dessus.

| Rang | site ; | Configuration | Style | Achats - Remplacer les paramètres par défaut | Délai d'achat | Achats - Arrêtés | Ventes - Remplacer les paramètres par défaut | Ventes - Arrêtées |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C2            | R3    | Oui                                  | 5                  |                    |                                   |                 |
| 10   |      | C2            | R2    | Oui                                  | 5                  | Oui                | Oui                               | Oui             |
| 10   |      | C2            | R1    | Oui                                  | 5                  | Oui                | Oui                               | Oui             |
| 10   |      | C1            | R3    | Oui                                  | 2                  |                    |                                   |                 |
| 10   |      | C1            | R2    | Oui                                  | 2                  | Oui                | Oui                               | Oui             |
| 10   |      | C1            | R1    | Oui                                  | 2                  | Oui                | Oui                               | Oui             |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Le classement dans ce cas n'importe pas réellement, vous pouvez donc choisir de le masquer. Cette solution introduit éventuellement un problème de maintenance. Toutefois, vous pouvez envisager d'utiliser ce paramètre si vous envisagez d'intégrer des systèmes de Gestion des cycles de vie des produits.



