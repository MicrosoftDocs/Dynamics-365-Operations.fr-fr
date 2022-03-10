---
title: Les paramètres du plan directeur n’existent pas
description: Lorsque vous essayez de confirmer une commande planifiée, vous recevez un message d’erreur indiquant qu’aucun paramètre n’existe pour le plan directeur.
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
ms.openlocfilehash: d039b79684f87e7791fb9dae7cbdc6ced220bc092d9a0ab624616c1c345986da
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756773"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a>Les paramètres du plan directeur n’existent pas

Code d’erreur : SYS25368

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une commande planifiée, vous recevez le message d’erreur suivant :

> Absence de paramètres pour le plan général %1.

## <a name="cause"></a>Cause

En raison de problèmes de configuration, le système ne peut pas trouver les paramètres du plan spécifié.

## <a name="resolution"></a>Résolution

- Accédez à **Plan directeur \> Paramétrage \> Plans \> Plans directeurs** et assurez-vous qu’un plan portant le nom spécifié existe.
