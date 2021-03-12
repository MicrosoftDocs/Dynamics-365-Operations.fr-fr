---
title: Taxe de vente harmonisée canadienne
description: Cette rubrique donne des informations sur la fonctionnalité de prise en charge de la taxe de vente harmonisée pour le secteur public.
author: velofog
manager: Ann Beebe
ms.date: 04/2/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PSNCanadianHSTTaxFeature
audience: Application User
ms.devlang: ''
ms.reviewer: roschlom
ms.tgt_pltfrm: ''
ms.custom: ''
ms.search.region: Global
ms.search.industry: public sector
ms.author: roschlom
ms.search.validFrom: 2020-4-01
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 9fce946fd997b0f6b3a86ff4e990700e23b54247
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968239"
---
# <a name="calculating-canadian-harmonized-sales-tax"></a><span data-ttu-id="b12f3-103">Calcul de la taxe de vente harmonisée canadienne</span><span class="sxs-lookup"><span data-stu-id="b12f3-103">Calculating Canadian Harmonized Sales Tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b12f3-104">Cette fonctionnalité permet à votre organisation de se conformer aux règles de la taxe de vente harmonisée (HST) canadienne.</span><span class="sxs-lookup"><span data-stu-id="b12f3-104">This feature lets your organization comply with Canadian Harmonized Sales Tax (HST) rules.</span></span> <span data-ttu-id="b12f3-105">La taxe HST aide les entités du secteur public à se conformer aux politiques fiscales canadiennes.</span><span class="sxs-lookup"><span data-stu-id="b12f3-105">The HST helps public sector entities maintain compliance with Canadian tax policies.</span></span> <span data-ttu-id="b12f3-106">Elle est utilisée par certaines provinces canadiennes et combine la taxe sur les produits et services et la taxe de vente provinciale.</span><span class="sxs-lookup"><span data-stu-id="b12f3-106">The HST is used by some Canadian provinces and is a combination of the Goods and Services Tax and the Provincial Sales Tax.</span></span>
<span data-ttu-id="b12f3-107">Des parties de la taxe HST peuvent être récupérées par les entités du secteur public si la taxe a été payée aux vendeurs, en fonction de l’intention de l’achat.</span><span class="sxs-lookup"><span data-stu-id="b12f3-107">Portions of the HST can be recovered by public sector entities if the tax has been paid to vendors, depending on the intent of the purchase.</span></span> <span data-ttu-id="b12f3-108">L’intention est désignée par les valeurs de dimension financière et le compte principal sur une ligne de transaction d’un document d’achat (par exemple, une demande d’achat, une commande fournisseur ou une facture fournisseur).</span><span class="sxs-lookup"><span data-stu-id="b12f3-108">The intent is designated by the financial dimension values and main account on a transaction line on a purchase document (for example, a purchase requisition, purchase order, or vendor invoice).</span></span>
<span data-ttu-id="b12f3-109">Remarque : cette fonctionnalité ne s’applique pas au journal des factures de la compabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b12f3-109">Note: This functionality does not apply to the Accounts payable Invoice journal.</span></span>

## <a name="enabling-the-hst-feature"></a><span data-ttu-id="b12f3-110">Activation de la fonctionnalité HST</span><span class="sxs-lookup"><span data-stu-id="b12f3-110">Enabling the HST feature</span></span>

1. <span data-ttu-id="b12f3-111">Allez dans **Comptabilité > Paramétrage de la comptabilité > Paramètres de comptabilité > Groupe de taxe**.</span><span class="sxs-lookup"><span data-stu-id="b12f3-111">Go to **General ledger > Ledger setup >General ledger parameters > Sales tax group**.</span></span>
2. <span data-ttu-id="b12f3-112">Définissez **Appliquer les règles de la taxe de vente harmonisée en vigueur au Canada** sur **Oui** pour activer la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="b12f3-112">Set the **Apply Canadian harmonized sales tax rules** to **Yes** to enable the feature.</span></span>

## <a name="define-the-dimensions-for-hst-rules"></a><span data-ttu-id="b12f3-113">Définir les dimensions des règles HST</span><span class="sxs-lookup"><span data-stu-id="b12f3-113">Define the dimensions for HST rules</span></span>

1. <span data-ttu-id="b12f3-114">Allez dans **Taxe > Taxes indirectes > Taxe**, puis cliquez sur **Dimensions de taxe de vente harmonisée**.</span><span class="sxs-lookup"><span data-stu-id="b12f3-114">Go to **Tax > Indirect taxes > Sales tax**, and then click **Harmonized sales tax dimensions**.</span></span> 
2. <span data-ttu-id="b12f3-115">Dans la page **Dimensions de taxe de vente harmonisée**, sélectionnez et hiérarchisez les dimensions financières (ainsi que le compte principal, le cas échéant) que vous souhaitez utiliser pour la taxe HST.</span><span class="sxs-lookup"><span data-stu-id="b12f3-115">In the **Harmonized sales tax dimensions** page, select and prioritize the financial dimensions (along with the main account, if appropriate) that you want to use for HST.</span></span> <span data-ttu-id="b12f3-116">Les dimensions financières des structures de compte sont associées au plan comptable.</span><span class="sxs-lookup"><span data-stu-id="b12f3-116">The financial dimensions in the account structures are associated with the chart of accounts.</span></span> <span data-ttu-id="b12f3-117">La priorité des dimensions aide à définir quelle taxe est appliquée s’il y a plusieurs possibilités.</span><span class="sxs-lookup"><span data-stu-id="b12f3-117">The priority of dimensions helps dictate which tax gets applied if there are multiple possibilities.</span></span> 



### <a name="note-only-the-financial-dimensions-that-are-used-in-the-current-legal-entity-will-be-available"></a><span data-ttu-id="b12f3-118">Remarque : seules les dimensions financières utilisées dans l’entité juridique actuelle sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="b12f3-118">Note: Only the financial dimensions that are used in the current legal entity will be available.</span></span>

## <a name="set-up-hst-rules"></a><span data-ttu-id="b12f3-119">Configurer les règles HST</span><span class="sxs-lookup"><span data-stu-id="b12f3-119">Set up HST rules</span></span>

<span data-ttu-id="b12f3-120">Après avoir défini les dimensions de la taxe HST, vous définissez les règles de dimension comptable qui s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="b12f3-120">After you define dimensions for HST, you set up ledger dimension rules that apply.</span></span> <span data-ttu-id="b12f3-121">Les règles HST affectent des codes de taxe en fonction des répartitions de compte d’une ligne de document.</span><span class="sxs-lookup"><span data-stu-id="b12f3-121">HST rules assign tax codes based on a document line’s account distributions.</span></span> <span data-ttu-id="b12f3-122">En effet, différents codes de taxe peuvent être appliqués, en fonction de l’objectif de l’achat.</span><span class="sxs-lookup"><span data-stu-id="b12f3-122">This is because different tax codes might be applied, based on the purpose of the purchase.</span></span>
1. <span data-ttu-id="b12f3-123">Allez dans **Taxe > Taxes indirectes > Taxe**, puis cliquez sur **Règles de la taxe de vente harmonisée**.</span><span class="sxs-lookup"><span data-stu-id="b12f3-123">Go to **Tax > Indirect taxes > Sales tax**, and then click **Harmonized sales tax rules**.</span></span> 
2. <span data-ttu-id="b12f3-124">Dans la page **Règles de la taxe de vente harmonisée**, les dimensions que vous avez sélectionnées pour la taxe HST s’affichent par ordre de priorité de gauche à droite.</span><span class="sxs-lookup"><span data-stu-id="b12f3-124">In the **Harmonized sales tax rules** page, the dimensions that you selected for HST appear in order of priority from left to right.</span></span> <span data-ttu-id="b12f3-125">Les colonnes restantes concernent les codes de taxe associés à cette combinaison de dimensions.</span><span class="sxs-lookup"><span data-stu-id="b12f3-125">The remaining columns are for sales tax codes associated with that dimension combination.</span></span> 
3. <span data-ttu-id="b12f3-126">Dans le volet Actions, cliquez sur **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="b12f3-126">On the Action Pane, click **New** to create a new record.</span></span>
4. <span data-ttu-id="b12f3-127">Définissez les valeurs de dimension.</span><span class="sxs-lookup"><span data-stu-id="b12f3-127">Define the dimension values.</span></span> 

### <a name="notes"></a><span data-ttu-id="b12f3-128">Notes :</span><span class="sxs-lookup"><span data-stu-id="b12f3-128">Notes:</span></span>
- <span data-ttu-id="b12f3-129">Deux lignes ne peuvent pas avoir des paramètres identiques.</span><span class="sxs-lookup"><span data-stu-id="b12f3-129">No two rows can have identical settings.</span></span>
- <span data-ttu-id="b12f3-130">Vous pouvez supprimer ou modifier des règles existantes.</span><span class="sxs-lookup"><span data-stu-id="b12f3-130">You can delete or modify existing rules.</span></span>
- <span data-ttu-id="b12f3-131">Vous pouvez choisir de laisser un segment vide.</span><span class="sxs-lookup"><span data-stu-id="b12f3-131">You can choose to leave a segment blank.</span></span> <span data-ttu-id="b12f3-132">Il fonctionnera comme un « caractère générique ».</span><span class="sxs-lookup"><span data-stu-id="b12f3-132">It will function as a “wild card.”</span></span> <span data-ttu-id="b12f3-133">Une ligne totalement vide s’applique à toutes les combinaisons de comptes pour lesquelles une règle plus spécifique n’est pas appliquée.</span><span class="sxs-lookup"><span data-stu-id="b12f3-133">A totally blank row applies to all account combinations that do not have a more specific rule applied.</span></span> <span data-ttu-id="b12f3-134">Vous pouvez ajouter une ligne avec toutes les dimensions financières vides si des codes de taxe doivent s’appliquer lorsqu’aucune règle ne correspond.</span><span class="sxs-lookup"><span data-stu-id="b12f3-134">You may want to add one row with all blank financial dimensions if there are sales tax codes which should apply when no rules match.</span></span>

5. <span data-ttu-id="b12f3-135">Sélectionnez jusqu’à cinq codes de taxe pouvant être appliqués aux dimensions sélectionnées pour la taxe HST.</span><span class="sxs-lookup"><span data-stu-id="b12f3-135">Select up to five sales tax codes that can be applied against the dimensions that have been selected for HST.</span></span> <span data-ttu-id="b12f3-136">Remarque : pour être appliqués, les codes de taxe définis ici doivent être présents dans la règle HST et dans les deux champs **Groupe de taxe** et **Groupe de taxe d’article** sélectionnés sur les lignes du document de transaction.</span><span class="sxs-lookup"><span data-stu-id="b12f3-136">Note To be applied, the sales tax codes defined here must be present in the HST rule and in both the **Sales tax group** and **Item sales tax group** that are selected on the transaction document lines.</span></span> 
6. <span data-ttu-id="b12f3-137">Cliquez sur **Enregistrer** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="b12f3-137">Click **Save** to save your changes.</span></span> 

### <a name="notes"></a><span data-ttu-id="b12f3-138">Notes :</span><span class="sxs-lookup"><span data-stu-id="b12f3-138">Notes:</span></span>
- <span data-ttu-id="b12f3-139">Après avoir défini les règles de la taxe HST, vous ne pouvez pas modifier les dimensions préexistantes de la taxe HST.</span><span class="sxs-lookup"><span data-stu-id="b12f3-139">After you define rules for HST, you cannot modify the pre-existing dimensions for HST.</span></span> <span data-ttu-id="b12f3-140">Pour apporter des modifications, vous devez d’abord supprimer l’ensemble des règles et codes de taxe dans le formulaire **Règles de la taxe de vente harmonisée**.</span><span class="sxs-lookup"><span data-stu-id="b12f3-140">To make changes, you must first remove all rules and sales tax codes in the **Harmonized sales tax rules** form.</span></span>
- <span data-ttu-id="b12f3-141">Plusieurs codes de taxe peuvent s’appliquer à une règle.</span><span class="sxs-lookup"><span data-stu-id="b12f3-141">More than one tax code can apply to a rule.</span></span>
- <span data-ttu-id="b12f3-142">Une seule règle s’applique à une répartition de compte.</span><span class="sxs-lookup"><span data-stu-id="b12f3-142">Only one rule applies to an account distribution.</span></span>
- <span data-ttu-id="b12f3-143">Plusieurs règles peuvent s’appliquer à une ligne d’un document de transaction comportant plusieurs répartitions.</span><span class="sxs-lookup"><span data-stu-id="b12f3-143">More than one rule can apply to a line in a transaction document that has multiple distributions.</span></span>

## <a name="how-rules-are-applied"></a><span data-ttu-id="b12f3-144">Mode d’application des règles</span><span class="sxs-lookup"><span data-stu-id="b12f3-144">How rules are applied</span></span>

<span data-ttu-id="b12f3-145">L’ordre dans lequel les règles sont appliquées est relativement complexe.</span><span class="sxs-lookup"><span data-stu-id="b12f3-145">The order in which rules are applied are somewhat complex.</span></span> <span data-ttu-id="b12f3-146">Le graphique suivant illustre le principe :</span><span class="sxs-lookup"><span data-stu-id="b12f3-146">The following graphic illustrates the principle:</span></span>

> <span data-ttu-id="b12f3-147">[![Définir les règles HST](./media/define-hst-rules.png)](./media/define-hst-rules.png)</span><span class="sxs-lookup"><span data-stu-id="b12f3-147">[![Define HST rules](./media/define-hst-rules.png)](./media/define-hst-rules.png)</span></span>

<span data-ttu-id="b12f3-148">Les codes de taxe sélectionnés pour la ligne de dimension sont les suivants si la transaction utilise un groupe de taxe et un groupe de taxe d’article avec tous les codes de taxe inclus.</span><span class="sxs-lookup"><span data-stu-id="b12f3-148">The sales tax codes selected for the dimension line will be following if the transaction uses a Sales tax group and Item sales tax group with all of the tax codes included.</span></span>

|<span data-ttu-id="b12f3-149">Dimensions financières</span><span class="sxs-lookup"><span data-stu-id="b12f3-149">Financial Dimensions</span></span>                     | <span data-ttu-id="b12f3-150">Codes taxe</span><span class="sxs-lookup"><span data-stu-id="b12f3-150">Sales tax codes</span></span>|
|-----------------------------------------|-----------------|   
|<span data-ttu-id="b12f3-151">Fonds 101, n’importe quelle division à l’exception des divisions 111 et 121</span><span class="sxs-lookup"><span data-stu-id="b12f3-151">Fund 101, Any Division except 111 and 121</span></span>| <span data-ttu-id="b12f3-152">Taxe1</span><span class="sxs-lookup"><span data-stu-id="b12f3-152">Tax1</span></span>            |
|   <span data-ttu-id="b12f3-153">Fonds 101, Division 111</span><span class="sxs-lookup"><span data-stu-id="b12f3-153">Fund 101, Division 111</span></span>                  |   <span data-ttu-id="b12f3-154">Taxe1, Taxe2, Taxe3</span><span class="sxs-lookup"><span data-stu-id="b12f3-154">Tax1, Tax2, Tax3</span></span>|
|   <span data-ttu-id="b12f3-155">Fonds 101, Division 121</span><span class="sxs-lookup"><span data-stu-id="b12f3-155">Fund 101, Division 121</span></span>                  | <span data-ttu-id="b12f3-156">Taxe2, Taxe3</span><span class="sxs-lookup"><span data-stu-id="b12f3-156">Tax2, Tax3</span></span>      |
|   <span data-ttu-id="b12f3-157">Fonds 303, n’importe quelle division à l’exception de la division 141</span><span class="sxs-lookup"><span data-stu-id="b12f3-157">Fund 303, Any Division except 141</span></span>         | <span data-ttu-id="b12f3-158">Taxe1, Taxe2, Taxe3</span><span class="sxs-lookup"><span data-stu-id="b12f3-158">Tax1, Tax2, Tax3</span></span>|
|   <span data-ttu-id="b12f3-159">Fonds 303, Division 141</span><span class="sxs-lookup"><span data-stu-id="b12f3-159">Fund 303, Division 141</span></span>                  | <span data-ttu-id="b12f3-160">Taxe1</span><span class="sxs-lookup"><span data-stu-id="b12f3-160">Tax1</span></span>            |
