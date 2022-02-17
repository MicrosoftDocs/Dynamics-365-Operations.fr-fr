---
title: Traiter les modifications des événements de vie
description: Cette rubrique explique comment traiter les modifications des événements de vie dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb894d9886c095d760efe66abcf773a975a99caa
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067602"
---
# <a name="process-life-event-changes"></a>Traiter les modifications des événements de vie


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
