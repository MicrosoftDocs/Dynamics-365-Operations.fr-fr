---
title: Exportation des données d’une filiale dans des fichiers
description: Cette rubrique explique comment préparer l’exportation de données à partir de Microsoft Dynamics 365 Finance et comment les importer dans une entité juridique consolidée.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: bae0a28c59f327e47378eef6392d5e304bbde9a8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826176"
---
# <a name="export-subsidiary-data-to-files"></a><span data-ttu-id="8ab5e-103">Exportation des données d’une filiale dans des fichiers</span><span class="sxs-lookup"><span data-stu-id="8ab5e-103">Export subsidiary data to files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ab5e-104">Vous devez utiliser la page **Exporter** (**Administration du système \> Espaces de travail \> Importer/Exporter**) pour préparer l’exportation des données d’une filiale vers des fichiers qui peuvent ensuite être importés dans une entité juridique consolidée.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-104">You use the **Export** page (**System administration \> Workspaces \> Import/Export**) to prepare to export subsidiary data to files that can then be imported into a consolidated legal entity.</span></span> <span data-ttu-id="8ab5e-105">Pour plus d’informations sur les processus d’importation et d’exportation, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="8ab5e-105">For more information about the import and export processes, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>

1. <span data-ttu-id="8ab5e-106">Créez une entité juridique pour le processus de consolidation.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-106">Create a legal entity for the consolidation process.</span></span> <span data-ttu-id="8ab5e-107">Pour plus d’informations sur la création d’entités juridiques, consultez [Créer une entité juridique](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span><span class="sxs-lookup"><span data-stu-id="8ab5e-107">For information about how to create legal entities, see [Create a legal entity](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span></span> <span data-ttu-id="8ab5e-108">Pour plus d’informations, voir [Préparer une entité juridique en vue de son utilisation dans le processus de consolidation](prepare-company-for-consolidation.md) et [Paramétrer une entité juridique filiale pour la consolidation](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="8ab5e-108">For more information, see [Prepare a legal entity for use in the consolidation process](prepare-company-for-consolidation.md) and [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span> 

2. <span data-ttu-id="8ab5e-109">Accédez à **Consolidations \> Exporter soldes de la société**.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-109">Go to **Consolidations \> Export company balances**.</span></span> <span data-ttu-id="8ab5e-110">Sur la page **Exporter soldes de la société**, sur l’onglet **Critères**, spécifiez les détails de la consolidation en définissant les champs suivants.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-110">On the **Export company balances** page, on the **Criteria** tab, specify the details of the consolidation by setting the following fields.</span></span>

    | <span data-ttu-id="8ab5e-111">Champ</span><span class="sxs-lookup"><span data-stu-id="8ab5e-111">Field</span></span>                             | <span data-ttu-id="8ab5e-112">Description</span><span class="sxs-lookup"><span data-stu-id="8ab5e-112">Description</span></span> |
    |-----------------------------------|-------|
    | <span data-ttu-id="8ab5e-113">Compte principal</span><span class="sxs-lookup"><span data-stu-id="8ab5e-113">Main account</span></span>                      | <span data-ttu-id="8ab5e-114">Spécifiez les comptes à consolider.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-114">Specify the accounts to consolidate.</span></span> <span data-ttu-id="8ab5e-115">Pour inclure tous les comptes, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-115">To include all accounts, leave this field blank.</span></span> |
    | <span data-ttu-id="8ab5e-116">Utiliser le compte de consolidation</span><span class="sxs-lookup"><span data-stu-id="8ab5e-116">Use consolidation account</span></span>         | <span data-ttu-id="8ab5e-117">Si vous avez spécifié des comptes de consolidation, définissez cette option sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-117">If you've specified consolidation accounts, set this option to **Yes**.</span></span> |
    | <span data-ttu-id="8ab5e-118">Sélectionner le compte de consolidation dans</span><span class="sxs-lookup"><span data-stu-id="8ab5e-118">Select consolidation account from</span></span> | <span data-ttu-id="8ab5e-119">Sélectionnez soit **Compte principal** ou **Groupe de comptes de consolidation**.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-119">Select either **Main account** or **Consolidation account group**.</span></span> |
    | <span data-ttu-id="8ab5e-120">Groupe de comptes de consolidation</span><span class="sxs-lookup"><span data-stu-id="8ab5e-120">Consolidation account group</span></span>       | <span data-ttu-id="8ab5e-121">Sélectionnez un groupe de comptes de consolidation pour le compte de consolidation que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-121">Select a consolidation account group for the consolidation account that you selected.</span></span> |
    | <span data-ttu-id="8ab5e-122">Période de consolidation</span><span class="sxs-lookup"><span data-stu-id="8ab5e-122">Consolidation period</span></span>              | <span data-ttu-id="8ab5e-123">Spécifiez les dates « De » et « À » pour la consolidation.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-123">Specify "from" and "to" dates for the consolidation.</span></span> |
    | <span data-ttu-id="8ab5e-124">Inclure les montants réels</span><span class="sxs-lookup"><span data-stu-id="8ab5e-124">Include actual amounts</span></span>            | <span data-ttu-id="8ab5e-125">Définissez cette option sur **Oui** pour inclure les montants réels.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-125">Set this option to **Yes** to include actual amounts.</span></span> |
    | <span data-ttu-id="8ab5e-126">Inclure les montants du budget</span><span class="sxs-lookup"><span data-stu-id="8ab5e-126">Include budget amounts</span></span>            | <span data-ttu-id="8ab5e-127">Définissez cette option sur **Oui** pour inclure les montants budgétaires dans les consolidations.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-127">Set this option to **Yes** to include budget amounts in consolidations.</span></span> |
    | <span data-ttu-id="8ab5e-128">Modèles de budget</span><span class="sxs-lookup"><span data-stu-id="8ab5e-128">Budget models</span></span>                     | <span data-ttu-id="8ab5e-129">Spécifiez le modèle de budget à inclure.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-129">Specify the budget model to include.</span></span> |

3. <span data-ttu-id="8ab5e-130">Sous l’onglet **Dimensions financières**, spécifiez les détails de la consolidation :</span><span class="sxs-lookup"><span data-stu-id="8ab5e-130">On the **Financial dimensions** tab, specify the details of the consolidation:</span></span>

    - <span data-ttu-id="8ab5e-131">Spécifiez les informations de dimension financière qui doivent être transférées des transactions des comptes de filiale vers les transactions de l’entité juridique consolidée.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-131">Specify the financial dimension information that should be transferred from the transactions in the subsidiary accounts to the transactions in the consolidated legal entity.</span></span>
    - <span data-ttu-id="8ab5e-132">Sélectionnez les dimensions financières dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-132">Select financial dimensions in the list.</span></span>
    - <span data-ttu-id="8ab5e-133">Identifiez la spécification correcte pour chaque dimension financière consolidée.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-133">Identify the correct specification for each financial dimension that is consolidated.</span></span> <span data-ttu-id="8ab5e-134">Les options disponibles comprennent **Dimension**, **Dimension de groupe**, **Comptes société**, et **Compte**.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-134">The available options include **Dimension**, **Group dimension**, **Company accounts**, and **Account**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="8ab5e-135">L’option **Dimension de groupe** vous permet de définir la valeur de dimension utilisée par le groupe de sociétés en cours de consolidation.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-135">The **Group dimension** option lets you define the dimension value that is used by the group of companies that is being consolidated.</span></span>

    - <span data-ttu-id="8ab5e-136">Spécifiez l’ordre des segments dans lequel consolider.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-136">Specify the segment order to consolidate in.</span></span>

4. <span data-ttu-id="8ab5e-137">Sur l’onglet **Entités juridiques**, procédez comme suit pour spécifier l’entité juridique que vous exportez :</span><span class="sxs-lookup"><span data-stu-id="8ab5e-137">On the **Legal entities** tab, follow these steps to specify the legal entity that you're exporting:</span></span>

    1. <span data-ttu-id="8ab5e-138">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-138">Select **New**.</span></span>
    2. <span data-ttu-id="8ab5e-139">Entrez l’entité juridique dans le champ **Entité juridique source**.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-139">In the **Source legal entity** field, enter the legal entity.</span></span>

        <span data-ttu-id="8ab5e-140">Si un même critère s’applique à plusieurs filiales d’une même base de données, vous pouvez transférer les données de ces filiales afin de séparer les fichiers d’exportation en une seule opération :</span><span class="sxs-lookup"><span data-stu-id="8ab5e-140">If the same criteria apply to several subsidiaries that are in the same database, you can transfer data from those subsidiaries to separate export files in a single operation:</span></span>

        1. <span data-ttu-id="8ab5e-141">Créez une ligne pour chaque entité juridique filiale dont les comptes doivent être exportés vers des fichiers.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-141">Create a line for each subsidiary legal entity for which accounts should be exported to files.</span></span> <span data-ttu-id="8ab5e-142">Ces fichiers seront importés dans l’entité juridique consolidée ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-142">These files will be imported into the consolidated legal entity later.</span></span>
        2. <span data-ttu-id="8ab5e-143">Pour chaque filiale, entrez le nom de la filiale et le nom du fichier d’exportation qui sera créé au cours de la tâche d’exportation.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-143">For each subsidiary, enter the subsidiary name and the name of the export file that will be created during the export job.</span></span>

    3. <span data-ttu-id="8ab5e-144">Dans le champ **Type de compte des différences de conversion**, sélectionnez **Résultat** ou **Bilan**.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-144">In **Account type of conversion differences** field, Select **Profit and loss** or **Balance sheet**.</span></span>
    4. <span data-ttu-id="8ab5e-145">Entrez un nom de fichier pour le fichier d’exportation qui sera créé.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-145">Enter a file name for the export file that will be created.</span></span>

5. <span data-ttu-id="8ab5e-146">Sélectionnez **OK** pour lancer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-146">Select **OK** to run the export.</span></span>

<span data-ttu-id="8ab5e-147">À la fin de l’exportation, vous recevez un message montrant le nombre d’enregistrements sauvegardés dans chaque fichier.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-147">When the export is completed, you receive a message that shows the number of records that were saved in each file.</span></span> <span data-ttu-id="8ab5e-148">Vous pouvez ensuite importer les fichiers dans l’entité juridique consolidée.</span><span class="sxs-lookup"><span data-stu-id="8ab5e-148">You can then import the files into the consolidated legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]