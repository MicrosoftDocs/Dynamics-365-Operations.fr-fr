---
title: Prévision de flux de trésorerie (version préliminaire)
description: Cette rubrique décrit la fonctionnalité de prévision des flux de trésorerie.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f97b8fc0896f0f7b95bf5609f94367b3a8230ca7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645246"
---
# <a name="cash-flow-forecast-preview"></a><span data-ttu-id="e96a5-103">Prévision de flux de trésorerie (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="e96a5-103">Cash flow forecast (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="e96a5-104">Le flux de trésorerie est essentiel à toute entreprise.</span><span class="sxs-lookup"><span data-stu-id="e96a5-104">Cash flow is critical to any business.</span></span> <span data-ttu-id="e96a5-105">Même les entreprises rentables peuvent être confrontées à l’insolvabilité si elles ne maintiennent pas les flux de trésorerie nécessaires pour répondre aux besoins immédiats.</span><span class="sxs-lookup"><span data-stu-id="e96a5-105">Even profitable companies can face insolvency if they don't maintain the cash flow to meet immediate needs.</span></span> <span data-ttu-id="e96a5-106">La capacité de prévision des flux de trésorerie dans les informations financières peut aider les entreprises à surveiller et à gérer efficacement leurs soldes de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="e96a5-106">The cash flow forecasting capability in Finance insights can help companies monitor and manage their cash balances effectively.</span></span> <span data-ttu-id="e96a5-107">Cette fonctionnalité utilise l’apprentissage automatique pour aider les entreprises à prévoir les flux de trésorerie avec plus de précision qu’auparavant.</span><span class="sxs-lookup"><span data-stu-id="e96a5-107">This feature uses machine learning to help businesses forecast cash flows more accurately than they have previously.</span></span> <span data-ttu-id="e96a5-108">Elle peut également aider les responsables à prendre des décisions qui optimisent les opportunités selon l’emplacement actuel de leurs disponibilités.</span><span class="sxs-lookup"><span data-stu-id="e96a5-108">It can also help managers make decisions that optimize opportunities in the context of their current cash position.</span></span> 

<span data-ttu-id="e96a5-109">Pour la plupart des entreprises, la gestion des flux de trésorerie et l’exécution de la prévision des flux de trésorerie sont un processus fastidieux, répétitif et manuel.</span><span class="sxs-lookup"><span data-stu-id="e96a5-109">For most companies, managing cash flow and running cash flow forecasting is a tedious, repetitive, and manual process.</span></span> <span data-ttu-id="e96a5-110">La plupart des entreprises comptent sur les solutions Microsoft Excel qui ont des degrés de complexité variables.</span><span class="sxs-lookup"><span data-stu-id="e96a5-110">Most companies rely on Microsoft Excel solutions that have varying degrees of complexity.</span></span> <span data-ttu-id="e96a5-111">Les défis liés à la prévision précise des flux de trésorerie sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="e96a5-111">The challenges of accurately forecasting cash flow include the following:</span></span>

- <span data-ttu-id="e96a5-112">Les données ne sont pas disponibles pour les décideurs, car elles sont dispersées à plusieurs endroits, notamment :</span><span class="sxs-lookup"><span data-stu-id="e96a5-112">Data isn't available to decision makers because it's scattered in multiple places, including:</span></span> 
  - <span data-ttu-id="e96a5-113">Le système de comptabilité ou de planification des ressources d’entreprise</span><span class="sxs-lookup"><span data-stu-id="e96a5-113">The accounting or enterprise resource planning system</span></span>
  - <span data-ttu-id="e96a5-114">Logiciel de planification financière</span><span class="sxs-lookup"><span data-stu-id="e96a5-114">Financial planning software</span></span>
  - <span data-ttu-id="e96a5-115">Excel</span><span class="sxs-lookup"><span data-stu-id="e96a5-115">Excel</span></span>
  - <span data-ttu-id="e96a5-116">Applications logicielles supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e96a5-116">Additional software applications</span></span> 
- <span data-ttu-id="e96a5-117">Les prévisions sont basées sur des connaissances internes en « silos » au sein de chaque domaine ou service.</span><span class="sxs-lookup"><span data-stu-id="e96a5-117">Forecasting is based on internal knowledge that resides in "silos" within each domain or department.</span></span>
- <span data-ttu-id="e96a5-118">Mesurer l’exactitude de la prévision des flux de trésorerie après la réalisation des états financiers est incertain et difficile.</span><span class="sxs-lookup"><span data-stu-id="e96a5-118">Measuring the accuracy of cash flow forecasting after the financials have been realized is uncertain and difficult.</span></span>
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a><span data-ttu-id="e96a5-119">Détails de la capacité de prévision des flux de trésorerie</span><span class="sxs-lookup"><span data-stu-id="e96a5-119">Details of the Cash flow forecasts capability</span></span>
<span data-ttu-id="e96a5-120">La fonction de prévision des flux de trésorerie comprend les fonctionnalités suivantes.</span><span class="sxs-lookup"><span data-stu-id="e96a5-120">The Cash flow forecasts feature includes the following functionality.</span></span> 

- <span data-ttu-id="e96a5-121">Facilite l’intégration des données de flux de trésorerie provenant de systèmes externes vers Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="e96a5-121">Makes it easy to integrate cash flow data from external systems to Dynamics 365 Finance.</span></span> <span data-ttu-id="e96a5-122">Les prévisions de flux de trésorerie peuvent également utiliser l’infrastructure d’importation-exportation des données.</span><span class="sxs-lookup"><span data-stu-id="e96a5-122">Cash flow forecasts can also use the data import-export framework.</span></span> <span data-ttu-id="e96a5-123">Cette infrastructure facilite l’intégration à Excel OData.</span><span class="sxs-lookup"><span data-stu-id="e96a5-123">This framework makes it easy to integrate with Excel OData.</span></span> <span data-ttu-id="e96a5-124">Vous pouvez également combiner des données provenant de plusieurs sources pour créer une solution complète de flux de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="e96a5-124">You can also combine data from multiple sources to create a comprehensive cash flow solution.</span></span> 

- <span data-ttu-id="e96a5-125">Introduit un emplacement intelligent des disponibilités.</span><span class="sxs-lookup"><span data-stu-id="e96a5-125">Introduces intelligent cash position.</span></span> <span data-ttu-id="e96a5-126">L’emplacement des disponibilités est créée en fonction du comportement de paiement du client pour prédire quand une entreprise peut s’attendre à ce que de l’argent arrive sur ses comptes.</span><span class="sxs-lookup"><span data-stu-id="e96a5-126">Cash position is created  based on customer’s payment behavior to predict when a company can expect cash to arrive in their accounts.</span></span> <span data-ttu-id="e96a5-127">Elle analyse également les modèles historiques de paiement des fournisseurs, afin de prédire quand les futures factures et commandes seront probablement payées.</span><span class="sxs-lookup"><span data-stu-id="e96a5-127">It also analyzes the historical patterns of paying vendors, to predict when future invoices and orders are likely to be paid.</span></span> 

- <span data-ttu-id="e96a5-128">Introduit la prévision intelligente des flux de trésorerie pour les prévisions à long terme, en utilisant la prévision de séries chronologiques grâce à une intégration automatisée avec AI Builder.</span><span class="sxs-lookup"><span data-stu-id="e96a5-128">Introduces intelligent cash flow forecasting for long-term forecasting, using time series forecasting through automated integration with AI Builder.</span></span>

- <span data-ttu-id="e96a5-129">Offre la possibilité d’enregistrer un emplacement ou des prévisions de flux de trésorerie spécifiques, de les modifier, puis de comparer et de mesurer facilement les performances des prévisions avec les données financières réelles.</span><span class="sxs-lookup"><span data-stu-id="e96a5-129">Provides the ability to save specific cash flow position or forecasts, edit them, and then easily compare and measure the forecast performance to the actual financials.</span></span>

- <span data-ttu-id="e96a5-130">Active l’analyse hypothétique via la comparaison de clichés.</span><span class="sxs-lookup"><span data-stu-id="e96a5-130">Enables what-if analysis through snapshot comparison.</span></span> <span data-ttu-id="e96a5-131">Par exemple, vous pouvez créer plusieurs instantanés qui représentent les vues optimistes, pessimistes et les plus réalistes de votre flux de trésorerie, puis comparer et afficher les différences.</span><span class="sxs-lookup"><span data-stu-id="e96a5-131">For example, you can create multiple snapshots that represent optimistic, pessimistic, and the most realistic views of your cash flow, and then compare and view the differences.</span></span>

- <span data-ttu-id="e96a5-132">Permet d’afficher les prévisions de flux de trésorerie dans plusieurs devises, à travers les entités juridiques, et de filtrer et d’afficher les flux de trésorerie liés à un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="e96a5-132">Provides the ability to view the cash flow forecast in multiple currencies, across legal entities, and filter and view cash flow related to a bank account.</span></span> 

- <span data-ttu-id="e96a5-133">Vous permet de filtrer et d’afficher les comptes bancaires liés aux dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="e96a5-133">Lets you filter and view bank accounts that are related to financial dimensions.</span></span>

<span data-ttu-id="e96a5-134">La fonctionnalité de prévision de flux de trésorerie dans Dynamics 365 Finance permettra à votre organisation de transformer une projection de flux de trésorerie fastidieuse, complexe, mais répétitive en un processus simple et automatisé.</span><span class="sxs-lookup"><span data-stu-id="e96a5-134">The cash flow forecasting functionality in Dynamics 365 Finance will empower your organization to transform tedious, complex, yet repetitive cash flow projection to a simple, automated process.</span></span> <span data-ttu-id="e96a5-135">L’automatisation des aspects les plus fastidieux de la prévision des flux de trésorerie vous permet de vous concentrer sur la prise de décision critique pour obtenir les résultats commerciaux souhaités.</span><span class="sxs-lookup"><span data-stu-id="e96a5-135">Automating the most tedious aspects of cash flow forecasting lets you focus on critical decision making to drive desired business outcomes.</span></span>

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a><span data-ttu-id="e96a5-136">Configuration des dimensions pour la prévision des flux de trésorerie</span><span class="sxs-lookup"><span data-stu-id="e96a5-136">Setting up Dimensions for Cash flow forecasting</span></span>
<span data-ttu-id="e96a5-137">Un nouvel onglet sur la page **Configuration des prévisions de flux de trésorerie** vous permet de contrôler les dimensions financières à utiliser pour le filtrage dans l’espace de travail **Prévision des flux de trésorerie**.</span><span class="sxs-lookup"><span data-stu-id="e96a5-137">A new tab on the **Cash flow forecasting setup** page lets you control what financial dimensions to use for filtering in the **Cash flow forecasting** workspace.</span></span> <span data-ttu-id="e96a5-138">Cet onglet n’apparaîtra que lorsque la fonction de prévision des flux de trésorerie est activée.</span><span class="sxs-lookup"><span data-stu-id="e96a5-138">This tab will only appear when the Cash flow forecasts feature is enabled.</span></span> 

<span data-ttu-id="e96a5-139">Sur l’onglet **Dimensions**, choisissez dans la liste des dimensions à utiliser pour le filtrage et utilisez les touches fléchées pour les déplacer vers la colonne de droite.</span><span class="sxs-lookup"><span data-stu-id="e96a5-139">On the **Dimensions** tab, choose from the list of dimensions to use for filtering, and use the arrow keys to move them to the right-hand column.</span></span> <span data-ttu-id="e96a5-140">Seules deux dimensions peuvent être sélectionnées pour filtrer les données de prévision des flux de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="e96a5-140">Only two dimensions can be selected for filtering cash flow forecast data.</span></span> 

#### <a name="privacy-notice"></a><span data-ttu-id="e96a5-141">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="e96a5-141">Privacy notice</span></span>
<span data-ttu-id="e96a5-142">Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.</span><span class="sxs-lookup"><span data-stu-id="e96a5-142">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>