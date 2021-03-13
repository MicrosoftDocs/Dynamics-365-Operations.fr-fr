---
title: Améliorer le modèle de prévision (version préliminaire)
description: Cette rubrique décrit les fonctionnalités que vous pouvez utiliser pour améliorer les performances des modèles de prédiction.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 2bcdea4a2a8f4386b274077cd1e95398fb6fac37
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009366"
---
# <a name="improve-the-prediction-model-preview"></a><span data-ttu-id="43fc3-103">Améliorer le modèle de prévision (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="43fc3-103">Improve the prediction model (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="43fc3-104">Cette rubrique décrit les fonctionnalités que vous pouvez utiliser pour améliorer les performances des modèles de prédiction.</span><span class="sxs-lookup"><span data-stu-id="43fc3-104">This topic describes features that you can use to improve the performance of prediction models.</span></span> <span data-ttu-id="43fc3-105">Vous commencez à améliorer votre modèle dans l’espace de travail **Prédictions de paiement client** dans Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="43fc3-105">You start to improve your model in the **Customer payment predictions** workspace in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="43fc3-106">Les étapes d’amélioration sont ensuite terminées dans AI Builder.</span><span class="sxs-lookup"><span data-stu-id="43fc3-106">The improvement steps are then completed in AI Builder.</span></span>

## <a name="select-historical-outcomes"></a><span data-ttu-id="43fc3-107">Sélectionnez les résultats historiques</span><span class="sxs-lookup"><span data-stu-id="43fc3-107">Select historical outcomes</span></span>

<span data-ttu-id="43fc3-108">Vous sélectionnez d’abord un ou plusieurs des trois résultats possibles pour les factures : **À temps**, **En retard**, et **Très tard**.</span><span class="sxs-lookup"><span data-stu-id="43fc3-108">You first select one or more of the three possible outcomes for invoices: **On time**, **Late**, and **Very late**.</span></span> <span data-ttu-id="43fc3-109">Les trois résultats doivent être sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="43fc3-109">All three outcomes should be selected.</span></span> <span data-ttu-id="43fc3-110">Si vous désactivez la sélection de l’un des résultats, les factures seront filtrées du processus de formation et la précision de la prédiction sera réduite.</span><span class="sxs-lookup"><span data-stu-id="43fc3-110">If you clear the selection of any of the outcomes, invoices will be filtered out of the training process and the accuracy of the prediction will be reduced.</span></span>

<span data-ttu-id="43fc3-111">[![Confirmer les résultats](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span><span class="sxs-lookup"><span data-stu-id="43fc3-111">[![Confirming outcomes](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span></span>

<span data-ttu-id="43fc3-112">Si votre organisation ne requiert que deux résultats, modifiez les seuils **En retard** et **Très tard** à 0 (zéro) jour.</span><span class="sxs-lookup"><span data-stu-id="43fc3-112">If your organization requires only two outcomes, change the **Late** and **Very late** thresholds to 0 (zero) days.</span></span> <span data-ttu-id="43fc3-113">De cette façon, vous réduisez efficacement la prédiction à un état binaire de **À temps** ou **En retard**.</span><span class="sxs-lookup"><span data-stu-id="43fc3-113">In this way, you effectively collapse the prediction to a binary state of **On time** or **Late**.</span></span>

## <a name="select-fields"></a><span data-ttu-id="43fc3-114">Sélectionner des champs</span><span class="sxs-lookup"><span data-stu-id="43fc3-114">Select fields</span></span>

<span data-ttu-id="43fc3-115">Lorsque vous sélectionnez des champs à inclure dans le modèle, sachez que la liste comprend tous les champs disponibles dans la table Microsoft Dataverse mappée aux données dans le lac de données Azure.</span><span class="sxs-lookup"><span data-stu-id="43fc3-115">When you're selecting fields to include in the model, be aware that the list includes all available fields in the Microsoft Dataverse table that is mapped to the data in the Azure data lake.</span></span> <span data-ttu-id="43fc3-116">Certains de ces champs devraient **ne pas** être sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="43fc3-116">Some of these fields should **not** be selected.</span></span> <span data-ttu-id="43fc3-117">Les champs qui ne doivent pas être sélectionnés appartiennent à l’une des trois catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="43fc3-117">The fields that should not be selected fall into one of three categories:</span></span>

- <span data-ttu-id="43fc3-118">Le champ est obligatoire pour la table Dataverse, mais il n’y a pas de données de sauvegarde pour elle dans le lac de données.</span><span class="sxs-lookup"><span data-stu-id="43fc3-118">The field is required for the Dataverse table, but there is no backing data for it in the data lake.</span></span>
- <span data-ttu-id="43fc3-119">Le champ est un ID et n’a donc pas de sens pour une fonctionnalité de Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="43fc3-119">The field is an ID and therefore doesn't make sense for a machine learning feature.</span></span>
- <span data-ttu-id="43fc3-120">Le champ représente des informations qui ne seront pas disponibles pendant la prédiction.</span><span class="sxs-lookup"><span data-stu-id="43fc3-120">The field represents information that won't be available during prediction.</span></span>

<span data-ttu-id="43fc3-121">Les sections suivantes présentent les champs disponibles pour la facture et les entités client, et répertorient les champs qui doivent **ne pas** être sélectionné pour la formation.</span><span class="sxs-lookup"><span data-stu-id="43fc3-121">The following sections show the fields that are available for the invoice and customer entities, and list the fields that should **not** be selected for training.</span></span> <span data-ttu-id="43fc3-122">La catégorie spécifiée pour chacun de ces champs fait référence aux catégories de la liste précédente.</span><span class="sxs-lookup"><span data-stu-id="43fc3-122">The category that is specified for each of those fields refers to the categories in the preceding list.</span></span>
 
### <a name="invoice-dataverse-table"></a><span data-ttu-id="43fc3-123">Table Dataverse de facturation</span><span class="sxs-lookup"><span data-stu-id="43fc3-123">Invoice Dataverse table</span></span>

<span data-ttu-id="43fc3-124">L’illustration suivante présente les champs disponibles pour la table de facturation.</span><span class="sxs-lookup"><span data-stu-id="43fc3-124">The following illustration shows the fields that are available for the invoice table.</span></span>

<span data-ttu-id="43fc3-125">[![Champs disponibles pour la table de facturation](./media/available-fields.png)](./media/available-fields.png)</span><span class="sxs-lookup"><span data-stu-id="43fc3-125">[![Available fields for the invoice table](./media/available-fields.png)](./media/available-fields.png)</span></span>

<span data-ttu-id="43fc3-126">Les champs suivants ne doivent pas être sélectionnés pour la formation :</span><span class="sxs-lookup"><span data-stu-id="43fc3-126">The following fields should not be selected for training:</span></span>

- <span data-ttu-id="43fc3-127">**Compte de facturation** (catégorie 2)</span><span class="sxs-lookup"><span data-stu-id="43fc3-127">**Invoice Account** (category 2)</span></span>
- <span data-ttu-id="43fc3-128">**Est fermé** (catégorie 3) – Ce champ est utilisé pour filtrer les factures pour la formation (fermée) et la prédiction (non clôturée).</span><span class="sxs-lookup"><span data-stu-id="43fc3-128">**Is closed** (category 3) – This field is used to filter invoices for training (closed) and prediction (not closed).</span></span>
- <span data-ttu-id="43fc3-129">**Nom** (catégorie 1)</span><span class="sxs-lookup"><span data-stu-id="43fc3-129">**Name** (category 1)</span></span>
- <span data-ttu-id="43fc3-130">**ID source** (catégorie 2)</span><span class="sxs-lookup"><span data-stu-id="43fc3-130">**Source Id** (category 2)</span></span>
- <span data-ttu-id="43fc3-131">**enregistrement source** (catégorie 2)</span><span class="sxs-lookup"><span data-stu-id="43fc3-131">**Source record** (category 2)</span></span>
- <span data-ttu-id="43fc3-132">**Table source** (catégorie 2)</span><span class="sxs-lookup"><span data-stu-id="43fc3-132">**Source table** (category 2)</span></span>

### <a name="customer-dataverse-table"></a><span data-ttu-id="43fc3-133">Table Dataverse des clients</span><span class="sxs-lookup"><span data-stu-id="43fc3-133">Customer Dataverse table</span></span>

<span data-ttu-id="43fc3-134">L’illustration suivante présente les champs disponibles pour la table client.</span><span class="sxs-lookup"><span data-stu-id="43fc3-134">The following illustration shows the fields that are available for the customer table.</span></span>

<span data-ttu-id="43fc3-135">[![Champs disponibles pour la table client](./media/related-entities.png)](./media/related-entities.png)</span><span class="sxs-lookup"><span data-stu-id="43fc3-135">[![Available fields for the customer table](./media/related-entities.png)](./media/related-entities.png)</span></span>

<span data-ttu-id="43fc3-136">Le champ suivant ne doit pas être sélectionné pour la formation :</span><span class="sxs-lookup"><span data-stu-id="43fc3-136">The following field should not be selected for training:</span></span>

- <span data-ttu-id="43fc3-137">**Clé unique de ligne** (catégorie 2)</span><span class="sxs-lookup"><span data-stu-id="43fc3-137">**Row Unique Key** (category 2)</span></span>

## <a name="filters"></a><span data-ttu-id="43fc3-138">Filtres</span><span class="sxs-lookup"><span data-stu-id="43fc3-138">Filters</span></span>

<span data-ttu-id="43fc3-139">Les filtres ne prennent actuellement pas en charge le scénario de prédicteur de paiement client.</span><span class="sxs-lookup"><span data-stu-id="43fc3-139">The filters don't currently support the Customer payment predictor scenario.</span></span> <span data-ttu-id="43fc3-140">Par conséquent, sélectionnez **Passer cette étape** et passez à la page de résumé.</span><span class="sxs-lookup"><span data-stu-id="43fc3-140">Therefore, select **Skip this step**, and continue to the summary page.</span></span>

<span data-ttu-id="43fc3-141">[![Modèle de mise au point avec filtres](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span><span class="sxs-lookup"><span data-stu-id="43fc3-141">[![Focus model with filters](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="43fc3-142">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="43fc3-142">Privacy notice</span></span>
<span data-ttu-id="43fc3-143">Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.</span><span class="sxs-lookup"><span data-stu-id="43fc3-143">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
