---
title: Enregistrement d'absence dans le module Pointage
description: Cette rubrique explique comment traiter les enregistrements d'absence dans le module Pointage.
author: johanhoffmann
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JMGParameters, JmgAbsenceCalendar
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 12a61f23ac5a16000275e53d3901c8aea202bab0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966628"
---
# <a name="absence-registration-in-time-and-attendance"></a>Enregistrement d'absence dans le module Pointage

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les concepts de l'absence et explique la gestion des absences dans le module Pointage.

## <a name="absence-that-is-based-on-regular-work-hours"></a>Une absence basée sur les heures de travail normales

Les travailleurs sont considérés absents pour toutes les heures non travaillées pendant leurs heures de travail normales. Les heures de travail normales sont définies dans le profil de temps standard d'un travailleur.

Par exemple, un travailleur travaille pendant un profil de jour avec pointage à l'arrivée à 7 h 00 et pointage à la sortie à 15 h 00. Si le travailleur pointe à l'arrivée à 9 h 00, il est considéré comme absent de 7 h 00 à 9 h 00 ce jour-là.

Dans ce cas, les travailleurs sont invités à entrer un motif pour leur absence. Ils peuvent indiquer un motif en sélectionnant un code absence.

## <a name="absence-codes"></a>Codes absence

Les codes d'absence définissent les différents types d'absences. Les codes d'absence sont définis par la société.

Plusieurs règles peuvent être appliquées aux codes d'absence. Par exemple, le code d'absence peut être configuré pour déduire ou accorder le salaire.

Par exemple, une société définit un code absence **En retard** que les travailleurs utilisent s'ils arrivent tard sans avoir un bon motif. La société définit également le code d'absence en **Cours interne** que les travailleurs utilisent pour le temps passé à suivre des cours internes. Ces codes d'absence peut être paramétrés pour que le code **En retard** déduise du salaire d'un travailleur mais que le code **Cours interne** ne déduise rien du salaire d'un travailleur.

Vous pouvez paramétrer des codes d'absence automatiques. Ces codes d'absence peuvent servir à calculer le temps d'un travailleur lorsqu'aucune absence n'est enregistrée. Le profil de temps du travailleur détermine si le code d'absence pour le temps standard ou des heures flexibles est utilisé.

### <a name="set-up-standard-time-and-flex-time"></a>Paramétrer le temps standard et les heures flexibles

- Configurez les paramètres du temps standard et des heures flexibles à l'aide des options **Insertion auto. absence** et **Insertion auto. flex-** sur la page **Paramètres de pointage**.

## <a name="absence-groups"></a>Groupes d'absence

Les codes d'absences sont regroupés en groupes d'absence. Vous utilisez les groupes d'absence pour regrouper les codes absence ayant des caractéristiques communes. Cela comprend, par exemple, les codes absence d'une absence légale, ou une absence due à un rendez-vous chez un médecin, à une participation à un jury ou à un enfant malade.

## <a name="planned-absence"></a>Absence prévue

Si vous savez qu'un travailleur est absent pour une période donnée, telle qu'un congé à venir, vous pouvez utiliser l'absence prévue. Vous paramétrez l'absence prévue en configurant le code d'absence afin qu'il tienne compte de l'absence prévue. Lorsque vous paramétrez une absence prévue, vous n'êtes pas invité à entrer de code d'absence pendant la période d'absence pour laquelle les enregistrements des heures de l'utilisateur sont calculés. L'absence prévue peut être définie pour un travailleur unique, ou vous pouvez définir un traitement par lots pour mettre à jour en bloc l'absence prévue des travailleurs.

### <a name="set-up-planned-absence"></a>Paramétrer l'absence prévue

1. Sélectionnez **Ressources humaines** &gt; **Travailleurs** &gt; **Employés**, puis sélectionnez un employé.
2. Sélectionnez **Heure** &gt; **Affectations d'heures** &gt; **Enregistrement d'absence de temps**, puis paramétrez l'absence prévue.

## <a name="interrupted-planned-absence"></a>Absence prévue interrompue

Si vous appliquez l'option **Interrompre** lorsque vous paramétrez une absence prévue, celle-ci est interrompue si le travailleur pointe à l'arrivée pendant la période d'absence prévue. L'absence prévue est marquée comme **Interrompue** et n'a aucun effet sur les futurs calculs.

### <a name="set-up-a-planned-absence-for-interruption"></a>Paramétrage de l'interruption d'une absence prévue

1. Ouvrez la page **Enregistrement d'absence de temps** comme décrit dans la procédure pour paramétrer l'absence prévue.
2. Sélectionnez **Interrompre**.

L'option **Interrompre** s'applique lorsque le temps est enregistré via le terminal ou le périphérique d'atelier. L'option ne s'applique pas si les enregistrements sont entrés sur les pages de calcul et d'approbation, ou sur la page **Carte de pointage électronique**.

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a>Exemples de l'utilisation de l'absence dans un profil flexible

Les trois exemples suivants présentent le calcul de l'absence dans un profil composé d'heures flexibles.

Les exemples utilisent le profil suivant.

| Pointage à l'arrivée | Durée standard    | Rupture             | Durée standard | Flex-        | Pointage à la sortie | Flex+        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| 8 h 00     | 9 h 00 à 11 h 30 | 11 h 30 à 12 h 00 | 12 h 00 à 15 h 00 | 15 h 00 à 16 h 00 | 16 h 00      | 16 h 00 à 18 h 00 |

### <a name="example-1-signing-out-during-a-flex--period"></a>Exemple 1 : Pointage à la sortie durant une période Flex-

Le travailleur pointe à l'arrivée à 8 h 00, puis à la sortie à 15 h 30. Dans ce cas, du fait que le travailleur pointe durant une période Flex-, aucune absence n'est calculée, et une demi-heure est déduite du solde flexible du travailleur.

### <a name="example-2-signing-out-in-during-standard-time-period"></a>Exemple 2 : Pointage à l'arrivée au cours d'une période de durée standard

Le travailleur pointe à l'arrivée à 8 h 00, puis à la sortie à 14 h 30. Dans ce cas, du fait que le travailleur pointe pendant la période de durée standard, l'absence est calculée de 14 h 30 à 16 h 00, et une période d'absence de 1,5 heure est enregistrée. Le code d'absence pour cette période est obligatoire.

### <a name="example-3-signing-out-during-a-flex-period"></a>Exemple 3 : Pointage à la sortie durant une période Flex+

Le travailleur pointe à l'arrivée à 8 h 00, puis à la sortie à 16 h 30. Dans ce cas, du fait que le travailleur pointe durant une période Flex+, aucune absence n'est calculée, et une demi-heure est ajoutée au solde flexible du travailleur.

## <a name="absence-in-the-calculation-and-approval-process"></a>Absence dans le calcul et processus d'approbation

Les enregistrements des heures des travailleurs doivent être calculés et approuvés avant d'être transférés vers un système de paie en tant qu'articles de salaire.

Un approbateur peut modifier les enregistrements des heures d'un travailleur. L'approbateur peut même modifier n'importe absence enregistrée par le travailleur. Si l'approbateur entre manuellement une période de temps avec le code d'absence, le code d'absence de cette période n'est pas remplacé par le code d'absence par défaut des paramètres de pointage.

Par exemple, une travailleuse pointe à l'arrivée à 10 h 00 et sélectionne un code d'absence qui indique qu'elle est en retard. Ensuite, elle signale à son superviseur qu'elle avait rendez-vous chez un médecin de 8 h 00 à 10 h 00. Le rendez-vous chez un médecin ne doit pas entraîner de retenue salariale pour la travailleuse. Par conséquent, dans ce cas, le superviseur peut ajuster les deux heures d'absence de 8 h 00 à 10 h 00 en entrant manuellement le code d'absence indiquant une maladie pendant ces deux heures.

### <a name="calculate-and-approve-absence"></a>Calcul et approbation des absences

- Sélectionnez **Pointage** &gt; **Révision et approbation** &gt; **Approbation ou calcul**.
