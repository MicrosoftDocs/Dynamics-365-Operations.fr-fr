---
title: Planification basée sur la priorité
description: Cet article décrit la fonctionnalité de planification basée sur la priorité de Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8f46a4d4e087a99c00ab7b4eabc74f60043cbf21
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186481"
---
# <a name="priority-based-planning"></a>Planification basée sur la priorité

[!include [banner](../../includes/banner.md)]

Cet article décrit la fonctionnalité de planification basée sur la priorité de Microsoft Dynamics 365 Supply Chain Management. La fonctionnalité ajoute la prise en charge de la planification pilotée par la demande, qui est une étape de la [Planification des besoins en matières basée sur la demande](ddmrp-overview.md). La planification basée sur les priorités permet à l’optimisation de la planification de générer des ordres planifiés basés sur les priorités de planification plutôt que sur les dates des besoins.

La planification basée sur les priorités vous permet de hiérarchiser les ordres de réapprovisionnement pour vous assurer que la demande urgente est prioritaire par rapport à la demande moins importante. Par exemple, un ordre de réapprovisionnement de stock insuffisant sera prioritaire par rapport à un ordre de réapprovisionnement standard. Le système peut diviser automatiquement les commandes plus importantes en commandes plus petites séparées où les lignes de commande sont regroupées par priorité. Il peut alors traiter en premier toutes les commandes prioritaires.

Pour obtenir un aperçu rapide de cette fonctionnalité, regardez la vidéo suivante : [Prise en charge de l’optimisation de la planification pour la planification basée sur les priorités dans Dynamics 365 Supply Chain Management](https://youtu.be/GmMHzFETTQc).

## <a name="turn-on-priority-based-planning-in-your-system"></a>Activez la planification basée sur les priorités dans votre système

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Planification*
- **Nom de la fonctionnalité :** *Support MRP basé sur la priorité pour l’optimisation de la planification*

## <a name="where-and-how-planning-priorities-are-assigned"></a>Où et comment les priorités de planification sont-elles attribuées

Les informations de *Priorité de planification* sur l’offre et la demande sont le socle de la planification fondée sur les priorités. La priorité de planification définit l’importance d’une demande ou d’une ligne d’approvisionnement. L’optimisation de la planification l’utilise lorsque le champ **Code de couverture** est défini sur *Priorité*.

La priorité de planification est généralement un nombre compris entre 0 (zéro) et 100, où 0 représente l’importance la plus élevée. Il est affiché et défini dans le champ **Priorité de planification**. Vous pouvez trouver ce champ sur les pages suivantes : **Lignes de prévision de la demande**, **Détails de la commande client**, **Détails de la commande fournisseur**, **Détails de l’ordre de transfert** et **Détails de la commande planifiée**.

Quand le champ **Code de couverture** de l’article ou du groupe de couverture concerné est défini sur *Priorité*, l’optimisation de la planification équilibre l’offre et la demande en utilisant une approche axée sur la demande lorsqu’elle calcule la priorité de planification et, pour chaque produit lancé, prend en compte les valeurs définies pour les champs **Minimum**, **Point de réapprovisionnement** et **Maximum** sur la page **Articles couverts**.

> [!NOTE]
> La valeur *Priorité* est disponible pour le champ **Code de couverture** uniquement lorsque l’optimisation de la planification est activée.

Les *modèles de priorité de planification* associés contrôlent la priorité de planification et décomposent les commandes planifiées par plage de priorités. Ils vous permettent également de définir des valeurs de priorité de planification par défaut pour chaque type d’approvisionnement ou de demande et de définir la méthode de calcul de priorité.

## <a name="types-of-priority-calculation-methods"></a>Types de méthodes de calcul de la priorité

Chaque modèle de priorité de planification a un paramètre **Méthode de calcul de la priorité** qui contrôle la manière dont la planification applique la priorité aux commandes planifiées. Les valeurs disponibles sont *Pourcentage de la quantité maximale de stock* et *Plages de priorité*. *Plages de priorité* représente une version plus avancée de la méthode *Pourcentage de la quantité maximale de stock*.

### <a name="percent-of-maximum-inventory-quantity"></a>Pourcentage de la quantité de stock maximale

Dans la méthode de calcul *Pourcentage de la quantité de stock maximale*, le calcul de priorité d’approvisionnement recherche *le stock total disponible* (flux net) sous forme de pourcentage de la valeur de **Quantité de stock maximale** définie pour un article. Une seule commande planifiée est alors créée par article et fournisseur (sauf si la quantité maximale de commande est utilisée pour forcer un fractionnement). La priorité de planification de la commande est calculée en pourcentage du maximum.

La formule utilisée est la suivante :

*Pourcentage du maximum* = (*Position de flux net* × 100) ÷ *Valeur maximale de la quantité de stock à partir de la couverture de l’article*

Dans cette formule, *Position de flux net* se calcule de la manière suivante :

*Position de flux net* = *Disponible* + *En commande* - *Demande qualifiée*

- *En commande* est l’approvisionnement prévu.
- *Demande qualifiée* représente les besoins nets qui ont la date du besoin dans la plage de gestion de planification.

Au cours de l’exécution de la planification, des commandes planifiées sont créées lorsque la position de flux net est inférieure à la quantité du point de nouvelle commande pour un article. La quantité de commande planifiée est la différence entre la valeur **Quantité maximale en stock** définie au niveau de l’article et la position de flux net. La priorité de commande planifiée est calculée comme un pourcentage de *position de flux net* de la valeur **Quantité maximale en stock**.

> [!NOTE]
> La priorité calculée ne peut pas être négative, même si la demande dépasse l’approvisionnement total. Si la demande dépasse l’approvisionnement total, la priorité calculée est définie sur 0 (zéro).

### <a name="priority-ranges"></a>Plages de priorité

La méthode de calcul *Plages de priorité* est plus avancée que la méthode *Pourcentage de la quantité maximale de stock* et est configurée au niveau du modèle de priorité de planification. Plusieurs nouveaux ordres d’approvisionnement planifiés peuvent être créés pour répondre à la demande par article. Les priorités de l’approvisionnement planifié suivent les valeurs définies dans la grille **Plages de priorité de planification** sur la page **Planification des modèles de priorité**.

Les règles supplémentaires suivantes entrent en vigueur lorsque le champ **Méthode de calcul de la priorité** est défini sur *Plages de priorité* :

- Si l’option **Tenir compte de la priorité de la demande** pour le modèle de priorité planifiée est définie sur *Oui*, la priorité définie sur chaque ligne de demande limitera le compartiment de la plage de priorités. La priorité de tout nouvel ordre planifié d’approvisionnement ne sera pas inférieure à la priorité de la demande. La valeur supérieure de la plage est considérée comme un seuil auquel la valeur de priorité de la demande est comparée. Si la priorité de la demande est exactement au milieu entre les valeurs de seuil supérieures de deux plages, la plage qui a la priorité la plus élevée (c’est-à-dire la valeur de priorité la plus basse) sera sélectionnée.
- Si le champ **Création de l’ordre planifié** du modèle de priorité planifié est défini sur *Approvisionnement unique avec la priorité la plus importante*, un seul approvisionnement sera créé pour remplir jusqu’au maximum. La priorité sera définie sur la priorité de la première plage qui déclenchera un approvisionnement.
- S’il n’y a pas de stock disponible, pas d’approvisionnement et pas de demande, la ligne de la grille **Plages de priorité de planification** où le champ **Quantité de départ** est défini sur *Zéro* sera utilisé.
- En cas de demande sans stock disponible ou d’approvisionnement prévu, la ligne de la grille **Plages de priorité de planification** où le champ **Quantité de départ** est défini sur *Zéro ou moins* sera utilisé.
- Lorsque la plage dont fait partie la demande est évaluée, le réglage de l’option **Tenir compte de la priorité de la demande** aura toujours un effet.

## <a name="differences-between-traditional-timeline-calculations-and-priority-based-planning"></a>Différences entre les calculs de calendrier traditionnels et la planification basée sur les priorités

La planification basée sur les priorités diffère des calculs de calendrier traditionnels des manières suivantes :

- Tous les processeurs de pré-planification habituels sont toujours en vigueur. Ces préprocesseurs incluent l’origine des besoins des commandes planifiées approuvées à la demande client, à la demande d’achat, au mappage et à la logique de réservation. Seule la demande non satisfaite par ces préprocesseurs est traitée.
- Pendant l’origine des besoins, tout l’approvisionnement est pris en compte, quelle que soit sa priorité. Cet approvisionnement comprend le stock disponible, l’approvisionnement lancé et la partie non liée des commandes planifiées approuvées.
- Aucune demande de « jours négatifs » ne peut être indexée sur l’approvisionnement pendant toute la durée de la couverture.
- Lorsque l’offre est liée à la demande, l’offre qui a la priorité la plus élevée (c’est-à-dire la valeur de priorité la plus basse) est utilisée en premier. L’approvisionnement en stock est considéré comme ayant une valeur prioritaire de 0 (zéro). Par conséquent, il sera consommé comme la toute première source.
- Des lignes d’approvisionnement planifiées seront créées selon les règles habituelles pour la taille de commande minimale, la taille de commande maximale, la quantité multiple, etc.

## <a name="planning-priority-models"></a>Modèles de priorité de la planification

Les *Modèles de planification de la priorité* sont affectés à des groupes de couverture et contrôlent la priorité de planification des ordres planifiés. Ils définissent la logique qui détermine comment la valeur de priorité de planification est calculée pour chaque ordre planifié et comment la priorité est affectée aux ordres planifiés, aux lignes d’approvisionnement et aux lignes de demande.

Pour travailler avec les modèles de priorité de planification, accédez à **Planification \> Configurer \> Modèle des priorité de la planification**. Comme nous l’avons vu précédemment, l’un des paramètres les plus importants d’un modèle est la valeur **Méthode de calcul de la priorité**. Ce paramètre contrôle la méthode de calcul utilisée lorsque la planification affecte une valeur de priorité aux ordres planifiés.

> [!NOTE]
> Les modèles de priorité de planification s’appliquent à l’ensemble de l’organisation, dans toutes les entités juridiques.

### <a name="coverage-group"></a>Groupe de couverture

Configurez un nouveau groupe de couverture que vous prévoyez d’utiliser pour la planification basée sur les priorités, comme décrit dans [Définir des règles de couverture pour les articles](../tasks/define-coverage-rules-items.md). Après avoir créé le groupe de couverture, définissez les champs supplémentaires suivants :

- **Code de couverture** – Sélectionnez *Priorité* si le groupe de couverture doit utiliser la planification basée sur les priorités.
- **Modèle de priorité de planification** – Sélectionnez n’importe quel modèle de priorité de planification à l’échelle de l’organisation.

### <a name="item-coverage"></a>Couverture de l’article

Configurez les paramètres de couverture des articles comme décrit dans [Paramètres de couverture](../coverage-settings.md). Par défaut, la valeur **Code de couverture** sélectionnée pour le groupe de couverture est copiée dans les paramètres de couverture de l’élément. Vous pouvez néanmoins remplacer la valeur par défaut comme vous le voulez. Dans certains cas, le champ **Code de couverture** d’un enregistrement de couverture d’article est défini sur *Planification*, mais aucun modèle de priorité de planification n’est défini pour le groupe de couverture associé. Dans ces cas, tout modèle où le champ **Méthode de calcul de la priorité** est défini sur *Pourcentage de la quantité maximale de stock* et le champ **Création de l’ordre planifié** est défini sur *Approvisionnement unique avec la priorité la plus importante* sera appliqué par défaut.

Définit le champ **Code de couverture** sur *Priorité* pour rendre disponible le champ **Point de réapprovisionnement** dans les paramètres de couverture d’article. Dans ce champ, saisissez la quantité du point de réapprovisionnement que le système doit utiliser pendant qu’il détermine quand passer les ordres planifiés qui ont une valeur **Code de couverture** de *Priorité*.

La quantité du point de réapprovisionnement est souvent calculée comme la demande pendant le délai plus une valeur minimale (stock de sécurité). Il doit s’agir d’une valeur comprise entre les valeurs **Minimum** et **Maximum**.

Par exemple, vous pouvez définir les champs de la manière suivante :

- **Minimum :** *10*
- **Point de réapprovisionnement :** *45*
- **Maximum :** *60*

Pour cet exemple, la quantité du point de réapprovisionnement est basée sur un délai de sept jours et une utilisation quotidienne moyenne de 5. Par conséquent, la demande pendant le délai est de 35. La valeur minimale de 10 (stock de sécurité) est ensuite ajoutée pour obtenir un point de réapprovisionnement de 45. Lorsque cette configuration est utilisée, l’approvisionnement sera suggéré lorsque le niveau en stock projeté est inférieur à 45. La priorité de la commande sera basée sur la configuration de la priorité de planification.

### <a name="manage-planning-priority-models"></a>Gérer les modèles de priorité de la planification

Pour utiliser vos modèles de priorités de planification. procédez comme suit.

1. Accédez à **Planification \> Paramétrage \> Modèles de priorité de planification**.
1. Sélectionnez un modèle existant dans le volet de liste ou sélectionnez **Nouveau** dans le volet Actions pour créer un modèle.
1. Dans l’en-tête de l’enregistrement, définissez les champs suivants :

    - **Nom** – Entrez un nom pour le modèle. Le nom doit être unique dans toutes les entités juridiques de votre organisation.
    - **Description** – Entrez une description du modèle.
    - **Méthode de calcul de la priorité** – Sélectionnez l’une des valeurs suivantes :

        - *Plages de priorité* – Lorsque vous sélectionnez cette valeur, la grille **Plages de priorité de planification** devient disponible. De là, vous devez établir plusieurs plages de priorité pour définir la valeur de priorité de planification.
        - *Pourcentage de la quantité de stock maximale* – Calculez la valeur de priorité de planification en pourcentage, en fonction du niveau de stock projeté par rapport à la quantité de stock maximale.

    - **Création de l’ordre planifié** – Ce champ est disponible lorsque le champ **Méthode de calcul de la priorité** est défini sur *Plages de priorité*. Vous devez sélectionner l’une des valeurs suivantes :

        - *Approvisionnement unique avec la priorité la plus importante* – Ne divisez pas les ordres planifiés en fonction de la plage de priorité. La priorité de planification d’un ordre planifié est basée sur la plage de priorités la plus importante (c’est-à-dire la valeur de priorité de planification la plus basse).
        - *Fractionner selon les plages de priorité* – Fractionnez la demande en plusieurs ordres planifiés, en fonction des plages de priorité de planification. La priorité de planification pour les ordres planifiés individuels est définie par la priorité de planification de la plage de priorités de planification associée.

    - **Tenir compte de la priorité de la demande** – Définissez cette option sur *Oui* pour limiter la priorité d’un ordre planifié créé pour l’approvisionnement. (La priorité ne sera pas inférieure à la priorité de la demande associée.) Si vous définissez cette option sur *Non*, la priorité de la commande client ne sera pas prise en compte lors du calcul de la priorité de la commande fournisseur.

1. Si vous définissez le champ **Méthode de calcul de la priorité** sur *Plages de priorité*, utilisez les boutons **Ajouter** et **Supprimer** de la barre d’outils du raccourci **Plages de priorité de planification** pour ajouter ou supprimer des lignes de plage de priorité selon vos besoins. S’il existe plusieurs lignes et que vous insérez une nouvelle ligne, la priorité de planification sera automatiquement définie sur la moyenne de la ligne sélectionnée et de la ligne au-dessus. Pour chaque ligne, définissez les champs suivants :

    - **Priorité de planification** – Saisissez une valeur comprise entre 0,00 et 100,00. Cette valeur représente la priorité de planification utilisée pour la ligne. La valeur de la priorité la plus basse représente la priorité la plus élevée. Une valeur par défaut est affectée, mais vous pouvez la modifier selon vos besoins. La même valeur de **Priorité de planification** ne peut pas être utilisée pour plusieurs plages de priorités de planification dans le même modèle de priorité de planification.
    - **Description** – Saisissez une description de la plage de priorité de planification (par ex. *Point de réapprovisionnement au maximum*).
    - **Quantité de début** – Limite inférieure de la plage de priorité de planification. Cette valeur est en lecture seule et est basée sur les valeurs **Quantité de fin** et **Pourcentage de la quantité** pour la plage de priorité de planification précédente.
    - **Quantité de fin** – Sélectionnez le champ de la couverture d’articles qui doit être utilisé pour définir la limite supérieure de la plage. Les valeurs suivantes sont prises en charge et influenceront la valeur **Quantité de début** de la plage suivante :

        - *Zéro* – Cette valeur représente une plage négative à zéro (*Zéro ou moins* à *Zéro*). Pour les lignes où cette valeur est sélectionnée, le champ **Pourcentage de la quantité** est en lecture seule et est toujours défini sur *100* pour cent.
        - *Quantité minimale en stock* – Cette valeur représente la valeur **Minimale** d’un article sur la page **Articles couverts**. Pour les lignes où cette valeur est sélectionnée, le champ **Pourcentage de la quantité** est modifiable et est utilisé pour définir la valeur **Quantité de début** de la plage suivante (par exemple, pour *80 % de la quantité minimale de stock*).
        - *Point de réapprovisionnement* – Cette valeur représente la valeur **Point de réapprovisionnement** d’un article sur la page **Articles couverts**. Pour les lignes où cette valeur est sélectionnée, le champ **Pourcentage de la quantité** est modifiable et est utilisé pour définir la valeur **Quantité de début** pour la plage suivante (par exemple, pour *80 % du point de rapprovisionnement*).
        - *Quantité maximale en stock* – Cette valeur représente la valeur **Maximale** d’un article sur la page **Articles couverts**. Pour les lignes où cette valeur est sélectionnée, le champ **Pourcentage de la quantité** est modifiable et est utilisé pour définir **Quantité de début** de la plage suivante (par exemple, pour *80 % de la quantité minimale de stock*).
        - *Infini* – Cette valeur représente un niveau supérieur infini de la plage (*Infini ou moins* à *Infini*). Pour les lignes où cette valeur est sélectionnée, le champ **Pourcentage de la quantité** est en lecture seule et est toujours défini sur *100* pour cent.

    - **Pourcentage de la quantité** – Saisissez une valeur en pourcentage utilisée pour calculer la limite supérieure de la plage de priorité de planification, en fonction de la valeur sélectionnée dans le champ **Quantité de fin**. Par exemple, si le champ **Quantité de début** est défini sur *Quantité minimale en stock*, et le champ **Pourcentage de la quantité** est défini sur *50*, la limite supérieure sera de 50 pour cent de la quantité de stock minimale de la couverture d’articles associée.

1. Sur le raccourci **Priorités de planification par défaut**, définissez les champs dont vous avez besoin pour définir les priorités de planification par défaut pour chaque type de ligne d’approvisionnement ou de demande (commande client, commande fournisseur, ordre de transfert ou prévision de la demande). Seules des valeurs positives peuvent être saisies.

## <a name="view-and-maintain-planning-priority"></a>Afficher et tenir à jour la priorité de la planification

La priorité de planification est affichée et définie dans le champ **Priorité de planification**. Vous pouvez trouver ce champ sur les pages répertoriées dans le tableau suivant. La priorité est définie en tant que nombre compris entre 0 (zéro) et 100, où 0 représente l’importance la plus élevée.

| Page | Emplacement du champ | Source de valeur |
|---|---|---|
| Lignes de prévision de la demande | <p>Onglet **Article**</p><p>(Sélectionnez une ligne dans la section supérieure, puis sélectionnez l’onglet **Article**.)</p> | Valeur par défaut ou valeur définie manuellement |
| Détails de la commande client | <p>Onglet **Livraison** sur le raccourci **Détails de ligne**</p><p>(Sélectionnez une ligne sur le raccourci **Lignes de commande client**, puis, sur le raccourci **Détails de la ligne**, sélectionnez l’onglet **Livraison**.)</p> | Valeur par défaut, valeur d’intersociétés ou valeur définie manuellement |
| Détails de la commande fournisseur | <p>Onglet **Livraison** sur le raccourci **Détails de ligne**</p><p>(Sélectionnez une ligne sur le raccourci **Lignes de commande fournisseur**, puis, sur le raccourci **Détails de la ligne**, sélectionnez l’onglet **Livraison**.)</p> | Valeur définie lors de la confirmation à partir des commandes planifiées, valeur d’intersociétés ou valeur définie manuellement |
| Détails de l’ordre de transfert | <p>Onglet **Livraison** sur le raccourci **Détails de ligne**</p><p>(Sélectionnez une ligne sur le raccourci **Lignes d’ordre de transfert**, puis, sur le raccourci **Détails de la ligne**, sélectionnez l’onglet **Livraison**.)</p> | Valeur définie lors de la confirmation à partir des ordres planifiés ou valeur définie manuellement |
| Détails de l’ordre prévisionnel | Raccourci **Général** | Valeur calculée lors de la planification ou valeur définie manuellement |

### <a name="intercompany-trade"></a>Commerce intersociétés

La valeur **Priorité de planification** sur les lignes d’offre et de demande intersociétés est partagée entre les entités liées. La modification de chaque côté sera répercutée sur la ligne de commande liée.

Voici quelques exemples :

- Un utilisateur modifie la priorité de planification d’une ligne de commande client intersociétés de 20 à 30. Cette modification est répercutée sur la ligne de commande fournisseur intersociétés liée.
- Un utilisateur modifie la priorité de planification d’une ligne de commande fournisseur intersociétés de 40 à 50. Cette modification est répercutée sur la ligne de commande client intersociétés liée.
