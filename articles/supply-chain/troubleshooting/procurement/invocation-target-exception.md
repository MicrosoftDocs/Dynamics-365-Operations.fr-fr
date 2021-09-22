---
title: Une exception se produit lors de la validation de la facture fournisseur
description: Une exception « Une exception a été levée par la cible d'un appel » se produit lors de la validation de la facture fournisseur.
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
ms.openlocfilehash: ecc63cb7d0d2392105d8e4290f8e837945ae0781
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476332"
---
# <a name="an-exception-occurs-during-vendor-invoice-posting"></a>Une exception se produit lors de la validation de la facture fournisseur


## <a name="symptoms"></a>Symptômes

Vous recevez l'exception suivante lors de la validation d'une facture fournisseur :

> Une exception a été levée par la cible d'un appel

## <a name="cause"></a>Cause

Ce problème peut se produire en raison d’une incohérence dans les répartitions des commandes fournisseur.

## <a name="resolution"></a>Résolution

Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l’état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**. Pour plus d’informations, consultez l’article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
