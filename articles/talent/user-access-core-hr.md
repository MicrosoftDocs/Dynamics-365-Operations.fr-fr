---
title: L'utilisateur peut accéder à Core HR, mais pas à Onboard ou Attract
description: Cette rubrique explique comment résoudre le problème que rencontre un utilisateur qui peut accéder à Microsoft Dynamics 365 Talent - Core HR, mais qui ne peut pas accéder à l'application Attract ou Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1a86936d756d8375761ce50c9d9bf33dc638dfad
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772917"
---
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a>L'utilisateur peut accéder à Core HR, mais pas à Onboard ou Attract

[!include [banner](includes/banner.md)]

**Détails de l'environnement**

- Le déploiement de Microsoft Dynamics Lifecycle Services (LCS) a été effectué par l'utilisateur A.
- L'utilisateur A a ajouté l'utilisateur B comme utilisateur de Microsoft Dynamics 365 Talent: Core HR.

**Sortie**

L'utilisateur B peut accéder à Core HR, mais ne peut pas accéder à l'application Talent: Attract ou Talent: Onboard. Lorsque l'utilisateur essaie d'accéder à **Applications d'expérience**, il est dirigé vers un environnement de test à la place.

**Solution**

L'utilisateur B doit se voir octroyer les droits d'afficher l'environnement Microsoft Power Apps que l'utilisateur A a créé lors du processus de mise en service.

Pour plus d'informations, voir la section « Octroi d'accès à l'environnement » dans [Mise en service de Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

**Solution à long terme**

Microsoft envisage d'affecter automatiquement les droits appropriés à Onboard et Attract lorsqu'un utilisateur est ajouté à Core HR.
