---
title: Droits d’accès pour les contrôleurs d’objet de coût
description: Cette rubrique fournit des informations sur les droits d’accès pour les contrôleurs d’objet de coût.
author: AndersGirke
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fa8faf0f0f45f901151b3b20a1792b3d8f264fa6
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897622"
---
# <a name="access-rights-for-cost-object-controllers"></a><span data-ttu-id="683c5-103">Droits d’accès pour les contrôleurs d’objet de coût</span><span class="sxs-lookup"><span data-stu-id="683c5-103">Access rights for cost object controllers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="683c5-104">L’espace de travail **Contrôle des coûts** est un point central où les responsables peuvent afficher les performances de leurs objets de coût.</span><span class="sxs-lookup"><span data-stu-id="683c5-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="683c5-105">Cet espace de travail permet aux responsables d’utiliser les données de contrôle de gestion même si elles ne concernent pas les comptables.</span><span class="sxs-lookup"><span data-stu-id="683c5-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="683c5-106">Pour des raisons de sécurité, les responsables doivent être autorisés à voir les données de contrôle de gestion liées aux objets de coût spécifiques dont ils sont responsables.</span><span class="sxs-lookup"><span data-stu-id="683c5-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="683c5-107">Il existe quatre rôles uniques dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="683c5-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="683c5-108">Nom de rôle</span><span class="sxs-lookup"><span data-stu-id="683c5-108">Role name</span></span>               | <span data-ttu-id="683c5-109">Licence</span><span class="sxs-lookup"><span data-stu-id="683c5-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="683c5-110">Gestionnaire de contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="683c5-110">Cost accounting manager</span></span> | <span data-ttu-id="683c5-111">Activité</span><span class="sxs-lookup"><span data-stu-id="683c5-111">Activity</span></span>     |
| <span data-ttu-id="683c5-112">Contrôleur de gestion</span><span class="sxs-lookup"><span data-stu-id="683c5-112">Cost accountant</span></span>         | <span data-ttu-id="683c5-113">Operations</span><span class="sxs-lookup"><span data-stu-id="683c5-113">Operations</span></span>   |
| <span data-ttu-id="683c5-114">Commis contrôleur de gestion</span><span class="sxs-lookup"><span data-stu-id="683c5-114">Cost accountant clerk</span></span>   | <span data-ttu-id="683c5-115">Operations</span><span class="sxs-lookup"><span data-stu-id="683c5-115">Operations</span></span>   |
| <span data-ttu-id="683c5-116">Contrôleur d’objet de coût</span><span class="sxs-lookup"><span data-stu-id="683c5-116">Cost object controller</span></span>  | <span data-ttu-id="683c5-117">Membres de l’équipe</span><span class="sxs-lookup"><span data-stu-id="683c5-117">Team members</span></span> |

<span data-ttu-id="683c5-118">Cette rubrique explique comment affecter le rôle **Contrôleur d’objet de coût** à un responsable.</span><span class="sxs-lookup"><span data-stu-id="683c5-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="683c5-119">Lorsque le rôle **Contrôleur d’objet de coût** est affecté à un responsable, le responsable peut effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="683c5-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="683c5-120">Accéder à l’espace de travail **Contrôle des coûts** (dans le client).</span><span class="sxs-lookup"><span data-stu-id="683c5-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="683c5-121">Extraire et avoir accès aux pages qui prennent en charge l’expérience d’extraction.</span><span class="sxs-lookup"><span data-stu-id="683c5-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="683c5-122">Accéder à l’espace de travail **Contrôle des coûts** (dans l’application mobile).</span><span class="sxs-lookup"><span data-stu-id="683c5-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="683c5-123">Le rôle **Contrôleur d’objet de coût** ne contrôle pas les objets de coût auxquels l’utilisateur peut accéder et dont il peut afficher les données.</span><span class="sxs-lookup"><span data-stu-id="683c5-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="683c5-124">La sécurité au niveau de la ligne est fournie via les hiérarchies de dimensions et la hiérarchie de liste d’accès.</span><span class="sxs-lookup"><span data-stu-id="683c5-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="683c5-125">Accorder des droits d’accès</span><span class="sxs-lookup"><span data-stu-id="683c5-125">Grant access rights</span></span>
<span data-ttu-id="683c5-126">L’exemple suivant montre ce à quoi une hiérarchie de dimensions peut ressembler.</span><span class="sxs-lookup"><span data-stu-id="683c5-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="683c5-127">**Détails sur la hiérarchie des dimensions**</span><span class="sxs-lookup"><span data-stu-id="683c5-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="683c5-128">Nom de la hiérarchie des dimensions</span><span class="sxs-lookup"><span data-stu-id="683c5-128">Dimension hierarchy name</span></span> | <span data-ttu-id="683c5-129">Dimension</span><span class="sxs-lookup"><span data-stu-id="683c5-129">Dimension</span></span>    | <span data-ttu-id="683c5-130">Nom du type de hiérarchie des dimensions</span><span class="sxs-lookup"><span data-stu-id="683c5-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="683c5-131">Hiérarchie de la liste d’accès</span><span class="sxs-lookup"><span data-stu-id="683c5-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="683c5-132">Organisation</span><span class="sxs-lookup"><span data-stu-id="683c5-132">Organization</span></span>             | <span data-ttu-id="683c5-133">Centres de coût</span><span class="sxs-lookup"><span data-stu-id="683c5-133">Cost centers</span></span> | <span data-ttu-id="683c5-134">Hiérarchie de classification de dimension</span><span class="sxs-lookup"><span data-stu-id="683c5-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="683c5-135">**Oui**</span><span class="sxs-lookup"><span data-stu-id="683c5-135">**Yes**</span></span>               |

<span data-ttu-id="683c5-136">Vous pouvez utiliser l’organisateur **Utilisateurs** dans le concepteur de hiérarchie pour ajouter un ou plusieurs ID utilisateur dans chaque nœud.</span><span class="sxs-lookup"><span data-stu-id="683c5-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|             <span data-ttu-id="683c5-137">Nœuds</span><span class="sxs-lookup"><span data-stu-id="683c5-137">Nodes</span></span>                 | <span data-ttu-id="683c5-138">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="683c5-138">Users</span></span>            | <span data-ttu-id="683c5-139">Membre de la dimension de départ</span><span class="sxs-lookup"><span data-stu-id="683c5-139">From dimension member</span></span>     |   <span data-ttu-id="683c5-140">Membre de la dimension de fin</span><span class="sxs-lookup"><span data-stu-id="683c5-140">To dimension member</span></span>   |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="683c5-141">Organisation</span><span class="sxs-lookup"><span data-stu-id="683c5-141">Organization</span></span>                      | <span data-ttu-id="683c5-142">Benjamin, Claire</span><span class="sxs-lookup"><span data-stu-id="683c5-142">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="683c5-143">&nbsp;&nbsp;Admin</span><span class="sxs-lookup"><span data-stu-id="683c5-143">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="683c5-144">Avril</span><span class="sxs-lookup"><span data-stu-id="683c5-144">April</span></span>            |                           |                         |
| <span data-ttu-id="683c5-145">&nbsp;&nbsp;&nbsp;&nbsp;Finances</span><span class="sxs-lookup"><span data-stu-id="683c5-145">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="683c5-146">Alicia</span><span class="sxs-lookup"><span data-stu-id="683c5-146">Alicia</span></span>           | <span data-ttu-id="683c5-147">CC002</span><span class="sxs-lookup"><span data-stu-id="683c5-147">CC002</span></span>                     | <span data-ttu-id="683c5-148">CC003</span><span class="sxs-lookup"><span data-stu-id="683c5-148">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="683c5-149">CC007</span><span class="sxs-lookup"><span data-stu-id="683c5-149">CC007</span></span>                     | <span data-ttu-id="683c5-150">CC007</span><span class="sxs-lookup"><span data-stu-id="683c5-150">CC007</span></span>                   |
| <span data-ttu-id="683c5-151">&nbsp;&nbsp;&nbsp;&nbsp;RH</span><span class="sxs-lookup"><span data-stu-id="683c5-151">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="683c5-152">Arnie</span><span class="sxs-lookup"><span data-stu-id="683c5-152">Arnie</span></span>            | <span data-ttu-id="683c5-153">CC001</span><span class="sxs-lookup"><span data-stu-id="683c5-153">CC001</span></span>                     | <span data-ttu-id="683c5-154">CC001</span><span class="sxs-lookup"><span data-stu-id="683c5-154">CC001</span></span>                   |
| <span data-ttu-id="683c5-155">&nbsp;&nbsp;Production</span><span class="sxs-lookup"><span data-stu-id="683c5-155">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="683c5-156">David</span><span class="sxs-lookup"><span data-stu-id="683c5-156">David</span></span>            |                           |                         |
| <span data-ttu-id="683c5-157">&nbsp;&nbsp;&nbsp;&nbsp;Emballage</span><span class="sxs-lookup"><span data-stu-id="683c5-157">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="683c5-158">Ellen</span><span class="sxs-lookup"><span data-stu-id="683c5-158">Ellen</span></span>            | <span data-ttu-id="683c5-159">CC005</span><span class="sxs-lookup"><span data-stu-id="683c5-159">CC005</span></span>                     | <span data-ttu-id="683c5-160">CC005</span><span class="sxs-lookup"><span data-stu-id="683c5-160">CC005</span></span>                   |
| <span data-ttu-id="683c5-161">&nbsp;&nbsp;&nbsp;&nbsp;Assemblage</span><span class="sxs-lookup"><span data-stu-id="683c5-161">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="683c5-162">Chris</span><span class="sxs-lookup"><span data-stu-id="683c5-162">Chris</span></span>            | <span data-ttu-id="683c5-163">CC006</span><span class="sxs-lookup"><span data-stu-id="683c5-163">CC006</span></span>                     | <span data-ttu-id="683c5-164">CC006</span><span class="sxs-lookup"><span data-stu-id="683c5-164">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="683c5-165">Les comptables doivent être affectés au niveau supérieur de la hiérarchie, de sorte qu’ils puissent visualiser toutes les écritures du contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="683c5-165">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="683c5-166">Avant que les paramètres de la hiérarchie de la liste d’accès et ses paramètres de sécurité puissent être appliqués, l’option **Activer l’affichage pour les membres de dimension d’objet de coût** doit être définie sur **Oui** dans l’onglet **Général** de la page **Paramètres de contrôle de gestion** (**Contrôle de gestion** > **Paramétrage** > **Paramètres**).</span><span class="sxs-lookup"><span data-stu-id="683c5-166">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="683c5-167">Les paramètres de la hiérarchie de la liste d’accès sont utilisés pour contrôler les données affichées dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="683c5-167">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="683c5-168">Espace de travail **Contrôle des coûts** (dans le client) :</span><span class="sxs-lookup"><span data-stu-id="683c5-168">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="683c5-169">Données dans les pages utilisées pour l’extraction</span><span class="sxs-lookup"><span data-stu-id="683c5-169">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="683c5-170">Espace de travail **Contrôle des coûts** (dans l’application mobile) :</span><span class="sxs-lookup"><span data-stu-id="683c5-170">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="683c5-171">Soldes dans les cartes</span><span class="sxs-lookup"><span data-stu-id="683c5-171">Balances in cards</span></span>

- <span data-ttu-id="683c5-172">Microsoft Power BI :</span><span class="sxs-lookup"><span data-stu-id="683c5-172">Microsoft Power BI:</span></span>

    - <span data-ttu-id="683c5-173">Données qui sont affichées dans une visualisation Power BI</span><span class="sxs-lookup"><span data-stu-id="683c5-173">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="683c5-174">Visualisations des données Power BI intégrées dans le client Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="683c5-174">Data Power BI visualizations that are embedded in the Dynamics 365 Finance client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="683c5-175">Avant que la hiérarchie de la liste d’accès puisse affecter des données Power BI, la hiérarchie de la liste d’accès et la sécurité au niveau de la ligne dans Power BI doivent être jumelées.</span><span class="sxs-lookup"><span data-stu-id="683c5-175">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="683c5-176">Pour plus d’informations, voir [Paramétrer la sécurité pour le pack de contenu de gestion des coûts](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span><span class="sxs-lookup"><span data-stu-id="683c5-176">For more information, see [Set up security for Cost accounting content pack](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span></span>
> - <span data-ttu-id="683c5-177">Cette rubrique affiche les paramétrages qui doivent être effectués pour utiliser l’espace de travail **Contrôle des coûts**.</span><span class="sxs-lookup"><span data-stu-id="683c5-177">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="683c5-178">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="683c5-178">Additional resources</span></span>

- [<span data-ttu-id="683c5-179">Espace de travail de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="683c5-179">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="683c5-180">Hiérarchie des dimensions</span><span class="sxs-lookup"><span data-stu-id="683c5-180">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="683c5-181">Paramétrer la sécurité du pack de contenu Contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="683c5-181">Set up security for Cost accounting content pack</span></span>](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
