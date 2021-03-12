---
title: Résoudre les problèmes de configuration des prévisions de trésorerie
description: Cette rubrique contient les réponses aux questions que vous vous posez lorsque vous configurez les prévisions de trésorerie. Elle répond aux questions fréquemment posées (FAQ) sur la configuration des flux de trésorerie, les mises à jour des flux de trésorerie et les flux de trésorerie Power BI.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 89eb2f1bcfc73a6a7171a275532b2356e858e87c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985285"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a><span data-ttu-id="a0780-104">Résoudre les problèmes de configuration des prévisions de trésorerie</span><span class="sxs-lookup"><span data-stu-id="a0780-104">Troubleshoot cash flow forecasting setup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a0780-105">Cette rubrique contient les réponses aux questions que vous vous posez lorsque vous configurez les prévisions de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="a0780-105">This topic provides answers to questions that you might have when you configure cash flow forecasting.</span></span> <span data-ttu-id="a0780-106">Elle répond aux questions fréquemment posées (FAQ) sur la configuration des flux de trésorerie, les mises à jour des flux de trésorerie et les flux de trésorerie Power BI.</span><span class="sxs-lookup"><span data-stu-id="a0780-106">It addresses frequently asked questions (FAQ) about the setup for cash flow, updates to cash flow, and cash flow Power BI.</span></span>

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a><span data-ttu-id="a0780-107">Pourquoi les flux de trésorerie sont-ils affichés une seule entité juridique ?</span><span class="sxs-lookup"><span data-stu-id="a0780-107">Why is cash flow shown for only one legal entity?</span></span>

<span data-ttu-id="a0780-108">La prévision des flux de trésorerie est configurée et calculée par entité juridique.</span><span class="sxs-lookup"><span data-stu-id="a0780-108">Cash flow forecasting is configured and calculated per legal entity.</span></span> <span data-ttu-id="a0780-109">Les rapports et la capacité de prévision des flux de trésorerie Power BI dans Finance Insights indiquent les résultats.</span><span class="sxs-lookup"><span data-stu-id="a0780-109">Power BI reports and the cash flow forecasts capability in Finance insights show the results.</span></span>

<span data-ttu-id="a0780-110">La prévision de flux de trésorerie doit être configurée pour chaque entité juridique pour laquelle vous souhaitez voir une prévision.</span><span class="sxs-lookup"><span data-stu-id="a0780-110">Cash flow forecasting must be set up for each legal entity that you want to see a forecast for.</span></span> <span data-ttu-id="a0780-111">Passez en revue la configuration des prévisions de trésorerie dans toutes vos entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="a0780-111">Review the configuration of cash flow forecasting in all your legal entities.</span></span> <span data-ttu-id="a0780-112">Vous pouvez également examiner la configuration de toutes les entités juridiques pour les prévisions de flux de trésorerie et vous assurer qu'elles sont définies comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="a0780-112">Alternatively, review the configuration of all the legal entities for cash flow forecasting, and make sure that they are set as you intended.</span></span>

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a><span data-ttu-id="a0780-113">Pourquoi Power BI n'affiche pas toutes les données de flux de trésorerie ?</span><span class="sxs-lookup"><span data-stu-id="a0780-113">Why doesn't Power BI show all the cash flow data?</span></span>

<span data-ttu-id="a0780-114">Plusieurs étapes doivent être effectuées avant que les prévisions de flux de trésorerie puissent apparaître dans les vues Power BI.</span><span class="sxs-lookup"><span data-stu-id="a0780-114">Several steps must be completed before cash flow forecasts can appear in Power BI views.</span></span> <span data-ttu-id="a0780-115">Passez en revue la liste de contrôle suivante et assurez-vous que chaque étape a été effectuée :</span><span class="sxs-lookup"><span data-stu-id="a0780-115">Review the following checklist, and make sure that every step has been completed:</span></span>

- <span data-ttu-id="a0780-116">Vous devez définir des flux de trésorerie pour chaque entité juridique.</span><span class="sxs-lookup"><span data-stu-id="a0780-116">Set up cash flow for each legal entity.</span></span>
- <span data-ttu-id="a0780-117">Dans les paramètres de Comptabilité, vous devez définir la devise du système et le type de taux de change du système.</span><span class="sxs-lookup"><span data-stu-id="a0780-117">In General ledger parameters, set the system currency and the system exchange rate type.</span></span>
- <span data-ttu-id="a0780-118">Vous devez définir la devise comptable et le type de taux de change.</span><span class="sxs-lookup"><span data-stu-id="a0780-118">Set the ledger accounting currency and the exchange rate type.</span></span>
- <span data-ttu-id="a0780-119">Vous devez entrer des taux de change entre la devise de la transaction et la devise comptable.</span><span class="sxs-lookup"><span data-stu-id="a0780-119">Enter exchange rates between the transaction currency and the accounting currency.</span></span>
- <span data-ttu-id="a0780-120">Vous devez entrer des taux de change entre la devise comptable et la devise système.</span><span class="sxs-lookup"><span data-stu-id="a0780-120">Enter exchange rates between the accounting currency and the system currency.</span></span>
- <span data-ttu-id="a0780-121">Vous devez entrer des taux de change entre la devise comptable et chaque devise bancaire.</span><span class="sxs-lookup"><span data-stu-id="a0780-121">Enter exchange rates between the accounting currency and each bank currency.</span></span>

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a><span data-ttu-id="a0780-122">Pourquoi les flux de trésorerie Power BI fonctionnaient dans les versions précédentes mais sont maintenant vides ?</span><span class="sxs-lookup"><span data-stu-id="a0780-122">Why did cash flow Power BI work in previous versions but is now blank?</span></span>

<span data-ttu-id="a0780-123">Vérifiez que les mesures « Mesure de flux de trésorerie V2 » et « LedgerCovLiquidityMeasurement » du magasin d'entités ont été configurées.</span><span class="sxs-lookup"><span data-stu-id="a0780-123">Verify that the "Cash flow measure V2" and "LedgerCovLiquidityMeasurement" measurements from Entity store have been configured.</span></span> <span data-ttu-id="a0780-124">Pour plus d'informations sur l'utilisation des données dans le magasin d'entités, consultez [Intégration de Power BI avec le magasin des entités](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Vérifiez que toutes les étapes requises pour afficher le contenu Power BI ont bien été effectuées.</span><span class="sxs-lookup"><span data-stu-id="a0780-124">For more information about how to work with data in Entity store, see [Power BI integration with Entity store](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verify that all the steps that are required to view Power BI content have been completed.</span></span> <span data-ttu-id="a0780-125">Pour plus d’informations, voir [Contenu Power BI - Vue d’ensemble des disponibilités](Cash-Overview-Power-BI-content.md).</span><span class="sxs-lookup"><span data-stu-id="a0780-125">For more information, see [Cash overview Power BI content](Cash-Overview-Power-BI-content.md).</span></span>

## <a name="have-the-entity-store-entities-been-refreshed"></a><span data-ttu-id="a0780-126">Les entités du magasin d'entités ont-elles été actualisées ?</span><span class="sxs-lookup"><span data-stu-id="a0780-126">Have the Entity store entities been refreshed?</span></span>

<span data-ttu-id="a0780-127">Vous devez actualiser périodiquement vos entités pour vous assurer que les données sont à jour et exactes.</span><span class="sxs-lookup"><span data-stu-id="a0780-127">You must periodically refresh your entities to ensure that the data is current and accurate.</span></span> <span data-ttu-id="a0780-128">Pour actualiser manuellement une entité spécifique, accédez à **Administration système \> Paramétrage \> Magasin des entités**, sélectionnez l'entité, puis sélectionnez **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="a0780-128">To manually refresh a specific entity, go to **System administration \> Setup \> Entity store**, select the entity, and then select **Refresh**.</span></span> <span data-ttu-id="a0780-129">Les données peuvent également être mises à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a0780-129">The data can also be updated automatically.</span></span> <span data-ttu-id="a0780-130">Sur la page **Magasin des entités**, définissez l'option **Actualisation automatique activée** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="a0780-130">On the **Entity store** page, set the **Automatic refresh enabled** option to **Yes**.</span></span>
