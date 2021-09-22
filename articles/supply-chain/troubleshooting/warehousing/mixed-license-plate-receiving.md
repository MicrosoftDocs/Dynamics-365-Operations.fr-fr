---
title: La réception de contenant mixte ne fonctionne pour aucun code de disposition
description: Quand le champ Action d’un code de disposition est défini sur Crédit ou Rebut, vous ne pouvez utiliser que l’élément de menu Réception de contenant mixte pour traiter les éléments retournés.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b762255bc5ef6a1e15688a9c635940e92e67db3c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476361"
---
# <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-but-credit"></a>La réception de contenant mixte ne fonctionne pour aucun code de disposition, sauf Crédit

## <a name="symptoms"></a>Symptômes

Quand le champ **Action** d’un code de disposition est défini sur *Crédit* ou *Rebut*, vous ne pouvez utiliser que l’élément de menu [Réception de contenant mixte](/dynamics365/supply-chain/warehousing/mixed-license-plate-receiving) pour traiter les éléments retournés.

## <a name="resolution"></a>Résolution

Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité. Actuellement, seuls les [codes de disposition](/dynamics365/supply-chain/service-management/set-up-disposition-codes) où le champ **Action** est défini sur *Crédit* ou *Rebut* sont pris en charge pour la réception de contenants mixtes.
