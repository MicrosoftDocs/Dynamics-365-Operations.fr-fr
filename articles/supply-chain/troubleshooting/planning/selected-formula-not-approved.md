---
title: Le numéro de formule sélectionné n’est pas approuvé pour un lot de commandes
description: Lorsque vous essayez de confirmer une commande planifiée, vous recevez un message d’erreur indiquant que le numéro de formule sélectionné n’est pas approuvé pour un lot de commandes.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294070"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a>Le numéro de formule sélectionné n’est pas approuvé pour un lot de commandes

Code d’erreur : PRO2614

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une commande planifiée, vous recevez le message d’erreur suivant :

> Le numéro de formule sélectionné n’est pas approuvé pour un lot de production.

## <a name="cause"></a>Cause

Le système valide l’opération de confirmation pour s’assurer qu’une formule approuvée est disponible pour l’article actif. Vous devez probablement approuver la formule.

## <a name="resolution"></a>Résolution

Pour approuver une formule, procédez comme suit.

1. Accédez à **Gestion des informations sur les produits \> Nomenclatures et formules \> Formules**.
1. Sélectionnez la formule appropriée.
1. Dans le volet Actions, sous l’onglet **Formule**, dans le groupe **Tenir à jour**, sélectionnez **Approuver la formule**.
1. Dans la boîte de dialogue **Approuver une nomenclature ou une formule**, sélectionnez un approbateur, puis sélectionnez **OK**.
