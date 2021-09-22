---
title: Les répartitions comptables sont sur-réparties ou sous-réparties
description: Une ou plusieurs répartitions comptables sont sur-réparties ou sous-réparties.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 7ff0172469df50da9e4272b3fa3f75001a4eb7eb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476334"
---
# <a name="accounting-distributions-are-either-over--or-under-distributed"></a>Les répartitions comptables sont sur-réparties ou sous-réparties


## <a name="symptoms"></a>Symptômes

Vous recevez le message d’erreur suivant :

> Une ou plusieurs répartitions comptables sont sur-réparties ou sous-réparties

## <a name="cause"></a>Cause

Ce problème peut se produire en raison d’une incohérence dans les répartitions des commandes fournisseur.

## <a name="resolution"></a>Résolution

Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l’état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**. Pour plus d’informations, consultez l’article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
