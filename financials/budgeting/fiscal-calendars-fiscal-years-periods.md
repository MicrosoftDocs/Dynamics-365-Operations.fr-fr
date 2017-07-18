---
title: "Calendriers fiscaux, exercices et périodes"
description: "Cet article présente des calendriers fiscaux, des exercices et des périodes et la manière de les utiliser pour les entités juridiques, les immobilisations et la budgétisation."
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FiscalCalendars
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 25851
ms.assetid: a968a5e5-585e-4389-aa4e-c885a7e23413
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 22a08b1b9e819f5c683d278f37bf3404e757d200
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="fiscal-calendars-fiscal-years-and-periods"></a>Calendriers fiscaux, exercices et périodes

[!include[banner](../includes/banner.md)]


Cet article présente des calendriers fiscaux, des exercices et des périodes et la manière de les utiliser pour les entités juridiques, les immobilisations et la budgétisation.

Les calendriers fiscaux fournissent la structure de base de l'activité financière d'une organisation. Chaque calendrier fiscal inclut un ou plusieurs exercices constitués de plusieurs périodes. Les calendriers fiscaux peuvent être basés sur une année civile allant du 1er janvier au 31 décembre, ou sur les dates que vous sélectionnez. Par exemple, certaines organisations choisissent un calendrier fiscal qui commence le 1er juillet de l'année et se termine le 30 juin de l'année suivante. 

Le nombre de calendriers fiscaux et le nombre d'exercices d'un calendrier fiscal ne sont soumis à aucune limitation.. Chaque calendrier fiscal est indépendant de votre organisation et peut être utilisé par plusieurs entités juridiques de celle-ci. Par exemple, une organisation est composée de huit départements, chacun étant associé à une entité juridique distincte. Cinq d'entre-eux partagent le même calendrier fiscal et trois utilisent différents calendriers fiscaux. Vous pouvez créer un calendrier fiscal unique pour les cinq entités juridiques qui partagent le même calendrier fiscal, puis créer des calendriers fiscaux distincts pour les autres entités juridiques.

## <a name="create-fiscal-calendars-fiscal-years-and-periods"></a>Création de calendriers fiscaux, d'exercices et de périodes
La page Calendriers fiscaux vous permet de créer et de supprimer des calendriers fiscaux, des exercices et des périodes. Vous pouvez également fractionner des périodes existantes et créer des périodes de clôture d'un exercice. 

Une période de clôture permet de séparer les écritures comptables générées à la clôture d'un exercice. Lorsque les transactions de clôture appartiennent à une période fiscale, il est plus simple de créer des tableaux d'analyse qui incluent ou excluent différents types d'entrées de clôture. Si un exercice est divisé en 12 périodes fiscales, la période de clôture est généralement la treizième. Toutefois, une période de clôture peut être créée à partir d'une période quelconque ayant le statut Ouverte. 

Lorsque vous créez une période de clôture, sélectionnez une période avec le statut Ouverte et les dates que vous souhaitez utiliser. La nouvelle période de clôture copie les dates de début et de fin à partir de la période existante. La période d'origine continue d'exister. Par exemple, sélectionnez Période 12, dernière période de l'exercice dont les dates vont du 1er août au 31 août. Entrez un nom pour la période de clôture, tel que Clôture. Une fois que vous avez créé la période de clôture, vous avez désormais la période d'origine et la période de clôture. Les dates de ces deux périodes débutent le 1er août et prennent fin le 31 août.

## <a name="select-fiscal-calendars-for-ledgers-fixed-assets-and-budget-cycles"></a>Sélection des calendriers fiscaux pour la comptabilité, les immobilisations et les cycles budgétaires
Les calendriers fiscaux sont utilisés dans le cadre de l'amortissement des immobilisations, des transactions financières et des cycles budgétaires. Lorsque vous créez un calendrier fiscal, vous pouvez l'utiliser à plusieurs fins. Vous pouvez sélectionner un calendrier pour un modèle de valeur ou un registre des amortissements afin de le convertir en calendrier des immobilisations. Vous pouvez sélectionner un calendrier fiscal pour la comptabilité pour le convertir en calendrier comptable. Vous pouvez également sélectionner un calendrier fiscal pour un cycle budgétaire pour le convertir en calendrier budgétaire. Vous pouvez utiliser le même calendrier fiscal pour toutes ces opérations.

### <a name="select-a-fiscal-calendar-for-your-legal-entity"></a>Sélection d'un calendrier fiscal pour votre entité juridique

Sélectionnez le calendrier fiscal à utiliser pour la comptabilité de votre entité juridique dans l'écran Comptabilité. Un calendrier fiscal doit être sélectionné dans l'écran Comptabilité pour chaque entité juridique. Une fois que vous avez sélectionné un calendrier fiscal, vous pouvez paramétrer des statuts et autorisations de période sur la page Calendrier comptable pour les périodes qui font partie d'un exercice.

### <a name="select-a-fiscal-calendar-for-fixed-assets"></a>Sélection d'un calendrier fiscal pour les immobilisations

Vous pouvez sélectionner un calendrier fiscal pour un modèle de valeur ou un registre des amortissements, qui sera utilisé par les immobilisations utilisant le modèle de valeur ou le registre des amortissements sélectionné. Vous pouvez effectuer votre sélection à partir de n'importe quel calendrier fiscal défini sur la page Calendriers fiscaux.

### <a name="define-budget-cycle-time-spans"></a>Définition des périodes de cycle budgétaire

Les cycles budgétaires sont la durée pendant laquelle un budget est utilisé. Ils peuvent inclure une partie d'un exercice ou plusieurs exercices (cycle budgétaire biennal de deux ans ou cycle budgétaire triennal de trois ans). La période de cycle budgétaire définit le nombre de périodes incluses dans le cycle budgétaire. La page Périodes de cycle budgétaire permet de spécifier la période de cycle budgétaire.

## <a name="maintain-periods-for-your-organization"></a>Mise à jour des périodes pour votre organisation
La page Calendrier comptable permet d'afficher les détails du calendrier fiscal, des exercices et des périodes utilisés par votre organisation. Vous pouvez également modifier le statut des périodes et sélectionner les utilisateurs pouvant valider les transactions de comptabilité dans les périodes. Par exemple, au début d'une nouvelle période, vous souhaitiez qu'un groupe d'utilisateurs termine la validation des transactions financières de la période précédente et que les autres groupes travaillent uniquement sur la nouvelle période.






