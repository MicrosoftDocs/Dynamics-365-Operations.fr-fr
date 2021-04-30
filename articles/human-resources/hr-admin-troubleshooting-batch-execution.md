---
title: Réinitialiser les traitements par lots bloqués
description: Cette rubrique explique comment résoudre les problèmes liés aux traitements par lots bloqués.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 906a391b3c28d15445f6ddf0fc547ebcf842ba19
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881758"
---
# <a name="reset-stuck-batch-jobs"></a>Réinitialiser les traitements par lots bloqués

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Sortie

Microsoft Dynamics 365 Human Resources peut rencontrer des problèmes avec des traitements par lots bloqués dans un état **Exécution** ou **Annulation** et qui n’aboutissent pas.

## <a name="resolution"></a>Résolution

Lorsqu’un traitement par lots est bloqué dans un état **Exécution** ou **Annulation**, vous pouvez réinitialiser le statut en forçant l’annulation de la tâche. Une fois que vous l’avez annulé, vous pouvez réinitialiser le traitement par lots en le définissant sur un statut **En attente**. Il sera ensuite repris pour exécution lors de la prochaine exécution planifiée de traitement par lots.

1. Dans l’espace de travail **Administration système**, sélectionnez la page **Liens** et sélectionnez **Traitements par lots**.

2. Sur la page de liste **Traitement par lots**, sélectionnez la tâche à réinitialiser.

3. Sur le ruban d’action, sélectionnez **Forcer l’annulation** et confirmez l’action.

   > [!NOTE]
   > L’action **Forcer l’annulation** n’est disponible que lorsque le traitement par lots sélectionné a un statut **Exécution** ou **Annulation** et qu’aucun processus d’exécution ou d’annulation de traitement par lots n’est en cours d’exécution pour la tâche.

4. Sur le ruban d’action, sélectionnez **Modifier le statut**.

5. Sur la page **Sélectionner un nouveau statut**, sélectionnez **En attente**, puis sélectionnez **OK**.

   ![Sélectionner un nouveau statut de traitement par lots](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>Voir également :

[Optimiser les performances en planifiant des traitements par lots en dehors des heures d’ouverture](hr-admin-troubleshooting-batch-jobs.md)<br>
[Optimiser les performances grâce aux tâches automatiques de nettoyage](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
