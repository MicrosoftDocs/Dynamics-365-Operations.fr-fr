---
title: Activer les propositions de budget (version préliminaire)
description: Cette rubrique explique comment activer la fonctionnalité de proposition de budget dans Informations financières.
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
ms.openlocfilehash: 948a3e051e5964c5c773cefd90c8587cf833a450
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222532"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="f51f0-103">Activer les propositions de budget (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="f51f0-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="f51f0-104">Cette rubrique explique comment activer la fonctionnalité de proposition de budget dans Informations financières.</span><span class="sxs-lookup"><span data-stu-id="f51f0-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="f51f0-105">Utilisez les informations de la page d’environnement dans Microsoft Dynamics Lifecycle Services (LCS) pour se connecter à l’instance principale d’Azure SQL pour cet environnement.</span><span class="sxs-lookup"><span data-stu-id="f51f0-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="f51f0-106">Exécutez la commande Transact-SQL (T-SQL) suivante pour activer les déploiements en mode Flighting pour l’environnement sandbox.</span><span class="sxs-lookup"><span data-stu-id="f51f0-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="f51f0-107">(Vous devrez peut-être activer l’accès pour votre adresse IP dans LCS avant de pouvoir vous connecter à distance à Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="f51f0-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="f51f0-108">Ignorez cette étape si vous utilisez la version 10.0.20 ou ultérieure, ou si vous utilisez un déploiement Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="f51f0-108">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="f51f0-109">L’équipe Informations financières devrait déjà avoir activé le déploiement en mode Flighting pour vous.</span><span class="sxs-lookup"><span data-stu-id="f51f0-109">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="f51f0-110">Si vous ne voyez pas la fonctionnalité dans l’espace de travail **Gestion des fonctionnalités**, ou si vous rencontrez des problèmes lorsque vous essayez de l’activer, contactez <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="f51f0-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="f51f0-111">Ouvrez l’espace de travail **Gestion des fonctionnalités** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f51f0-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="f51f0-112">Sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="f51f0-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="f51f0-113">Recherchez **Proposition de budget** et activez cette fonction.</span><span class="sxs-lookup"><span data-stu-id="f51f0-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="f51f0-114">Aller à **Budgétisation \> Configurer \> Budgétisation de base \> Proposition de budget (version préliminaire)** et sélectionnez **Activer la fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="f51f0-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
