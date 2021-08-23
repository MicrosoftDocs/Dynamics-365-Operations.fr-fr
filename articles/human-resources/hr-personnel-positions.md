---
title: Postes
description: Cette rubrique décrit les éléments conceptuels qu’un poste peut inclure. Elle fournit également des exemples qui montrent comment vous pouvez utiliser ces éléments dans votre organisation.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: anbichse
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 269054
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c8311df31326faeadd280585115338317b19125d54f3a526b4ccc6ef6684ad2c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754750"
---
# <a name="positions"></a>Postes

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit les éléments conceptuels qu’un poste peut inclure. Elle fournit également des exemples qui montrent comment vous pouvez utiliser ces éléments dans votre organisation.

Avant de pouvoir créer un poste, une tâche doit être configurée. Certains détails de poste, tels que la région de rémunération, l’affectation de l’employé, la durée du poste et la relation hiérarchique, sont en vigueur à la date.

## <a name="general-information"></a>Informations générales

Lorsque vous créez un poste, vous devez sélectionner une tâche. Les informations suivantes seront automatiquement renseignées à partir du poste que vous sélectionnez :

- Description 
- Titre
- Équivalent temps plein
- Famille de tâches

Le titre du poste est utilisé pour référencer le titre d’un employé. (Le titre qui est inscrit sur l’employé n’est pas utilisé.) Par conséquent, les titres de poste doivent être normalisés autant que possible.

> [!NOTE]
> Un employé ne peut pas être affecté à un poste à une date antérieure à la date de disponibilité.
>
> Un paramètre de l’onglet **Postes** de la page **Paramètres partagés des ressources humaines** contrôle le comportement d’affectation des employés. Vous devez sélectionner l’une des valeurs suivantes :
>
> - **Toujours** – Vous ne pouvez pas affecter de collaborateurs à de nouveaux postes lorsque des postes sont créés. Lorsque des postes sont créés, la date et l’heure **Disponible pour affectation** de l’onglet **Général** de la page **Poste** sont automatiquement définis à la date et à l’heure de création.
> - **Jamais** – Vous ne pouvez pas affecter de collaborateurs à de nouveaux postes lorsque des postes sont créés. Si vous sélectionnez cette option, vous devez ouvrir la page **Poste** pour chaque nouveau poste au fur et à mesure qu’il devient disponible. Ensuite, sur l’onglet **Général**, entrez la date **Disponible pour affectation** afin d’activer l’affectation des employés. Si vous sélectionnez cette option, la date d’affectation de l’employé sera définie sur **Jamais** par défaut lorsque vous tenterez d’affecter l’employé.

## <a name="position-duration"></a>Durée du poste

Chaque poste est effectif pour une période de temps spécifique nommée durée. Par exemple, les postes d’été peuvent avoir une durée qui s’étend du 1er mai 2021 au 31 août 2021. La date d’activation est la date à laquelle le poste est actif dans le système. La date d’arrêt est la date à laquelle le poste n’est plus actif dans le système.

Notez que ni la date de disponibilité ni la date d’affectation de l’employé ne peuvent être antérieurs à la date d’activation. Un poste n’est pas considéré comme actif tant que la date d’activation n’a pas été atteinte. De plus, une affectation d’employé ne peut pas s’étendre au-delà de la date de retraite du poste.

## <a name="reports-to-position"></a>Poste de supérieur hiérarchique

Les postes sont des éléments importants du niveau inférieur d’une hiérarchie d’organisation. Sur la page **Poste**, vous pouvez spécifier le poste de supérieur hiérarchique dont dépend un poste. Lorsque vous affectez un travailleur à un poste qui dépend d’un autre poste, vous créez une relation hiérarchique entre les travailleurs affectés à ces deux postes. Par exemple, le poste 000220 dépend du poste 000300. Pierre Lopez est affecté au poste 000220 et Sanjay Patel est affecté au poste 000300. Par conséquent, Pierre Lopez relève de Sanjay Patel.

> [!TIP]
> Le poste de supérieur hiérarchique est utilisé dans l’ensemble du système pour déterminer qui est le responsable d’un employé. Dans l’exemple précédent, si le rôle de manager est attribué à Sanjay Patel dans le système, il verra Pierre Lopez comme un subordonné direct dans Libre-service Responsable. La relation hiérarchique peut également être utilisée lorsque vous créez des règles de routage de workflow et des tâches de liste de contrôle.

## <a name="relationships"></a>Relations

Si votre organisation utilise une hiérarchie matricielle ou une autre hiérarchie personnalisée, vous pouvez configurer des types de hiérarchie de postes. Vous pouvez ensuite ajouter des relations hiérarchiques aux postes pour chaque type de hiérarchie que vous configurez. Par exemple, Lori Penor est directrice général chez Adventure Works et est affecté au poste de **Directeur général**. Lori gère le développement d’un produit utilisé pour nettoyer les widgets. Elle a besoin d’un comptable pour l’aider avec les finances. Par conséquent, elle a recruté Pierre Lopez comme comptable. Pierre est sous l’autorité directe de Sanjay Patel, mais il travaille également avec Lori Penor sur l’aspect financier du développement du nettoyeur de widget.

Dans l’exemple précédent, vous effectueriez les tâches suivantes pour paramétrer la relation de travail entre Pierre Lopez et Lori Penor :

1. Création d’un type de hiérarchie de poste personnalisé appelé **Widget** pour créer une hiérarchie qui inclut les postes responsables du travail sur le produit de nettoyage de widget.
2. Spécifiez le poste **Directeur général** comme poste dont dépend le poste de Pierre dans la hiérarchie **Widget**.
3. Utilisez la hiérarchie des postes pour afficher la structure hiérarchique des postes. Si plusieurs hiérarchies des postes, vous pouvez afficher la hiérarchie de chaque type de hiérarchie de la hiérarchie des postes. Vous pouvez également rechercher un poste à l’aide de l’ID du poste ou du nom du travailleur affecté au poste. La hiérarchie des postes est une hiérarchie d’organisation.

## <a name="labor-union"></a>Syndicat

Vous pouvez enregistrer si un accord syndical est requis pour le poste et quel syndicat est utilisé. Vous pouvez également associer l’accord à une entité juridique.

## <a name="financial-dimensions"></a>Dimensions financières

Lorsque vous créez la dimension financière d’un poste, vous devez spécifier une entité juridique. Vous pouvez sélectionner les dimensions par défaut pour chaque dimension individuellement. Vous pouvez également sélectionner un modèle de distribution pour remplir automatiquement les dimensions par défaut. Un modèle de distribution offre également la possibilité d’allouer des montants sur plusieurs valeurs de dimension.
