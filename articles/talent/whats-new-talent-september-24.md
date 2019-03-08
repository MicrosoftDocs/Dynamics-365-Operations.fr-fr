---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (24 septembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/21/2018
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
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: aeb75fe4c775b9003c6429de536498f495224098
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304379"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-24-2018"></a>Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (24 septembre 2018)

[!include [banner](includes/banner.md)]

**Version 8.1.1015.0**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.

## <a name="currency-added-to-benefits"></a>Devise ajoutée aux avantages

Les plans d'avantages ont été mis à jour pour inclure la devise de l'avantage. Ce nouveau champ est également disponible dans la page Avantages inscrits du collaborateur. Ce nouveau champ fait partie des privilèges de sécurité pour Tenir à jour les avantages et Afficher la liste des avantages.

## <a name="update-proration-process--leave-and-absence"></a>Mettre à jour le processus de calcul au prorata – Congé et absence

Les organisations accordent des congés différemment selon la date à laquelle les employés entrent ou quittent la société. Pour les employés qui quittent l'organisation, certains doivent mettre fin à la prime à la date de résiliation du contrat, tandis que d'autres se basent sur le dernier jour travaillé pour arrêter le processus de régularisation. Ces modifications permettent aux organisations de choisir quand mettre fin à l'inscription pendant le processus de résiliation. Ces nouvelles options font partie des privilèges pour Mettre fin au contrat d'un collaborateur et Mettre un terme au contrat d'un collaborateur à partir du libre-service des responsables. 

## <a name="other-changes"></a>Autres modifications

Cette version contient plusieurs correctifs de bogue supplémentaires.

## <a name="known-issue"></a>Problème connu

-   **Problème** : lors de l'ajout d'une nouvelle pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés. **Solution de contournement** : avant d'ouvrir la page de la pièce jointe, vérifiez que les récapitulatifs de la page **Collaborateur** sont fermés. Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons des pièces jointes sont activés. (Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)
