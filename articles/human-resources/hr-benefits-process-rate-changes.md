---
title: Traiter les modifications de taux
description: Cette rubrique explique comment traiter les modifications de taux d’avantages dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e0dfbdde8ee950a0341fffb1e268fff05434953
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070373"
---
# <a name="process-rate-changes"></a>Traiter les modifications de taux


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique explique comment traiter les modifications de taux d’avantages dans Microsoft Dynamics 365 Human Resources lorsque des paramètres de règles d’éligibilité ont changé dans un plan d’avantages nouveau ou existant. Si une nouvelle règle d’éligibilité est créée et affectée au plan, le système réexécute l’admissibilité des collaborateurs pour vérifier s’ils sont toujours éligibles au plan en fonction des nouvelles options d’éligibilité. 

1. Dans l’espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Traitement d’un changement de taux**.

2. Dans la boîte de dialogue **Exécuter le processus de changement de taux d’avantages**, spécifiez des valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Période d’inscription** | La période d’inscription pour traiter les modifications de taux. |

3. Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l’arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus s’exécutera avec les paramètres que vous définissez.

4. Cliquez sur **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
