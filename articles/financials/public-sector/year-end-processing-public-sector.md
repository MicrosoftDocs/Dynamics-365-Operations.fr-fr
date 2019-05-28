---
title: Traitement de fin d'exercice dans le secteur public
description: Cet article fournit des informations sur le processus de fin d'exercice pour des organisations du secteur public.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchYearEndClose
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 19601
ms.assetid: ba9a7abc-bd18-47c2-b745-96cdcec8ac98
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c2fb0043e87840bd811d7a4936ebd3212bf544e
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1537868"
---
# <a name="year-end-processing-in-the-public-sector"></a>Traitement de fin d'exercice dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur le processus de fin d'exercice pour des organisations du secteur public.

Cette rubrique décrit la fonctionnalité de fin d'exercice disponible pour le secteur public. À la fin d'un exercice, vous devez générer des transactions de clôture et préparer vos comptes pour l'exercice suivant.  Les clients du secteur public ont les fonctionnalités suivantes :

-   Sélectionner des comptes par fonds pour la clôture de fin d'exercice.
-   Fermer les fonds à différents comptes. Par exemple, vous pouvez clôturer les comptes de gestion associés aux fonds gouvernementaux pour financer les soldes. Vous pouvez également clôturer les comptes de gestion associés aux fonds propriétaires aux bénéfices non répartis.
-   Paramétrer clôture de fin d'exercice pour tous les fonds et non-fonds. Les non-fonds ne disposent pas de dimension de fonds dans la structure de compte.
-   Paramétrer plusieurs périodes de clôture pour séparer différents types d'entrées de clôture, telles qu'une clôture générale de fin d'exercice et des ajustements d'audit.

## <a name="can-the-year-end-process-be-run-more-than-one-time-on-the-same-data"></a>Le processus de fin d'exercice peut-il être exécuté plusieurs fois sur les mêmes données ?
Oui, le processus de fin d'exercice peut être exécuté plusieurs fois pour le même ensemble de données. Généralement, si des transactions supplémentaires doivent être traitées après l'exécution d'un processus de fin d'exercice comptable, le processus de fin d'exercice peut être exécuté de nouveau pour clôturer les comptes de gestion et pour paramétrer correctement les soldes d'ouverture dans la nouvelle année.

## <a name="how-do-i-set-up-funds-for-year-end-processing"></a>Comment paramétrer des fonds pour le traitement de fin d'exercice ?
Le traitement de fin d'exercice des soldes comptables est contrôlé par les paramètres de configuration de fonds dans deux endroits :

-   Le processus de fin d'exercice visant la clôture des soldes comptables de l'année passée et le paramétrage des soldes d'ouverture dans la nouvelle année est effectué par l'intermédiaire de la page **Transactions d'ouverture**. Un fonds unique ou une plage des fonds est requis pour le traitement.
-   L'option de traitement de fin d'exercice pour les engagements de commande fournisseur est définie sur la page **Processus de fin d'exercice de commande fournisseur**. Vous pouvez remplacer l'option sur un fonds spécifique, à condition que les paramètres de comptabilité aient été définis pour autoriser les remplacements. Pour plus d'informations sur ces paramètres, voir [Comptabilité dans le secteur public](general-ledger-public-sector.md).

## <a name="how-do-i-set-up-main-accounts-for-year-end-processing"></a>Comment paramétrer des comptes principaux pour le traitement de fin d'exercice ?
Vous devez sélectionner un type de clôture pour chaque compte dans votre plan de comptes. Le type de clôture détermine la manière dont le processus de fin d'exercice traite ce compte principal. Il existe quatre types de clôture :

-   **Réel** – Le solde est utilisé pour établir des soldes d'ouverture dans la nouvelle année.
-   **Nominal** – Le compte est clôturé par le processus de fin d'exercice.
-   **Nominal - pas de clôture** – Le compte est géré par d'autres processus de clôture, comme les comptes d'engagement pour la clôture de commande fournisseur.
-   **Non applicable** – Le compte n'est pas inclus dans le traitement de fin d'exercice.

Les définitions de validation régissent la comptabilité qui concerne les entrées de clôture, et elles permettent également de créer des transactions d'ouverture pour la nouvelle année. Pour plus d'informations, voir [Définitions de validation dans le secteur public](posting-definitions-public-sector.md).



