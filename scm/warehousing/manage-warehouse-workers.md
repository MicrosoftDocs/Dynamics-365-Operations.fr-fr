---
title: Gestion des magasiniers
description: "Cet article décrit la manière dont vous pouvez utiliser Microsoft Dynamics AX pour mieux contrôler et surveiller le travail qui est mené à bien par les employés dans vos entrepôts."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorker, InventLocation, WHSLaborStandards, WHSWorker, WHSWorkTable, WHSWorkTableListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72891
ms.assetid: feaa6f15-49d2-41f5-9b87-453463c52e4e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d037a1e99fa29140f4e241c27408138164bd251f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="manage-warehouse-workers"></a>Gestion des magasiniers

[!include[banner](../includes/banner.md)]


Cet article décrit la manière dont vous pouvez utiliser Microsoft Dynamics AX pour mieux contrôler et surveiller le travail qui est mené à bien par les employés dans vos entrepôts.

Si vous utilisez la fonctionnalité de gestion des entrepôts, toutes les opérations des magasiniers sont appelées *travail*. Les travaux tels que le prélèvement, le déplacement, et l'inventaire du stock disponible sont enregistrés en utilisant des périphériques mobiles. Pour qu'un magasinier puisse effectuer le travail, il doit être associé à un collaborateur dans les Ressources humaines. Chaque compte de **Collaborateur** peut être associé à plusieurs utilisateurs de travail d'entrepôt. Ces utilisateurs de travail peuvent travailler dans différents entrepôts et avoir des niveaux d'accès différents aux menus du périphérique portable. Vous pouvez penser aux utilisateurs de travail d'entrepôt comme plusieurs connexions pour le collaborateur sélectionné. Chaque utilisateur de travail a un entrepôt par défaut, et des workflows spécifiques sont exposés par les articles de menus qui sont accessibles à cet utilisateur de travail. 

Pour créer un utilisateur de travaux, dans la page **Collaborateurs**, sous l'onglet **Général** dans la section **Entrepôts**, cliquez sur **Collaborateur**. Vous devez spécifier un ID utilisateur, un nom d'utilisateur, un entrepôt par défaut, et un nom de menu. Ce menu est chargé lorsque l'utilisateur se connecte dans le portail des périphériques portables d'entrepôt, et vous permet de définir les options de menu auxquelles l'utilisateur a accès. 

Dans le cadre du paramétrage pour chaque utilisateur de travail, vous pouvez également définir des workflows de processus spécifiques. Par exemple, vous pouvez utiliser le champ **Superviseur d'inventaire tournant** pour indiquer si l'utilisateur peut procéder à des ajustements des écarts d'inventaire tournant lors d'une opération de comptage, ou si ces ajustements doivent d'abord être examinés par une autre personne.

## <a name="defining-labor-standards"></a>Définition des normes de main d'œuvre
La page **Normes de main d'œuvre** vous permet de définir les modes de calcul utilisés par le système pour calculer le temps estimé nécessaire pour un type donné de travail. Ce paramètre peut être défini à un niveau générique ou à un niveau spécifique. Par exemple, vous pouvez définir le temps qui doit être requis pour traiter une sélection de commande client par poids pour une définition d'unité spécifique lorsqu'un processus spécifique de prélèvement est utilisé. En même temps, vous pouvez enregistrer le temps, selon un autre mode de calcul, de l'opération de placement du stock disponible qui est prélevé. 

Pour activer les normes de main d'œuvre définies, vous devez sélectionner l'option **Autoriser les normes de main d'œuvre** pour chaque entrepôt où les normes de main d'œuvre sont utilisées.

## <a name="monitoring-and-controlling-warehouse-work"></a>Surveillance et contrôle du travail d'entrepôt
La page **Tout le travail** vous permet de surveiller et de tenir à jour tout le travail qui est prévu, en cours et achevé. Dans cette page, vous pouvez mettre à jour divers processus, tels que des affectations d'utilisateur de travail d'entrepôt et la priorité du travail. Vous pouvez également afficher les détails associés à l'en-tête du travail et aux lignes de travail pour mieux comprendre les processus de travail prévus ou achevés. 

Si vous activez l'option **Normes de main d'œuvre**, vous pouvez afficher le temps estimé calculé pour le travail. Puis, lorsque le travail est traité, le temps réel est également affiché pour chaque opération de travail. De cette manière, vous pouvez comparer les calculs de temps estimés avec le temps réel. 

En outre, vous pouvez utiliser le temps estimé dans les règles pour fractionner automatiquement le travail lors de la création du travail. De cette manière, vous pouvez équilibrer la charge de travail, selon la durée estimée pour terminer les tâches. 

L'analyse du temps qui est utilisée pour traiter les éléments de travail permet d'améliorer le rendement des magasiniers. Les états suivants sont disponibles pour aider à cette analyse :

-   **Main d'œuvre par utilisateur** – Cet état indique la productivité du collaborateur, par comparaison entre les durées réelles et les durées estimées.
-   **Main d'œuvre par type de transaction de travail** – Vous pouvez utiliser cet état pour rechercher les inefficacités dans les processus spécifiques d'entrepôt. Par exemple, vous remarquez que les prélèvements pour les ordres de transfert prennent plus longtemps cette semaine que dans les semaines précédentes. Vous pouvez ensuite utiliser ces informations pour une étude ultérieure.





