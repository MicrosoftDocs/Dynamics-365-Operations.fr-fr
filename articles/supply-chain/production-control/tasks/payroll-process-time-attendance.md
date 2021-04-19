---
title: Activer le processus de paie pour le pointage
description: Cette procédure décrit comment activer le processus de paie pour le pointage.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 411b5c3f1a486a30ec7d8d2c3896dacbf97b39ed
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821030"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a>Activer le processus de paie pour le pointage

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment activer le processus de paie pour le pointage. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-a-pay-type-with-a-related-pay-rate"></a>Créer un type de salaire avec un taux de salaire associé
1. Pointage > Paramétrage > Paie > Types de salaire
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Type de paie.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Enregistrer.
6. Cliquez sur Taux.
    * Les taux pour les types de paie sont paramétrés pour des intervalles de temps spécifiques, et il est possible de créer des taux individuels pour les travailleurs. Il n’est pas toujours nécessaire de créer des taux pour les types de paie dans le module Pointage. Ces informations sont peut-être déjà présentes dans le système de paie utilisé pour générer les salaires.  
7. Cliquez sur Nouveau.
8. Dans la liste, marquez la ligne sélectionnée.
9. Entrez un nombre dans le champ Taux.
10. Cliquez sur Enregistrer.

## <a name="create-a-pay-agreement"></a>Création d’un accord salarial
1. Fermez la page.
2. Fermez la page.
3. Allez dans Accords salariaux.
    * Pointage > Paramétrage > Accords salariaux  
4. Cliquez sur Nouveau.
5. Tapez une valeur dans le champ Accord salarial.
6. Dans le champ Description, entrez une valeur.
7. Cliquez sur Enregistrer.
8. Cliquez sur Lignes d’accord.
9. Cliquez sur Nouveau.
10. Dans la liste, marquez la ligne sélectionnée.
11. Saisissez ou sélectionnez une valeur dans le champ Type de profil.
12. Saisissez ou sélectionnez une valeur dans le champ Type de paie.

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a>Paramétrer un accord salarial pour le collaborateur qualifié pour l’enregistrement des heures
1. Fermez la page.
2. Fermez la page.
3. Allez dans Enregistrement du temps des collaborateurs.
    * Pointage > Paramétrage > Enregistrement du temps des collaborateurs  
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Cliquez sur l’onglet Emploi.
6. Développez la section Enregistrement du temps.
7. Cliquez sur Modifier.
8. Saisissez ou sélectionnez une valeur dans le champ Accord salarial.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]