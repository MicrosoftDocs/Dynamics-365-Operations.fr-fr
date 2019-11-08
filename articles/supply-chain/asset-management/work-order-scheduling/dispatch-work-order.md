---
title: Répartir un ordre de travail
description: Cette rubrique explique comment répartir un ordre de travail dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 026b34934d6527416a4632d8e1aee76a8836dcb0
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652009"
---
# <a name="dispatch-work-order"></a>Répartir un ordre de travail

[!include [banner](../../includes/banner.md)]

 

Vous pouvez planifier un ordre de travail ou des tâches d'un ordre de travail pour un collaborateur à l'aide de la fonctionnalité **Répartir**.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail dans la liste.

3. Sous l'onglet **Général**, cliquez sur **Répartir**.

4. Dans la boîte de dialogue **Planifier un ordre de travail**, sélectionnez le collaborateur dans le champ **Collaborateur**.

5. Dans le champ **Planifier les heures**, vous pouvez insérer des heures de travail prévues si jamais elles différent des heures de la prévision.

6. Dans le champ **Début prévu**, vous pouvez modifier la date et l'heure de début, si nécessaire.

7. Si le processus de planification doit respecter des limites de capacité pour les ressources déjà planifiées avec d'autres tâches, assurez-vous que les boutons à bascule **Actif**, **Outil** et **Collaborateur** sont définis sur **Oui**. Si vous souhaitez afficher des informations détaillées sur le processus de planification, sélectionnez **Oui** sur le bouton à bascule **Détaillé**. Cela signifie que des informations détaillées sur les scores calculés sur l'ordre de travail sont affichées dans la fenêtre infos.

8. Sélectionnez **Oui** sur le bouton à bascule **Ignorer la planification** pour ignorer les jours fermés dans le calendrier (s'applique à l'actif, au collaborateur et aux outils). Sélectionnez **Oui** sur le bouton à bascule **Ignore l'exécution planifiée** pour ignorer les limitations qui peuvent avoir été sélectionnées sur l'ordre de travail concernant la planification. 

    Pour obtenir des informations sur le paramétrage de l'exécution prévue, reportez à la section [Exécution prévue](../setup-for-work-orders/scheduled-execution.md).

9. Cliquez sur **OK**. L'état du cycle de vie du bon de travail est automatiquement mis à jour dans l'état du cycle de vie **Planifié** spécifié dans **Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Modèles de cycle de vie**.

L'illustration suivante présente un exemple de sélection d'expédition dans la boîte de dialogue **Planifier un ordre de travail**.

![Figure 1](media/04-work-order-scheduling.png)

[!NOTE]
Si vous souhaitez supprimer le programme sur un ordre de travail, sélectionnez ce dernier dans **Tous les ordres de travail**, puis cliquez sur **Supprimer programme** dans l'onglet **Général**. N'oubliez pas de mettre à jour manuellement l'état du cycle de vie de l'ordre de travail si vous supprimez le programme.

