---
title: Vous ne pouvez ajouter que le compte principal comme compte de crédit pour des raisons de rapprochement
description: Lorsque vous configurez un motif de rapprochement dans la gestion des transports, vous ne pouvez ajouter que le compte principal comme compte de crédit.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026493"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a>Vous ne pouvez ajouter que le compte principal comme compte de crédit pour des raisons de rapprochement

Numéro de la base de connaissances : 4603538

## <a name="symptoms"></a>Symptômes

Lorsque vous configurez un motif de rapprochement dans la gestion des transports, vous ne pouvez ajouter que le compte principal comme compte de crédit. Vous ne pouvez pas ajouter de centre de coûts ou toute autre dimension comme compte de crédit. Cependant, le compte de débit vous permet de sélectionner d'autres dimensions.

## <a name="resolution"></a>Résolution

Si le rapprochement n'est pas effectué pour payer le fournisseur mais pour créditer un compte principal spécifique, le système ne vous permet pas de sélectionner une dimension financière pour le compte de crédit lorsque vous configurez le motif de rapprochement.

Si la structure du compte nécessite une valeur de dimension financière spécifique pour le compte principal de crédit, le journal fournisseur résultant ne peut pas être validé automatiquement, car la valeur de dimension financière est manquante. Par conséquent, vous devez d'abord spécifier manuellement le compte de crédit en utilisant la page **Journal des factures**.

Étant donné qu'une valeur de dimension est requise pour le compte de crédit, le journal des factures fournisseur ne peut pas être automatiquement imputé. Vous devez le valider manuellement après avoir ajouté manuellement la valeur de dimension au compte principal pour la limite de crédit.
