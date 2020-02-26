---
title: Traitez les modifications de taux
description: Traitez les modifications de taux de prestations dans Microsoft Dynamics 365 Human Resources lorsqu'un régime d'avantages sociaux nouveau ou existant a changé et que les paramètres des règles d'admissibilité doivent être actualisés.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 9ebe5cfc2bdf7790770d27ece2dc67f7677db593
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008973"
---
# <a name="process-rate-changes"></a>Traitez les modifications de taux

[!include [banner](includes/preview-feature.md)]

Traitez les modifications de taux de prestations dans Microsoft Dynamics 365 Human Resources lorsqu'un régime d'avantages sociaux nouveau ou existant a changé et que les paramètres des règles d'admissibilité doivent être actualisés. Si une nouvelle règle d'éligibilité est créée et affectée au plan, le système réexécute l'admissibilité des collaborateurs pour vérifier s'ils sont toujours éligibles au plan en fonction des nouvelles options d'éligibilité. 

1. Dans l'espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Traitement d'un changement de taux**.

2. Dans la boîte de dialogue **Exécuter le processus de changement de taux d'avantages**, spécifiez des valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | Période d'inscription | La période d'inscription pour traiter les modifications de taux. |

3. Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l'arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus s'exécutera avec les paramètres que vous définissez.

4. Cliquez sur **OK**.
