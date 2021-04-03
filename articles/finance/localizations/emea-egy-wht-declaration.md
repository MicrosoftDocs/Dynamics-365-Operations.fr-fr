---
title: Déclaration de retenue à la source pour l’Égypte
description: Cette rubrique explique comment configurer et générer les déclarations de retenue à la source pour l’Égypte.
author: sndray
manager: AnnBe
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: cec903c56439957bcafb77c3da774a903d4433a1
ms.sourcegitcommit: a3052f76ad71894dbef66566c07c6e2c31505870
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2021
ms.locfileid: "5574326"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a><span data-ttu-id="d3d89-103">Déclaration de retenue à la source pour l’Égypte (EG-00005)</span><span class="sxs-lookup"><span data-stu-id="d3d89-103">Withholding tax declaration for Egypt (EG-00005)</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a><span data-ttu-id="d3d89-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="d3d89-104">Overview</span></span>
<span data-ttu-id="d3d89-105">Cette rubrique explique comment configurer et générer la déclaration de retenue à la source et les formulaires 41 et 11 de déclaration de retenue à la source pour les entités juridiques en Égypte</span><span class="sxs-lookup"><span data-stu-id="d3d89-105">This topic explains how to set up and generate the withholding tax declaration and the withholding tax declaration forms 41 and 11 for legal entities in Egypt</span></span> 

<span data-ttu-id="d3d89-106">Toutes les entités égyptiennes doivent préparer le formulaire 41 qui récapitule toutes les taxes retenues des fournisseurs et des prestataires de services locaux.</span><span class="sxs-lookup"><span data-stu-id="d3d89-106">All Egyptian entities must prepare the form  41 which summarizes all taxes that are retained from local suppliers and service providers.</span></span> <span data-ttu-id="d3d89-107">En plus du formulaire 41, le formulaire 11 doit être généré pour détailler toutes les retenues des fournisseurs étrangers.</span><span class="sxs-lookup"><span data-stu-id="d3d89-107">In addition to form 41, form 11 must be generated to detail all of the retained taxed from foreign providers.</span></span> 

<span data-ttu-id="d3d89-108">L’état **Déclaration de retenue à la source** dans Dynamics 365 Finance comprend les états suivants :</span><span class="sxs-lookup"><span data-stu-id="d3d89-108">The **Withholding tax declaration** report in Dynamics 365 Finance includes the following reports:</span></span>

- <span data-ttu-id="d3d89-109">Numéro du formulaire de déclaration</span><span class="sxs-lookup"><span data-stu-id="d3d89-109">Declaration form No.</span></span> <span data-ttu-id="d3d89-110">41</span><span class="sxs-lookup"><span data-stu-id="d3d89-110">41</span></span>
- <span data-ttu-id="d3d89-111">Numéro du formulaire de déclaration</span><span class="sxs-lookup"><span data-stu-id="d3d89-111">Declaration form No.</span></span> <span data-ttu-id="d3d89-112">11</span><span class="sxs-lookup"><span data-stu-id="d3d89-112">11</span></span>
    
    
## <a name="prerequisites"></a><span data-ttu-id="d3d89-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="d3d89-113">Prerequisites</span></span>
<span data-ttu-id="d3d89-114">L’adresse principale de l’entité juridique doit être en Égypte.</span><span class="sxs-lookup"><span data-stu-id="d3d89-114">The primary address of the legal entity must be in Egypt.</span></span>
<span data-ttu-id="d3d89-115">Dans l’espace de travail **Gestion des fonctionnalités**, les fonctionnalités suivantes doivent être activées :</span><span class="sxs-lookup"><span data-stu-id="d3d89-115">In the **Feature management** workspace, the following feature must be enabled:</span></span>

   - <span data-ttu-id="d3d89-116">**Retenue à la source globale**</span><span class="sxs-lookup"><span data-stu-id="d3d89-116">**Global withholding tax**</span></span>

<span data-ttu-id="d3d89-117">Pour plus d’informations sur l’activation des fonctionnalités, voir [Présentation de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d3d89-117">For more information about how to enable features, see [Feature management overview.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span></span>

1. <span data-ttu-id="d3d89-118">Accédez à **Taxe** > **Paramétrage** > **Paramètres** > **Paramètres de comptabilité**, puis dans l’onglet **Retenue à la source** définissez l’option **Activer la retenue à la source globale** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-118">Go to **Tax** > **Setup** > **Parameters** > **General ledger parameters**, and on the **Withholding tax** tab, set **Enable global withholding tax** to **Yes**.</span></span>
2. <span data-ttu-id="d3d89-119">Dans l’espace de travail **Gestion des états électroniques**, importez les formats de gestion des états électroniques suivants à partir du référentiel :</span><span class="sxs-lookup"><span data-stu-id="d3d89-119">In the **Electronic reporting** workspace, import the following Electronic reporting formats from the repository:</span></span>

    - <span data-ttu-id="d3d89-120">Déclaration de WHT Excel (EG)</span><span class="sxs-lookup"><span data-stu-id="d3d89-120">WHT Declaration Excel (EG)</span></span>

    > [!NOTE]
    > <span data-ttu-id="d3d89-121">Le format ci-dessus est basé sur le **Modèle de déclaration fiscale** et utilise la **Mise en correspondance des modèles de déclaration fiscale**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-121">The format above is based on the **Tax declaration model** and uses the **Tax declaration model mapping**.</span></span> <span data-ttu-id="d3d89-122">Cette configuration supplémentaire est automatiquement importée.</span><span class="sxs-lookup"><span data-stu-id="d3d89-122">This additional configuration is automatically imported.</span></span>

<span data-ttu-id="d3d89-123">Pour plus d’informations sur la manière d’importer des configurations de gestion des états électroniques, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="d3d89-123">For more information about how to import Electronic reporting configurations, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

## <a name="download-electronic-reporting-configurations"></a><span data-ttu-id="d3d89-124">Télécharger des configurations de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="d3d89-124">Download Electronic reporting configurations</span></span>

<span data-ttu-id="d3d89-125">La mise en œuvre des formulaires de déclaration de WHT pour l’Égypte est basée sur des configurations de gestion des états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="d3d89-125">The implementation of the WHT declaration forms for Egypt is based on Electronic reporting (ER) configurations.</span></span> <span data-ttu-id="d3d89-126">Pour plus d’informations sur les fonctionnalités et les concepts de la gestion des états, voir [Gestion des états électroniques](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="d3d89-126">For more information about the capabilities and concepts of configurable reporting, see [Electronic reporting](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span></span>

<span data-ttu-id="d3d89-127">Pour les environnements de production et de test d’acceptation par l’utilisateur (UAT), suivez les instructions de la rubrique [Télécharger les configurations d’états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="d3d89-127">For production and user acceptance testing (UAT) environments, follow the instructions in the topic, [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

<span data-ttu-id="d3d89-128">Pour générer les déclarations de retenue dans une entité juridique égyptienne, vous devez télécharger les configurations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3d89-128">To generate the Withholding declarations in an Egyptian legal entity, you need to upload the following configurations:</span></span>

- <span data-ttu-id="d3d89-129">Déclaration fiscale version model.version.82.xml ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="d3d89-129">Tax declaration model.version.82.xml or later version</span></span>
- <span data-ttu-id="d3d89-130">Déclaration fiscale version model mapping.version.82.133.xml ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="d3d89-130">Tax declaration model mapping.version.82.133.xml or a later version</span></span>
- <span data-ttu-id="d3d89-131">Déclaration de WHT Excel (EG).version.82.21 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="d3d89-131">WHT Declaration Excel (EG).version.82.21  or a later version</span></span>

<span data-ttu-id="d3d89-132">Après avoir terminé le téléchargement des configurations ER à partir de Lifecycle Services (LCS) ou du référentiel global, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d3d89-132">After you finish downloading the ER configurations from Lifecycle Services (LCS) or the global repository, complete the following steps.</span></span>

1. <span data-ttu-id="d3d89-133">Accédez à l’espace de travail **Génération des états électronique** et sélectionnez la vignette **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-133">Go to the **Electronic reporting** workspace and select the **Reporting configurations** tile.</span></span>
1. <span data-ttu-id="d3d89-134">Sur la page **Configurations**, dans le volet Action, sélectionnez **Échanger > Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-134">On the **Configurations** page, on the Action Pane, select **Exchange > Load from XML file**.</span></span>
1. <span data-ttu-id="d3d89-135">Chargez tous les fichiers dans l’ordre dans lequel ils sont répertoriés dans les puces précédentes.</span><span class="sxs-lookup"><span data-stu-id="d3d89-135">Upload all the files in the order in which they are listed in the previous bullets.</span></span> <span data-ttu-id="d3d89-136">Une fois toutes les configurations chargées, l’arborescence de configuration doit être présente dans Finance.</span><span class="sxs-lookup"><span data-stu-id="d3d89-136">After all of the configurations are uploaded, the configuration tree should be present in Finance.</span></span>

## <a name="set-up-application-specific-parameters"></a><span data-ttu-id="d3d89-137">Configurer des paramètres spécifiques à l’application</span><span class="sxs-lookup"><span data-stu-id="d3d89-137">Set up application-specific parameters</span></span>

<span data-ttu-id="d3d89-138">L’option des paramètres spécifiques à l’application permet aux utilisateurs d’établir les critères de classement et de calcul des transactions de taxe dans chaque ligne d’un rapport généré en fonction de la configuration du **groupe d’articles de retenue à la source** ou d’autres critères établis dans la définition de la recherche.</span><span class="sxs-lookup"><span data-stu-id="d3d89-138">The application-specific parameters option lets users establish the criteria of how the tax transactions will be classified and calculated in each line of a generated report depending on the configuration of **withholding tax item group** or other criteria established in the definition of lookup.</span></span>

<span data-ttu-id="d3d89-139">Le formulaire 41 de déclaration de retenue à la source comprend une colonne spécifique dans laquelle la transaction de retenue à la source doit être classée conformément à la classification des autorités fiscales nommée **Type de code de remise**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-139">Withholding declaration form 41 includes a specific column where the withholding tax transaction must be classified in accordance with the tax authority classification named **Discount code type**.</span></span> <span data-ttu-id="d3d89-140">Au lieu d’inclure ces nouvelles classifications en tant que nouvelles données d’entrée lorsque les transactions sont validées, les classifications seront déterminées en fonction des différentes recherches introduites dans **Configurations** > **Configurer les paramètres spécifiques à l’application** > **Paramétrage** pour répondre aux exigences des états de retenue pour l’Égypte.</span><span class="sxs-lookup"><span data-stu-id="d3d89-140">Instead of including these new classifications as new entry data when the transactions are posted, the classifications will be determined based on the different lookups introduced in **Configurations** > **Set up application-specific parameters** > **Setup** to meet the requirements of withholding reports for Egypt.</span></span> 

<span data-ttu-id="d3d89-141">La configuration suivante permet de classer les transactions dans l’état du formulaire 41 de déclaration de retenue :</span><span class="sxs-lookup"><span data-stu-id="d3d89-141">The following configuration is used to classify the transactions in the Withholding declaration form 41 report:</span></span>

- <span data-ttu-id="d3d89-142">**DiscountTaxTypeLookup** -> Colonne n° 18</span><span class="sxs-lookup"><span data-stu-id="d3d89-142">**DiscountTaxTypeLookup**-> Column No 18</span></span> 

<span data-ttu-id="d3d89-143">Procédez comme suit pour configurer les différentes recherches utilisées pour générer la déclaration de WHT et les états de registres associés.</span><span class="sxs-lookup"><span data-stu-id="d3d89-143">Complete the following steps to set up the different lookups used to generate the WHT declaration and related books reports.</span></span> 

1. <span data-ttu-id="d3d89-144">Dans l’espace de travail **Gestion des états électroniques**, sélectionnez **Configurations** > **Paramétrage** pour configurer les règles d’identification du classement des transactions dans l’état déclaration de WHT.</span><span class="sxs-lookup"><span data-stu-id="d3d89-144">In the **Electronic reporting** workspace, select **Configurations** > **Setup** to set up the rules to identify how transactions are classified in the WHT declaration report.</span></span> 
2. <span data-ttu-id="d3d89-145">Sélectionnez la version actuelle et, sur le raccourci **Recherches**, sélectionnez le nom de la recherche.</span><span class="sxs-lookup"><span data-stu-id="d3d89-145">Select the current version, and on the **Lookups** FastTab, select the lookup name.</span></span> <span data-ttu-id="d3d89-146">Par exemple, **DiscountTaxTypeLookup**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-146">For example, **DiscountTaxTypeLookup**.</span></span> <span data-ttu-id="d3d89-147">Cette recherche identifie la liste des types de remise requis par l’administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="d3d89-147">This lookup identifies the list of discount types required by the tax authority.</span></span>
3. <span data-ttu-id="d3d89-148">Sur le raccourci **Conditions**, sélectionnez **Ajouter** et, dans la nouvelle ligne dans la colonne **Résultat de la recherche**, sélectionnez la ligne associée qui représente la classification dans la **Colonne 18**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-148">On the **Conditions** FastTab, select **Add** and in the new line in the **Lookup result** column, select the related line that represents the classification in the **Column 18**.</span></span>
4. <span data-ttu-id="d3d89-149">Dans la colonne **Groupe d’articles de retenue à la source**, sélectionnez le code associé utilisé pour identifier la classification.</span><span class="sxs-lookup"><span data-stu-id="d3d89-149">In the **Withholding tax item group** column, select the related code that's used to identify the classification.</span></span> <span data-ttu-id="d3d89-150">Par exemple, **Remise autorisée**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-150">For example, **Allowed discount**.</span></span>  
5. <span data-ttu-id="d3d89-151">Répétez les étapes 3 et 4 pour toutes les recherches disponibles.</span><span class="sxs-lookup"><span data-stu-id="d3d89-151">Repeat steps 3 and 4 for all available lookups.</span></span>
6. <span data-ttu-id="d3d89-152">Sélectionnez **Ajouter** à nouveau pour inclure la ligne d’enregistrement finale, et dans la colonne **Résultat de la recherche**, sélectionnez **Non applicable**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-152">Select **Add** again to include the final record line, and in the **Lookup result** column, select **Not applicable**.</span></span> 
7. <span data-ttu-id="d3d89-153">Dans les colonnes restantes, sélectionnez **Non vide**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-153">In the remaining columns, select **Not blank**.</span></span> 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a><span data-ttu-id="d3d89-154">Définir les paramètres de comptabilité</span><span class="sxs-lookup"><span data-stu-id="d3d89-154">Set up General ledger parameters</span></span>

<span data-ttu-id="d3d89-155">Pour générer les états du formulaire de déclaration de WHT dans Microsoft Excel, définissez un format ER sur la page **Paramètres de Comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-155">To generate the WHT declaration form reports in Microsoft Excel, define an ER format on the **General ledger parameters** page.</span></span>

1. <span data-ttu-id="d3d89-156">Accédez à **Taxe** > **Paramétrage** > **Paramètres de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-156">Go to **Tax** > **Setup** > **General ledger parameters**.</span></span>
2. <span data-ttu-id="d3d89-157">Sur l’onglet **Retenue à la source**, dans le champ **Mise en correspondance des formats de déclaration de WHT**, sélectionnez **Déclaration de WHT Excel (EG)**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-157">On the **Withholding tax** tab, in the **WHT declaration format mapping** field, select **WHT Declaration Excel (EG)**.</span></span> <span data-ttu-id="d3d89-158">Si vous laissez le champ vide, l’état de taxe standard sera généré au format SSRS.</span><span class="sxs-lookup"><span data-stu-id="d3d89-158">If you leave the field blank, the standard sales tax report will be generated in SSRS format.</span></span>


![Formulaire de déclaration](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a><span data-ttu-id="d3d89-160">Générer les formulaires de déclaration de retenue</span><span class="sxs-lookup"><span data-stu-id="d3d89-160">Generate the Withholding declaration forms</span></span>
<span data-ttu-id="d3d89-161">Le processus de préparation et d’envoi d’un formulaire de déclaration de retenue pour une période spécifique est basé sur les transactions de retenue à la source validées pendant la tâche de règlement et de validation de la taxe.</span><span class="sxs-lookup"><span data-stu-id="d3d89-161">The process of preparing and submitting a Withholding declaration form for a specific period is based on the withholding tax transactions posted during the settle and post payment tax job.</span></span> <span data-ttu-id="d3d89-162">Pour plus d’informations sur la retenue à la source globale, voir [Retenue à la source globale](../general-ledger/global-withholding-tax-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d3d89-162">For more information about global withholding tax, see [Global withholding tax](../general-ledger/global-withholding-tax-overview.md).</span></span>

<span data-ttu-id="d3d89-163">Effectuez les étapes de configuration suivantes pour générer l’état de déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="d3d89-163">Complete the following steps to generate the tax declaration report.</span></span>

1. <span data-ttu-id="d3d89-164">Accédez à **Taxe** > **Déclarations** > **Retenue à la source** > \**Paiement de la retenue à la source*.</span><span class="sxs-lookup"><span data-stu-id="d3d89-164">Go to **Tax** > **Declarations** > **Withholding tax** > \**Withholding tax payment*.</span></span>
2. <span data-ttu-id="d3d89-165">Sélectionnez la période de règlement, puis sélectionnez la date de début de l’état.</span><span class="sxs-lookup"><span data-stu-id="d3d89-165">Select the settlement period and then select the from date for the report.</span></span> 
3. <span data-ttu-id="d3d89-166">Entrez la date de transaction, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-166">Enter the transaction date and then select **OK**.</span></span>
4. <span data-ttu-id="d3d89-167">Dans la boîte de dialogue qui s’ouvre, sélectionnez un ou plusieurs types de formulaires **Formulaire N° 41**, **Formulaire N° 11** ou **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-167">In the dialog box that opens, select one or more of the form types \*\*Form No 41 \*\*, **Form No 11**, or **None**.</span></span> <span data-ttu-id="d3d89-168">Si vous sélectionnez **Aucun**, l’état standard est généré.</span><span class="sxs-lookup"><span data-stu-id="d3d89-168">If you select **None**, the standard report is generated.</span></span> 
5. <span data-ttu-id="d3d89-169">Sélectionnez la langue.</span><span class="sxs-lookup"><span data-stu-id="d3d89-169">Select the language.</span></span> <span data-ttu-id="d3d89-170">Tous les états sont traduits en **en-us** et en **ar-eg**.</span><span class="sxs-lookup"><span data-stu-id="d3d89-170">All reports are translated in **en-us** and **ar-eg**.</span></span>
6. <span data-ttu-id="d3d89-171">Entrez la branche et le nom de la banque où le paiement de la taxe sera payé.</span><span class="sxs-lookup"><span data-stu-id="d3d89-171">Enter the branch and name of the bank where the tax payment will be paid.</span></span>
7. <span data-ttu-id="d3d89-172">Sélectionnez le type d’entreprise, puis saisissez les numéros de vérification et de document.</span><span class="sxs-lookup"><span data-stu-id="d3d89-172">Select the business type and then enter the check and document numbers.</span></span> 
8. <span data-ttu-id="d3d89-173">Saisissez le type d’entité.</span><span class="sxs-lookup"><span data-stu-id="d3d89-173">Enter the entity type.</span></span> 
9. <span data-ttu-id="d3d89-174">Saisissez le nom de la personne inscrite afin que le formulaire lui soit attribué et sélectionnez **OK** pour confirmer la génération de l’état.</span><span class="sxs-lookup"><span data-stu-id="d3d89-174">Enter the name of person registered to assign the form and select **OK** to confirm the report generation.</span></span> 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
