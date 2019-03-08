---
title: L'utilisateur peut accéder à Core HR mais pas à l'application Onboard ou Attract
description: Cette rubrique explique comment résoudre le problème où un utilisateur peut accéder à Dynamics 365 for Talent Core HR, mais ne peut pas accéder à l'application Attract ou Onboard.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2e5d0b1bf993aec89c7d2c6d4916732f5824310d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304404"
---
# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a><span data-ttu-id="2d378-103">L'utilisateur peut accéder à Core HR mais pas à l'application Onboard ou Attract</span><span class="sxs-lookup"><span data-stu-id="2d378-103">User can access Core HR but not the Onboard or Attract app</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2d378-104">**Détails de l'environnement**</span><span class="sxs-lookup"><span data-stu-id="2d378-104">**Environment details**</span></span>

- <span data-ttu-id="2d378-105">Le déploiement de Microsoft Dynamics Lifecycle Services (LCS) a été effectué par l'utilisateur A.</span><span class="sxs-lookup"><span data-stu-id="2d378-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="2d378-106">L'utilisateur A a ajouté l'utilisateur B comme utilisateur de Microsoft Dynamics 365 for Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="2d378-106">User A added user B as a user to Microsoft Dynamics 365 for Talent Core HR.</span></span>

<span data-ttu-id="2d378-107">**Problème**</span><span class="sxs-lookup"><span data-stu-id="2d378-107">**Issue**</span></span>

<span data-ttu-id="2d378-108">L'utilisateur B peut accéder à Core HR, mais ne peut pas accéder à l'application Talent: Attract ou Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="2d378-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="2d378-109">Lorsque l'utilisateur essaie d'accéder à **Applications d'expérience**, il est dirigé vers un environnement de test à la place.</span><span class="sxs-lookup"><span data-stu-id="2d378-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="2d378-110">**Solution**</span><span class="sxs-lookup"><span data-stu-id="2d378-110">**Solution**</span></span>

<span data-ttu-id="2d378-111">L'utilisateur B doit se voir octroyer les droits d'afficher l'environnement Microsoft PowerApps que l'utilisateur A a créé lors du processus de mise en service.</span><span class="sxs-lookup"><span data-stu-id="2d378-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="2d378-112">Pour plus d'informations, voir la section « Octroi d'accès à l'environnement » dans [Mise en service de Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="2d378-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="2d378-113">**Solution à long terme**</span><span class="sxs-lookup"><span data-stu-id="2d378-113">**Long-term solution**</span></span>

<span data-ttu-id="2d378-114">Microsoft envisage d'affecter automatiquement les droits appropriés à Onboard et Attract lorsqu'un utilisateur est ajouté à Core HR.</span><span class="sxs-lookup"><span data-stu-id="2d378-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
