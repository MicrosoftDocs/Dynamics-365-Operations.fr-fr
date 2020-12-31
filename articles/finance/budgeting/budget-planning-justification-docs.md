---
title: Documents justificatifs de planification budgétaire
description: Les documents justificatifs fournissent des informations narratives pour ceux qui demandent un budget pour expliquer pourquoi un budget spécifique est nécessaire.
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 321da6643b421070ddd9f32bddd3e8d72f0adb86
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443295"
---
# <a name="budget-planning-justification-documents"></a><span data-ttu-id="e8888-103">Documents justificatifs de planification budgétaire</span><span class="sxs-lookup"><span data-stu-id="e8888-103">Budget planning justification documents</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8888-104">Les documents justificatifs fournissent des informations narratives pour ceux qui demandent un budget pour expliquer pourquoi un budget spécifique est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e8888-104">Justification documents provide a narrative for those requesting a budget to explain why a specific budget is necessary.</span></span> 

<span data-ttu-id="e8888-105">Un modèle de plan budgétaire est créé par le responsable du budget dans Microsoft Word et affecté au processus de planification budgétaire actuel.</span><span class="sxs-lookup"><span data-stu-id="e8888-105">A budget plan template is created by the budget manager in Microsoft Word and assigned to the current budget planning process.</span></span> <span data-ttu-id="e8888-106">Les propriétaires de budget peuvent alors ouvrir le modèle et renseigner automatiquement les données dans Word selon leur demande de budget.</span><span class="sxs-lookup"><span data-stu-id="e8888-106">Budget owners can then open the template and have data automatically populated in Word based on their budget request.</span></span> <span data-ttu-id="e8888-107">Ils peuvent ensuite ajouter du texte ou des données supplémentaires avant d’enregistrer et de joindre leur document justificatif personnalisé à leur plan budgétaire.</span><span class="sxs-lookup"><span data-stu-id="e8888-107">They can then add additional text or data prior to saving and attaching their personalized justification document to their budget plan.</span></span>

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a><span data-ttu-id="e8888-108">Configurer le complément Office Microsoft Dynamics pour Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="e8888-108">Set up Microsoft Dynamics Office Add-in for Microsoft Word</span></span>

1.  <span data-ttu-id="e8888-109">Ouvrez un nouveau document Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="e8888-109">Open a new Microsoft Word document.</span></span>
2.  <span data-ttu-id="e8888-110">Cliquez sur **Insérer** sur le ruban, puis sur **Magasin**.</span><span class="sxs-lookup"><span data-stu-id="e8888-110">Click **Insert** on the ribbon, and click **Store**.</span></span>
3.  <span data-ttu-id="e8888-111">Recherchez le complément Office Microsoft Dynamics et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e8888-111">Search for Microsoft Dynamics Office Add-in and click **Add**.</span></span>
4.  <span data-ttu-id="e8888-112">Dans Word, dans le volet droit, cliquez sur **Ajouter des informations sur le serveur**.</span><span class="sxs-lookup"><span data-stu-id="e8888-112">In Word, in the right pane, click **Add server information**.</span></span>
5.  <span data-ttu-id="e8888-113">Tapez ou collez l’URL du serveur et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8888-113">Type or paste the server URL and click **OK**.</span></span>

##### <a name="define-the-justification-template-in-microsoft-word"></a><span data-ttu-id="e8888-114">Définir le modèle de justification dans Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="e8888-114">Define the Justification template in Microsoft Word</span></span>

1.  <span data-ttu-id="e8888-115">Cliquez sur **Créer** dans le complément Office Microsoft Dynamics une fois que vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="e8888-115">Click **Design** in the Microsoft Dynamics Office Add-in after you’ve logged in.</span></span>
2.  <span data-ttu-id="e8888-116">Pour les informations d’en-tête, utilisez le bouton **Ajouter des champs**.</span><span class="sxs-lookup"><span data-stu-id="e8888-116">For header information, use the **Add fields** button.</span></span>
3.  <span data-ttu-id="e8888-117">Sélectionnez la source de données d’entité BudgetPlanJustification, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e8888-117">Select the entity data source of BudgetPlanJustification, and click **Next**.</span></span> <span data-ttu-id="e8888-118">**Remarque :** cette entité est requise pour tout document justificatif.</span><span class="sxs-lookup"><span data-stu-id="e8888-118">**Note:** This entity is required for any justification document.</span></span> <span data-ttu-id="e8888-119">D’autres entités peuvent être utilisées mais le téléchargement vers Microsoft Dynamics 365 Finance échouera si cette entité n’est pas incluse.</span><span class="sxs-lookup"><span data-stu-id="e8888-119">Other entities can be used but the upload back to Microsoft Dynamics 365 Finance will fail if this entity isn’t included.</span></span>
4.  <span data-ttu-id="e8888-120">Ajoutez les étiquettes et les valeurs BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter et DocumentNumber dans le document Word.</span><span class="sxs-lookup"><span data-stu-id="e8888-120">Add the BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter, and DocumentNumber labels and values in the Word document.</span></span> <span data-ttu-id="e8888-121">**Remarque :** vous pouvez utiliser vos propres étiquettes personnalisées au lieu des étiquettes standard, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e8888-121">**Note:** You can use your own custom labels, rather than the standard labels, if needed.</span></span>
5.  <span data-ttu-id="e8888-122">Cliquez sur **Terminé** pour terminer la section d’en-tête.</span><span class="sxs-lookup"><span data-stu-id="e8888-122">Click **Done** to complete the header section.</span></span>
6.  <span data-ttu-id="e8888-123">Pour le détail au niveau de la ligne des montants du plan budgétaire, cliquez sur **Ajouter une table**.</span><span class="sxs-lookup"><span data-stu-id="e8888-123">For line level detail of budget plan amounts, click **Add table**.</span></span>
7.  <span data-ttu-id="e8888-124">Sélectionnez à nouveau la source de données d’entité BudgetPlanJustification, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e8888-124">Again, select the entity data source of BudgetPlanJustification, and click **Next**.</span></span>
8.  <span data-ttu-id="e8888-125">Ajoutez des champs pour EffectiveDate, ScenarioName, AccountDisplayValue et AccountingCurrencyExpenseAmount.</span><span class="sxs-lookup"><span data-stu-id="e8888-125">Add fields for EffectiveDate, ScenarioName, AccountDisplayValue, and AccountingCurrencyExpenseAmount.</span></span> <span data-ttu-id="e8888-126">**Remarque :** si vous souhaitez ajouter des commentaires dans les lignes de plan budgétaire individuelles, ceux-ci peuvent être ajoutés à la table ici.</span><span class="sxs-lookup"><span data-stu-id="e8888-126">**Note:** If comments are available to add within individual budget plan lines, those can be added to the table here.</span></span>
9.  <span data-ttu-id="e8888-127">Ajoutez des instructions supplémentaires à fournir à l’utilisateur final, puis appliquez la mise en forme ou le style nécessaire au document.</span><span class="sxs-lookup"><span data-stu-id="e8888-127">Add any additional instructions to provide to the end user, and perform any necessary formatting or styling to the document.</span></span>
10. <span data-ttu-id="e8888-128">Enregistrez le document sur votre ordinateur local et fermez le fichier avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="e8888-128">Save the document to your local computer and close the file before continuing.</span></span>

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a><span data-ttu-id="e8888-129">Paramétrer le processus de planification budgétaire pour utiliser le modèle de justification</span><span class="sxs-lookup"><span data-stu-id="e8888-129">Set up the Budget planning process to use the Justification template</span></span>

1.  <span data-ttu-id="e8888-130">Accédez à **Budgétisation** &gt; **Paramétrage** &gt; **Planification budgétaire** &gt; **Modèles de document justificatif**.</span><span class="sxs-lookup"><span data-stu-id="e8888-130">Go to **Budgeting** &gt; **Setup** &gt; **Budget planning** &gt; **Justification document templates**.</span></span>
2.  <span data-ttu-id="e8888-131">Cliquez sur **Nouveau** et accédez à votre document Microsoft Word nouvellement créé.</span><span class="sxs-lookup"><span data-stu-id="e8888-131">Click **New** and browse to your newly created Microsoft Word document.</span></span>
3.  <span data-ttu-id="e8888-132">Entrez un nom complet et une description pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="e8888-132">Enter a template display name and description.</span></span> <span data-ttu-id="e8888-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8888-133">Click **OK**.</span></span>
4.  <span data-ttu-id="e8888-134">Accédez à **Budgétisation** &gt; **Paramétrage** &gt; **Planification** **budgétaire** &gt; **Processus de planification budgétaire**.</span><span class="sxs-lookup"><span data-stu-id="e8888-134">Go to **Budgeting** &gt; **Setup** &gt; **Budget** **planning** &gt; **Budget planning process**.</span></span>
5.  <span data-ttu-id="e8888-135">Sélectionnez le processus dans lequel le modèle de justification doit être utilisé, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e8888-135">Select the process where the justification template should be used, and click **Edit**.</span></span>
6.  <span data-ttu-id="e8888-136">Dans le champ **Modèle de document de justificatif**, sélectionnez le modèle approprié et enregistrez-le.</span><span class="sxs-lookup"><span data-stu-id="e8888-136">In the **Justification document template** field, select the appropriate template and save.</span></span>

##### <a name="edit-and-save-personalized-justification-documents"></a><span data-ttu-id="e8888-137">Modifier et enregistrer les documents justificatifs personnalisés</span><span class="sxs-lookup"><span data-stu-id="e8888-137">Edit and save personalized justification documents</span></span>

1.  <span data-ttu-id="e8888-138">Créez un nouveau plan budgétaire ou ouvrez un plan budgétaire existant.</span><span class="sxs-lookup"><span data-stu-id="e8888-138">Create a new budget plan or open an existing budget plan.</span></span>
2.  <span data-ttu-id="e8888-139">Dans le menu déroulant **Justification**, sélectionnez **Créer une justification**.</span><span class="sxs-lookup"><span data-stu-id="e8888-139">In the **Justification** drop-down menu, select **Create new justification**.</span></span>
3.  <span data-ttu-id="e8888-140">Après avoir renseigné les détails, sélectionnez pour télécharger le document personnalisé à partir du menu déroulant **Justification**.</span><span class="sxs-lookup"><span data-stu-id="e8888-140">After filling in the details, select to upload the personalized document from the **Justification** drop-down menu.</span></span>




