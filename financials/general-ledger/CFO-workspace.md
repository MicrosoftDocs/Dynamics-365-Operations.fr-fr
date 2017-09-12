---
title: "Ajouter des dimensions financières à l'espace de travail CFO"
description: "Cette rubrique explique comment ajouter des dimensions financières à l'espace de travail CFO, afin qu'elles puissent être utilisées pour les états comptables et budgétaires."
author: aolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.2.0
ms.translationtype: HT
ms.sourcegitcommit: 9953d2f29a67b35f4bb43f577df1c4d910e379a1
ms.openlocfilehash: 05fd7ce5293b3a300aabc073a6e492c5804d1897
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---

# <a name="add-financial-dimensions-to-the-cfo-workspace"></a><span data-ttu-id="af146-103">Ajouter des dimensions financières à l'espace de travail CFO</span><span class="sxs-lookup"><span data-stu-id="af146-103">Add financial dimensions to the CFO workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="af146-104">Cette rubrique explique comment ajouter des dimensions financières à l'espace de travail Directeur financier, afin qu'elles puissent être utilisées pour les états comptables et budgétaires.</span><span class="sxs-lookup"><span data-stu-id="af146-104">This topic explains how to add financial dimensions to the Chief Financial Officer (CFO) workspace, so that they can be used for the ledger and budget reports.</span></span> <span data-ttu-id="af146-105">L'espace de travail CFO comprend un onglet **Vue d'ensemble** et un onglet **Financier**.</span><span class="sxs-lookup"><span data-stu-id="af146-105">The CFO workspace has an **Overview** tab and a **Financial** tab.</span></span> <span data-ttu-id="af146-106">Les états de ces deux onglets sont soutenus par deux mesures : LedgerActivityMeasure et BudgetActivityMeasure.</span><span class="sxs-lookup"><span data-stu-id="af146-106">The reports on these two tabs are backed by two measures: LedgerActivityMeasure and BudgetActivityMeasure.</span></span> <span data-ttu-id="af146-107">Dans la mise à jour de juillet 2017 de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, il existe une relation entre ces deux mesures et l'entité DimensionCombinationEntity.</span><span class="sxs-lookup"><span data-stu-id="af146-107">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition July 2017 update, there is a relation between those two measures and the DimensionCombinationEntity entity.</span></span> <span data-ttu-id="af146-108">Par conséquent, vous pouvez sélectionner des dimensions.</span><span class="sxs-lookup"><span data-stu-id="af146-108">Therefore, you can select dimensions.</span></span>

1. <span data-ttu-id="af146-109">Dans Finance and Operations, dans la page **Magasin des entités**, mettez à jour les mesures **LedgerActivityMeasure** et **BudgetActivityMeasure**.</span><span class="sxs-lookup"><span data-stu-id="af146-109">In Finance and Operations, on the **Entity Store** page, update the **LedgerActivityMeasure** and the **BudgetActivityMeasure** measures.</span></span>
2. <span data-ttu-id="af146-110">Dans Microsoft Visual Studio, ouvrez l'Explorateur d'application et recherchez **LedgerCFO**.</span><span class="sxs-lookup"><span data-stu-id="af146-110">In Microsoft Visual Studio, open Application Explorer, and search for **LedgerCFO**.</span></span>
3. <span data-ttu-id="af146-111">Sous **Ressources**, ouvrez **LedgerCFOWorkspacePBIX**.</span><span class="sxs-lookup"><span data-stu-id="af146-111">Under **Resources**, open **LedgerCFOWorkspacePBIX**.</span></span>
4. <span data-ttu-id="af146-112">Lorsque la ressource s'ouvre dans Microsoft Power BI Desktop, sélectionnez **Obtenir des données**, **Base de données SQL Server**, puis **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="af146-112">When the resource opens in Microsoft Power BI desktop, select **Get Data**, select **SQL Server database**, and then select **Connect**.</span></span>
5. <span data-ttu-id="af146-113">Entrez le nom du serveur, puis **AxDW** comme base de données.</span><span class="sxs-lookup"><span data-stu-id="af146-113">Enter the server name, and enter **AxDW** as the database.</span></span> <span data-ttu-id="af146-114">Sélectionnez **DirectQuery**, puis **OK**.</span><span class="sxs-lookup"><span data-stu-id="af146-114">Select **DirectQuery**, and then select **OK**.</span></span>
6. <span data-ttu-id="af146-115">Recherchez et sélectionnez **LedgerActivityMeasure\_DimensionCombination**, puis sélectionnez **Charger**.</span><span class="sxs-lookup"><span data-stu-id="af146-115">Search for and select **LedgerActivityMeasure\_DimensionCombination**, and then select **Load**.</span></span>

    > [!TIP]
    > <span data-ttu-id="af146-116">Dans la liste **Champs**, renommez la table **Dimensions financières** pour l'identifier facilement.</span><span class="sxs-lookup"><span data-stu-id="af146-116">In the **Fields** list, rename the table **Financial dimensions**, so that it's easy to identify.</span></span>

7. <span data-ttu-id="af146-117">Sélectionnez **Gérer les relations**, puis **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="af146-117">Select **Manage Relationships**, and then select **New**.</span></span>
8. <span data-ttu-id="af146-118">Dans le premier champ, sélectionnez **Activités liées à la comptabilité**, puis **LedgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="af146-118">In the first field, select **General Ledger Activities**, and then select **LedgerDimension**.</span></span>
9. <span data-ttu-id="af146-119">Dans le deuxième champ, sélectionnez **LedgerActivityMeasure\_DimensionCombination** (ou **Dimensions financières** si vous avez renommé la table).</span><span class="sxs-lookup"><span data-stu-id="af146-119">In the second field, select **LedgerActivityMeasure\_DimensionCombination** (or **Financial dimensions** if you renamed the table).</span></span> <span data-ttu-id="af146-120">Sélectionnez l'en-tête **DimensionCombinationRECID**.</span><span class="sxs-lookup"><span data-stu-id="af146-120">Select the  **DimensionCombinationRECID** header.</span></span>
10. <span data-ttu-id="af146-121">Dans le champ **Cardinalité**, sélectionnez **Plusieurs à un**.</span><span class="sxs-lookup"><span data-stu-id="af146-121">In the **Cardinality** field, select **Many to One**.</span></span>
11. <span data-ttu-id="af146-122">Définissez la valeur **Direction de filtre croisé** sur **Unique**.</span><span class="sxs-lookup"><span data-stu-id="af146-122">Change the **Cross filter direction** value to **Single**.</span></span>
12. <span data-ttu-id="af146-123">Sélectionnez **Rendre cette relation active** et **Supposer l'intégrité référentielle**, sélectionnez **OK**, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="af146-123">Select both **Make this relationship active** and **Assume referential integrity**, select **OK**, and then select **Close**.</span></span>

    <span data-ttu-id="af146-124">[![Créer une relation](./media/Create-relationship.png)](./media/Create-relationship.png)</span><span class="sxs-lookup"><span data-stu-id="af146-124">[![Create a relationship](./media/Create-relationship.png)](./media/Create-relationship.png)</span></span>

13. <span data-ttu-id="af146-125">Dans la liste **Champs**, la table et les dimensions financières disponibles doivent s'afficher.</span><span class="sxs-lookup"><span data-stu-id="af146-125">In the **Fields** list, you should see the table and the available financial dimensions.</span></span> <span data-ttu-id="af146-126">Faites glisser les dimensions financières souhaitées vers les filtres au niveau de l'état.</span><span class="sxs-lookup"><span data-stu-id="af146-126">Drag the financial dimensions that you want to the report-level filters.</span></span>
14. <span data-ttu-id="af146-127">Enregistrez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="af146-127">Save your changes.</span></span>
15. <span data-ttu-id="af146-128">Dans l'arbre d'objets d'application (AOT), cliquez avec le bouton droit sur votre projet, puis sélectionnez **Synchroniser**.</span><span class="sxs-lookup"><span data-stu-id="af146-128">In the Application Object Tree (AOT), right-click your project, and then select **Synchronize**.</span></span>
16. <span data-ttu-id="af146-129">Générez votre projet, puis ouvrez l'application pour afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="af146-129">Build your project, and then open the application to view the results.</span></span>

    <span data-ttu-id="af146-130">[![Espace de travail terminé](./media/workspace.png)](./media/workspace.png)</span><span class="sxs-lookup"><span data-stu-id="af146-130">[![Completed workspace](./media/workspace.png)](./media/workspace.png)</span></span>

