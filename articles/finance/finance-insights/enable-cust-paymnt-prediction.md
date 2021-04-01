---
title: Activer les prédictions de paiement des clients (version préliminaire)
description: Cette rubrique explique comment activer et configurer la fonctionnalité de Prédictions de paiement des clients dans Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: b8c5fc4a915aa0aba6ff683fac59379f6e319fff
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256809"
---
# <a name="enable-customer-payment-predictions-preview"></a><span data-ttu-id="6adf1-103">Activer les prédictions de paiement des clients (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="6adf1-103">Enable customer payment predictions (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="6adf1-104">Cette rubrique explique comment activer et configurer la fonctionnalité de Prédictions de paiement des clients dans Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="6adf1-104">This topic explains how to turn on and configure the Customer payment predictions feature in Finance insights.</span></span> <span data-ttu-id="6adf1-105">Vous activez la fonction dans l’espace de travail **Gestion des fonctionnalités** et entrez les paramètres de configuration sur la page **Paramètres Finance insights**.</span><span class="sxs-lookup"><span data-stu-id="6adf1-105">You turn on the feature in the **Feature management** workspace and enter configuration settings on the **Financial insights parameters** page.</span></span> <span data-ttu-id="6adf1-106">Cette rubrique comprend également des informations qui peuvent vous aider à utiliser efficacement la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="6adf1-106">This topic also includes information that can help you effectively use the feature.</span></span>

> [!NOTE]
> <span data-ttu-id="6adf1-107">Avant d’effectuer les étapes suivantes, assurez-vous de suivre les étapes prérequises dans la rubrique [Configurer pour Finance insights](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="6adf1-107">Before you complete the following steps, be sure to complete the prerequisite steps in the [Configure for Finance insights](configure-for-fin-insites.md) topic.</span></span>

1. <span data-ttu-id="6adf1-108">Utilisez les informations de la page d’environnement dans Microsoft Dynamics Lifecycle Services (LCS) pour se connecter à l’instance principale d’Azure SQL pour cet environnement.</span><span class="sxs-lookup"><span data-stu-id="6adf1-108">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="6adf1-109">Exécutez la commande Transact-SQL (T-SQL) suivante pour activer les déploiements en mode Flighting pour l’environnement sandbox.</span><span class="sxs-lookup"><span data-stu-id="6adf1-109">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="6adf1-110">(Vous devrez peut-être activer l’accès pour votre adresse IP dans LCS avant de pouvoir vous connecter à distance à Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="6adf1-110">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > <span data-ttu-id="6adf1-111">Si votre déploiement de Microsoft Dynamics 365 Finance est un déploiement Service Fabric, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="6adf1-111">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="6adf1-112">L’équipe Finance Insights devrait déjà avoir activé le déploiement en mode Flighting pour vous.</span><span class="sxs-lookup"><span data-stu-id="6adf1-112">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="6adf1-113">Si vous ne voyez pas la fonctionnalité dans l’espace de travail **Gestion des fonctionnalités**, ou si vous rencontrez des problèmes lorsque vous essayez de l’activer, contactez <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="6adf1-113">If you don't see the feature in the **Feature management** workspace, or if experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="6adf1-114">Activez la fonctionnalité Informations sur les paiements des clients :</span><span class="sxs-lookup"><span data-stu-id="6adf1-114">Turn on the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="6adf1-115">Accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="6adf1-115">Go to **System administration \> Workspaces \> Feature management**.</span></span>
    2. <span data-ttu-id="6adf1-116">Trouvez la fonctionnalité nommée **Informations sur les paiements des clients (version préliminaire)**.</span><span class="sxs-lookup"><span data-stu-id="6adf1-116">Find the feature that is named **Customer payment insights (preview)**.</span></span>
    3. <span data-ttu-id="6adf1-117">Sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="6adf1-117">Select **Enable now**.</span></span>

    <span data-ttu-id="6adf1-118">La fonctionnalité Informations sur les paiements des clients est maintenant activée et prête à être configurée.</span><span class="sxs-lookup"><span data-stu-id="6adf1-118">The Customer payment insights feature is now turned on and ready to be configured.</span></span>

3. <span data-ttu-id="6adf1-119">Configurez la fonctionnalité Informations sur les paiements des clients :</span><span class="sxs-lookup"><span data-stu-id="6adf1-119">Configure the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="6adf1-120">Aller à **Crédits et collections \> Configurer \> Finance Insights \> Paramètres Finance Insights**.</span><span class="sxs-lookup"><span data-stu-id="6adf1-120">Go to **Credit and collections \> Setup \> Finance insights \> Finance insights parameters**.</span></span>

        <span data-ttu-id="6adf1-121">[![Page de paramètres Finance Insights avant la configuration de la fonctionnalité](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span><span class="sxs-lookup"><span data-stu-id="6adf1-121">[![Financial insights parameters page before the feature is configured](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span></span>

    2. <span data-ttu-id="6adf1-122">Sur la page **Paramètres Finance Insights**, sur l’onglet **Informations sur les paiements des clients**, sélectionnez le lien **Afficher les champs de données utilisés dans le modèle de prédiction** pour ouvrir la page **Champs de données pour le modèle de prédiction**.</span><span class="sxs-lookup"><span data-stu-id="6adf1-122">On the **Financial insights parameters** page, on the **Customer payment insights** tab, select the **View the data fields used in the prediction model** link to open the **Data fields for prediction model** page.</span></span> <span data-ttu-id="6adf1-123">Là, vous pouvez afficher la liste par défaut des champs qui sont utilisés pour créer le modèle de prédiction d’intelligence artificielle (IA) pour les prédictions de paiement des clients.</span><span class="sxs-lookup"><span data-stu-id="6adf1-123">There, you can view the default list of fields that are used to create the artificial intelligence (AI) prediction model for customer payment predictions.</span></span>

        <span data-ttu-id="6adf1-124">Pour utiliser la liste de champs par défaut pour créer le modèle de prédiction, fermez la page **Champs de données pour le modèle de prédiction**, puis sur la page **Paramètres Finance Insights**, définissez l’option **Activer la fonctionnalité** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6adf1-124">To use the default list of fields to create the prediction model, close the **Data fields for prediction model** page, and then, on the **Financial insights parameters** page, set the **Enable feature** option to **Yes**.</span></span>

    3. <span data-ttu-id="6adf1-125">Spécifiez la période de transaction "très tardive" pour définir ce que le compartiment de prédiction **Très tard** signifie pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="6adf1-125">Specify the "very late" transaction period to define what the **Very late** prediction bucket means for your business.</span></span>

        <span data-ttu-id="6adf1-126">Pour chaque facture ouverte, le système prédit la probabilité de paiement en trois catégories : **À temps**, **En retard**, et **Très tard**.</span><span class="sxs-lookup"><span data-stu-id="6adf1-126">For each open invoice, the system predicts the probability of payment in three buckets: **On time**, **Late**, and **Very late**.</span></span>

        - <span data-ttu-id="6adf1-127">**À temps** – Ce compartiment comprend les paiements qui devraient être payés au plus tard à la date d’échéance de la transaction.</span><span class="sxs-lookup"><span data-stu-id="6adf1-127">**On time** – This bucket includes payments that are predicted to be paid on or before the transaction due date.</span></span>
        - <span data-ttu-id="6adf1-128">**En retard** – Ce compartiment comprend les paiements dont le paiement est prévu après la date d’échéance de la transaction mais avant le début de la période de transaction "très tardive".</span><span class="sxs-lookup"><span data-stu-id="6adf1-128">**Late** – This bucket includes payments that are predicted to be paid after the transaction due date but before the start of the "very late" transaction period.</span></span>
        - <span data-ttu-id="6adf1-129">**Très tard** – Ce compartiment comprend les paiements dont le paiement est prévu après la date d’échéance de la transaction mais avant le début de la période de transaction "très tardive".</span><span class="sxs-lookup"><span data-stu-id="6adf1-129">**Very late** – This bucket includes payments that are predicted to be paid after the start of the "very late" transaction period.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6adf1-130">Si vous modifiez la période de transaction "très tardive" et sélectionnez **Modifier le seuil de retard** une fois que le modèle de prédiction IA pour les paiements des clients a été créé, le modèle de prédiction existant est supprimé et un modèle est créé.</span><span class="sxs-lookup"><span data-stu-id="6adf1-130">If you change the "very late" transaction period and select **Change late threshold** after the AI prediction model for customer payments has been created, the existing prediction model is deleted, and a new model is created.</span></span> <span data-ttu-id="6adf1-131">Le nouveau modèle de prédiction déplacera les transactions dans la période "très tardive", en fonction des paramètres qui ont été saisis pour la définir.</span><span class="sxs-lookup"><span data-stu-id="6adf1-131">The new prediction model will move transactions into the "very late" period, based on the settings that were entered to define it.</span></span>

    4. <span data-ttu-id="6adf1-132">Après avoir défini la période de transaction "très tardive", sélectionnez **Créer un modèle de prédiction** pour créer le modèle de prédiction.</span><span class="sxs-lookup"><span data-stu-id="6adf1-132">After you've finished defining the "very late" transaction period, select **Create prediction model** to create the prediction model.</span></span> <span data-ttu-id="6adf1-133">La section **Modèle de prédiction** sur la page **Paramètres Finance Insights** affiche l’état du modèle de prédiction.</span><span class="sxs-lookup"><span data-stu-id="6adf1-133">The **Prediction model** section on the **Financial insights parameters** page shows the status of the prediction model.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6adf1-134">A tout moment pendant la création du modèle de prédiction, vous pouvez sélectionner **Réinitialiser la création du modèle** pour redémarrer le processus.</span><span class="sxs-lookup"><span data-stu-id="6adf1-134">At any time while the prediction model is being created, you can select **Reset model creation** to restart the process.</span></span>

    <span data-ttu-id="6adf1-135">La fonction a maintenant été configurée et est prête à être utilisée.</span><span class="sxs-lookup"><span data-stu-id="6adf1-135">The feature has now been configured and is ready to be used.</span></span>

<span data-ttu-id="6adf1-136">Une fois que la fonction a été activée et configurée, et que le modèle de prédiction a été créé et fonctionne, la section **Modèle de prédiction** de la page **Paramètres Finance Insights** montre la précision du modèle, comme indiqué dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="6adf1-136">After the feature has been turned on and configured, and the prediction model has been created and is working, the **Prediction model** section of the **Financial insights parameters** page shows the accuracy of the model, as shown in the following illustration.</span></span>

<span data-ttu-id="6adf1-137">[![Précision du modèle de prédiction sur la page de paramètres Financial insights](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span><span class="sxs-lookup"><span data-stu-id="6adf1-137">[![Accuracy of the prediction model on the Financial insights parameters page](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span></span>

## <a name="release-details"></a><span data-ttu-id="6adf1-138">Détails du lancement</span><span class="sxs-lookup"><span data-stu-id="6adf1-138">Release details</span></span>

<span data-ttu-id="6adf1-139">La version préliminaire publique de Finance Insights est disponible pour les déploiements d’essai aux États-Unis, en Europe et au Royaume-Uni.</span><span class="sxs-lookup"><span data-stu-id="6adf1-139">Finance insights public preview is available for trial deployments in the United States of America, Europe, and the United Kingdom.</span></span> <span data-ttu-id="6adf1-140">Microsoft ajoute progressivement la prise en charge de plusieurs régions.</span><span class="sxs-lookup"><span data-stu-id="6adf1-140">Microsoft is incrementally adding support for more regions.</span></span>

<span data-ttu-id="6adf1-141">Les fonctionnalités en version préliminaire publiques peuvent et doivent être activées uniquement dans les environnements sandbox de niveau 2.</span><span class="sxs-lookup"><span data-stu-id="6adf1-141">Public preview features can and should be turned on only in Tier-2 sandbox environments.</span></span> <span data-ttu-id="6adf1-142">Les modèles de configuration et IA créés dans un environnement sandbox ne peuvent pas être migrés vers un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="6adf1-142">Setup and AI models that are created in a sandbox environment can't be migrated to a production environment.</span></span> <span data-ttu-id="6adf1-143">Pour plus d’informations, voir [Conditions d’utilisation supplémentaires pour les versions préliminaires de Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span><span class="sxs-lookup"><span data-stu-id="6adf1-143">For more information, see [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="6adf1-144">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="6adf1-144">Privacy notice</span></span>

<span data-ttu-id="6adf1-145">Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.</span><span class="sxs-lookup"><span data-stu-id="6adf1-145">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]