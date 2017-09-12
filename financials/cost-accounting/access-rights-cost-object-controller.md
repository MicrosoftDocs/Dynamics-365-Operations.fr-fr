---
title: "Définir les droits d'accès des contrôleurs d'objets de coût"
description: "Cette rubrique fournit des informations sur les droits d'accès pour les contrôleurs d'objet de coût."
author: YuyuScheller
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: c520e14233fb03646aa4a273362e596bd1990a8c
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

## <a name="access-rights-of-a-cost-object-controller"></a><span data-ttu-id="7c815-103">Droits d'accès d'un contrôleur d'objet de coût</span><span class="sxs-lookup"><span data-stu-id="7c815-103">Access rights of a cost object controller</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7c815-104">L'espace de travail **Contrôle des coûts** est un point central où les responsables peuvent afficher les performances de leurs objets de coût.</span><span class="sxs-lookup"><span data-stu-id="7c815-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="7c815-105">Cet espace de travail permet aux responsables d'utiliser les données de contrôle de gestion même si elles ne concernent pas les comptables.</span><span class="sxs-lookup"><span data-stu-id="7c815-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="7c815-106">Pour des raisons de sécurité, les responsables doivent être autorisés à voir les données de contrôle de gestion liées aux objets de coût spécifiques dont ils sont responsables.</span><span class="sxs-lookup"><span data-stu-id="7c815-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="7c815-107">Il existe quatre rôles uniques dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="7c815-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="7c815-108">Nom de rôle</span><span class="sxs-lookup"><span data-stu-id="7c815-108">Role name</span></span>               | <span data-ttu-id="7c815-109">Licence</span><span class="sxs-lookup"><span data-stu-id="7c815-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="7c815-110">Gestionnaire de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="7c815-110">Cost accounting manager</span></span> | <span data-ttu-id="7c815-111">Activité</span><span class="sxs-lookup"><span data-stu-id="7c815-111">Activity</span></span>     |
| <span data-ttu-id="7c815-112">Contrôleur de gestion</span><span class="sxs-lookup"><span data-stu-id="7c815-112">Cost accountant</span></span>         | <span data-ttu-id="7c815-113">Operations</span><span class="sxs-lookup"><span data-stu-id="7c815-113">Operations</span></span>   |
| <span data-ttu-id="7c815-114">Commis contrôleur de gestion</span><span class="sxs-lookup"><span data-stu-id="7c815-114">Cost accountant clerk</span></span>   | <span data-ttu-id="7c815-115">Operations</span><span class="sxs-lookup"><span data-stu-id="7c815-115">Operations</span></span>   |
| <span data-ttu-id="7c815-116">Contrôleur d'objet de coût</span><span class="sxs-lookup"><span data-stu-id="7c815-116">Cost object controller</span></span>  | <span data-ttu-id="7c815-117">Membres de l'équipe</span><span class="sxs-lookup"><span data-stu-id="7c815-117">Team members</span></span> |

<span data-ttu-id="7c815-118">Cette rubrique explique comment affecter le rôle **Contrôleur d'objet de coût** à un responsable.</span><span class="sxs-lookup"><span data-stu-id="7c815-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="7c815-119">Lorsque le rôle **Contrôleur d'objet de coût** est affecté à un responsable, le responsable peut effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="7c815-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="7c815-120">Accéder à l'espace de travail **Contrôle des coûts** (dans le client).</span><span class="sxs-lookup"><span data-stu-id="7c815-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="7c815-121">Extraire et avoir accès aux pages qui prennent en charge l'expérience d'extraction.</span><span class="sxs-lookup"><span data-stu-id="7c815-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="7c815-122">Accéder à l'espace de travail **Contrôle des coûts** (dans l'application mobile).</span><span class="sxs-lookup"><span data-stu-id="7c815-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="7c815-123">Le rôle **Contrôleur d'objet de coût** ne contrôle pas les objets de coût auxquels l'utilisateur peut accéder et dont il peut afficher les données.</span><span class="sxs-lookup"><span data-stu-id="7c815-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="7c815-124">La sécurité au niveau de la ligne est fournie via les hiérarchies de dimensions et la hiérarchie de liste d'accès.</span><span class="sxs-lookup"><span data-stu-id="7c815-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="7c815-125">Accorder des droits d'accès</span><span class="sxs-lookup"><span data-stu-id="7c815-125">Grant access rights</span></span>
<span data-ttu-id="7c815-126">L'exemple suivant montre ce à quoi une hiérarchie de dimensions peut ressembler.</span><span class="sxs-lookup"><span data-stu-id="7c815-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="7c815-127">**Détails sur la hiérarchie des dimensions**</span><span class="sxs-lookup"><span data-stu-id="7c815-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="7c815-128">Nom de la hiérarchie des dimensions</span><span class="sxs-lookup"><span data-stu-id="7c815-128">Dimension hierarchy name</span></span> | <span data-ttu-id="7c815-129">Dimension</span><span class="sxs-lookup"><span data-stu-id="7c815-129">Dimension</span></span>    | <span data-ttu-id="7c815-130">Nom du type de hiérarchie des dimensions</span><span class="sxs-lookup"><span data-stu-id="7c815-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="7c815-131">Hiérarchie de la liste d'accès</span><span class="sxs-lookup"><span data-stu-id="7c815-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="7c815-132">Organisation</span><span class="sxs-lookup"><span data-stu-id="7c815-132">Organization</span></span>             | <span data-ttu-id="7c815-133">Centres de coût</span><span class="sxs-lookup"><span data-stu-id="7c815-133">Cost centers</span></span> | <span data-ttu-id="7c815-134">Hiérarchie de classification de dimension</span><span class="sxs-lookup"><span data-stu-id="7c815-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="7c815-135">**Oui**</span><span class="sxs-lookup"><span data-stu-id="7c815-135">**Yes**</span></span>               |

<span data-ttu-id="7c815-136">Vous pouvez utiliser l'organisateur **Utilisateurs** dans le concepteur de hiérarchie pour ajouter un ou plusieurs ID utilisateur dans chaque nœud.</span><span class="sxs-lookup"><span data-stu-id="7c815-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|                                   | <span data-ttu-id="7c815-137">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7c815-137">Users</span></span>            | <span data-ttu-id="7c815-138">Plages de membres de la dimension</span><span class="sxs-lookup"><span data-stu-id="7c815-138">Dimension member ranges</span></span>   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="7c815-139">**Nœuds**</span><span class="sxs-lookup"><span data-stu-id="7c815-139">**Nodes**</span></span>                         | <span data-ttu-id="7c815-140">**ID utilisateur**</span><span class="sxs-lookup"><span data-stu-id="7c815-140">**User ID**</span></span>      | <span data-ttu-id="7c815-141">**Membre de la dimension de départ**</span><span class="sxs-lookup"><span data-stu-id="7c815-141">**From dimension member**</span></span> | <span data-ttu-id="7c815-142">**Membre de la dimension de fin**</span><span class="sxs-lookup"><span data-stu-id="7c815-142">**To dimension member**</span></span> |
| <span data-ttu-id="7c815-143">Organisation</span><span class="sxs-lookup"><span data-stu-id="7c815-143">Organization</span></span>                      | <span data-ttu-id="7c815-144">Benjamin, Claire</span><span class="sxs-lookup"><span data-stu-id="7c815-144">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="7c815-145">&nbsp;&nbsp;Admin</span><span class="sxs-lookup"><span data-stu-id="7c815-145">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="7c815-146">Avril</span><span class="sxs-lookup"><span data-stu-id="7c815-146">April</span></span>            |                           |                         |
| <span data-ttu-id="7c815-147">&nbsp;&nbsp;&nbsp;&nbsp;Finances</span><span class="sxs-lookup"><span data-stu-id="7c815-147">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="7c815-148">Alicia</span><span class="sxs-lookup"><span data-stu-id="7c815-148">Alicia</span></span>           | <span data-ttu-id="7c815-149">CC002</span><span class="sxs-lookup"><span data-stu-id="7c815-149">CC002</span></span>                     | <span data-ttu-id="7c815-150">CC003</span><span class="sxs-lookup"><span data-stu-id="7c815-150">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="7c815-151">CC007</span><span class="sxs-lookup"><span data-stu-id="7c815-151">CC007</span></span>                     | <span data-ttu-id="7c815-152">CC007</span><span class="sxs-lookup"><span data-stu-id="7c815-152">CC007</span></span>                   |
| <span data-ttu-id="7c815-153">&nbsp;&nbsp;&nbsp;&nbsp;RH</span><span class="sxs-lookup"><span data-stu-id="7c815-153">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="7c815-154">Arnie</span><span class="sxs-lookup"><span data-stu-id="7c815-154">Arnie</span></span>            | <span data-ttu-id="7c815-155">CC001</span><span class="sxs-lookup"><span data-stu-id="7c815-155">CC001</span></span>                     | <span data-ttu-id="7c815-156">CC001</span><span class="sxs-lookup"><span data-stu-id="7c815-156">CC001</span></span>                   |
| <span data-ttu-id="7c815-157">&nbsp;&nbsp;Production</span><span class="sxs-lookup"><span data-stu-id="7c815-157">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="7c815-158">David</span><span class="sxs-lookup"><span data-stu-id="7c815-158">David</span></span>            |                           |                         |
| <span data-ttu-id="7c815-159">&nbsp;&nbsp;&nbsp;&nbsp;Emballage</span><span class="sxs-lookup"><span data-stu-id="7c815-159">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="7c815-160">Ellen</span><span class="sxs-lookup"><span data-stu-id="7c815-160">Ellen</span></span>            | <span data-ttu-id="7c815-161">CC005</span><span class="sxs-lookup"><span data-stu-id="7c815-161">CC005</span></span>                     | <span data-ttu-id="7c815-162">CC005</span><span class="sxs-lookup"><span data-stu-id="7c815-162">CC005</span></span>                   |
| <span data-ttu-id="7c815-163">&nbsp;&nbsp;&nbsp;&nbsp;Assemblage</span><span class="sxs-lookup"><span data-stu-id="7c815-163">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="7c815-164">Chris</span><span class="sxs-lookup"><span data-stu-id="7c815-164">Chris</span></span>            | <span data-ttu-id="7c815-165">CC006</span><span class="sxs-lookup"><span data-stu-id="7c815-165">CC006</span></span>                     | <span data-ttu-id="7c815-166">CC006</span><span class="sxs-lookup"><span data-stu-id="7c815-166">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="7c815-167">Les comptables doivent être affectés au niveau supérieur de la hiérarchie, de sorte qu'ils puissent visualiser toutes les écritures du contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="7c815-167">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="7c815-168">Avant que les paramètres de la hiérarchie de la liste d'accès et ses paramètres de sécurité puissent être appliqués, l'option **Activer l'affichage pour les membres de dimension d'objet de coût** doit être définie sur **Oui** dans l'onglet **Général** de la page **Paramètres de contrôle de gestion** (**Contrôle de gestion** > **Paramétrage** > **Paramètres**).</span><span class="sxs-lookup"><span data-stu-id="7c815-168">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="7c815-169">Les paramètres de la hiérarchie de la liste d'accès sont utilisés pour contrôler les données affichées dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="7c815-169">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="7c815-170">Espace de travail **Contrôle des coûts** (dans le client) :</span><span class="sxs-lookup"><span data-stu-id="7c815-170">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="7c815-171">Données dans les pages utilisées pour l'extraction</span><span class="sxs-lookup"><span data-stu-id="7c815-171">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="7c815-172">Espace de travail **Contrôle des coûts** (dans l'application mobile) :</span><span class="sxs-lookup"><span data-stu-id="7c815-172">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="7c815-173">Soldes dans les cartes</span><span class="sxs-lookup"><span data-stu-id="7c815-173">Balances in cards</span></span>

- <span data-ttu-id="7c815-174">Microsoft Power BI :</span><span class="sxs-lookup"><span data-stu-id="7c815-174">Microsoft Power BI:</span></span>

    - <span data-ttu-id="7c815-175">Données qui sont affichées dans une visualisation Power BI</span><span class="sxs-lookup"><span data-stu-id="7c815-175">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="7c815-176">Les visualisations des données Power BI sont intégrées dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, client</span><span class="sxs-lookup"><span data-stu-id="7c815-176">Data Power BI visualizations that are embedded in the Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="7c815-177">Avant que la hiérarchie de la liste d'accès puisse affecter des données Power BI, la hiérarchie de la liste d'accès et la sécurité au niveau de la ligne dans Power BI doivent être jumelées.</span><span class="sxs-lookup"><span data-stu-id="7c815-177">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="7c815-178">Pour plus d'informations, voir [Paramétrer la sécurité pour le pack de contenu de gestion des coûts](/dynamics365/unified-operations/dev-itpro/analytics/setup-security-cost-accounting-content-pack).</span><span class="sxs-lookup"><span data-stu-id="7c815-178">For more information, see [Set up security for Cost accounting content pack](/dynamics365/unified-operations/dev-itpro/analytics/setup-security-cost-accounting-content-pack).</span></span>
> - <span data-ttu-id="7c815-179">Cette rubrique affiche les paramétrages qui doivent être effectués pour utiliser l'espace de travail **Contrôle des coûts**.</span><span class="sxs-lookup"><span data-stu-id="7c815-179">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="7c815-180">Voir également :</span><span class="sxs-lookup"><span data-stu-id="7c815-180">See also</span></span>

- [<span data-ttu-id="7c815-181">Espace de travail de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="7c815-181">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="7c815-182">Hiérarchie des dimensions</span><span class="sxs-lookup"><span data-stu-id="7c815-182">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="7c815-183">Paramétrer la sécurité du pack de contenu Contrôle de gestion pour Power BI</span><span class="sxs-lookup"><span data-stu-id="7c815-183">Set up security for Cost accounting content pack</span></span>](/dynamics365/unified-operations/dev-itpro/analytics/setup-security-cost-accounting-content-pack)

