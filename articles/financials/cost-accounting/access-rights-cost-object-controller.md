---
title: "Définir les droits d'accès des contrôleurs d'objets de coût"
description: "Cette rubrique fournit des informations sur les droits d'accès pour les contrôleurs d'objet de coût."
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e0ba52f4c06d5cd18c8f0ff7972671cc722289e7
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="access-rights-of-a-cost-object-controller"></a><span data-ttu-id="2dbe5-103">Droits d'accès d'un contrôleur d'objet de coût</span><span class="sxs-lookup"><span data-stu-id="2dbe5-103">Access rights of a cost object controller</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="2dbe5-104">L'espace de travail **Contrôle des coûts** est un point central où les responsables peuvent afficher les performances de leurs objets de coût.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="2dbe5-105">Cet espace de travail permet aux responsables d'utiliser les données de contrôle de gestion même si elles ne concernent pas les comptables.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="2dbe5-106">Pour des raisons de sécurité, les responsables doivent être autorisés à voir les données de contrôle de gestion liées aux objets de coût spécifiques dont ils sont responsables.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="2dbe5-107">Il existe quatre rôles uniques dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="2dbe5-108">Nom de rôle</span><span class="sxs-lookup"><span data-stu-id="2dbe5-108">Role name</span></span>               | <span data-ttu-id="2dbe5-109">Licence</span><span class="sxs-lookup"><span data-stu-id="2dbe5-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="2dbe5-110">Gestionnaire de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="2dbe5-110">Cost accounting manager</span></span> | <span data-ttu-id="2dbe5-111">Activité</span><span class="sxs-lookup"><span data-stu-id="2dbe5-111">Activity</span></span>     |
| <span data-ttu-id="2dbe5-112">Contrôleur de gestion</span><span class="sxs-lookup"><span data-stu-id="2dbe5-112">Cost accountant</span></span>         | <span data-ttu-id="2dbe5-113">Operations</span><span class="sxs-lookup"><span data-stu-id="2dbe5-113">Operations</span></span>   |
| <span data-ttu-id="2dbe5-114">Commis contrôleur de gestion</span><span class="sxs-lookup"><span data-stu-id="2dbe5-114">Cost accountant clerk</span></span>   | <span data-ttu-id="2dbe5-115">Operations</span><span class="sxs-lookup"><span data-stu-id="2dbe5-115">Operations</span></span>   |
| <span data-ttu-id="2dbe5-116">Contrôleur d'objet de coût</span><span class="sxs-lookup"><span data-stu-id="2dbe5-116">Cost object controller</span></span>  | <span data-ttu-id="2dbe5-117">Membres de l'équipe</span><span class="sxs-lookup"><span data-stu-id="2dbe5-117">Team members</span></span> |

<span data-ttu-id="2dbe5-118">Cette rubrique explique comment affecter le rôle **Contrôleur d'objet de coût** à un responsable.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="2dbe5-119">Lorsque le rôle **Contrôleur d'objet de coût** est affecté à un responsable, le responsable peut effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="2dbe5-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="2dbe5-120">Accéder à l'espace de travail **Contrôle des coûts** (dans le client).</span><span class="sxs-lookup"><span data-stu-id="2dbe5-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="2dbe5-121">Extraire et avoir accès aux pages qui prennent en charge l'expérience d'extraction.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="2dbe5-122">Accéder à l'espace de travail **Contrôle des coûts** (dans l'application mobile).</span><span class="sxs-lookup"><span data-stu-id="2dbe5-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="2dbe5-123">Le rôle **Contrôleur d'objet de coût** ne contrôle pas les objets de coût auxquels l'utilisateur peut accéder et dont il peut afficher les données.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="2dbe5-124">La sécurité au niveau de la ligne est fournie via les hiérarchies de dimensions et la hiérarchie de liste d'accès.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="2dbe5-125">Accorder des droits d'accès</span><span class="sxs-lookup"><span data-stu-id="2dbe5-125">Grant access rights</span></span>
<span data-ttu-id="2dbe5-126">L'exemple suivant montre ce à quoi une hiérarchie de dimensions peut ressembler.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="2dbe5-127">**Détails sur la hiérarchie des dimensions**</span><span class="sxs-lookup"><span data-stu-id="2dbe5-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="2dbe5-128">Nom de la hiérarchie des dimensions</span><span class="sxs-lookup"><span data-stu-id="2dbe5-128">Dimension hierarchy name</span></span> | <span data-ttu-id="2dbe5-129">Dimension</span><span class="sxs-lookup"><span data-stu-id="2dbe5-129">Dimension</span></span>    | <span data-ttu-id="2dbe5-130">Nom du type de hiérarchie des dimensions</span><span class="sxs-lookup"><span data-stu-id="2dbe5-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="2dbe5-131">Hiérarchie de la liste d'accès</span><span class="sxs-lookup"><span data-stu-id="2dbe5-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="2dbe5-132">Organisation</span><span class="sxs-lookup"><span data-stu-id="2dbe5-132">Organization</span></span>             | <span data-ttu-id="2dbe5-133">Centres de coût</span><span class="sxs-lookup"><span data-stu-id="2dbe5-133">Cost centers</span></span> | <span data-ttu-id="2dbe5-134">Hiérarchie de classification de dimension</span><span class="sxs-lookup"><span data-stu-id="2dbe5-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="2dbe5-135">**Oui**</span><span class="sxs-lookup"><span data-stu-id="2dbe5-135">**Yes**</span></span>               |

<span data-ttu-id="2dbe5-136">Vous pouvez utiliser l'organisateur **Utilisateurs** dans le concepteur de hiérarchie pour ajouter un ou plusieurs ID utilisateur dans chaque nœud.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|                                   | <span data-ttu-id="2dbe5-137">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="2dbe5-137">Users</span></span>            | <span data-ttu-id="2dbe5-138">Plages de membres de la dimension</span><span class="sxs-lookup"><span data-stu-id="2dbe5-138">Dimension member ranges</span></span>   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="2dbe5-139">**Nœuds**</span><span class="sxs-lookup"><span data-stu-id="2dbe5-139">**Nodes**</span></span>                         | <span data-ttu-id="2dbe5-140">**ID utilisateur**</span><span class="sxs-lookup"><span data-stu-id="2dbe5-140">**User ID**</span></span>      | <span data-ttu-id="2dbe5-141">**Membre de la dimension de départ**</span><span class="sxs-lookup"><span data-stu-id="2dbe5-141">**From dimension member**</span></span> | <span data-ttu-id="2dbe5-142">**Membre de la dimension de fin**</span><span class="sxs-lookup"><span data-stu-id="2dbe5-142">**To dimension member**</span></span> |
| <span data-ttu-id="2dbe5-143">Organisation</span><span class="sxs-lookup"><span data-stu-id="2dbe5-143">Organization</span></span>                      | <span data-ttu-id="2dbe5-144">Benjamin, Claire</span><span class="sxs-lookup"><span data-stu-id="2dbe5-144">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="2dbe5-145">&nbsp;&nbsp;Admin</span><span class="sxs-lookup"><span data-stu-id="2dbe5-145">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="2dbe5-146">Avril</span><span class="sxs-lookup"><span data-stu-id="2dbe5-146">April</span></span>            |                           |                         |
| <span data-ttu-id="2dbe5-147">&nbsp;&nbsp;&nbsp;&nbsp;Finances</span><span class="sxs-lookup"><span data-stu-id="2dbe5-147">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="2dbe5-148">Alicia</span><span class="sxs-lookup"><span data-stu-id="2dbe5-148">Alicia</span></span>           | <span data-ttu-id="2dbe5-149">CC002</span><span class="sxs-lookup"><span data-stu-id="2dbe5-149">CC002</span></span>                     | <span data-ttu-id="2dbe5-150">CC003</span><span class="sxs-lookup"><span data-stu-id="2dbe5-150">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="2dbe5-151">CC007</span><span class="sxs-lookup"><span data-stu-id="2dbe5-151">CC007</span></span>                     | <span data-ttu-id="2dbe5-152">CC007</span><span class="sxs-lookup"><span data-stu-id="2dbe5-152">CC007</span></span>                   |
| <span data-ttu-id="2dbe5-153">&nbsp;&nbsp;&nbsp;&nbsp;RH</span><span class="sxs-lookup"><span data-stu-id="2dbe5-153">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="2dbe5-154">Arnie</span><span class="sxs-lookup"><span data-stu-id="2dbe5-154">Arnie</span></span>            | <span data-ttu-id="2dbe5-155">CC001</span><span class="sxs-lookup"><span data-stu-id="2dbe5-155">CC001</span></span>                     | <span data-ttu-id="2dbe5-156">CC001</span><span class="sxs-lookup"><span data-stu-id="2dbe5-156">CC001</span></span>                   |
| <span data-ttu-id="2dbe5-157">&nbsp;&nbsp;Production</span><span class="sxs-lookup"><span data-stu-id="2dbe5-157">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="2dbe5-158">David</span><span class="sxs-lookup"><span data-stu-id="2dbe5-158">David</span></span>            |                           |                         |
| <span data-ttu-id="2dbe5-159">&nbsp;&nbsp;&nbsp;&nbsp;Emballage</span><span class="sxs-lookup"><span data-stu-id="2dbe5-159">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="2dbe5-160">Ellen</span><span class="sxs-lookup"><span data-stu-id="2dbe5-160">Ellen</span></span>            | <span data-ttu-id="2dbe5-161">CC005</span><span class="sxs-lookup"><span data-stu-id="2dbe5-161">CC005</span></span>                     | <span data-ttu-id="2dbe5-162">CC005</span><span class="sxs-lookup"><span data-stu-id="2dbe5-162">CC005</span></span>                   |
| <span data-ttu-id="2dbe5-163">&nbsp;&nbsp;&nbsp;&nbsp;Assemblage</span><span class="sxs-lookup"><span data-stu-id="2dbe5-163">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="2dbe5-164">Chris</span><span class="sxs-lookup"><span data-stu-id="2dbe5-164">Chris</span></span>            | <span data-ttu-id="2dbe5-165">CC006</span><span class="sxs-lookup"><span data-stu-id="2dbe5-165">CC006</span></span>                     | <span data-ttu-id="2dbe5-166">CC006</span><span class="sxs-lookup"><span data-stu-id="2dbe5-166">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="2dbe5-167">Les comptables doivent être affectés au niveau supérieur de la hiérarchie, de sorte qu'ils puissent visualiser toutes les écritures du contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-167">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="2dbe5-168">Avant que les paramètres de la hiérarchie de la liste d'accès et ses paramètres de sécurité puissent être appliqués, l'option **Activer l'affichage pour les membres de dimension d'objet de coût** doit être définie sur **Oui** dans l'onglet **Général** de la page **Paramètres de contrôle de gestion** (**Contrôle de gestion** > **Paramétrage** > **Paramètres**).</span><span class="sxs-lookup"><span data-stu-id="2dbe5-168">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="2dbe5-169">Les paramètres de la hiérarchie de la liste d'accès sont utilisés pour contrôler les données affichées dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="2dbe5-169">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="2dbe5-170">Espace de travail **Contrôle des coûts** (dans le client) :</span><span class="sxs-lookup"><span data-stu-id="2dbe5-170">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="2dbe5-171">Données dans les pages utilisées pour l'extraction</span><span class="sxs-lookup"><span data-stu-id="2dbe5-171">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="2dbe5-172">Espace de travail **Contrôle des coûts** (dans l'application mobile) :</span><span class="sxs-lookup"><span data-stu-id="2dbe5-172">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="2dbe5-173">Soldes dans les cartes</span><span class="sxs-lookup"><span data-stu-id="2dbe5-173">Balances in cards</span></span>

- <span data-ttu-id="2dbe5-174">Microsoft Power BI :</span><span class="sxs-lookup"><span data-stu-id="2dbe5-174">Microsoft Power BI:</span></span>

    - <span data-ttu-id="2dbe5-175">Données qui sont affichées dans une visualisation Power BI</span><span class="sxs-lookup"><span data-stu-id="2dbe5-175">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="2dbe5-176">Les visualisations des données Power BI sont intégrées dans le client Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2dbe5-176">Data Power BI visualizations that are embedded in the Microsoft Dynamics 365 for Finance and Operations, client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="2dbe5-177">Avant que la hiérarchie de la liste d'accès puisse affecter des données Power BI, la hiérarchie de la liste d'accès et la sécurité au niveau de la ligne dans Power BI doivent être jumelées.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-177">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="2dbe5-178">Pour plus d'informations, voir [Paramétrer la sécurité pour le pack de contenu de gestion des coûts](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span><span class="sxs-lookup"><span data-stu-id="2dbe5-178">For more information, see [Set up security for Cost accounting content pack](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span></span>
> - <span data-ttu-id="2dbe5-179">Cette rubrique affiche les paramétrages qui doivent être effectués pour utiliser l'espace de travail **Contrôle des coûts**.</span><span class="sxs-lookup"><span data-stu-id="2dbe5-179">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="2dbe5-180">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2dbe5-180">See also</span></span>

- [<span data-ttu-id="2dbe5-181">Espace de travail de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="2dbe5-181">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="2dbe5-182">Hiérarchie des dimensions</span><span class="sxs-lookup"><span data-stu-id="2dbe5-182">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="2dbe5-183">Paramétrer la sécurité du pack de contenu Contrôle de gestion pour Power BI</span><span class="sxs-lookup"><span data-stu-id="2dbe5-183">Set up security for Cost accounting content pack</span></span>](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)

