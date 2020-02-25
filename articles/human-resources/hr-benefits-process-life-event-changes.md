---
title: Traitement des changements d'événement de vie
description: Traitez les changements d'événements de vie dans Microsoft Dynamics 365 Human Resources pour les changements d'événements de vie.
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
ms.openlocfilehash: f9bce9394a361bbecfcc0531c5d7ebe9302c8f11
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009027"
---
# <a name="process-life-event-changes"></a>Traitement des changements d'événement de vie

[!include [banner](includes/preview-feature.md)]

Traitez les changements d'événements de vie dans Microsoft Dynamics 365 Human Resources pour deux changements d'événements de vie :

- Changements d'anniversaire
- Changements d'expiration de remplacement de règle d'éligibilité 

1. Dans l'espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Traitement de modification des événements de vie**.

2. Dans la boîte de dialogue **Exécuter le processus des modifications d'événement de vie**, spécifiez des valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | Période d'inscription | Période d'inscription pour laquelle traiter les modifications d'événement de vie. |
   | Entité juridique | Entité juridique pour laquelle traiter les modifications d'événement de vie. |

3. Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l'arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus s'exécutera avec les paramètres que vous définissez.

4. Cliquez sur **OK**.
