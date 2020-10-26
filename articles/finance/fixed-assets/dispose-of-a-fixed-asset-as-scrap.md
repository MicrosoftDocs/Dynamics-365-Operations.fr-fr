---
title: Céder une immobilisation comme mise au rebut
description: La rubrique décrit le processus afin d'éliminer les transactions pour une immobilisation qui a été cédée comme mise au rebut.
author: moaamer
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 371cc2efa64916698da8e4230825c3c949920698
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975242"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a><span data-ttu-id="70819-103">Céder une immobilisation comme mise au rebut</span><span class="sxs-lookup"><span data-stu-id="70819-103">Dispose of a fixed asset as scrap</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70819-104">La rubrique décrit le processus afin d'éliminer les transactions pour une immobilisation qui a été cédée comme mise au rebut.</span><span class="sxs-lookup"><span data-stu-id="70819-104">The topic describes the process of eliminating transactions for a fixed asset that was disposed of as scrap.</span></span> <span data-ttu-id="70819-105">Les types de transaction pouvant être éliminés incluent des transactions d'acquisition et d'amortissement cumulé d'un actif et toute autre transaction d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="70819-105">The transaction types that can be eliminated include an asset's acquisition and accumulated depreciation transactions and other fixed asset transactions.</span></span> <span data-ttu-id="70819-106">L'élimination de ces transactions a un impact sur les comptes de bilan, comme l'ajustement d'acquisition, l'ajustement d'amortissement, la réévaluation, la description, et les comptes de revalorisation et de dévalorisation.</span><span class="sxs-lookup"><span data-stu-id="70819-106">Elimination of these transactions affects balance sheet accounts, such as acquisition adjustment, depreciation adjustment, revaluation, write-up, and write-down accounts.</span></span>

| <span data-ttu-id="70819-107">Transaction</span><span class="sxs-lookup"><span data-stu-id="70819-107">Transaction</span></span>                                         | <span data-ttu-id="70819-108">Débit (Dr.)</span><span class="sxs-lookup"><span data-stu-id="70819-108">Debit (Dr.)</span></span> | <span data-ttu-id="70819-109">Crédit (Cr.)</span><span class="sxs-lookup"><span data-stu-id="70819-109">Credit (Cr.)</span></span> |
|-----------------------------------------------------|-------------|--------------|
| <span data-ttu-id="70819-110">Amortissement cumulé dr.</span><span class="sxs-lookup"><span data-stu-id="70819-110">Dr. Accumulated depreciation</span></span>                        | <span data-ttu-id="70819-111">O</span><span class="sxs-lookup"><span data-stu-id="70819-111">X</span></span>           |              |
| <span data-ttu-id="70819-112">Perte/gain d'immobilisations cr.</span><span class="sxs-lookup"><span data-stu-id="70819-112">Cr. Fixed assets gain/loss</span></span>                          |             | <span data-ttu-id="70819-113">O</span><span class="sxs-lookup"><span data-stu-id="70819-113">X</span></span>            |
| <span data-ttu-id="70819-114">Perte/gain d'immobilisations dr.</span><span class="sxs-lookup"><span data-stu-id="70819-114">Dr. Fixed assets gain/loss</span></span>                          | <span data-ttu-id="70819-115">O</span><span class="sxs-lookup"><span data-stu-id="70819-115">X</span></span>           |              |
| <span data-ttu-id="70819-116">Compte d'acquisition d'immobilisations cr.</span><span class="sxs-lookup"><span data-stu-id="70819-116">Cr. Fixed asset acquisition account</span></span>                 |             | <span data-ttu-id="70819-117">O</span><span class="sxs-lookup"><span data-stu-id="70819-117">X</span></span>            |
| <span data-ttu-id="70819-118">Gain/perte d'immobilisations dr. (valeur nette \[NBV\])</span><span class="sxs-lookup"><span data-stu-id="70819-118">Dr. Fixed assets gain/loss (net book value \[NBV\])</span></span> | <span data-ttu-id="70819-119">O</span><span class="sxs-lookup"><span data-stu-id="70819-119">X</span></span>           |              |
| <span data-ttu-id="70819-120">Perte/gain d'immobilisations cr. (NV)</span><span class="sxs-lookup"><span data-stu-id="70819-120">Cr. Fixed assets gain/loss (NBV)</span></span>                    |             | <span data-ttu-id="70819-121">O</span><span class="sxs-lookup"><span data-stu-id="70819-121">X</span></span>            |

> [!NOTE]
> <span data-ttu-id="70819-122">Nous vous recommandons de travailler en étroite collaboration avec votre directeur ou votre contrôleur financier afin d'identifier les comptes appropriés à utiliser pour chaque type de transaction et afin de vérifier que le processus d'élimination et les transactions qu'il génère mettent à jour correctement ces comptes.</span><span class="sxs-lookup"><span data-stu-id="70819-122">We recommend that you work closely with your company's chief financial officer (CFO) or controller to identify the correct accounts that should be used for each transaction type, and also to verify that the disposal process and the transactions that it generates update those accounts correctly.</span></span>

<span data-ttu-id="70819-123">Avant d'éliminer une immobilisation comme mise au rebut, vous devez créer des comptes généraux associés à la valeur d'acquisition de l'actif, l'amortissement pour l'année actuel, l'amortissement pour les années passées et la VN de l'actif.</span><span class="sxs-lookup"><span data-stu-id="70819-123">Before you dispose of a fixed asset as scrap, you must create ledger accounts that are associated with the asset's acquisition value, depreciation for the current year, depreciation for previous years, and the asset's NBV.</span></span> <span data-ttu-id="70819-124">Les types de transactions d'immobilisation sont répertoriés sur la page **Profils de validation d'immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="70819-124">The fixed asset transaction types are listed on the **Fixed assets posting profile** page.</span></span> <span data-ttu-id="70819-125">Accédez à **Immobilisations \> Paramétrage \> Profils de validation d'immobilisations**, puis sur l'organisateur **Cession**, sélectionnez **Mise au rebut** dans le champ au-dessus de la grille.</span><span class="sxs-lookup"><span data-stu-id="70819-125">Go to **Fixed assets \> Setup \> Fixed asset posting profiles**, and then, on the **Disposal** FastTab, select **Scrap** in the field above the grid.</span></span> <span data-ttu-id="70819-126">L'illustration suivante indique que la liste des types de transactions d'immobilisation sur la page **Profils de validation d'immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="70819-126">The following illustration shows the list of fixed asset transaction types on the **Fixed asset posting profiles** page.</span></span>


<span data-ttu-id="70819-127">[![Éliminer un actif comme mise au rebut, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span><span class="sxs-lookup"><span data-stu-id="70819-127">[![Disposing of an asset as scap, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span></span>

<span data-ttu-id="70819-128">Pour l'exemple suivant, une immobilisation a été acquise le 1er janvier 2018, et elle sera mise au rebut le 31 mars 2019.</span><span class="sxs-lookup"><span data-stu-id="70819-128">For the following example, a fixed asset was acquired on January 1, 2018, and it will be scrapped on March 31, 2019.</span></span>

- <span data-ttu-id="70819-129">**Prix d'acquisition :** 24 000 euros (EUR)</span><span class="sxs-lookup"><span data-stu-id="70819-129">**Acquisition price:** 24,000.00 US dollars (USD)</span></span>
- <span data-ttu-id="70819-130">**Durée de vie :** deux ans</span><span class="sxs-lookup"><span data-stu-id="70819-130">**Service life:** Two years</span></span>
- <span data-ttu-id="70819-131">**Méthode d'amortissement :** linéaire sur la durée de vie</span><span class="sxs-lookup"><span data-stu-id="70819-131">**Depreciation method:** Straight line service life</span></span>
- <span data-ttu-id="70819-132">**Montant de l'amortissement :** 1 000 EUR par mois</span><span class="sxs-lookup"><span data-stu-id="70819-132">**Depreciation amount:** 1,000.00 USD per month</span></span>

<span data-ttu-id="70819-133">La VN d'une immobilisation est calculée à l'aide de la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="70819-133">The NBV of a fixed asset is calculated by using the following formula:</span></span>

<span data-ttu-id="70819-134">Valeur nette = Prix d'achat - amortissement</span><span class="sxs-lookup"><span data-stu-id="70819-134">Net book value = Acquisition price – Depreciation</span></span>

<span data-ttu-id="70819-135">Dans cet exemple, l'immobilisation a été acquise et amortie sur 15 mois, de janvier 2018 à mars 2019.</span><span class="sxs-lookup"><span data-stu-id="70819-135">In this example, the fixed asset was acquired and was depreciated for 15 months, from January 2018 through March 2019.</span></span> <span data-ttu-id="70819-136">Par conséquent, la VN de l'actif est 9 000 EUR (24 000 EUR - 15 000 EUR).</span><span class="sxs-lookup"><span data-stu-id="70819-136">Therefore, the asset's NBV is 9,000.00 USD (24,000.00 USD – 15,000.00 USD).</span></span>

<span data-ttu-id="70819-137">[![Exemple d'amortissement des immobilisations](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span><span class="sxs-lookup"><span data-stu-id="70819-137">[![Fixed asset depreciation example](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span></span>


<span data-ttu-id="70819-138">Pour créer un journal de cession, **Immobilisations \> Entrées de journal \> Journal des immobilisations**, puis, dans le volet Actions, sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="70819-138">To create a disposal journal, go to **Fixed assets \> Journal entries \> Fixed assets journal**, and then, on the Action Pane, select **Lines**.</span></span> <span data-ttu-id="70819-139">Sélectionnez **Cession – Mise au rebut**, puis sélectionnez un ID d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="70819-139">Select **Disposal – scrap**, and then select a fixed asset ID.</span></span> <span data-ttu-id="70819-140">Pour céder intégralement l'actif, ne saisissez pas de valeur dans le champ **Débit** ou dans le champ **Crédit**.</span><span class="sxs-lookup"><span data-stu-id="70819-140">To fully dispose of the asset, don't enter a value in either the **Debit** field or the **Credit** field.</span></span>

<span data-ttu-id="70819-141">[![Journal des immobilisations](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span><span class="sxs-lookup"><span data-stu-id="70819-141">[![Fixed assets journal](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span></span>

<span data-ttu-id="70819-142">La transaction de la mise au rebut de la cession de l'immobilisation change les champs de valeur pour le registre des immobilisations des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="70819-142">The fixed asset disposal scrap transaction changes the field values for the fixed asset book in the following ways:</span></span>

- <span data-ttu-id="70819-143">Dans la section **Solde**, le champ **Statut** est mis jour sur **Mis au rebut**.</span><span class="sxs-lookup"><span data-stu-id="70819-143">In the **Balance** section, the **Status** field is updated to **Scrapped**.</span></span>
- <span data-ttu-id="70819-144">Dans la section **Problème**, le champ **Date de cession** est défini sur la date à laquelle l'immobilisation a été mise au rebut.</span><span class="sxs-lookup"><span data-stu-id="70819-144">In the **Issue** section, the **Disposal date** field is set to the date when the asset was scrapped.</span></span>

<span data-ttu-id="70819-145">[![Détail du journal des immobilisations](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span><span class="sxs-lookup"><span data-stu-id="70819-145">[![Fixed assets journal detail](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span></span>

<span data-ttu-id="70819-146">L'illustration suivante présente le solde d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="70819-146">The following illustration shows the fixed asset balance.</span></span>

<span data-ttu-id="70819-147">[![Solde d'immobilisation](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span><span class="sxs-lookup"><span data-stu-id="70819-147">[![Fixed asset balance](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span></span>

<span data-ttu-id="70819-148">L'illustration suivante présente le document validé.</span><span class="sxs-lookup"><span data-stu-id="70819-148">The following illustration shows the voucher that is posted.</span></span>

<span data-ttu-id="70819-149">[![Valeur comptable nette](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span><span class="sxs-lookup"><span data-stu-id="70819-149">[![Net book value](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span></span>
