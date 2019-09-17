---
title: L'utilisateur peut accéder à Core HR mais pas à l'application Onboard ou Attract
description: Cette rubrique explique comment résoudre le problème où un utilisateur peut accéder à Dynamics 365 for Talent Core HR, mais ne peut pas accéder à l'application Attract ou Onboard.
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
ms.openlocfilehash: 6fc27a4c137fef2f8d204d90366c316389da08e6
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741713"
---
# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a><span data-ttu-id="e0eec-103">L'utilisateur peut accéder à Core HR mais pas à l'application Onboard ou Attract</span><span class="sxs-lookup"><span data-stu-id="e0eec-103">User can access Core HR but not the Onboard or Attract app</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e0eec-104">**Détails de l'environnement**</span><span class="sxs-lookup"><span data-stu-id="e0eec-104">**Environment details**</span></span>

- <span data-ttu-id="e0eec-105">Le déploiement de Microsoft Dynamics Lifecycle Services (LCS) a été effectué par l'utilisateur A.</span><span class="sxs-lookup"><span data-stu-id="e0eec-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="e0eec-106">L'utilisateur A a ajouté l'utilisateur B comme utilisateur de Microsoft Dynamics 365 for Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="e0eec-106">User A added user B as a user to Microsoft Dynamics 365 for Talent Core HR.</span></span>

<span data-ttu-id="e0eec-107">**Problème**</span><span class="sxs-lookup"><span data-stu-id="e0eec-107">**Issue**</span></span>

<span data-ttu-id="e0eec-108">L'utilisateur B peut accéder à Core HR, mais ne peut pas accéder à l'application Talent: Attract ou Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="e0eec-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="e0eec-109">Lorsque l'utilisateur essaie d'accéder à **Applications d'expérience**, il est dirigé vers un environnement de test à la place.</span><span class="sxs-lookup"><span data-stu-id="e0eec-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="e0eec-110">**Solution**</span><span class="sxs-lookup"><span data-stu-id="e0eec-110">**Solution**</span></span>

<span data-ttu-id="e0eec-111">L'utilisateur B doit se voir octroyer les droits d'afficher l'environnement Microsoft PowerApps que l'utilisateur A a créé lors du processus de mise en service.</span><span class="sxs-lookup"><span data-stu-id="e0eec-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="e0eec-112">Pour plus d'informations, voir la section « Octroi d'accès à l'environnement » dans [Mise en service de Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="e0eec-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="e0eec-113">**Solution à long terme**</span><span class="sxs-lookup"><span data-stu-id="e0eec-113">**Long-term solution**</span></span>

<span data-ttu-id="e0eec-114">Microsoft envisage d'affecter automatiquement les droits appropriés à Onboard et Attract lorsqu'un utilisateur est ajouté à Core HR.</span><span class="sxs-lookup"><span data-stu-id="e0eec-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
