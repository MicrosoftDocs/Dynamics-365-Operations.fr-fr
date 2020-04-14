---
title: Traiter le journal de répartition comptable
description: Cette rubrique explique comment traiter une demande de répartition dans Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 33e989d3641ae1eaa28a55398fcf51674ac1ed72
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144957"
---
# <a name="process-ledger-allocation-journal"></a>Traiter le journal de répartition comptable

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment traiter une demande de répartition. Utilisez la page Traiter la demande de répartition pour créer un journal de répartition qui puisse être consulté et approuvé avant la validation dans la comptabilité ou être validé directement dans la comptabilité. Avant de créer un journal de répartition, il doit exister au moins une règle de répartition de comptabilité active. La société fictive USMF est citée en exemple dans cette tâche.

1. Dans le volet de navigation, accédez à **Modules > Comptabilité > Répartitions > Traiter la demande de répartition**.
2. Dans le champ **Règle**, sélectionnez l'enregistrement souhaité dans le menu déroulant.
3. Dans le champ **À partir du**, saisissez une date.

    - Le champ **À partir du** est très important lorsque la comptabilité est la source de données de la règle. Cette date contrôle les soldes comptables à inclure dans la répartition.  
    - Dans le champ **Aucune origine**, sélectionnez **Arrêter**. Cela arrête le processus de répartition et affiche un message qui indique qu'un montant source nul est sélectionné.  

4. Dans le champ **Options de proposition**, sélectionnez **Proposition uniquement**. Sélectionnez **Proposition uniquement** pour consulter uniquement et éventuellement approuver le résultat dans les journaux de répartition avant de valider la répartition dans la comptabilité.  
5. Entrez une date dans le champ Date de validation dans la comptabilité.
6. Cliquez sur **OK**.
7. Dans le volet de navigation, accédez à **Modules > Comptabilité > Répartitions > Journaux de répartition**.
8. Sélectionnez **Lignes**.
9. Sélectionnez **Valider**.
10. Sélectionnez **Valider**.

