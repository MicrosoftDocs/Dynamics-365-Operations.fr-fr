---
title: Mise en conteneur
description: Cette rubrique décrit comment automatiser la mise en conteneur des charges. La mise en conteneur automatisée crée des conteneurs et le travail de prélèvement pour les expéditions lorsqu’une vague est traitée.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable, WHSContainerizatonHistory, WHSContainerPackingPolicyChange, WHSManifestShipmentContainers, WHSAllowedContainerTypeGroup, WHSPostMethod, WHSContainerCreateDialog, WHSContainerCloseDiag, WHSContainer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 3546547bd064835d195a2c6ac7e4eb1d5afc9b00
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838104"
---
# <a name="containerization"></a>Mise en conteneur

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment automatiser la mise en conteneur des charges. La mise en conteneur automatisée crée des conteneurs et le travail de prélèvement pour les expéditions lorsqu’une vague est traitée.

Pour paramétrer la mise en conteneur, vous devez créer les éléments suivants :

- **Type de conteneur** - Permet de définir les caractéristiques physiques des conteneurs. Les types de conteneur permettent de conditionner les articles en stock dans un type et une taille spécifiques d’emballage, tel que des casiers ou des palettes.
- **Groupes de conteneurs** - Permet de créer des groupes de types de conteneur qui sont similaires. Par exemple, un groupe de conteneurs peut inclure des types de conteneur ayant des dimensions de taille similaires. Un groupe de conteneurs spécifie l’ordre dans lequel les conteneurs sont emballés, et le pourcentage de remplissage de chaque conteneur.
- **Modèle de construction de conteneur** - permet de créer des modèles qui définissent les règles de mise en conteneur. Par exemple, les règles de mélange de stock et autres stratégies d’emballage.
- **Modèles de vague** - Permet de paramétrer un ou plusieurs modèles de vague pour créer le travail de prélèvement pour la mise en conteneur.

## <a name="create-wave-templates-for-containerization"></a>Créer des modèles de vague pour la mise en conteneur

Vous devez paramétrer un ou plusieurs modèles de vague d’expédition pour la mise en conteneur. Les modèles de vague incluent les critères qui déterminent ce qui suit :

- Le traitement des vagues. Il peut être manuel ou automatique.
- La création du travail de prélèvement. Il est déterminé par les méthodes de vague. Le modèle de vague doit inclure la méthode de **mise en conteneur**.
- Le rapprochement des articles ou des lignes de répartition avec une vague.

Pour plus d’informations, voir [Modèles de vague](wave-templates.md).

## <a name="create-container-types"></a>Créer des types de conteneur

Les types de conteneur permettent de créer des descriptions des conteneurs, notamment les valeurs maximales des dimensions de taille physiques et la capacité de poids. Lorsqu’une vague mise en conteneur est traitée, les conteneurs sont créés selon les informations de type de conteneur.

Pour paramétrer un type de conteneur, suivez les étapes suivantes :

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Type de conteneur**.
1. Sélectionnez **Nouveau** pour créer un type de conteneur.
1. Entrez un identificateur (ID) unique et une description pour le type de conteneur.
1. Dans le champ **Tare**, entrez le poids réel ou estimé du conteneur.
1. Dans le champ **Poids maximal**, entrez le poids maximal que le conteneur peut renfermer.
1. Dans les champs **Volume maximum de mise en conteneur**, **Longueur maximale de mise en conteneur**, **Largeur maximale de mise en conteneur**, et **Hauteur maximale de mise en conteneur**, spécifiez les dimensions physiques du conteneur.

    > [!NOTE]
    > Les valeurs de la longueur et la largeur sont interchangeables. Cela signifie que vous pouvez faire pivoter les articles latéralement, ou sur l’axe X, si nécessaire. Par exemple, si la longueur est de 2 mètres, et largeur est de 1 mètre, vous pouvez configurer une longueur de 1 mètre et une largeur de 2 mètres. Notez que cela ne s’applique pas à la dimension de hauteur. Vous ne pouvez pas modifier la valeur de la hauteur pour faire pivoter un article verticalement.

1. Sélectionnez les valeurs d’attribut personnalisées du conteneur dans les champs pour les attributs. Les attributs sont des valeurs personnalisées utilisées pour filtrer et trier les articles selon une valeur qui n’est sinon pas disponible. Par exemple, si vous souhaitez conditionner des articles pour un client spécifique, vous pouvez créer un attribut du nom du client. Vous créez des attributs sur la page **Attributs de conteneur**.

## <a name="create-container-groups"></a>Créer des groupes de conteneurs

Vous pouvez paramétrer des groupes logiques de types de conteneur. Pour chaque groupe, vous pouvez spécifier l’ordre dans lequel les conteneurs sont emballés, et le pourcentage de remplissage de chaque conteneur. Les dimensions de taille de l’article déterminent s’il tiendra dans un conteneur. Le conteneur qui est le plus proche des dimensions de taille de l’article est utilisé. Si vous avez plusieurs types de conteneur dans un groupe, nous vous recommandons de réorganiser l’ordre par taille, afin que le conteneur le plus grand soit en premier, numéro 1 dans l’ordre, et que le plus petit conteneur soit le dernier.

Pour paramétrer un groupe de conteneurs, suivez les étapes suivantes :

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Groupes de conteneurs**.
1. Sélectionnez **Nouveau** pour créer un groupe de conteneurs.
1. Entrez un ID unique et une description pour le groupe de conteneurs.
1. Sur le raccourci **Détails**, sélectionnez **Nouveau** pour ajouter un type de conteneurs au groupe.
1. Dans le champ **Type de conteneur**, sélectionnez un type de conteneur.
1. Sélectionnez **Déplacer vers le haut** ou **Déplacer vers le bas** pour spécifier l’ordre dans lequel les types de conteneurs sont emballés.

## <a name="create-container-build-templates"></a>Créer des modèles de création de conteneur

Vous pouvez paramétrer des règles pour le processus de mise en conteneur, tel que les règles de mélange de stock et d’autres stratégies de conditionnement. Par exemple, vous pouvez paramétrer une règle afin que les collaborateurs ne puissent pas conditionner les lignes de répartition qui représentent des commandes client de clients différents dans le même conteneur.

Pour paramétrer un modèle de création de conteneur, suivez les étapes suivantes.

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Modèles de création de conteneur**.
1. Créez un modèle de création de conteneur.
1. Dans les champs **Nom de la mise en conteneur** et **Numéro séquentiel**, entrez le nom du modèle de mise en conteneur et de la commande qui est mise en correspondance avec les lignes de répartition.

    > [!NOTE]
    > Le système appliquera le premier modèle dont la ligne de répartition respecte les critères de requête. Il est donc recommandé de placer le modèle avec les critères les plus spécifiques en haut de la liste. Plus les critères sont larges, plus une ligne de répartition est susceptible de répondre aux critères. Cela peut entrainer l’affectation de lignes au mauvais conteneur. Si nécessaire, vous pouvez sélectionner **Déplacer vers le haut** ou **Déplacer vers le bas** pour changer l’ordre des modèles.

1. Dans le champ **ID du groupe de conteneurs**, sélectionnez le groupe de conteneurs à partir duquel créer des conteneurs.
1. Dans le champ **Types de requête de base**, sélectionnez le type de requête qui déterminera quels éléments conditionner et sur quoi baser la requête de filtre. Les options suivantes sont disponibles :

      - **Lignes de répartition des ventes** - Les lignes de répartition de conditionnement sont créées pour les commandes client.
      - **Ligne de répartition des transferts** - Les lignes de répartition de conditionnement sont créées pour les ordres de transfert.
      - **Conteneur** - Permet de conditionner un conteneur déjà créé par le processus de mise en conteneur. Par exemple, cette option est utilisée pour imbriquer des conteneurs.

        > [!NOTE]
        > Pour utiliser l’imbrication de conteneurs, vous devez faire en sorte que la méthode de mise en conteneur puisse se répéter. Pour plus d’informations, voir [Modèles de vague](wave-templates.md).

1. Dans le raccourci **Général**, dans le champ **Code étape de vague**, entrez l’identificateur unique de la méthode de traitement de la vague qui lie le modèle de création de conteneur aux étapes d’un modèle de vague.
1. Activez la case à cocher **Autoriser la répartition des prélèvements** pour autoriser les collaborateurs à conditionner les articles d’un ordre d’exécution dans des conteneurs distincts. Cela nécessite que l’intégralité de la quantité tienne dans le conteneur. La plus grande unité de mesure dans la ligne de répartition est toujours utilisée.
1. Dans le champ **Unité de conditionnement**, sélectionnez l’unité de mesure qui représente le conteneur. Par exemple, vous pouvez indiquer qu’un casier est un conteneur. Si vous conditionnez par unité de mesure, vous ne pouvez pas spécifier de groupe de conteneurs car l’unité de mesure est le conteneur.
1. Dans le champ **Stratégie de conditionnement de conteneur**, sélectionnez la stratégie de conditionnement à utiliser. Les options suivantes sont disponibles :

    > [!NOTE]
    > La stratégie ne s’applique qu’aux lignes de répartition de vente et aux lignes de répartition de transfert.

      - **Conditionner dans tous les conteneurs ouverts** – Le système évalue si la ligne de répartition tiendra dans un conteneur créé au cours du cycle de mise en conteneur.
      - **Conditionner dans le conteneur en cours uniquement** – Le système n’évalue que si la ligne de répartition tiendra dans le conteneur créé le plus récemment.

1. Pour définir des règles de conditionnement des lignes de répartition dans des conteneurs, sélectionnez **Décompositions de la logique de mélange**. Par exemple, vous pouvez créer une règle qui permettra aux collaborateurs de conditionner les lignes de répartition de deux articles différents dans le même conteneur. Pour définir une règle de mélange, procédez comme suit :

    1. Dans la page **Décompositions de la logique de mélange**, sélectionnez **Nouveau**.
    1. Dans le champ **Table**, sélectionnez le tableau contenant le champ à utiliser comme critère pour la décomposition de la logique de mélange.
    1. Dans le champ **Sélectionner champ**, sélectionnez le champ à utiliser comme critère pour la décomposition de la logique de mélange.
    1. Répétez ces étapes jusqu’à ce que vous ayez ajouté tous les critères de la décomposition de la logique de mélange.

    > [!NOTE]
    > Si vous utilisez une logique de mélange, nous vous recommandons de trier selon les mêmes champs dans la requête de critère de filtre. Cela réduira le nombre de conteneurs créés.
