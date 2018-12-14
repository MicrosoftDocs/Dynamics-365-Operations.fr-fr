---
title: "Le client Talent se déconnecte"
description: "Cette rubrique explique comment procéder si le client est déconnecté de son environnement et ne sait pas pourquoi."
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
ms.openlocfilehash: 4f96b986059c179268f8a96ea7e7725831a93524
ms.contentlocale: fr-fr
ms.lasthandoff: 12/04/2018

---

# <a name="talent-client-disconnects"></a><span data-ttu-id="d4416-103">Le client Talent se déconnecte</span><span class="sxs-lookup"><span data-stu-id="d4416-103">Talent client disconnects</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d4416-104">**Détails de l'environnement**</span><span class="sxs-lookup"><span data-stu-id="d4416-104">**Environment details**</span></span> 

<span data-ttu-id="d4416-105">Ce problème peut se produire dans tous les environnements.</span><span class="sxs-lookup"><span data-stu-id="d4416-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="d4416-106">**Symptôme**</span><span class="sxs-lookup"><span data-stu-id="d4416-106">**Symptom**</span></span> 

<span data-ttu-id="d4416-107">Le client est déconnecté de son environnement et ne sait pas pourquoi.</span><span class="sxs-lookup"><span data-stu-id="d4416-107">The customer is disconnected from his or her environment and doesn't know why.</span></span> <span data-ttu-id="d4416-108">Le client reçoit un des messages d'erreur suivants :</span><span class="sxs-lookup"><span data-stu-id="d4416-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="d4416-109">Votre connexion a été perdue.</span><span class="sxs-lookup"><span data-stu-id="d4416-109">We've lost your connection.</span></span> <span data-ttu-id="d4416-110">Cliquez sur Fermer pour continuer de travailler.</span><span class="sxs-lookup"><span data-stu-id="d4416-110">Click Close to continue working.</span></span>
- <span data-ttu-id="d4416-111">Il semble que la connectivité réseau soit perdue. Cliquez sur Réessayer pour faire une nouvelle tentative.</span><span class="sxs-lookup"><span data-stu-id="d4416-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="d4416-112">**Alerte**</span><span class="sxs-lookup"><span data-stu-id="d4416-112">**Red flag**</span></span>

<span data-ttu-id="d4416-113">Ce problème se produit souvent lorsque les utilisateurs se trouvent à l'étape d'implémentation, comparent des informations entre les environnements de production et de test, puis oublient qu'ils passent d'une session à l'autre.</span><span class="sxs-lookup"><span data-stu-id="d4416-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="d4416-114">Si les utilisateurs sont à cette étape, ils rencontreront probablement ce problème.</span><span class="sxs-lookup"><span data-stu-id="d4416-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="d4416-115">**Problème**</span><span class="sxs-lookup"><span data-stu-id="d4416-115">**Issue**</span></span> 

<span data-ttu-id="d4416-116">**Types de navigateur :** Google Chrome, Internet Explorer et Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d4416-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="d4416-117">La plateforme Microsoft Dynamics 365 for Talent déconnecte les utilisateurs lorsque deux sessions différentes sont ouvertes en même temps pour le même utilisateur et le même type de navigateur.</span><span class="sxs-lookup"><span data-stu-id="d4416-117">The Microsoft Dynamics 365 for Talent platform disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="d4416-118">(Par exemple, l'utilisateur A affiche l'environnement 1 et l'environnement 2 dans chrome). Peu importe que les utilisateurs ouvrent différentes fenêtres de navigateur ou différents onglets.</span><span class="sxs-lookup"><span data-stu-id="d4416-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="d4416-119">Si les mêmes informations d'identification de l'utilisateur sont utilisées pour se connecter à l'environnement 1 et à l'environnement 2 en même temps et dans le même type de navigateur, Talent déconnecte une des sessions.</span><span class="sxs-lookup"><span data-stu-id="d4416-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Talent disconnects one of the sessions.</span></span>

<span data-ttu-id="d4416-120">**Solution**</span><span class="sxs-lookup"><span data-stu-id="d4416-120">**Solution**</span></span>

<span data-ttu-id="d4416-121">Assurez-vous qu'un seul environnement est ouvert à la fois pour un type de navigateur donné.</span><span class="sxs-lookup"><span data-stu-id="d4416-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="d4416-122">Les utilisateurs peuvent ouvrir plusieurs sessions dans le même environnement (c'est-à-dire, plusieurs onglets dans le même navigateur).</span><span class="sxs-lookup"><span data-stu-id="d4416-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="d4416-123">Les utilisateurs qui souhaitent passer d'un environnement à l'autre en même temps doivent ouvrir chaque environnement dans un type de navigateur différent.</span><span class="sxs-lookup"><span data-stu-id="d4416-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="d4416-124">(Par exemple, l'utilisateur A peut afficher l'environnement 1 dans Chrome et l'environnement 2 dans Microsoft Edge.)</span><span class="sxs-lookup"><span data-stu-id="d4416-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>

