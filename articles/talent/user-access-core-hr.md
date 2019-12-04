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
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a><span data-ttu-id="82254-103">L'utilisateur peut accéder à Core HR, mais pas à Onboard ou Attract</span><span class="sxs-lookup"><span data-stu-id="82254-103">User can access Core HR but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="82254-104">**Détails de l'environnement**</span><span class="sxs-lookup"><span data-stu-id="82254-104">**Environment details**</span></span>

- <span data-ttu-id="82254-105">Le déploiement de Microsoft Dynamics Lifecycle Services (LCS) a été effectué par l'utilisateur A.</span><span class="sxs-lookup"><span data-stu-id="82254-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="82254-106">L'utilisateur A a ajouté l'utilisateur B comme utilisateur de Microsoft Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="82254-106">User A added user B as a user to Microsoft Dynamics 365 Talent: Core HR.</span></span>

<span data-ttu-id="82254-107">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="82254-107">**Issue**</span></span>

<span data-ttu-id="82254-108">L'utilisateur B peut accéder à Core HR, mais ne peut pas accéder à l'application Talent: Attract ou Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="82254-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="82254-109">Lorsque l'utilisateur essaie d'accéder à **Applications d'expérience**, il est dirigé vers un environnement de test à la place.</span><span class="sxs-lookup"><span data-stu-id="82254-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="82254-110">**Solution**</span><span class="sxs-lookup"><span data-stu-id="82254-110">**Solution**</span></span>

<span data-ttu-id="82254-111">L'utilisateur B doit se voir octroyer les droits d'afficher l'environnement Microsoft Power Apps que l'utilisateur A a créé lors du processus de mise en service.</span><span class="sxs-lookup"><span data-stu-id="82254-111">User B must be assigned the rights to view the Microsoft Power Apps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="82254-112">Pour plus d'informations, voir la section « Octroi d'accès à l'environnement » dans [Mise en service de Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="82254-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="82254-113">**Solution à long terme**</span><span class="sxs-lookup"><span data-stu-id="82254-113">**Long-term solution**</span></span>

<span data-ttu-id="82254-114">Microsoft envisage d'affecter automatiquement les droits appropriés à Onboard et Attract lorsqu'un utilisateur est ajouté à Core HR.</span><span class="sxs-lookup"><span data-stu-id="82254-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
