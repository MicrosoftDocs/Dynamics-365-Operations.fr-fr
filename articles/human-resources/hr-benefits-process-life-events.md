---
title: Traitement des événements de vie
description: Pendant le cycle de vie des employés dans Microsoft Dynamics 365 Human Resources, chaque employé peut rencontrer divers changements d'événement de vie.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba8d21482a18c6baa93437fc65c165907bdb515d
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229925"
---
# <a name="process-life-events"></a>Traitement des événements de vie

Pendant le cycle de vie des employés dans Microsoft Dynamics 365 Human Resources, chaque employé peut rencontrer divers changements d'événement de vie. Par exemple, mariage, changement d'emploi ou changement de personne à charge / bénéficiaire. Pour utiliser des événements de vie, vous devez activer les événements de vie dans l'écran des paramètres d'avantages, configurer les types d'événements de vie et configurer les options d'événements de vie pour les types de plan.

Avant de pouvoir traiter des événements de vie, vous devez avoir déjà exécuté l'inscription ouverte au moins une fois au cours d'une période d'embauche. Aux États-Unis, l'inscription ouverte est généralement une fois par an. En dehors des États-Unis, l'inscription ouverte peut être exécutée au moment de l'embauche. Un collaborateur n'a pas besoin de sélectionner un régime d'avantages pour que les événements de vie soient traités, mais ils doivent avoir été inclus dans le processus d'inscription ouverte. 

Utilisez le traitement des événements de vie lorsque vous avez des collaborateurs dont les événements de vie ont lieu à une date ultérieure. Cet événement traitera tous les événements de vie qui n'ont pas été traités (comme les événements de vie futurs ou les événements de vie ajoutés qui ne sont pas spécifiques à un collaborateur - un exemple est un nouvel avantage). Les événements de vie en temps réel sont cachés.

Par exemple, si aujourd'hui est le 1er février et que le 14 février, le collaborateur Joe Smith doit changer d'entité juridique, si vous exécutez le traitement des événements de vie pour le 15 février, le système traite tous les événements jusqu'au 15 février. 

1. Dans l'espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Traitement des événements de vie**.

2. Dans la boîte de dialogue **Exécuter le processus d'événement de vie**, spécifiez des valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Période d'inscription** | Période d'inscription pour laquelle traiter les événements de vie. |
   | **Entité juridique** | Entité juridique pour laquelle traiter les événements de vie. |
   | **Date de l'événement de vie** | Le système traite tous les événements de la période d'inscription qui se produisent jusqu'à cette date. |
   | **Collaborateur** | Collaborateur pour lequel traiter les événements de vie. Si vous laissez ce champ vide, les événements de vie seront traités pour tous les collaborateurs. |

3. Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l'arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus s'exécutera avec les paramètres que vous définissez.

4. Cliquez sur **OK**.
