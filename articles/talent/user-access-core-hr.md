---
title: "L'utilisateur peut accéder à Core HR mais pas à l'application Onboard ou Attract"
description: "Cette rubrique explique comment résoudre le problème où un utilisateur peut accéder à Microsoft Dynamics 365 for Talent Core HR, mais ne peut pas accéder à l'application Attract ou Onboard."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2e5d0b1bf993aec89c7d2c6d4916732f5824310d
ms.contentlocale: fr-fr
ms.lasthandoff: 12/04/2018

---

# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a>L'utilisateur peut accéder à Core HR mais pas à l'application Onboard ou Attract

[!include [banner](includes/banner.md)]

**Détails de l'environnement**

- Le déploiement de Microsoft Dynamics Lifecycle Services (LCS) a été effectué par l'utilisateur A.
- L'utilisateur A a ajouté l'utilisateur B comme utilisateur de Microsoft Dynamics 365 for Talent Core HR.

**Problème**

L'utilisateur B peut accéder à Core HR, mais ne peut pas accéder à l'application Talent: Attract ou Talent: Onboard. Lorsque l'utilisateur essaie d'accéder à **Applications d'expérience**, il est dirigé vers un environnement de test à la place.

**Solution**

L'utilisateur B doit se voir octroyer les droits d'afficher l'environnement Microsoft PowerApps que l'utilisateur A a créé lors du processus de mise en service.

Pour plus d'informations, voir la section « Octroi d'accès à l'environnement » dans [Mise en service de Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

**Solution à long terme**

Microsoft envisage d'affecter automatiquement les droits appropriés à Onboard et Attract lorsqu'un utilisateur est ajouté à Core HR.
