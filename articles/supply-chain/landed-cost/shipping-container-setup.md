---
title: Conteneurs d’expédition
description: Cette rubrique décrit comment configurer les conteneurs d’expédition pour le module de coût au débarquement.
author: Weijiesa
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 96710cf2b5a2e39f9492aadb0ba6f3241f0666f4
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690552"
---
# <a name="shipping-container-setup"></a>Configuration du conteneur d’expédition

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment configurer les conteneurs d’expédition pour le module de **coût au débarquement**.

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a>Paramétrer des types de conteneurs d’expédition

Les types de conteneurs d’expédition définissent les types de conteneurs d’expédition disponibles pour une utilisation pendant l’expédition et les voyages.

Pour travailler avec les types de conteneurs d’expédition, accédez à **Prix au débarquement \> Configuration des conteneur \> Types de conteneurs d’expédition**. Là, vous pouvez afficher, ajouter et supprimer des enregistrements pour vos types de conteneurs. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Type de conteneur d’expédition | Entrez un nom/numéro d’identification unique pour le type de conteneur. |
| Description | Permet d’entrer la description du groupe de types de conteneurs d’expédition. |
| Volume | Saisissez le volume maximal autorisé dans les conteneurs d’expédition de ce type. |
| Pondération | Saisissez le poids maximal autorisé dans les conteneurs d’expédition de ce type. |
| Pouvant faire l’objet d’un retour | Indiquez si les conteneurs d’expédition de ce type peuvent être retournés au fournisseur après avoir été utilisés pendant un voyage. Si cette option est définie sur *Oui*, des frais supplémentaires peuvent s’appliquer pour le retour des conteneurs d’expédition de ce type au port d’origine. |

## <a name="set-up-shipping-containers"></a>Configuration des conteneurs d’expédition

Vous utilisez les enregistrements de conteneurs d’expédition pour identifier chaque conteneur que vous utilisez pendant les voyages. Lorsque vous créez un voyage, vous pouvez sélectionner un conteneur spécifique pour celui-ci dans la liste de tous les enregistrements de conteneurs d’expédition que vous avez définis ici. Cette fonctionnalité est particulièrement utile si votre entreprise possède ses propres conteneurs d’expédition.

Vous n’êtes pas obligé de saisir les numéros de conteneur d’expédition pour les conteneurs d’expédition qui ne seront utilisés qu’une seule fois. Au lieu de cela, vous pouvez ajouter le numéro du conteneur d’expédition lorsque vous créez un voyage.

Les enregistrements des conteneurs d’expédition ne sont utilisés que dans le coût au débarquement. Ils ne sont pas disponibles dans le module **Gestion des transports** (TMS) standard.

Pour travailler avec les conteneurs d’expédition, accédez à **Prix au débarquement \> Configuration des conteneur \> Conteneurs d’expédition**. Là, vous pouvez afficher, ajouter et supprimer des enregistrements pour vos conteneurs. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Conteneur d’expédition | Entrez un nom/numéro d’identification unique pour le conteneur. |
| Type de conteneur d’expédition | Sélectionnez le type de conteneur d’expédition. Pour plus d’informations, voir [Paramétrer des types de conteneurs d’expédition](#shipping-container-types) précédemment dans cette rubrique. |

> [!NOTE]
> - La configuration du conteneur d’expédition est facultative. En règle générale, vous ne l’utiliserez que si votre entreprise possède ses propres conteneurs d’expédition ou réutilise souvent les mêmes conteneurs d’expédition.
> - Aucun chiffre de contrôle n’est calculé pour les numéros de conteneur d’expédition.

## <a name="set-up-unit-types"></a><a name="unit-types"></a>Configurer les types d’unités

Les types d’unités établissent des regroupements et des méthodes d’identification supplémentaires pour les conteneurs d’expédition. Le type d’unité est généralement utilisé pour identifier le type de conteneur dans lequel les marchandises sont emballées, comme des palettes ou des fûts. Vous pouvez sélectionner un type d’unité lorsque vous configurez un conteneur sur la page **Tous les conteneurs d’expédition**.

Les types d’unités ne sont utilisés que dans le coût au débarquement. Ils ne sont pas disponibles dans TMS.

Pour travailler avec les types d’unités, accédez à **Prix au débarquement \> Configuration des conteneur \> Types d’unités**. Là, vous pouvez afficher, ajouter et supprimer des enregistrements pour vos types d’unités. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Type d’unité | Entrez un nom/numéro d’identification unique pour le type d’unité. |
| Description | Permet d’entrer la description du type d’unité. |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a>Paramétrage des types de réfrigérations

Les types de réfrigération définissent des moyens supplémentaire de regrouper et d’identifier les conteneurs d’expédition (en général des conteneurs réfrigérés). Vous pouvez sélectionner un type de réfrigération lorsque vous configurez un conteneur sur la page **Tous les conteneurs d’expédition**.

Pour travailler avec les types de réfrigérations, accédez à **Prix au débarquement \> Configuration des conteneur \> Types de réfrigérations**. Là, vous pouvez afficher, ajouter et supprimer des enregistrements pour vos types de réfrigérations. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Type de réfrigération | Entrez un nom/numéro d’identification unique pour le type de réfrigération. |
| Description | Permet d’entrer une description du type de réfrigération. |
