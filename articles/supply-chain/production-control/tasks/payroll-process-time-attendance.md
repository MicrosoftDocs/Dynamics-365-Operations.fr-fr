---
title: Activer le processus de paie pour le pointage
description: "Cette procédure décrit comment activer le processus de paie pour le pointage."
author: johanhoffmann
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 16d8fc2120dfb7b356b238957019a29d05963f9a
ms.contentlocale: fr-fr
ms.lasthandoff: 02/06/2018

---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a>Activer le processus de paie pour le pointage

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment activer le processus de paie pour le pointage. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-a-pay-type-with-a-related-pay-rate"></a>Créer un type de salaire avec un taux de salaire associé
1. Pointage > Paramétrage > Paie > Types de salaire
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Type de paie.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Enregistrer.
6. Cliquez sur Taux.
    * Les taux pour les types de paie sont paramétrés pour des intervalles de temps spécifiques, et il est possible de créer des taux individuels pour les travailleurs. Il n'est pas toujours nécessaire de créer des taux pour les types de paie dans le module Pointage. Ces informations sont peut-être déjà présentes dans le système de paie utilisé pour générer les salaires.  
7. Cliquez sur Nouveau.
8. Dans la liste, marquez la ligne sélectionnée.
9. Entrez un nombre dans le champ Taux.
10. Cliquez sur Enregistrer.

## <a name="create-a-pay-agreement"></a>Création d'un accord salarial
1. Fermez la page.
2. Fermez la page.
3. Allez dans Accords salariaux.
    * Pointage > Paramétrage > Accords salariaux  
4. Cliquez sur Nouveau.
5. Tapez une valeur dans le champ Accord salarial.
6. Dans le champ Description, entrez une valeur.
7. Cliquez sur Enregistrer.
8. Cliquez sur Lignes d'accord.
9. Cliquez sur Nouveau.
10. Dans la liste, marquez la ligne sélectionnée.
11. Saisissez ou sélectionnez une valeur dans le champ Type de profil.
12. Saisissez ou sélectionnez une valeur dans le champ Type de paie.

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a>Paramétrer un accord salarial pour le collaborateur qualifié pour l'enregistrement des heures
1. Fermez la page.
2. Fermez la page.
3. Allez dans Enregistrement du temps des collaborateurs.
    * Pointage > Paramétrage > Enregistrement du temps des collaborateurs  
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Cliquez sur l'onglet Emploi.
6. Développez la section Enregistrement du temps.
7. Cliquez sur Modifier.
8. Saisissez ou sélectionnez une valeur dans le champ Accord salarial.

