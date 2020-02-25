---
title: L'utilisateur peut accéder à Ressources humaines mais pas à Onboard ou Attract
description: 'Cette rubrique explique comment résoudre le problème suivant : un utilisateur peut accéder à Microsoft Dynamics 365 Talent - Ressources humaines mais pas à Attract ou Onboard.'
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
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006308"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a><span data-ttu-id="7abdc-103">L'utilisateur peut accéder à Ressources humaines mais pas à Onboard ou Attract</span><span class="sxs-lookup"><span data-stu-id="7abdc-103">User can access Human Resources but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7abdc-104">**Détails de l'environnement**</span><span class="sxs-lookup"><span data-stu-id="7abdc-104">**Environment details**</span></span>

- <span data-ttu-id="7abdc-105">Le déploiement de Microsoft Dynamics Lifecycle Services (LCS) a été effectué par l'utilisateur A.</span><span class="sxs-lookup"><span data-stu-id="7abdc-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="7abdc-106">L'utilisateur A a ajouté l'utilisateur B comme utilisateur de Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7abdc-106">User A added user B as a user to Microsoft Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="7abdc-107">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7abdc-107">**Issue**</span></span>

<span data-ttu-id="7abdc-108">L'utilisateur B peut accéder à Ressources humaines mais ne peut pas accéder à l'application Talent - Attract ou à l'application Talent - Onboard.</span><span class="sxs-lookup"><span data-stu-id="7abdc-108">User B can access Human Resources, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="7abdc-109">Lorsque l'utilisateur essaie d'accéder à **Applications d'expérience**, il est dirigé vers un environnement de test à la place.</span><span class="sxs-lookup"><span data-stu-id="7abdc-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="7abdc-110">**Solution**</span><span class="sxs-lookup"><span data-stu-id="7abdc-110">**Solution**</span></span>

<span data-ttu-id="7abdc-111">L'utilisateur B doit se voir octroyer les droits d'afficher l'environnement Microsoft Power Apps que l'utilisateur A a créé lors du processus de mise en service.</span><span class="sxs-lookup"><span data-stu-id="7abdc-111">User B must be assigned the rights to view the Microsoft Power Apps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="7abdc-112">Pour plus d'informations, voir la section « Octroi d'accès à l'environnement » dans [Mise en service de Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="7abdc-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="7abdc-113">**Solution à long terme**</span><span class="sxs-lookup"><span data-stu-id="7abdc-113">**Long-term solution**</span></span>

<span data-ttu-id="7abdc-114">Microsoft envisage d'affecter automatiquement les droits appropriés vers Onboard et Attract lorsqu'un utilisateur est ajouté à Ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="7abdc-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Human Resources.</span></span>
