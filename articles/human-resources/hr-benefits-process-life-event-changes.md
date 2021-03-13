---
title: Traitement des changements d’événement de vie
description: Traitez les changements d’événements de vie dans Microsoft Dynamics 365 Human Resources pour les changements d’événements de vie.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d32d6ba893a99149e27f644ac80e430db3c08fa0
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112548"
---
# <a name="process-life-event-changes"></a>Traitement des changements d’événement de vie

Traitez les changements d’événements de vie dans Microsoft Dynamics 365 Human Resources pour deux changements d’événements de vie :

- Changements d’anniversaire
- Changements d’expiration de remplacement de règle d’éligibilité 

1. Dans l’espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Traitement de modification des événements de vie**.

2. Dans la boîte de dialogue **Exécuter le processus des modifications d’événement de vie**, spécifiez des valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | Période d’inscription | Période d’inscription pour laquelle traiter les modifications d’événement de vie. |
   | Entité juridique | Entité juridique pour laquelle traiter les modifications d’événement de vie. |

3. Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l’arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus s’exécutera avec les paramètres que vous définissez.

4. Cliquez sur **OK**.
