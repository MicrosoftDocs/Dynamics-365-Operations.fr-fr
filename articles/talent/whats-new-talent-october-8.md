---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (1 octobre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 92eb1508905309294e17b770829b1c5a22be1316
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304409"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-8-2018"></a>Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (8 octobre 2018)

[!include [banner](includes/banner.md)]

**Version 8.1.1050.0**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.

## <a name="allow-other-dates-to-be-used-on-leave-tier-basis-leave-management"></a>Autoriser l'utilisation d'autres dates sur la base de niveau de congé (Gestion des congés)

Lors de l'attribuant de congés aux employés, la base de niveau de prime détermine le nombre d'heures de congés qu'un employé régularise. Actuellement, ces niveaux dépendent de la date de début de l'employé et de sa date d'ancienneté. Dans certains cas, les organisations ont besoin que ces niveaux soient basés sur d'autres dates, telles que la date d'anniversaire ou la date d'embauche d'origine. Ces dates sont déjà utilisées sur le plan de congé pour déterminer si les régularisations ont lieu, la capacité pour ces mêmes dates d'être utilisées lorsqu'un employé est inscrit dans un plan ont été ajoutés pour déterminer le montant de régularisation. 

## <a name="other-changes"></a>Autres modifications
Divers correctifs ont été inclus dans cette version.

## <a name="known-issue"></a>Problème connu

**Problème** : lors de l'ajout d'une nouvelle pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés. **Solution de contournement** : avant d'ouvrir la page de la pièce jointe, vérifiez que les récapitulatifs de la page **Collaborateur** sont fermés. Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons de pièces jointes sont activés. (Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)
