---
title: "Groupes de comptes de consolidation et comptes de consolidation supplémentaires"
description: "Cette rubrique fournit des informations sur les groupes de comptes de consolidation et des comptes de consolidation supplémentaires, et la elles sont utilisées dans Microsoft Dynamics 365 pour les opérations."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f9c5aaa389c9c2f85d1ab91cbf3d2222cbebef55
ms.lasthandoff: 03/31/2017


---

# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Groupes de comptes de consolidation et comptes de consolidation supplémentaires

Cette rubrique fournit des informations sur les groupes de comptes de consolidation et des comptes de consolidation supplémentaires, et la elles sont utilisées dans Microsoft Dynamics 365 pour les opérations.

<a name="consolidation-account-groups"></a>Groupes de comptes de consolidation
----------------------------

Les groupes de comptes de consolidation vous permettent de créer des groupes de comptes à utiliser pour regrouper les données. Le plus souvent, un groupe de comptes de consolidation représente un plan de comptes gouvernement- mandaté ou met en correspondance les comptes à un groupe qui est défini par Retail Siège de la société. Vous pouvez trouver des groupes de comptes de consolidation dans ** paramétrage ** la zone ** des consolidations ** du module. Lorsque vous ajoutez un nouveau groupe, vous entrez un identificateur unique pour le groupe de comptes et un nom.

## <a name="additional-consolidation-accounts"></a>Comptes de consolidation supplémentaires
Les comptes de consolidation supplémentaires permettent d'affecter un compte d'un plan de comptes existant à un groupe de comptes de consolidation. Vous pouvez spécifier une valeur et un nom de compte de consolidation. 

Vous pouvez trouver des comptes de consolidation supplémentaires dans ** paramétrage ** la zone ** des consolidations ** du module. Lorsque vous créez un compte de consolidation, vous devez spécifier les informations suivantes :

-   ** Compte principal ** – ce champ est une recherche cette présente tous les comptes principaux basées sur le plan de comptes sélectionné dans la page. Lorsque vous sélectionnez un compte, le nom est automatiquement entré dans ** nom du compte principal ** le champ.
-   ** Groupe de comptes de consolidation ** – Ce champ permet de spécifier le groupe auquel affecter le compte. Si vous consolidez de deux manières différentes, vous devez ajouter le même compte à chacun des quatre groupes de comptes de consolidation.
-   ** Compte de consolidation ** – Permet d'entrer la valeur du compte de consolidation. Cette valeur ne doit pas être un compte d'un plan de comptes. Ce peut être n'importe quelle valeur dont vous avez besoin.
-   ** Nom du compte de consolidation ** – Permet d'entrer le nom du compte comme vous souhaitez voir apparaître dans les recherches et des états.
-   ** Niveau de SAT ** – Ce champ est utilisé pour déclarer des relevés de compte aux administrations fiscales mexicaines. 

Lorsque vous avez terminé de créer les groupes de comptes de consolidation et comptes de consolidation supplémentaires, vous pouvez sélectionner le groupe dans le processus de consolidation en ligne.



