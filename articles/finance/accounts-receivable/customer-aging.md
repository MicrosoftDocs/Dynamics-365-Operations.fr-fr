---
title: Balance âgée des clients
description: L’état Balance âgée des clients affiche les soldes dus par les clients, triés par intervalle de dates ou plage âgée.
author: JodiChristiansen
manager: AnnBe
ms.date: 10/06/2020
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
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9291299e0b2ee040bc25ef21237a73c3bc0ea412
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995661"
---
# <a name="customer-aging-report"></a><span data-ttu-id="50d64-103">Balance âgée des clients</span><span class="sxs-lookup"><span data-stu-id="50d64-103">Customer aging report</span></span> 

<span data-ttu-id="50d64-104">L’état **Balance âgée des clients** affiche les soldes dus par les clients, triés par intervalle de dates ou plage âgée.</span><span class="sxs-lookup"><span data-stu-id="50d64-104">The **Customer aging** report displays the balances that are due from customers, sorted by date interval, or aging period.</span></span>

<span data-ttu-id="50d64-105">Lorsque vous générez cet état, les paramètres par défaut suivants sont affichés.</span><span class="sxs-lookup"><span data-stu-id="50d64-105">When you generate this report, the following default parameters are displayed.</span></span> <span data-ttu-id="50d64-106">Ces paramètres permettent de filtrer les données qui seront affichées dans l’état.</span><span class="sxs-lookup"><span data-stu-id="50d64-106">You can use these parameters to filter the data that will be displayed on the report.</span></span> <span data-ttu-id="50d64-107">Pour plus d’informations, voir [Paramétrer des recouvrements](set-up-collections.md).</span><span class="sxs-lookup"><span data-stu-id="50d64-107">For more information, see [Set up collections](set-up-collections.md).</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="50d64-108">Champ</span><span class="sxs-lookup"><span data-stu-id="50d64-108">Field</span></span></p></th>
<th><p><span data-ttu-id="50d64-109">Description</span><span class="sxs-lookup"><span data-stu-id="50d64-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50d64-110"><strong>Classification de facturation</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-110"><strong>Billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-111">Sélectionnez une ou plusieurs classifications de facturation à inclure dans l’état.</span><span class="sxs-lookup"><span data-stu-id="50d64-111">Select one or more billing classifications to include on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="50d64-112">**Remarque :** ce contrôle n’est disponible que si la clé de configuration <STRONG>Secteur public</STRONG> est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="50d64-112">**Note:** This control is available only if the <STRONG>Public Sector</STRONG> configuration key is selected.</span></span></P>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d64-113"><strong>Ajouter des transactions sans classification de facturation</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-113"><strong>Include transactions without a billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-114">Lorsque cette case à cocher est activée, les transactions sans classification de facturation affectée sont affichées dans l’état.</span><span class="sxs-lookup"><span data-stu-id="50d64-114">If this check box is selected, all transactions that do not have a billing classification assigned to them will be displayed on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="50d64-115">**Remarque :** ce contrôle n’est disponible que si la clé de configuration <STRONG>Secteur public</STRONG> est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="50d64-115">**Note:** This control is available only if the <STRONG>Public sector</STRONG> configuration key is selected.</span></span></P>

</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d64-116"><strong>Agé tel que</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-116"><strong>Aging as of</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-117">Entrez la date utilisée sur la plage âgée actuelle.</span><span class="sxs-lookup"><span data-stu-id="50d64-117">Enter the date used on the current aging bucket.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d64-118"><strong>Solde en date du</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-118"><strong>Balance as of</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-119">Entrez la date pour laquelle afficher les soldes du client.</span><span class="sxs-lookup"><span data-stu-id="50d64-119">Enter the date to view the customer balances for.</span></span> <span data-ttu-id="50d64-120">Elle est également appelée date limite pour les transactions.</span><span class="sxs-lookup"><span data-stu-id="50d64-120">This is also known as a cutoff date for transactions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d64-121"><strong>Date de début</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-121"><strong>Start date</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-122">Entrez une date comprise dans le premier intervalle de périodes ou dans la plage âgée à inclure dans l’état.</span><span class="sxs-lookup"><span data-stu-id="50d64-122">Enter a date that is in the first period interval or aging period to include on the report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d64-123"><strong>Critères</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-123"><strong>Criteria</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-124">Sélectionnez le type de date sur lequel baser l’état.</span><span class="sxs-lookup"><span data-stu-id="50d64-124">Select the type of date to base the report on.</span></span></p>
<ul>
<li><p><span data-ttu-id="50d64-125"><strong>Date de transaction</strong> – Date de validation des transactions.</span><span class="sxs-lookup"><span data-stu-id="50d64-125"><strong>Transaction date</strong> – The posting date of the transactions.</span></span> <span data-ttu-id="50d64-126">Par exemple, il peut s’agir d’une date de facture qui sert de base au calcul de date d’échéance.</span><span class="sxs-lookup"><span data-stu-id="50d64-126">For example, this might be an invoice date that is the basis for the calculation of the due date.</span></span></p></li>
<li><p><span data-ttu-id="50d64-127"><strong>Date d’échéance</strong> – Date d’échéance des transactions, basée sur les conditions de paiement.</span><span class="sxs-lookup"><span data-stu-id="50d64-127"><strong>Due date</strong> – The due date of the transactions, based on the terms of payment.</span></span></p></li>
<li><p><span data-ttu-id="50d64-128"><strong>Date de document</strong> – Date de document définie par l’utilisateur, qui sert de base de calcul de la date d’échéance.</span><span class="sxs-lookup"><span data-stu-id="50d64-128"><strong>Document date</strong> – A user-defined document date that is the basis for the calculation of the due date.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d64-129"><strong>Définition de la période de balance âgée</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-129"><strong>Aging period definition</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-130">Sélectionnez une définition de période de balance âgée.</span><span class="sxs-lookup"><span data-stu-id="50d64-130">Select an aging period definition.</span></span> <span data-ttu-id="50d64-131">Le champ <strong>Intervalle</strong> n’est pas utilisé si vous sélectionnez une définition de plage âgée.</span><span class="sxs-lookup"><span data-stu-id="50d64-131">The <strong>Interval</strong> field is not used if you select an aging period definition.</span></span></p>
<p><span data-ttu-id="50d64-132">Les définitions de plage âgée comprenant plus de six plages âgées ne peuvent pas être utilisées dans l’état imprimé.</span><span class="sxs-lookup"><span data-stu-id="50d64-132">Aging period definitions that have more than six aging periods cannot be used on the printed report.</span></span></p>
<div class="alert">

<span data-ttu-id="50d64-133">**Remarque :** vous pouvez configurer des plages âgées sur la page <STRONG>Définitions des plages âgées</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="50d64-133">**Note:** You can set up aging periods on the <STRONG>Aging period definitions</STRONG> page.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d64-134"><strong>Imprimer la description de la période de balance âgée</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-134"><strong>Print aging period description</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-135">Sélectionnez <strong>Oui</strong> pour inclure des descriptions de plage âgée en haut de chaque colonne de plage âgée de l’état.</span><span class="sxs-lookup"><span data-stu-id="50d64-135">Select <strong>Yes</strong> to include aging period descriptions at the top of each aging period column on the report.</span></span> <span data-ttu-id="50d64-136">Sélectionnez <strong>Non</strong> pour imprimer l’état sans les en-têtes de colonnes.</span><span class="sxs-lookup"><span data-stu-id="50d64-136">Select <strong>No</strong> to print the report without column headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d64-137"><strong>Intervalle</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-137"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-138">Permet de définir la période à utiliser en entrant le nombre d’unités de jours ou de mois dans chaque période.</span><span class="sxs-lookup"><span data-stu-id="50d64-138">Define the period to use by entering the number of the day or month units in each period.</span></span> <span data-ttu-id="50d64-139">Par exemple, pour afficher des informations de balance âgée par semaine, entrez 7 dans ce champ, puis sélectionnez <strong>Jour</strong> dans le champ <strong>Jour/mois</strong>.</span><span class="sxs-lookup"><span data-stu-id="50d64-139">For example, to view aging information by week, enter 7 in this field and select <strong>Day</strong> in the <strong>Day/Mth</strong> field.</span></span></p>
<div class="alert">

<span data-ttu-id="50d64-140">**Remarque :** les informations entrées dans ce champ ne sont utilisées que si vous n’avez pas sélectionné de définition de plage âgée.</span><span class="sxs-lookup"><span data-stu-id="50d64-140">**Note:** The information that you enter in this field is used only if you have not selected an aging period definition.</span></span> <span data-ttu-id="50d64-141">Sinon, le sens d’impression est défini sur la définition de la plage âgée.</span><span class="sxs-lookup"><span data-stu-id="50d64-141">Otherwise, the printing direction is defined on the aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d64-142"><strong>Jour/mois</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-142"><strong>Day/Mth</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-143">Permet de sélectionner l’unité, soit <strong>Jour</strong> soit <strong>Mois</strong>, utilisée pour définir la période dans le champ <strong>Intervalle</strong>.</span><span class="sxs-lookup"><span data-stu-id="50d64-143">Select the unit, either <strong>Day</strong> or <strong>Month</strong>, that is used to define the period in the <strong>Interval</strong> field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d64-144"><strong>Sens d’impression</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-144"><strong>Printing direction</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-145">Sélectionnez si les soldes doivent être calculés et si l’état de plage âgée doit être imprimée pour des périodes passées et futures.</span><span class="sxs-lookup"><span data-stu-id="50d64-145">Select whether to calculate balances and print the aging report for past or future periods.</span></span> <span data-ttu-id="50d64-146">Les dates sont évaluées par rapport à la date sélectionnée dans le champ <strong>Solde à la date</strong>.</span><span class="sxs-lookup"><span data-stu-id="50d64-146">The dates are evaluated relative to the date that is selected in the <strong>Balance as on</strong> field.</span></span> <span data-ttu-id="50d64-147">Sélectionnez <strong>En arrière</strong> pour afficher les informations pour les périodes passées.</span><span class="sxs-lookup"><span data-stu-id="50d64-147">Select <strong>Backward</strong> to show information for past periods.</span></span> <span data-ttu-id="50d64-148">Sélectionnez <strong>En avant</strong> pour afficher les informations pour les périodes futures.</span><span class="sxs-lookup"><span data-stu-id="50d64-148">Select <strong>Forward</strong> to show information for future periods.</span></span></p>
<div class="alert"><span data-ttu-id="50d64-149">
  
<STRONG>Remarque :</STRONG> les informations entrées dans ce champ ne sont utilisées que si vous n’avez pas sélectionné de définition de plage âgée.</span><span class="sxs-lookup"><span data-stu-id="50d64-149">
  
<STRONG>Note:</STRONG> The information that you enter in this field is used only if you have not selected an aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d64-150"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-150"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-151">Sélectionnez cette option pour répertorier les transactions comprises dans les soldes affichés dans l’état.</span><span class="sxs-lookup"><span data-stu-id="50d64-151">Select to list the transactions that are included in the balances that are shown on the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d64-152"><strong>Inclure les montants en devise de transaction</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-152"><strong>Include amounts in transaction currency</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-153">Sélectionnez cette option pour inclure les montants dans la devise de transaction, en plus des montants dans la devise comptable.</span><span class="sxs-lookup"><span data-stu-id="50d64-153">Select to include amounts in the transaction currency in addition to amounts in the accounting currency.</span></span> <span data-ttu-id="50d64-154">Si cette case à cocher n’est pas activée, les montants de l’état ne sont affichés que dans la devise comptable.</span><span class="sxs-lookup"><span data-stu-id="50d64-154">If this check box is not selected, the amounts on the report are displayed only in the accounting currency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d64-155"><strong>Solde négatif</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-155"><strong>Negative balance</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-156">Sélectionnez pour inclure les comptes client qui ont des soldes négatifs.</span><span class="sxs-lookup"><span data-stu-id="50d64-156">Select to include customer accounts that have negative balances.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50d64-157"><strong>Exclure les comptes à solde nul</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-157"><strong>Exclude zero balance accounts</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-158">Sélectionnez pour exclure les comptes client qui ont un solde nul.</span><span class="sxs-lookup"><span data-stu-id="50d64-158">Select to exclude customer accounts that have a zero balance.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50d64-159"><strong>Positionnement des paiements</strong></span><span class="sxs-lookup"><span data-stu-id="50d64-159"><strong>Payment positioning</strong></span></span></p></td>
<td><p><span data-ttu-id="50d64-160">Sélectionnez pour afficher les paiements non réglés.</span><span class="sxs-lookup"><span data-stu-id="50d64-160">Select to display payments that have not been settled.</span></span> <span data-ttu-id="50d64-161">Ceux-ci sont affichés dans la première colonne de l’état.</span><span class="sxs-lookup"><span data-stu-id="50d64-161">These are displayed in the first column of the report.</span></span></p></td>
</tr>
</tbody>
</table>

