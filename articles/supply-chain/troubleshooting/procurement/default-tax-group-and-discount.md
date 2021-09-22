---
title: Le groupe de taxes et l'escompte de règlement par défaut ne sont pas renseignés à partir du compte de facturation
description: Un groupe de taxes par défaut et un escompte de règlement par défaut ne sont pas renseignés à partir du compte de facturation
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
ms.openlocfilehash: bb984eb17209dc92e336df5ad475bb0f70c6e35c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476329"
---
# <a name="default-tax-group-and-cash-discount-arent-filled-in-from-the-invoice-account"></a>Le groupe de taxes et l'escompte de règlement par défaut ne sont pas renseignés à partir du compte de facturation

## <a name="symptoms"></a>Symptômes

Si vous utilisez un compte de facturation différent du compte client, un groupe de taxes par défaut et un escompte de règlement par défaut ne sont pas renseignés à partir du compte de facturation lors de la création d’une commande fournisseur.

## <a name="resolution"></a>Résolution

Ce comportement est fait exprès. Les valeurs par défaut du groupe de taxes, des escomptes de règlement et d’autres informations sur les prix sont basées sur le compte client et non sur le compte de facturation.
