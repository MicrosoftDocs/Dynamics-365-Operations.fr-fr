---
title: Traiter le journal de répartition comptable
description: Utilisez la page Traiter la demande de répartition pour créer un journal de répartition qui puisse être consulté et approuvé avant la validation dans la comptabilité ou être validé directement dans la comptabilité.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d2046e25719c9023bee99736488a4ee6f22723fe
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "335644"
---
# <a name="process-ledger-allocation-journal"></a>Traiter le journal de répartition comptable

[!include [task guide banner](../../includes/task-guide-banner.md)]

Utilisez la page Traiter la demande de répartition pour créer un journal de répartition qui puisse être consulté et approuvé avant la validation dans la comptabilité ou être validé directement dans la comptabilité. Avant de créer un journal de répartition, il doit exister au moins une règle de répartition de comptabilité active. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à Comptabilité > Répartition > Traiter la demande de répartition.
2. Dans le champ Règle, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Entrez une date dans le champ À partir de.
    * Le champ À partir du est très important lorsque la comptabilité est la source de données de la règle. Cette date contrôle les soldes comptables à inclure dans la répartition.     Dans le champ Aucune origine, sélectionnez Arrêter. Cela arrête le processus de répartition et affiche un message qui indique qu'un montant source nul est sélectionné.  
6. Dans le champ Options de proposition, sélectionnez « Proposition uniquement ».
    * Sélectionnez Proposition uniquement pour consulter uniquement et éventuellement approuver le résultat dans les journaux de répartition avant de valider la répartition dans la comptabilité.  
7. Entrez une date dans le champ Date de validation dans la comptabilité.
8. Cliquez sur OK.
9. Accédez à Comptabilité > Répartition > Journaux de répartition.
10. Cliquez sur Lignes.
11. Cliquez sur Valider.
12. Cliquez sur Valider.

