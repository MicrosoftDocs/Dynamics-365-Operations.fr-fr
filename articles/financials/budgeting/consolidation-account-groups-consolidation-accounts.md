---
title: Groupes de comptes de consolidation et comptes de consolidation supplémentaires
description: Cette rubrique fournit des informations sur les groupes de comptes de consolidation et les comptes de consolidation supplémentaires, et explique comment ils sont utilisés dans Microsoft Dynamics 365 for Finance and Operations.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f1c463ee54512b07f5e45c4df995aefed6110cb0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "366395"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Groupes de comptes de consolidation et comptes de consolidation supplémentaires

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les groupes de comptes de consolidation et les comptes de consolidation supplémentaires, et explique comment ils sont utilisés dans Microsoft Dynamics 365 for Finance and Operations.

<a name="consolidation-account-groups"></a>Groupes de comptes de consolidation
----------------------------

Les groupes de comptes de consolidation permettent de créer des groupes de comptes à utiliser pour consolider les données. Le plus souvent, un groupe de comptes de consolidation représente un plan de comptes imposé par l'administration ou met en correspondance des comptes avec un groupe défini par le siège de la société. Vous pouvez rechercher des groupes de comptes de consolidation dans la zone **Paramétrage** du module **Consolidations**. Lorsque vous ajoutez un nouveau groupe, vous entrez un identificateur unique pour le groupe de comptes et un nom.

## <a name="additional-consolidation-accounts"></a>Comptes de consolidation supplémentaires
Les comptes de consolidation supplémentaires permettent d'affecter un compte issu d'un plan de comptes existant à un groupe de comptes de consolidation. Vous pouvez ensuite spécifier une valeur et un nom de compte de consolidation. 

Vous pouvez rechercher des comptes de consolidation supplémentaires dans la zone **Paramétrage** du module **Consolidations**. Lorsque vous créez un compte de consolidation, vous devez spécifier les informations suivantes :

-   **Compte principal** – Ce champ est une recherche qui affiche tous les comptes principaux basés sur le plan de comptes sélectionné dans la page. Lorsque vous sélectionnez un compte, le nom est automatiquement entré dans le champ **Nom du compte principal**.
-   **Groupe de comptes de consolidation** – Ce champ permet de spécifier le groupe auquel affecter le compte. Si vous effectuez une consolidation de deux façons différentes, vous devez ajouter le même compte aux quatre groupes de comptes de consolidation.
-   **Compte de consolidation** – Permet d'entrer la valeur du compte de consolidation. Cette valeur ne doit pas être un compte issu d'un plan de comptes. Il peut s'agir de n'importe quelle valeur de votre choix.
-   **Nom du compte de consolidation** – Permet d'entrer le nom du compte tel qu'il doit apparaître dans les recherches et les états.
-   **Niveau SAT** – Ce champ est utilisé pour déclarer des relevés de compte aux autorités fiscales mexicaines. 

Lorsque vous avez terminé de créer vos groupes de comptes de consolidation et vos comptes de consolidation supplémentaires, vous pouvez sélectionner le groupe dans le processus Consolidation en ligne.


Pour plus d'informations, voir [Créer des groupes de consolidation et comptes de consolidation supplémentaires](../general-ledger/tasks/create-consolidation-groups.md). 



