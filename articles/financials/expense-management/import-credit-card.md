---
title: "Importer et tenir à jour les transactions de carte de crédit"
description: "Cette rubrique décrit la procédure d'importation et de gestion des transactions de carte de crédit liées aux dépenses. Ces transactions peuvent être configurées en vue d'être importées automatiquement dans un calendrier récurrent, ou elles peuvent être importées manuellement en fonction des besoins."
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 63bf043124797b328116fd7951913eaeda6ff97b
ms.openlocfilehash: 3af32fbe435d92e7ca45b757414c325e6d389ac1
ms.contentlocale: fr-fr
ms.lasthandoff: 01/12/2018

---

# <a name="import-and-maintain-credit-card-transactions"></a><span data-ttu-id="2250c-104">Importer et tenir à jour les transactions de carte de crédit</span><span class="sxs-lookup"><span data-stu-id="2250c-104">Import and maintain credit card transactions</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2250c-105">Les transactions par carte de crédit liées aux dépenses peuvent être configurées de manière à être automatiquement importées selon un calendrier récurrent.</span><span class="sxs-lookup"><span data-stu-id="2250c-105">Expense-related credit card transactions can be set up so that they are automatically imported on a recurring schedule.</span></span> <span data-ttu-id="2250c-106">Sinon, les transactions peuvent être importées manuellement lorsqu'elles sont requises.</span><span class="sxs-lookup"><span data-stu-id="2250c-106">Alternatively, the transactions can be manually imported as they are required.</span></span> <span data-ttu-id="2250c-107">Les transactions de carte de crédit sont importées via l'entité de données de transactions de carte de crédit.</span><span class="sxs-lookup"><span data-stu-id="2250c-107">The credit card transactions are imported through the Credit card transactions data entity.</span></span>

<span data-ttu-id="2250c-108">Pour plus d'informations sur les entités de données, voir la rubrique [Entités de données](../../dev-itpro/data-entities/data-entities.md).</span><span class="sxs-lookup"><span data-stu-id="2250c-108">For more information about data entities, see [Data entities](../../dev-itpro/data-entities/data-entities.md).</span></span>

## <a name="import-credit-card-transactions"></a><span data-ttu-id="2250c-109">Importer les transactions de carte de crédit</span><span class="sxs-lookup"><span data-stu-id="2250c-109">Import credit card transactions</span></span>

1. <span data-ttu-id="2250c-110">Sur la page **Transactions de carte de crédit**, sélectionnez **Importer les transactions**.</span><span class="sxs-lookup"><span data-stu-id="2250c-110">On the **Credit card transactions** page, select **Import transactions**.</span></span> <span data-ttu-id="2250c-111">Si vous ouvrez le module Gestion des données pour la première fois, le système doit mettre à jour la liste des entités de données avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="2250c-111">If you’re opening data management for the first time, the system must update the list of data entities before you can continue.</span></span>
2. <span data-ttu-id="2250c-112">Dans le champ **Nom**, entrez une description unique de la tâche d'importation.</span><span class="sxs-lookup"><span data-stu-id="2250c-112">In the **Name** field, enter a unique description of the import job.</span></span>
3. <span data-ttu-id="2250c-113">Dans le champ **Format de données source**, sélectionnez le format du fichier contenant les transactions de carte de crédit à importer.</span><span class="sxs-lookup"><span data-stu-id="2250c-113">In the **Source data format** field, select the format of the file that contains the credit card transactions to import.</span></span>
4. <span data-ttu-id="2250c-114">Sélectionnez **Charger**, puis recherchez et sélectionnez le fichier à importer.</span><span class="sxs-lookup"><span data-stu-id="2250c-114">Select **Upload**, and then find and select the file to import.</span></span>
5. <span data-ttu-id="2250c-115">Une fois que le fichier a été téléchargé, validez la mise en correspondance du fichier de transactions de carte de crédit et les colonnes de l'entité de données de transactions de carte de crédit en sélectionnant le lien **Afficher le mappage** sur la vignette.</span><span class="sxs-lookup"><span data-stu-id="2250c-115">After the file has been uploaded, validate the mapping of the credit card transaction file and the columns of the Credit card transactions data entity by selecting the **View map** link on the tile.</span></span> <span data-ttu-id="2250c-116">En cas d'erreurs de mise en correspondance, ou si vous devez modifier la mise en correspondance, effectuez les modifications de mise en correspondance à partir de l'onglet **Visualisation de la mise en correspondance** ou de l'onglet **Détails de la mise en correspondance**.</span><span class="sxs-lookup"><span data-stu-id="2250c-116">If there are mapping errors, or if you must change the mapping, make the mapping changes from either the **Mapping visualization** tab or the **Mapping details** tab.</span></span>
6. <span data-ttu-id="2250c-117">Pour automatiser les transactions de carte de crédit, sélectionnez **Créer une tâche de données répétitive**.</span><span class="sxs-lookup"><span data-stu-id="2250c-117">To automate the credit card transactions, select **Create recurring data job**.</span></span> <span data-ttu-id="2250c-118">Vous pouvez alors définir la récurrence qui définit la fréquence à laquelle les transactions de carte de crédit doivent être importées.</span><span class="sxs-lookup"><span data-stu-id="2250c-118">You can then set the recurrence that defines how often credit card transactions should be imported.</span></span> <span data-ttu-id="2250c-119">Lorsque vous avez terminé, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="2250c-119">When you’ve finished, select **OK**.</span></span>
7. <span data-ttu-id="2250c-120">Pour importer le fichier sélectionné maintenant, sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="2250c-120">To import the selected file now, select **Import**.</span></span>
8. <span data-ttu-id="2250c-121">Si des erreurs surviennent lors de l'importation, vous pouvez afficher le journal des exécutions ou les données intermédiaires pour voir les erreurs que vous devez corriger pour garantir une importation réussie.</span><span class="sxs-lookup"><span data-stu-id="2250c-121">If errors occur during the import, you can view the execution log or staging data to see the errors that you must fix to help guarantee a successful import.</span></span>

> [!NOTE]
> <span data-ttu-id="2250c-122">Si vous devez importer plusieurs formats de fichier, vous devez créer des tâches d'importation distinctes pour chaque type de format.</span><span class="sxs-lookup"><span data-stu-id="2250c-122">If you must import more than one file format, you must create separate import jobs for each format type.</span></span>

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a><span data-ttu-id="2250c-123">Réaffecter les transactions de carte de crédit pour les employés dont le contrat est terminé</span><span class="sxs-lookup"><span data-stu-id="2250c-123">Reassign the credit card transactions for terminated employees</span></span>

<span data-ttu-id="2250c-124">Une fois qu'un enregistrement d'employé est terminé, le compte des services de domaine Active Directory (AD DS) de l'employé est désactivé.</span><span class="sxs-lookup"><span data-stu-id="2250c-124">After an employee record is terminated, the employee’s Active Directory Domain Services (AD DS) account is disabled.</span></span> <span data-ttu-id="2250c-125">Toutefois, il peut y avoir des transactions de carte de crédit actives qui doivent encore faire l'objet d'une dépense et d'un remboursement.</span><span class="sxs-lookup"><span data-stu-id="2250c-125">However, there might be active credit card transactions that must still be expensed and reimbursed.</span></span> <span data-ttu-id="2250c-126">Dans la page **Transactions de carte de crédit**, vous pouvez réaffecter à l'employé toute transaction de carte de crédit pour laquelle le contrat de l'employé associé a pris fin.</span><span class="sxs-lookup"><span data-stu-id="2250c-126">From the **Credit card transactions** page, you can reassign the employee for any credit card transaction where the associated employee has been terminated.</span></span>

<span data-ttu-id="2250c-127">Sélectionnez une ou plusieurs transactions de carte de crédit, puis sélectionnez **Réaffecter les transactions**.</span><span class="sxs-lookup"><span data-stu-id="2250c-127">Select one or more credit card transactions, and then select **Reassign transactions**.</span></span> <span data-ttu-id="2250c-128">Vous pouvez ensuite sélectionner un autre employé auquel affecter les transactions de carte de crédit.</span><span class="sxs-lookup"><span data-stu-id="2250c-128">You can then select another employee to assign the credit card transactions to.</span></span> <span data-ttu-id="2250c-129">Une fois les transactions de carte de crédit réaffectées, elles peuvent être sélectionnées pour un rapport de dépenses et payées selon le processus habituel de remboursement des dépenses.</span><span class="sxs-lookup"><span data-stu-id="2250c-129">After the credit card transactions have been reassigned, they can be selected for an expense report and paid through the usual process for expense report reimbursement.</span></span>

