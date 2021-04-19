---
title: Activer les propositions de budget (version préliminaire)
description: Cette rubrique explique comment activer la fonctionnalité de proposition de budget dans Finance Insights.
author: ShivamPandey-msft
ms.date: 07/24/2020
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
ms.openlocfilehash: 7e90a1a2f2a8e7808f03ce9a6ee58c027bd48d8d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818702"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="cead2-103">Activer les propositions de budget (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="cead2-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="cead2-104">Cette rubrique explique comment activer la fonctionnalité de proposition de budget dans Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="cead2-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="cead2-105">Utilisez les informations de la page d’environnement dans Microsoft Dynamics Lifecycle Services (LCS) pour se connecter à l’instance principale d’Azure SQL pour cet environnement.</span><span class="sxs-lookup"><span data-stu-id="cead2-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="cead2-106">Exécutez la commande Transact-SQL (T-SQL) suivante pour activer les déploiements en mode Flighting pour l’environnement sandbox.</span><span class="sxs-lookup"><span data-stu-id="cead2-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="cead2-107">(Vous devrez peut-être activer l’accès pour votre adresse IP dans LCS avant de pouvoir vous connecter à distance à Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="cead2-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="cead2-108">Si votre déploiement de Microsoft Dynamics 365 Finance est un déploiement Service Fabric, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="cead2-108">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="cead2-109">L’équipe Finance Insights devrait déjà avoir activé le déploiement en mode Flighting pour vous.</span><span class="sxs-lookup"><span data-stu-id="cead2-109">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="cead2-110">Si vous ne voyez pas la fonctionnalité dans l’espace de travail **Gestion des fonctionnalités**, ou si vous rencontrez des problèmes lorsque vous essayez de l’activer, envoyez un e-mail à [l’équipe de la version préliminaire de l’application Finance Insights](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="cead2-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, send email to the [Finance Insights App Preview team](mailto:fiap@microsoft.com).</span></span>

2. <span data-ttu-id="cead2-111">Ouvrez l’espace de travail **Gestion des fonctionnalités** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cead2-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="cead2-112">Sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="cead2-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="cead2-113">Recherchez **Proposition de budget** et activez cette fonction.</span><span class="sxs-lookup"><span data-stu-id="cead2-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="cead2-114">Aller à **Budgétisation \> Configurer \> Budgétisation de base \> Proposition de budget (version préliminaire)** et sélectionnez **Activer la fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="cead2-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="cead2-115">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="cead2-115">Privacy notice</span></span>
<span data-ttu-id="cead2-116">Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.</span><span class="sxs-lookup"><span data-stu-id="cead2-116">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]