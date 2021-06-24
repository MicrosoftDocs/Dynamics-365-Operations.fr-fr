---
title: Activer la prévision des flux de trésorerie (version préliminaire)
description: Cette rubrique explique comment activer la fonctionnalité de prévisions de flux de trésorerie dans Informations financières.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ba8acb2191291e2abed5cabf234c19fe09e6c8ff
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222556"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="5a439-103">Activer la prévision des flux de trésorerie (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="5a439-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="5a439-104">Cette rubrique explique comment activer la fonctionnalité de prévisions de flux de trésorerie dans Informations financières.</span><span class="sxs-lookup"><span data-stu-id="5a439-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="5a439-105">Pour utiliser les prévisions de paiement dans le flux de trésorerie, vous devez configurer la fonction de prévision de paiement client comme décrit dans [Activer les prédictions de paiement des clients](enable-cust-paymnt-prediction.md).</span><span class="sxs-lookup"><span data-stu-id="5a439-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="5a439-106">Utilisez les informations de la page d’environnement dans Microsoft Dynamics Lifecycle Services (LCS) pour se connecter à l’instance principale d’Azure SQL pour cet environnement.</span><span class="sxs-lookup"><span data-stu-id="5a439-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="5a439-107">Exécutez la commande Transact-SQL (T-SQL) suivante pour activer les déploiements en mode Flighting pour l’environnement sandbox.</span><span class="sxs-lookup"><span data-stu-id="5a439-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="5a439-108">(Vous devrez peut-être activer l’accès pour votre adresse IP dans LCS avant de pouvoir vous connecter à distance à Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="5a439-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="5a439-109">Ignorez cette étape si vous utilisez la version 10.0.20 ou ultérieure, ou si vous utilisez un déploiement Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="5a439-109">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="5a439-110">L’équipe Informations financières devrait déjà avoir activé le déploiement en mode Flighting pour vous.</span><span class="sxs-lookup"><span data-stu-id="5a439-110">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="5a439-111">Si vous ne voyez pas la fonctionnalité dans l’espace de travail **Gestion des fonctionnalités**, ou si vous rencontrez des problèmes lorsque vous essayez de l’activer, contactez <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="5a439-111">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="5a439-112">Ouvrez l’espace de travail **Gestion des fonctionnalités** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5a439-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="5a439-113">Sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="5a439-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="5a439-114">Activer les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="5a439-114">Turn on the following features:</span></span>

        - <span data-ttu-id="5a439-115">Nouveau contrôle de grille</span><span class="sxs-lookup"><span data-stu-id="5a439-115">New grid control</span></span>
        - <span data-ttu-id="5a439-116">Regroupement en grilles (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="5a439-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="5a439-117">Prévisions de paiement client (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="5a439-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="5a439-118">Prévisions de flux de trésorerie (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="5a439-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="5a439-119">Aller à **Gestion de la trésorerie et de la banque \> Configuration des prévisions de trésorerie**, et ajoutez les comptes de liquidité à inclure dans les prévisions.</span><span class="sxs-lookup"><span data-stu-id="5a439-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a439-120">Si les comptes de liquidité ne sont pas configurés, le flux de trésorerie ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="5a439-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="5a439-121">Aller à **Gestion de la trésorerie et de la banque \> Configurer \> Informations financières (version préliminaire) \> Prévisions de flux de trésorerie (version préliminaire)** et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="5a439-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="5a439-122">Sur l’onglet **Prévisions de trésorerie**, sélectionnez **Activer la fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="5a439-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="5a439-123">Sélectionner **Créer un modèle de prédiction**.</span><span class="sxs-lookup"><span data-stu-id="5a439-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="5a439-124">Pour plus d’informations sur la fonctionnalité des prévisions de flux de trésorerie, voir [Prévisions de flux de trésorerie](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="5a439-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
