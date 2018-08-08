---
title: Provisionnement d'abonnements
description: "Les services récurrents permettent de provisionner manuellement le produit dans les périodes suivant la date à laquelle vous avez facturé une transaction de frais."
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: a183e17749c04b407eb17155ecb1363e96ade18a
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="accruing-subscriptions"></a><span data-ttu-id="f6d5a-103">Provisionnement d'abonnements</span><span class="sxs-lookup"><span data-stu-id="f6d5a-103">Accruing subscriptions</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f6d5a-104">Les services récurrents permettent de provisionner manuellement le produit dans les périodes suivant la date à laquelle vous avez facturé une transaction de frais.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-104">With service subscriptions, you manually accrue revenue in the periods following the date when you invoiced a fee transaction.</span></span>

<span data-ttu-id="f6d5a-105">Des périodes de régularisation sont créées pour la période de facturation paramétrée pour les frais d'abonnement. Elles sont basées sur le code période de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-105">Accrual periods are created for the invoice period that you set up for the subscription fee, and the accrual periods are based on the period code of the subscription.</span></span>

<span data-ttu-id="f6d5a-106">Vous pouvez provisionner et contrepasser le produit à recevoir.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-106">You can accrue and reverse accrued revenue.</span></span>

## <a name="reverse-accruals-of-credit-amounts"></a><span data-ttu-id="f6d5a-107">Contrepassation des régularisations des montants créditeurs</span><span class="sxs-lookup"><span data-stu-id="f6d5a-107">Reverse accruals of credit amounts</span></span>

<span data-ttu-id="f6d5a-108">Si vous créditez des montants d'abonnement facturés, vous pouvez utiliser deux méthodes pour contrepasser les montants de régularisation :</span><span class="sxs-lookup"><span data-stu-id="f6d5a-108">If you credit invoiced subscription amounts, you can use two methods to reverse the accrual amounts:</span></span>

  - <span data-ttu-id="f6d5a-109">Vous pouvez contrepasser chaque transaction de produit à recevoir individuellement avant de créer la proposition d'avoir pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-109">You can reverse each accrued revenue transaction individually before you create the credit note proposal for the transaction.</span></span> <span data-ttu-id="f6d5a-110">Il s'agit de la méthode manuelle.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-110">This is the manual method.</span></span> <span data-ttu-id="f6d5a-111">(manuel)</span><span class="sxs-lookup"><span data-stu-id="f6d5a-111">(manual)</span></span>

  - <span data-ttu-id="f6d5a-112">Vous pouvez contrepasser automatiquement les montants de régularisation à la date de validation de l'avoir ou à la date de validation d'origine de la régularisation.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-112">You can have the accrued amounts reversed on the date where the credit note is posted or on the original posting date of the accrual.</span></span>

<span data-ttu-id="f6d5a-113">Pour plus d'informations, voir [Paramètres d'abonnement (écran)](https://technet.microsoft.com/en-us/library/aa619615.aspx).</span><span class="sxs-lookup"><span data-stu-id="f6d5a-113">For more information, see [Subscription parameters (form)](https://technet.microsoft.com/en-us/library/aa619615.aspx).</span></span>

## <a name="setup-requirements"></a><span data-ttu-id="f6d5a-114">Paramétrer des besoins</span><span class="sxs-lookup"><span data-stu-id="f6d5a-114">Setup requirements</span></span>

<span data-ttu-id="f6d5a-115">Pour provisionner le produit, vérifiez que les conditions suivantes relatives aux données sont remplies :</span><span class="sxs-lookup"><span data-stu-id="f6d5a-115">To accrue revenue, make sure that the following data requirements are met:</span></span>

## <a name="account-setup"></a><span data-ttu-id="f6d5a-116">Paramétrage des comptes</span><span class="sxs-lookup"><span data-stu-id="f6d5a-116">Account setup</span></span>

<span data-ttu-id="f6d5a-117">Les comptes **Travaux en cours - abonnement** et **Produit à recevoir - abonnement** doivent être paramétrés dans le module **Projet**.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-117">The **WIP - subscription** and the **Accrued revenue - subscription** accounts must be set up in the **Project** module.</span></span>

<span data-ttu-id="f6d5a-118">Lorsque vous validez des produits à recevoir, le compte **Travaux en cours - abonnement** est débité du montant de régularisation et le compte **Produit à recevoir - abonnement** est crédité du montant de régularisation.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-118">When you post accrued revenue, the **WIP - subscription** account is debited with the accrual amount, and the **Accrued revenue - subscription** account is credited with the accrual amount.</span></span>

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a><span data-ttu-id="f6d5a-119">Paramétrage de comptes pour la régularisation de produits d'abonnement</span><span class="sxs-lookup"><span data-stu-id="f6d5a-119">Set up accounts for accrual of subscription revenue</span></span>

1.  <span data-ttu-id="f6d5a-120">Cliquez sur **Gestion et comptabilité des projets** \> **Paramétrage** \> **Validation** \> **Paramétrage de la validation dans la comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-120">Click **Project management and accounting** \> **Setup** \> **Posting** \> **Ledger posting setup**.</span></span>

2.  <span data-ttu-id="f6d5a-121">Cliquez sur l'onglet **Comptes de produit** et sélectionnez **Travaux en cours - abonnement** ou **Produit à recevoir - abonnement** pour paramétrer les comptes.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-121">Click the **Revenue accounts** tab, and select **WIP - subscription** or **Accrued revenue - subscription** to set up the accounts.</span></span>

## <a name="subscription-group-setup"></a><span data-ttu-id="f6d5a-122">Paramétrage de groupes d'abonnements</span><span class="sxs-lookup"><span data-stu-id="f6d5a-122">Subscription group setup</span></span>

<span data-ttu-id="f6d5a-123">La case à cocher **Provisionner le produit** doit être activée pour provisionner le produit pour les abonnements.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-123">To be able to accrue revenue for subscriptions, the **Accrue revenue** check box must be selected.</span></span> <span data-ttu-id="f6d5a-124">Cette case est située dans l'écran **Groupes d'abonnements** pour le groupe associé à cet abonnement.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-124">This is found on the **Subscription groups** form for the group that is attached to the subscription.</span></span> <span data-ttu-id="f6d5a-125">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Services récurrents** \> **Groupes d'abonnements**.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-125">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="enable-revenue-accrual-on-a-subscription-group"></a><span data-ttu-id="f6d5a-126">Activation du provisionnement du produit dans un groupe d'abonnements</span><span class="sxs-lookup"><span data-stu-id="f6d5a-126">Enable revenue accrual on a subscription group</span></span>

1.  <span data-ttu-id="f6d5a-127">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Services récurrents** \> **Groupes d'abonnements**.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-127">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="periods"></a><span data-ttu-id="f6d5a-128">Périodes</span><span class="sxs-lookup"><span data-stu-id="f6d5a-128">Periods</span></span>

<span data-ttu-id="f6d5a-129">Vous devez paramétrer un code période de facturation.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-129">You must set up an invoicing period code.</span></span> <span data-ttu-id="f6d5a-130">Vous devez également paramétrer une période de régularisation, sauf si vous souhaitez provisionner le produit dans les intervalles de temps utilisés dans le cadre de la facturation.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-130">Unless you want to accrue revenue in the same time intervals as you use for invoicing, you must also set up an accrual period.</span></span>

<span data-ttu-id="f6d5a-131">Le tableau suivant offre un aperçu des types de périodes de régularisation que vous pouvez paramétrer pour chaque période de facturation :</span><span class="sxs-lookup"><span data-stu-id="f6d5a-131">The following table provides an overview of which accrual periods can be set up for each invoicing period:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f6d5a-132">Période de facturation</span><span class="sxs-lookup"><span data-stu-id="f6d5a-132">Invoicing period</span></span></p></th>
<th><p><span data-ttu-id="f6d5a-133">Période de régularisation</span><span class="sxs-lookup"><span data-stu-id="f6d5a-133">Accrual period</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6d5a-134"><strong>Années</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-134"><strong>Years</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6d5a-135"><strong>Années</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-135"><strong>Years</strong></span></span></p></li>
<li><p><span data-ttu-id="f6d5a-136"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-136"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="f6d5a-137"><strong>Mois</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-137"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="f6d5a-138"><strong>Jour</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-138"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d5a-139"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-139"><strong>Quarter</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6d5a-140"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-140"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="f6d5a-141"><strong>Mois</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-141"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="f6d5a-142"><strong>Jour</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-142"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d5a-143"><strong>Mois</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-143"><strong>Month</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6d5a-144"><strong>Mois</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-144"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="f6d5a-145"><strong>Jour</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-145"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6d5a-146"><strong>Semaine</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-146"><strong>Week</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6d5a-147"><strong>Jour</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-147"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6d5a-148"><strong>Jour</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-148"><strong>Day</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6d5a-149"><strong>Jour</strong></span><span class="sxs-lookup"><span data-stu-id="f6d5a-149"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f6d5a-150">Le paramétrage de la période de facturation est obligatoire dans le cadre du paramétrage global du groupe d'abonnements.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-150">Setting up the invoicing period is a mandatory part of the overall subscription group setup.</span></span> <span data-ttu-id="f6d5a-151">Vous pouvez également décider de paramétrer une période de régularisation pour le groupe d'abonnements.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-151">You can decide whether to also set up an accrual period for the subscription group.</span></span> <span data-ttu-id="f6d5a-152">Si vous paramétrez une période de régularisation pour le groupe d'abonnements, cette période est suggérée dans le champ **Code période**.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-152">If you set up an accrual period for the subscription group, this period is suggested in the **Period code** field.</span></span> <span data-ttu-id="f6d5a-153">Ce champ est disponible dans l'écran **Provisionner le produit d'abonnement**, lorsque vous provisionnez le produit d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-153">This field is found in the **Accrue subscription revenue** form, when you accrue subscription revenue.</span></span> <span data-ttu-id="f6d5a-154">Cependant, la période de régularisation est une information facultative pour le groupe d'abonnements.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-154">However, the accrual period is optional information about the subscription group.</span></span>


> [!NOTE]
> <P><span data-ttu-id="f6d5a-155">Utilisez le chemin suivant pour ouvrir l'écran <STRONG>Provisionner le produit d'abonnement</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-155">Use the following path to open the <STRONG>Accrue subscription revenue</STRONG> form.</span></span> <span data-ttu-id="f6d5a-156">Cliquez sur <STRONG>Gestion des services</STRONG> &gt; <STRONG>Périodique</STRONG> &gt; <STRONG>Services récurrents</STRONG> &gt; <STRONG>Provisionner le produit d'abonnement</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-156">Click <STRONG>Service management</STRONG> &gt; <STRONG>Periodic</STRONG> &gt; <STRONG>Service subscriptions</STRONG> &gt; <STRONG>Accrue subscription revenue</STRONG>.</span></span></P>


## <a name="transactions"></a><span data-ttu-id="f6d5a-157">Transactions</span><span class="sxs-lookup"><span data-stu-id="f6d5a-157">Transactions</span></span>

<span data-ttu-id="f6d5a-158">Vous pouvez contrôler le nombre d'écritures comptables créées lorsque vous validez le produit à recevoir.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-158">You can control the number of ledger transactions that are created when you post accrued revenue.</span></span> <span data-ttu-id="f6d5a-159">Dans le cadre des abonnements, définissez si les écritures comptables doivent être créées en tant que total ou par ligne.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-159">On subscriptions, define if the ledger transactions should be created as a total or per line.</span></span>

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a><span data-ttu-id="f6d5a-160">Spécifiez le niveau de détail de la validation à afficher pour les transactions à recevoir.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-160">Specify the level of posting details to display for accrued transactions</span></span>

1.  <span data-ttu-id="f6d5a-161">Cliquez sur **Gestion et comptabilité des projets** \> **Paramétrage** \> **Paramètres de gestion et comptabilité des projets**.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-161">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="f6d5a-162">Sous l'onglet **Financier**, dans le champ **Facture**, sélectionnez **Total** ou **Ligne**.</span><span class="sxs-lookup"><span data-stu-id="f6d5a-162">On the **Financial** tab, in the **Invoice** field, select **Total** or **Line**.</span></span>


## <a name="see-also"></a><span data-ttu-id="f6d5a-163">Voir également :</span><span class="sxs-lookup"><span data-stu-id="f6d5a-163">See also</span></span>

[<span data-ttu-id="f6d5a-164">Provisionner l'abonnement</span><span class="sxs-lookup"><span data-stu-id="f6d5a-164">Accrue subscription revenue</span></span>](accrue-subscription-revenue.md)

  



