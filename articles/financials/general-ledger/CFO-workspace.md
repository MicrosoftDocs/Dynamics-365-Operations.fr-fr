---
title: "Ajouter des dimensions financières à l'espace de travail CFO"
description: "Cette rubrique explique comment ajouter des dimensions financières à l'espace de travail CFO, afin qu'elles puissent être utilisées pour les états comptables et budgétaires."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: a15414eff99751d4e77e5b3bf315a556efb7ad5d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="add-financial-dimensions-to-the-cfo-workspace"></a><span data-ttu-id="a8ada-103">Ajouter des dimensions financières à l'espace de travail CFO</span><span class="sxs-lookup"><span data-stu-id="a8ada-103">Add financial dimensions to the CFO workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8ada-104">Cette rubrique explique comment ajouter des dimensions financières à l'espace de travail Directeur financier, afin qu'elles puissent être utilisées pour les états comptables et budgétaires.</span><span class="sxs-lookup"><span data-stu-id="a8ada-104">This topic explains how to add financial dimensions to the Chief Financial Officer (CFO) workspace, so that they can be used for the ledger and budget reports.</span></span> <span data-ttu-id="a8ada-105">L'espace de travail CFO contient un onglet **Vue d'ensemble** et un onglet **Rapport financier**. Les états de ces deux onglets sont soutenus par deux mesures : LedgerActivityMeasure et BudgetActivityMeasure.</span><span class="sxs-lookup"><span data-stu-id="a8ada-105">The CFO workspace has an **Overview** tab and a **Financial** tab. The reports on these two tabs are backed by two measures: LedgerActivityMeasure and BudgetActivityMeasure.</span></span> <span data-ttu-id="a8ada-106">Dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Juillet 2017), il existe une relation entre ces deux mesures et l'entité DimensionCombinationEntity.</span><span class="sxs-lookup"><span data-stu-id="a8ada-106">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), there is a relation between those two measures and the DimensionCombinationEntity entity.</span></span> <span data-ttu-id="a8ada-107">Par conséquent, vous pouvez sélectionner des dimensions.</span><span class="sxs-lookup"><span data-stu-id="a8ada-107">Therefore, you can select dimensions.</span></span>

1. <span data-ttu-id="a8ada-108">Dans Finance and Operations, dans la page **Magasin des entités**, mettez à jour les mesures **LedgerActivityMeasure** et **BudgetActivityMeasure**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-108">In Finance and Operations, on the **Entity Store** page, update the **LedgerActivityMeasure** and the **BudgetActivityMeasure** measures.</span></span>
2. <span data-ttu-id="a8ada-109">Dans Microsoft Visual Studio, ouvrez l'Explorateur d'application et recherchez **LedgerCFO**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-109">In Microsoft Visual Studio, open Application Explorer, and search for **LedgerCFO**.</span></span>
3. <span data-ttu-id="a8ada-110">Sous **Ressources**, ouvrez **LedgerCFOWorkspacePBIX**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-110">Under **Resources**, open **LedgerCFOWorkspacePBIX**.</span></span>
4. <span data-ttu-id="a8ada-111">Lorsque la ressource s'ouvre dans Microsoft Power BI Desktop, sélectionnez **Obtenir des données**, **Base de données SQL Server**, puis **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-111">When the resource opens in Microsoft Power BI desktop, select **Get Data**, select **SQL Server database**, and then select **Connect**.</span></span>
5. <span data-ttu-id="a8ada-112">Entrez le nom du serveur, puis **AxDW** comme base de données.</span><span class="sxs-lookup"><span data-stu-id="a8ada-112">Enter the server name, and enter **AxDW** as the database.</span></span> <span data-ttu-id="a8ada-113">Sélectionnez **DirectQuery**, puis **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-113">Select **DirectQuery**, and then select **OK**.</span></span>
6. <span data-ttu-id="a8ada-114">Recherchez et sélectionnez **LedgerActivityMeasure\_DimensionCombination**, puis sélectionnez **Charger**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-114">Search for and select **LedgerActivityMeasure\_DimensionCombination**, and then select **Load**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a8ada-115">Dans la liste **Champs**, renommez la table **Dimensions financières** pour l'identifier facilement.</span><span class="sxs-lookup"><span data-stu-id="a8ada-115">In the **Fields** list, rename the table **Financial dimensions**, so that it's easy to identify.</span></span>

7. <span data-ttu-id="a8ada-116">Sélectionnez **Gérer les relations**, puis **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-116">Select **Manage Relationships**, and then select **New**.</span></span>
8. <span data-ttu-id="a8ada-117">Dans le premier champ, sélectionnez **Activités liées à la comptabilité**, puis **LedgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-117">In the first field, select **General Ledger Activities**, and then select **LedgerDimension**.</span></span>
9. <span data-ttu-id="a8ada-118">Dans le deuxième champ, sélectionnez **LedgerActivityMeasure\_DimensionCombination** (ou **Dimensions financières** si vous avez renommé la table).</span><span class="sxs-lookup"><span data-stu-id="a8ada-118">In the second field, select **LedgerActivityMeasure\_DimensionCombination** (or **Financial dimensions** if you renamed the table).</span></span> <span data-ttu-id="a8ada-119">Sélectionnez l'en-tête **DimensionCombinationRECID**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-119">Select the  **DimensionCombinationRECID** header.</span></span>
10. <span data-ttu-id="a8ada-120">Dans le champ **Cardinalité**, sélectionnez **Plusieurs à un**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-120">In the **Cardinality** field, select **Many to One**.</span></span>
11. <span data-ttu-id="a8ada-121">Définissez la valeur **Direction de filtre croisé** sur **Unique**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-121">Change the **Cross filter direction** value to **Single**.</span></span>
12. <span data-ttu-id="a8ada-122">Sélectionnez **Rendre cette relation active** et **Supposer l'intégrité référentielle**, sélectionnez **OK**, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-122">Select both **Make this relationship active** and **Assume referential integrity**, select **OK**, and then select **Close**.</span></span>

    <span data-ttu-id="a8ada-123">[![Créer une relation](./media/Create-relationship.png)](./media/Create-relationship.png)</span><span class="sxs-lookup"><span data-stu-id="a8ada-123">[![Create a relationship](./media/Create-relationship.png)](./media/Create-relationship.png)</span></span>

13. <span data-ttu-id="a8ada-124">Dans la liste **Champs**, la table et les dimensions financières disponibles doivent s'afficher.</span><span class="sxs-lookup"><span data-stu-id="a8ada-124">In the **Fields** list, you should see the table and the available financial dimensions.</span></span> <span data-ttu-id="a8ada-125">Faites glisser les dimensions financières souhaitées vers les filtres au niveau de l'état.</span><span class="sxs-lookup"><span data-stu-id="a8ada-125">Drag the financial dimensions that you want to the report-level filters.</span></span>
14. <span data-ttu-id="a8ada-126">Enregistrez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="a8ada-126">Save your changes.</span></span>
15. <span data-ttu-id="a8ada-127">Dans l'arbre d'objets d'application (AOT), cliquez avec le bouton droit sur votre projet, puis sélectionnez **Synchroniser**.</span><span class="sxs-lookup"><span data-stu-id="a8ada-127">In the Application Object Tree (AOT), right-click your project, and then select **Synchronize**.</span></span>
16. <span data-ttu-id="a8ada-128">Générez votre projet, puis ouvrez l'application pour afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="a8ada-128">Build your project, and then open the application to view the results.</span></span>

    <span data-ttu-id="a8ada-129">[![Espace de travail terminé](./media/workspace.png)](./media/workspace.png)</span><span class="sxs-lookup"><span data-stu-id="a8ada-129">[![Completed workspace](./media/workspace.png)](./media/workspace.png)</span></span>

