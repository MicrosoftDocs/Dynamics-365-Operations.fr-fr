---
title: Les utilisateurs Attract ne peuvent pas soumettre leur candidature depuis le portail de carrière
description: Cette rubrique explique comment résoudre un problème où les utilisateurs Attract ne peuvent pas postuler à des emplois à partir du portail carrière.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461128"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a><span data-ttu-id="88616-103">Les utilisateurs Attract ne peuvent pas soumettre leur candidature depuis le portail de carrière</span><span class="sxs-lookup"><span data-stu-id="88616-103">Attract users can't apply for jobs from career portal</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="88616-104">Sortie</span><span class="sxs-lookup"><span data-stu-id="88616-104">Issue</span></span>

<span data-ttu-id="88616-105">Les utilisateurs Attract ne peuvent pas soumettre leur candidature depuis le portail de carrière.</span><span class="sxs-lookup"><span data-stu-id="88616-105">Attract users can't apply for jobs from the career portal.</span></span> <span data-ttu-id="88616-106">Lorsqu'ils essaient de postuler pour un emploi créé dans Dynamics 365 Talent: Attract, le navigateur charge la page en continu et ne termine pas l'action.</span><span class="sxs-lookup"><span data-stu-id="88616-106">When they try to apply for a job that was created in Dynamics 365 Talent: Attract, the browser loads the page continuously and doesn't complete the action.</span></span>

## <a name="cause"></a><span data-ttu-id="88616-107">Cause</span><span class="sxs-lookup"><span data-stu-id="88616-107">Cause</span></span>

<span data-ttu-id="88616-108">Ce problème se produit lorsque l'équipe de relations Talent n'a pas le rôle d'utilisateur Talent.</span><span class="sxs-lookup"><span data-stu-id="88616-108">This problem occurs when the Talent Relationship Team doesn't have the Talent user role.</span></span>

## <a name="resolution"></a><span data-ttu-id="88616-109">Résolution</span><span class="sxs-lookup"><span data-stu-id="88616-109">Resolution</span></span>

<span data-ttu-id="88616-110">Attribuez le rôle d'utilisateur Talent à l'équipe de relations Talent.</span><span class="sxs-lookup"><span data-stu-id="88616-110">Assign the Talent user role to the Talent Relationship Team.</span></span>

1. <span data-ttu-id="88616-111">Connectez-vous au [centre d'administration Power Platform](https://admin.powerplatform.microsoft.com) avec l'une des informations d'identification d'administrateur suivantes :</span><span class="sxs-lookup"><span data-stu-id="88616-111">Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com) with any of the following admin credentials:</span></span>

   - <span data-ttu-id="88616-112">Administrateur Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="88616-112">Dynamics 365 admin</span></span>
   - <span data-ttu-id="88616-113">Administrateur général</span><span class="sxs-lookup"><span data-stu-id="88616-113">Global admin</span></span>
   - <span data-ttu-id="88616-114">Administrateur Power Platform</span><span class="sxs-lookup"><span data-stu-id="88616-114">Power Platform admin</span></span>

2. <span data-ttu-id="88616-115">Dans le volet de navigation, sélectionnez **Environnements**, puis sélectionnez l'environnement dans lequel attribuer le rôle d'utilisateur Talent à l'équipe de relations Talent.</span><span class="sxs-lookup"><span data-stu-id="88616-115">In the navigation pane, select **Environments**, and then select the environment in which to assign the Talent user role to the Talent Relationship Team.</span></span>

   ![Sélectionner un environnement](./media/attract-troubleshoot-career-portal-select-environment.png)

3. <span data-ttu-id="88616-117">Dans le volet **Environnements**, sélectionnez l'**URL d'environnement** et connectez-vous au portail d'administration de l'environnement (par exemple, https:<orgname>.crm.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="88616-117">In the **Environments** pane, select the **Environment URL** and sign in to the environment's admin portal (for example, https:<orgname>.crm.dynamics.com).</span></span>

4. <span data-ttu-id="88616-118">Sélectionnez **Paramètres**, sélectionnez **Système**, puis **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="88616-118">Select **Settings**, select **System**, and then select **Security**.</span></span>

   ![Accédez à la sécurité](./media/attract-troubleshoot-career-portal-security.png)

5. <span data-ttu-id="88616-120">Sélectionnez **Équipes**.</span><span class="sxs-lookup"><span data-stu-id="88616-120">Select **Teams**.</span></span>

   ![Sélectionnez Équipes](./media/attract-troubleshoot-career-portal-security-teams.png)

6. <span data-ttu-id="88616-122">Rechercher **Équipe des relations Talent** dans la zone de recherche, puis sélectionnez l'équipe dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="88616-122">Search for **Talent Relationship Team** in the search box, and then select the team from the search results.</span></span>

7. <span data-ttu-id="88616-123">Sélectionnez **GÉRER LES RÔLES** dans le ruban.</span><span class="sxs-lookup"><span data-stu-id="88616-123">Select **MANAGE ROLES** from the ribbon.</span></span>

8. <span data-ttu-id="88616-124">Dans la boîte de dialogue **Gérer les rôles de l'équipe**, sélectionnez **Utilisateur Talent** dans la liste des rôles disponibles, puis sélectionnez **OK** pour appliquer le rôle.</span><span class="sxs-lookup"><span data-stu-id="88616-124">In the **Manage Team Roles** dialog, select **Talent user** from the list of available roles, and then select **OK** to apply the role.</span></span>

   ![Appliquer le rôle](./media/attract-troubleshoot-career-portal-apply-role.png)

9. <span data-ttu-id="88616-126">Testez vos modifications :</span><span class="sxs-lookup"><span data-stu-id="88616-126">Test your changes:</span></span>

   1. <span data-ttu-id="88616-127">Connectez-vous au portail des carrières à partir d'une nouvelle fenêtre de navigateur.</span><span class="sxs-lookup"><span data-stu-id="88616-127">Sign in to the career portal from a new browser window.</span></span>
   2. <span data-ttu-id="88616-128">Postulez à l'emploi depuis le portail carrière.</span><span class="sxs-lookup"><span data-stu-id="88616-128">Apply for the job from the career portal.</span></span> 