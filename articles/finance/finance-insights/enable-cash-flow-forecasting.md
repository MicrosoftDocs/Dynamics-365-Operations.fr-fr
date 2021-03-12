---
title: Activer la prévision des flux de trésorerie (version préliminaire)
description: Cette rubrique explique comment activer la fonctionnalité de prévisions de flux de trésorerie dans Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
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
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 1977dac4a3ab66cca2248dc0124d3a06d6963f40
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978762"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="56a4d-103">Activer la prévision des flux de trésorerie (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="56a4d-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="56a4d-104">Cette rubrique explique comment activer la fonctionnalité de prévisions de flux de trésorerie dans Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="56a4d-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="56a4d-105">Pour utiliser les prévisions de paiement dans le flux de trésorerie, vous devez configurer la fonction de prévision de paiement client comme décrit dans [Activer les prédictions de paiement des clients](enable-cust-paymnt-prediction.md).</span><span class="sxs-lookup"><span data-stu-id="56a4d-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="56a4d-106">Utilisez les informations de la page d’environnement dans Microsoft Dynamics Lifecycle Services (LCS) pour se connecter à l’instance principale d’Azure SQL pour cet environnement.</span><span class="sxs-lookup"><span data-stu-id="56a4d-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="56a4d-107">Exécutez la commande Transact-SQL (T-SQL) suivante pour activer les déploiements en mode Flighting pour l’environnement sandbox.</span><span class="sxs-lookup"><span data-stu-id="56a4d-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="56a4d-108">(Vous devrez peut-être activer l’accès pour votre adresse IP dans LCS avant de pouvoir vous connecter à distance à Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="56a4d-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="56a4d-109">Si votre déploiement de Microsoft Dynamics 365 Finance est un déploiement Service Fabric, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="56a4d-109">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="56a4d-110">L’équipe Finance Insights devrait déjà avoir activé le déploiement en mode Flighting pour vous.</span><span class="sxs-lookup"><span data-stu-id="56a4d-110">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="56a4d-111">Si vous ne voyez pas les fonctionnalités dans l’espace de travail **Gestion des fonctionnalités**, ou si vous rencontrez des problèmes lorsque vous essayez de les activer, contactez <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="56a4d-111">If you don't see the features in the **Feature management** workspace, or if experience issues when you try to turn them on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="56a4d-112">Ouvrez l’espace de travail **Gestion des fonctionnalités** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="56a4d-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="56a4d-113">Sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="56a4d-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="56a4d-114">Activer les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="56a4d-114">Turn on the following features:</span></span>

        - <span data-ttu-id="56a4d-115">Nouveau contrôle de grille</span><span class="sxs-lookup"><span data-stu-id="56a4d-115">New grid control</span></span>
        - <span data-ttu-id="56a4d-116">Regroupement en grilles (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="56a4d-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="56a4d-117">Prévisions de paiement client (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="56a4d-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="56a4d-118">Prévisions de flux de trésorerie (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="56a4d-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="56a4d-119">Aller à **Gestion de la trésorerie et de la banque \> Configuration des prévisions de trésorerie**, et ajoutez les comptes de liquidité à inclure dans les prévisions.</span><span class="sxs-lookup"><span data-stu-id="56a4d-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="56a4d-120">Si les comptes de liquidité ne sont pas configurés, le flux de trésorerie ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="56a4d-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="56a4d-121">Aller à **Gestion de la trésorerie et de la banque \> Configurer \> Finance Insights (version préliminaire) \> Prévisions de flux de trésorerie (version préliminaire)** et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="56a4d-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="56a4d-122">Sur l’onglet **Prévisions de trésorerie**, sélectionnez **Activer la fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="56a4d-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="56a4d-123">Sélectionner **Créer un modèle de prédiction**.</span><span class="sxs-lookup"><span data-stu-id="56a4d-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="56a4d-124">Pour plus d’informations sur la fonctionnalité des prévisions de flux de trésorerie, voir [Prévisions de flux de trésorerie](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="56a4d-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="56a4d-125">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="56a4d-125">Privacy notice</span></span>

<span data-ttu-id="56a4d-126">Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.</span><span class="sxs-lookup"><span data-stu-id="56a4d-126">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
