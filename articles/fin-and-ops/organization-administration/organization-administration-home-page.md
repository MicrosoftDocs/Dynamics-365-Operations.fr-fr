---
title: Page d'accueil de l'administration de l'organisation
description: "Cette rubrique redirige vers des ressources utiles pour exploiter Microsoft Dynamics 365 for Finance and Operations, Enterprise edition dans votre organisation."
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 20421
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c73eeaaf28df8db720431d4bcd317c9721baa99d
ms.openlocfilehash: eb8674a6401b11e8e33d3cba54add1fb4bca1cd3
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="organization-administration-home-page"></a>Page d'accueil de l'administration de l'organisation

[!include[banner](../includes/banner.md)]


Cette rubrique redirige vers un contenu qui aidera les utilisateurs et les administrateurs à configurer Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Ce contenu les aidera à configurer le système pour qu'il fonctionne sans heurts et efficacement pour votre organisation et votre activité.

La plupart du contenu répertorié ici s'applique aux fonctions du module **Administration de l'organisation**. Cependant, plusieurs tâches, telles que la création et l'utilisation d'un modèle d'enregistrement, peuvent être effectuées dans n'importe quel module pour aider votre organisation à fonctionner plus efficacement. 

<a name="number-sequences"></a>Souches de numéros
----------------
Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transactions qui en exigent. Un enregistrement de données principales ou de transaction nécessitant un identificateur est également appelé *référence*. Avant de pouvoir créer des enregistrements pour une référence, vous devez paramétrer une souche de numéros et l'associer à la référence.

-   [Vue d'ensemble des souches de numéros](number-sequence-overview.md)
-   [Configurer les souches de numéros à l'aide d'un assistant](tasks/set-up-number-sequences-wizard.md) (Guide de tâche)
-   [Paramétrer des souches de numéros sur une base individuelle](tasks/set-up-number-sequences-individual-basis.md) (Guide de tâche)

## <a name="organizations"></a>Organisations
Une organisation est un groupe de personnes qui travaillent ensemble pour réaliser un processus entreprise ou atteindre un objectif. Les hiérarchies organisationnelles représentent les relations entre les organisations qui composent votre entreprise.

Avant de paramétrer des organisations et des hiérarchies d'organisation dans Finance and Operations, veillez à planifier votre modèle d'entreprise. Le modèle d'organisation a un impact considérable sur l'implémentation de Finance and Operations et les processus entreprise.

-   [Organisations et hiérarchies d'organisation](organizations-organizational-hierarchies.md)
-   [Planification de votre hiérarchie d'organisation](plan-organizational-hierarchy.md)
-   [Création ou modification d'une hiérarchie d'organisation](tasks/create-organization-hierarchy.md) (Guide de tâche)
-   [Création d'une entité juridique](tasks/create-legal-entity.md) (Guide de tâche)
-   [Création d'une unité opérationnelle](tasks/create-operating-unit.md) (Guide de tâche)

## <a name="address-books"></a>Carnets d'adresses
Le Carnet d'adresses global est un référentiel centralisé pour les données principales qui doivent être enregistrées pour toutes les personnes et organisations internes et externes avec lesquelles la société interagit. Les données associées aux enregistrements de parties comprennent le nom, l'adresse, les informations de contact de la partie. 

Une fois que vous avez créé le carnet d'adresses global, vous pouvez créer des carnets d'adresses supplémentaires selon vos besoins, par exemple un carnet d'adresses distinct pour chaque société de votre organisation ou pour chaque activité. 

-   [Carnet d'adresses global](overview-global-address-book.md)
-   [Planification pour la configuration du carnet d'adresses global et de carnets d'adresses supplémentaires](plan-configuration-global-address-book-additional-address-books.md)
- [Configurer le carnet d'adresses global](tasks/configure-global-address-book.md)
-   [FAQ sur les carnets d'adresses](qa-address-books.md)


## <a name="workflow"></a>Workflow
Un workflow est un système installé avec Finance and Operations qui permet de créer des workflows individuels, ou des processus métier. Lorsque vous créez un workflow, vous pouvez spécifier la circulation ou la progression d'un document dans le système en indiquant qui doit traiter une tâche, prendre une décision ou approuver un document. 

-   [Vue d'ensemble du workflow](overview-workflow-system.md)
-   [Éléments du workflow](workflow-elements.md)
-   [Actions de workflow](workflow-actions.md)
-   [Création d'un workflow](create-workflow.md)

## <a name="electronic-signatures"></a>Signatures électroniques
Une signature électronique confirme l'identité d'une personne qui va commencer ou approuver une procédure informatique. Dans certains secteurs, une signature électronique représente un engagement juridique aussi important qu'une signature manuscrite. La signature électronique est un impératif de conformité aux réglementations pour certaines industries réglementées, telles que les industries pharmaceutique, alimentaire et aérospatiale et de défense.

Dans Finance and Operations, vous pouvez utiliser des signatures électroniques pour des processus d'entreprise importants. Certains processus disposent d'une fonction de signature électronique intégrée. Vous pouvez également créer des demandes de signature personnalisées pour les tables et les champs de base de données.

-   [Vue d'ensemble de la signature électronique](electronic-signature-overview.md)
-   [Paramétrage de signatures électroniques](tasks/set-up-electronic-signatures.md) (Guide de tâche)

## <a name="case-management"></a>Gestion des dossiers
La planification, le suivi et l'analyse des incidents permettent d'aboutir à des résolutions efficaces susceptibles d'être utilisées pour des problèmes semblables. Par exemple, lorsque des représentants du service client ou des chargés des ressources humaines créent des incidents, ils peuvent trouver des informations dans les articles de base de connaissances sur la résolution efficace d'un incident. 

-   [Vue d'ensemble de la gestion des dossiers](cases.md)
-   [Configurer la sécurité, les processus, et les catégories d'incident](plan-case-management.md)

## <a name="record-templates"></a>Modèles d'enregistrement
Les modèles d'enregistrement vous aident à créer des enregistrements plus rapidement. Vous pouvez créer un modèle d'enregistrement pour ne pas avoir à saisir explicitement les valeurs de champ utilisées régulièrement pour chaque nouvel enregistrement. 

-   [Modèles d'enregistrement](record-templates.md)
- [Créer un modèle d'enregistrement pour faciliter la saisie des données](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Guide de tâche)
- [Utiliser un modèle d'enregistrement pour créer un enregistrement](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (Guide de tâche)

## <a name="general-organization-administration"></a>Administration d’organisation générale
-   [Modification de la bannière ou du logo](../get-started/tasks/change-banner-or-logo.md) (Guide de tâche)
- [Configurer la gestion des documents](configure-document-management.md)
- [Configuration et envoi d'e-mail](configure-email.md)
-   [Données de date/d'heure et fuseaux horaires](date-time-zones.md)








