---
title: L'erreur « Référence d'objet non définie » se produit lors de la confirmation de la commande fournisseur
description: L'erreur « Référence d'objet non définie » se produit lors de la confirmation de la commande fournisseur
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
ms.openlocfilehash: 78e5e365f7197c1a0c25bf6eb63bcd5bd0f482ed
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476357"
---
# <a name="error-object-reference-not-set-occurs-during-purchase-order-confirmation"></a>L'erreur « Référence d'objet non définie » se produit lors de la confirmation de la commande fournisseur

## <a name="symptoms"></a>Symptômes

Vous recevez l'exception suivante lors de la confirmation d'une commande fournisseur :

> Référence d'objet non définie

## <a name="cause"></a>Cause

Ce problème peut se produire en raison d’une incohérence dans les répartitions des commandes fournisseur.

## <a name="resolution"></a>Résolution

Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l’état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**. Pour plus d’informations, consultez l’article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
