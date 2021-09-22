---
title: Erreur lors du nouvel envoi d‘une commande fournisseur à un flux de travail après une modification
description: Erreur lors du nouvel envoi d‘une commande fournisseur à un flux de travail après une modification
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4b8465d198c440f27a4b3cc4268445e0aa450f5b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476383"
---
# <a name="error-on-resubmitting-a-purchase-order-to-a-workflow-after-a-change"></a>Erreur lors du nouvel envoi d‘une commande fournisseur à un flux de travail après une modification


## <a name="symptoms"></a>Symptômes

L’erreur suivante se produit dans le workflow lorsqu’une commande fournisseur est soumise à nouveau après une modification :

> Bloqué (erreur) : X ++ Exception : les modifications de la commande fournisseur PO0000569 ne sont autorisées que dans l’état Brouillon lorsque la gestion des modifications est activée sur<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

Ce problème se produit uniquement si la commande fournisseur était dans un état *Confirmé* avant la demande des modifications. Si vous demandez des modifications alors que la commande fournisseur est dans un état *Approuvé*, le flux de travail peut être traité avec succès.

## <a name="resolution"></a>Résolution

Ce problème peut se produire en raison d’une incohérence dans les répartitions des commandes fournisseur.

Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l’état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**. Pour plus d’informations, consultez l’article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

Le problème sera résolu via [cet article de la Base de connaissances Microsoft (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).
