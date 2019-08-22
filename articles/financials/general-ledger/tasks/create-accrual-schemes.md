---
title: Création de plans de régularisation
description: Ce guide accompagne l'utilisateur le long de la création d'un plan de régularisation.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e0ae55000a5cf1593d057d940dc3dbbf9e5cb3f3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834881"
---
# <a name="create-accrual-schemes"></a>Création de plans de régularisation

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide accompagne l'utilisateur le long de la création d'un plan de régularisation. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à Comptabilité > Paramétrage du journal > Plans de régularisation.
2. Cliquez sur Nouveau.
3. Dans le champ Identification de la régularisation, entrez une valeur.
4. Dans le champ Description du plan de régularisation, entrez une valeur.
5. Dans le champ Débit, spécifiez les valeurs souhaitées.
    * Le compte principal défini remplacera le compte principal de débit dans la ligne de N° document de journal et il sera également utilisé pour la contrepassation des différés en fonction des transactions de régularisation des comptes.  
6. Dans le champ Crédit, spécifiez les valeurs souhaitées.
    * Le compte principal défini remplacera le compte principal de crédit dans la ligne de N° document de journal et il sera également utilisé pour la contrepassation des différés en fonction des transactions de régularisation des comptes.  
7. Dans le champ N° document, sélectionnez la manière dont vous souhaitez que le N° document soit déterminé lorsque les transactions sont validées.
8. Dans le champ Description, entrez une valeur pour décrire les transactions qui seront validées.
9. Dans le champ Fréquence, sélectionnez la fréquence à laquelle les transactions doivent se produire.
10. Entrez un nombre dans le champ Occurrences par période.
11. Dans le champ Valider les transactions, sélectionnez à quel moment transactions doivent être validées, comme Mensuel.

