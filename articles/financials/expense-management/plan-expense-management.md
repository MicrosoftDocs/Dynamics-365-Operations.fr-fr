---
title: "Configurer la gestion des dépenses"
description: "Cet article décrit les considérations et les décisions que vous devez prendre au cours du processus de planification avant de configurer la gestion des dépenses dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4fad62c5da11e88e07f4e9d4343c4ac1a487bdd8
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="configure-expense-management"></a><span data-ttu-id="81537-103">Configurer la gestion des dépenses</span><span class="sxs-lookup"><span data-stu-id="81537-103">Configure expense management</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="81537-104">Cette rubrique décrit les considérations et les décisions que vous devez prendre au cours du processus de planification avant de configurer la gestion des dépenses dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="81537-104">This topic describes the considerations and the decisions that you must make during the planning process before you configure Expense management in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="81537-105">Dans Gestion des dépenses, vous pouvez stocker des informations sur les modes de paiement, des demandes de voyage, états de dépenses, et des stratégies, etc.</span><span class="sxs-lookup"><span data-stu-id="81537-105">In Expense management, you can store information about payment methods, travel requisitions, expense reports, policies, and so on.</span></span>

<span data-ttu-id="81537-106">Étant donné qu'un bon nombre des décisions que vous prenez lorsque vous planifiez la configuration de la gestion des dépenses sont basées sur la hiérarchie et la structure financière de votre organisation, vous devez vous référer aux documents de planification pour ces domaines.</span><span class="sxs-lookup"><span data-stu-id="81537-106">Because many of the decisions that you make when you plan your configuration for Expense management are based on your organization’s hierarchy and financial structure, you must refer to the planning documents for those areas.</span></span>

## <a name="intercompany-expenses"></a><span data-ttu-id="81537-107">Dépenses intersociétés</span><span class="sxs-lookup"><span data-stu-id="81537-107">Intercompany expenses</span></span>

<span data-ttu-id="81537-108">Lorsque vous activez les dépenses intersociétés, vous autorisez les entités juridiques et les employés à effectuer des dépenses au nom d'une autre entité juridique, ainsi qu'à recueillir des paiements en sa provenance au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81537-108">When you enable intercompany expenses, you allow legal entities and employees to incur expenses on behalf of another legal entity, and collect payment from the legal entity of employment within your organization.</span></span> <span data-ttu-id="81537-109">Par exemple, un employé de l'entité juridique A gère un projet pour l'entité juridique B, et le projet supporte les dépenses liées au voyage.</span><span class="sxs-lookup"><span data-stu-id="81537-109">For example, an employee in legal entity A completes a project for legal entity B, and the project incurs travel related expenses.</span></span> <span data-ttu-id="81537-110">Si les dépenses intersociétés sont activées, l'employé peut alors déposer un rapport de dépenses qui affichera la dépense à l'entité juridique B et la dépense devra alors être payée par l'entité juridique A. Si votre organisation n'a pas plusieurs entités juridiques, vous n'avez pas à activer les dépenses intersociétés.</span><span class="sxs-lookup"><span data-stu-id="81537-110">If intercompany expenses are enabled, the employee can then file an expense report that will post the expense to legal entity B, and the expense must then be paid by legal entity A. If your organization doesn’t have multiple legal entities, you don’t have to enable intercompany expenses.</span></span>

<span data-ttu-id="81537-111">**Décision :** souhaitez-vous activer les dépenses intersociétés ?</span><span class="sxs-lookup"><span data-stu-id="81537-111">**Decision:** Do you want to enable intercompany expenses?</span></span>

## <a name="financial-management"></a><span data-ttu-id="81537-112">Gestion financière</span><span class="sxs-lookup"><span data-stu-id="81537-112">Financial management</span></span>

<span data-ttu-id="81537-113">La gestion des dépenses est étroitement intégrée à la gestion financière de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81537-113">Expense management is tightly integrated with the financial management of your organization.</span></span> <span data-ttu-id="81537-114">Une grande partie de votre configuration de la gestion des dépenses sera basée sur les décisions que vous avez prises en ce qui concerne les finances de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81537-114">Lots of your configuration for Expense management will be based on the decisions that you’ve made about your organization’s finances.</span></span> <span data-ttu-id="81537-115">Les sections suivantes décrivent les différents domaines nécessitant une planification et des décisions basées sur les décisions financières de votre organisation et les consignes de votre équipe de direction.</span><span class="sxs-lookup"><span data-stu-id="81537-115">The following sections describe the various areas that require planning and decisions, based on your organization’s financial decisions and guidance from your leadership team.</span></span>

### <a name="per-diems"></a><span data-ttu-id="81537-116">Indemnités journalières</span><span class="sxs-lookup"><span data-stu-id="81537-116">Per diems</span></span>

<span data-ttu-id="81537-117">Vous devez définir les indemnités journalières des employés proposées par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81537-117">You must define the employee per diems that your organization provides.</span></span> <span data-ttu-id="81537-118">Étant donné que les indemnités journalières sont généralement utilisés pour couvrir des dépenses telles que les repas, l'hébergement, ainsi que d'autres dépenses fortuites, vous pouvez créer des règles pour les indemnités journalières que votre organisation propose.</span><span class="sxs-lookup"><span data-stu-id="81537-118">Because per diems are typically used to cover expenses such as meals, lodging, and other incidental expenses, you can create rules for the per diem allowances that your organization offers.</span></span> <span data-ttu-id="81537-119">Les taux d'indemnités journalières peuvent être basés sur la période de l'année ou sur la destination du déplacement, voire sur les deux.</span><span class="sxs-lookup"><span data-stu-id="81537-119">per diem rates can be based on the time of year, the travel location, or both.</span></span> <span data-ttu-id="81537-120">Lorsque vous définissez une règle d'indemnité journalière, vous pouvez indiquer qu'un pourcentage du taux d'indemnité journalière soit retenu si un collaborateur bénéficie de repas ou de services gratuits.</span><span class="sxs-lookup"><span data-stu-id="81537-120">When you define a per diem rule, you can specify that a percentage of the per diem rate will be withheld if a worker receives complimentary meals or services.</span></span> <span data-ttu-id="81537-121">Vous pouvez également définir des catégories de taux d'indemnités journalières afin de paramétrer un nombre d'heures minimal et maximal pendant lequel le taux d'indemnité journalière peut être appliqué dans le cadre du déplacement d'un collaborateur.</span><span class="sxs-lookup"><span data-stu-id="81537-121">You can also define per diem rate tiers to set the minimum and maximum number of hours that the per diem rate can be applied to a worker’s travel.</span></span>

<span data-ttu-id="81537-122">**Décisions :**</span><span class="sxs-lookup"><span data-stu-id="81537-122">**Decisions:**</span></span>

- <span data-ttu-id="81537-123">Règles d'indemnités journalières par défaut pour le premier et dernier jours :</span><span class="sxs-lookup"><span data-stu-id="81537-123">Default per diem rules for the first and last days:</span></span>

    - <span data-ttu-id="81537-124">Quel est le nombre d'heures minimal qu'un employé peut déclarer pour un jour et recevoir quand même une indemnité journalière ?</span><span class="sxs-lookup"><span data-stu-id="81537-124">What is the minimum number of hours that an employee can claim for a day and still receive a per diem?</span></span>
    - <span data-ttu-id="81537-125">Y a-t-il une réduction du montant proposé pour les repas pour le premier jour et le dernier jour ?</span><span class="sxs-lookup"><span data-stu-id="81537-125">Is there a reduction in the amount that is offered for meals for the first day and last day?</span></span> <span data-ttu-id="81537-126">S'il existe une réduction, quel est le pourcentage de la réduction ?</span><span class="sxs-lookup"><span data-stu-id="81537-126">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="81537-127">Y a-t-il une réduction du montant proposé pour un hôtel pour le premier jour et le dernier jour ?</span><span class="sxs-lookup"><span data-stu-id="81537-127">Is there a reduction in the amount that is offered for a hotel for the first day and last day?</span></span> <span data-ttu-id="81537-128">S'il existe une réduction, quel est le pourcentage de la réduction ?</span><span class="sxs-lookup"><span data-stu-id="81537-128">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="81537-129">Y a-t-il une réduction du montant proposé pour les autres dépenses encourues le premier jour et le dernier jour ?</span><span class="sxs-lookup"><span data-stu-id="81537-129">Is there a reduction in the amount that is offered for other expenses that are incurred on the first day and last day?</span></span> <span data-ttu-id="81537-130">S'il existe une réduction, quel est le pourcentage de la réduction ?</span><span class="sxs-lookup"><span data-stu-id="81537-130">If there is a reduction, what is the percentage of the reduction?</span></span>

- <span data-ttu-id="81537-131">Règles d'indemnités journalières par défaut :</span><span class="sxs-lookup"><span data-stu-id="81537-131">Default per diem rules:</span></span>

    - <span data-ttu-id="81537-132">Y a-t-il un pourcentage de réduction de l'indemnité journalière pour chaque repas si, par exemple, le repas est gratuit ?</span><span class="sxs-lookup"><span data-stu-id="81537-132">Is there a percentage reduction in the per diem allowance for each meal if, for example, the meal is complimentary?</span></span> <span data-ttu-id="81537-133">S'il existe une réduction, quel est le pourcentage de la réduction pour chaque repas ?</span><span class="sxs-lookup"><span data-stu-id="81537-133">If there is a reduction, what is the reduction percentage for each meal?</span></span>
    - <span data-ttu-id="81537-134">La réduction concernant les repas est-elle calculée par jour, par déplacement, ou par nombre de repas par jour ?</span><span class="sxs-lookup"><span data-stu-id="81537-134">Is the meal reduction calculated per day, per trip, or by the number of meals per day?</span></span>
    - <span data-ttu-id="81537-135">Les indemnités journalières doivent-elles être arrondies de manière régulière ou vers le haut ?</span><span class="sxs-lookup"><span data-stu-id="81537-135">Should per diem amounts be rounded in the regular manner or rounded up?</span></span>
    - <span data-ttu-id="81537-136">Les indemnités journalières sont-elles calculées sur une période de 24 heures ou sur un jour civil ?</span><span class="sxs-lookup"><span data-stu-id="81537-136">Are per diems calculated on a 24-hour period or on a calendar day?</span></span>

- <span data-ttu-id="81537-137">Règles d'indemnités journalières qui dépendent de l'emplacement :</span><span class="sxs-lookup"><span data-stu-id="81537-137">Per diem rules that are based on location:</span></span>

    - <span data-ttu-id="81537-138">Les indemnités journalières varient-elles en fonction de l'emplacement ?</span><span class="sxs-lookup"><span data-stu-id="81537-138">Do per diem rates vary according to location?</span></span> <span data-ttu-id="81537-139">Quels emplacements sont inclus ?</span><span class="sxs-lookup"><span data-stu-id="81537-139">What locations are included?</span></span>
    - <span data-ttu-id="81537-140">Si les taux d'indemnité journalière varient en fonction de l'emplacement, pour chaque emplacement, le pourcentage est proposé pour les types de dépenses suivants :</span><span class="sxs-lookup"><span data-stu-id="81537-140">If per diem rates vary according to location, for each location, what percentage amount is provided for the following types of expenses:</span></span>

        - <span data-ttu-id="81537-141">Repas</span><span class="sxs-lookup"><span data-stu-id="81537-141">Meals</span></span>
        - <span data-ttu-id="81537-142">Hôtel</span><span class="sxs-lookup"><span data-stu-id="81537-142">Hotel</span></span>
        - <span data-ttu-id="81537-143">Autres dépenses</span><span class="sxs-lookup"><span data-stu-id="81537-143">Other expenses</span></span>

### <a name="expense-management-journals-and-accounts"></a><span data-ttu-id="81537-144">Journaux et comptes de gestion des dépenses</span><span class="sxs-lookup"><span data-stu-id="81537-144">Expense management journals and accounts</span></span>

<span data-ttu-id="81537-145">La gestion des dépenses exige que vous utilisiez plusieurs journaux et comptes.</span><span class="sxs-lookup"><span data-stu-id="81537-145">Expense management requires that you use multiple journals and accounts.</span></span> <span data-ttu-id="81537-146">Vous devez décider si, par exemple, le même compte est utilisé pour les avances de disponibilités et les litiges de paiement de carte de crédit.</span><span class="sxs-lookup"><span data-stu-id="81537-146">You must decide, for example, whether the same account is used for cash advances and credit card disputes.</span></span>

<span data-ttu-id="81537-147">**Décisions :**</span><span class="sxs-lookup"><span data-stu-id="81537-147">**Decisions:**</span></span>

- <span data-ttu-id="81537-148">Dans quel journal comptable les états de dépenses approuvés sont-ils validés ?</span><span class="sxs-lookup"><span data-stu-id="81537-148">Which ledger journal are approved expense reports posted to?</span></span>
- <span data-ttu-id="81537-149">Quel compte est-il utilisé pour les avances de disponibilités ?</span><span class="sxs-lookup"><span data-stu-id="81537-149">Which account is used for cash advances?</span></span>
- <span data-ttu-id="81537-150">Les avances de disponibilités doivent-elles être validées immédiatement ?</span><span class="sxs-lookup"><span data-stu-id="81537-150">Should cash advances be posted immediately?</span></span>

### <a name="payment-methods"></a><span data-ttu-id="81537-151">Modes de paiement</span><span class="sxs-lookup"><span data-stu-id="81537-151">Payment methods</span></span>

<span data-ttu-id="81537-152">Lorsque vous autorisez les employés à encourir des dépenses au nom de votre entreprise, vous devez définir les modes de paiement qu'ils sont autorisés à utiliser.</span><span class="sxs-lookup"><span data-stu-id="81537-152">When you allow employees to incur expenses on behalf of your business, you must define the payment methods that employees are allowed to use.</span></span> <span data-ttu-id="81537-153">Par exemple, vous pouvez autoriser vos employés à utiliser des disponibilités en liquide ou une carte de crédit professionnelle.</span><span class="sxs-lookup"><span data-stu-id="81537-153">For example, you might allow employees to use cash or a corporate credit card.</span></span> <span data-ttu-id="81537-154">Vous pouvez également autoriser vos employés à utiliser leurs cartes de crédit personnelles, et les rembourser par la suite.</span><span class="sxs-lookup"><span data-stu-id="81537-154">You might also allow employees to use personal credit cards, and then reimburse the employees.</span></span> <span data-ttu-id="81537-155">Vous devez prendre les décisions suivantes pour chaque mode de paiement que vous autorisez.</span><span class="sxs-lookup"><span data-stu-id="81537-155">You must make the following decisions for each payment method that you allow.</span></span>

<span data-ttu-id="81537-156">**Décisions :**</span><span class="sxs-lookup"><span data-stu-id="81537-156">**Decisions:**</span></span>

- <span data-ttu-id="81537-157">Quels modes de paiement sont-ils autorisés ?</span><span class="sxs-lookup"><span data-stu-id="81537-157">What payment methods are allowed?</span></span>
- <span data-ttu-id="81537-158">Qui est propriétaire des dépenses du mode de paiement ?</span><span class="sxs-lookup"><span data-stu-id="81537-158">Who owns the payment method expenses?</span></span>
- <span data-ttu-id="81537-159">Existe-t-il un type de compte de contrepartie ?</span><span class="sxs-lookup"><span data-stu-id="81537-159">Is there an offset account type?</span></span> <span data-ttu-id="81537-160">S'il existe un type de compte de contrepartie, quel est-il ?</span><span class="sxs-lookup"><span data-stu-id="81537-160">If there is an offset account type, what is it?</span></span>
- <span data-ttu-id="81537-161">S'il existe un compte de contrepartie, quel est ce compte ?</span><span class="sxs-lookup"><span data-stu-id="81537-161">If there is an offset account, what is the account?</span></span>
- <span data-ttu-id="81537-162">Si le mode de paiement est une carte de crédit, le mode de paiement doit-il uniquement être utilisé avec les transactions importées ?</span><span class="sxs-lookup"><span data-stu-id="81537-162">If the payment method is a credit card, should the payment method be used only with imported transactions?</span></span>

### <a name="expense-categories-and-shared-categories"></a><span data-ttu-id="81537-163">Catégories de dépenses et catégories partagées</span><span class="sxs-lookup"><span data-stu-id="81537-163">Expense categories and shared categories</span></span>

<span data-ttu-id="81537-164">Lorsque les employés créent un état de dépenses, chaque dépense qu'ils enregistrent doit être associée à une catégorie de dépense.</span><span class="sxs-lookup"><span data-stu-id="81537-164">When employees create an expense report, each expense that they record must be associated with an expense category.</span></span> <span data-ttu-id="81537-165">Les catégories de dépenses sont dérivées des catégories partagées qui peuvent être partagées par toutes les entités juridiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81537-165">Expense categories are derived from shared categories that can be shared across the legal entities in your organization.</span></span> <span data-ttu-id="81537-166">Ces catégories peuvent également être partagées dans le module Gestion et comptabilité des projets, selon la façon dont votre organisation est définie.</span><span class="sxs-lookup"><span data-stu-id="81537-166">These categories can also be shared in Project management and accounting, depending on the way that your organization is defined.</span></span> <span data-ttu-id="81537-167">Selon la définition de votre organisation et les instructions de l'équipe d'implémentation, déterminez si les catégories utilisées dans le cadre de la gestion des dépenses seront utilisées exclusivement en matière de gestion des dépenses ou si elles sont partagées entre la gestion de projets, ainsi que la comptabilité et la gestion des dépenses.</span><span class="sxs-lookup"><span data-stu-id="81537-167">Based on the definition of your organization and guidance from the implementation team, determine whether the categories that are used in Expense management will be used only in Expense management, or whether they should be shared between Project management and accounting and Expense management.</span></span> <span data-ttu-id="81537-168">Notez que ces catégories peuvent être partagées entre le projet et les dépenses ou entre le projet et la production, mais pas entre les dépenses et la production.</span><span class="sxs-lookup"><span data-stu-id="81537-168">Note that these categories can be shared between Project and Expense or Project and Production, but not between Expense and Production.</span></span> <span data-ttu-id="81537-169">Vous devez prendre les décisions suivantes pour chaque catégorie de dépense.</span><span class="sxs-lookup"><span data-stu-id="81537-169">You must make the following decisions for each expense category.</span></span>

<span data-ttu-id="81537-170">**Décisions :**</span><span class="sxs-lookup"><span data-stu-id="81537-170">**Decisions:**</span></span>

- <span data-ttu-id="81537-171">Quelle est la catégorie de dépense ?</span><span class="sxs-lookup"><span data-stu-id="81537-171">What is the expense category?</span></span> <span data-ttu-id="81537-172">Les exemples incluent des catégories pour les vols, l'hôtel ou le kilométrage.</span><span class="sxs-lookup"><span data-stu-id="81537-172">Examples include categories for flights, hotel, or mileage.</span></span>
- <span data-ttu-id="81537-173">La catégorie de dépense peut-elle être utilisée dans le module Gestion et comptabilité des projets ?</span><span class="sxs-lookup"><span data-stu-id="81537-173">Can the expense category also be used in Project management and accounting?</span></span>
- <span data-ttu-id="81537-174">Quel est le type de dépense ?</span><span class="sxs-lookup"><span data-stu-id="81537-174">What is the expense type?</span></span>
- <span data-ttu-id="81537-175">Quel est le mode de paiement par défaut pour la catégorie de dépense ?</span><span class="sxs-lookup"><span data-stu-id="81537-175">What is the default payment method for the expense category?</span></span>
- <span data-ttu-id="81537-176">Les dépenses dans la catégorie des dépenses doivent-elles être détaillées ?</span><span class="sxs-lookup"><span data-stu-id="81537-176">Do expenses in the expense category have to be itemized?</span></span>
- <span data-ttu-id="81537-177">Quel est le compte principal par défaut pour la catégorie de dépense ?</span><span class="sxs-lookup"><span data-stu-id="81537-177">What is the main default account for the expense category?</span></span>
- <span data-ttu-id="81537-178">Quel est le groupe de taxe d’article par défaut pour la catégorie de dépense ?</span><span class="sxs-lookup"><span data-stu-id="81537-178">What is the default item sales tax group for the expense category?</span></span>
- <span data-ttu-id="81537-179">Des modes de paiement supplémentaires sont-ils autorisés pour cette catégorie de dépense ?</span><span class="sxs-lookup"><span data-stu-id="81537-179">Are additional payment methods allowed for the expense category?</span></span> <span data-ttu-id="81537-180">Si des méthodes de paiement supplémentaires sont autorisées, quelles sont-elles ?</span><span class="sxs-lookup"><span data-stu-id="81537-180">If additional payment methods are allowed, what are they?</span></span>
- <span data-ttu-id="81537-181">Cette catégorie de dépense comporte-t-elle des sous-catégories ?</span><span class="sxs-lookup"><span data-stu-id="81537-181">Are there subcategories in this expense category?</span></span> <span data-ttu-id="81537-182">S'il existe des sous-catégories, vous devez également prendre les décisions suivantes :</span><span class="sxs-lookup"><span data-stu-id="81537-182">If there are subcategories, you must also make the following decisions:</span></span>

    - <span data-ttu-id="81537-183">Certaines sous-catégories sont-elles exclues du recouvrement fiscal ?</span><span class="sxs-lookup"><span data-stu-id="81537-183">Are any of the subcategories excluded from tax recovery?</span></span>
    - <span data-ttu-id="81537-184">Quel est le groupe de taxe d’article de la sous-catégorie ?</span><span class="sxs-lookup"><span data-stu-id="81537-184">What is the item sales tax group of the subcategories?</span></span>

<span data-ttu-id="81537-185">Si la catégorie de dépense est également utilisée dans le module Gestion et comptabilité des projets, répondez aux questions restantes.</span><span class="sxs-lookup"><span data-stu-id="81537-185">If the expense category is also used in Project management and accounting, answer the remaining questions.</span></span> <span data-ttu-id="81537-186">Sinon, passez à la section suivante.</span><span class="sxs-lookup"><span data-stu-id="81537-186">Otherwise, move on to the next section.</span></span>

- <span data-ttu-id="81537-187">Quels comptes de coût seront-ils utilisés pour les dépenses suivantes ?</span><span class="sxs-lookup"><span data-stu-id="81537-187">Which cost accounts will be used for the following expenses?</span></span>

    - <span data-ttu-id="81537-188">Charge</span><span class="sxs-lookup"><span data-stu-id="81537-188">Cost</span></span>
    - <span data-ttu-id="81537-189">Répartition des salaires</span><span class="sxs-lookup"><span data-stu-id="81537-189">Payroll allocation</span></span>
    - <span data-ttu-id="81537-190">Travaux en cours - coût</span><span class="sxs-lookup"><span data-stu-id="81537-190">WIP-cost value</span></span>
    - <span data-ttu-id="81537-191">Coût - Article</span><span class="sxs-lookup"><span data-stu-id="81537-191">Cost-item</span></span>
    - <span data-ttu-id="81537-192">Travaux en cours - coût - article</span><span class="sxs-lookup"><span data-stu-id="81537-192">WIP-cost value-item</span></span>
    - <span data-ttu-id="81537-193">Perte à recevoir</span><span class="sxs-lookup"><span data-stu-id="81537-193">Accrued loss</span></span>
    - <span data-ttu-id="81537-194">Travaux en cours - perte à recevoir</span><span class="sxs-lookup"><span data-stu-id="81537-194">WIP-accrued loss</span></span>

- <span data-ttu-id="81537-195">Quels comptes de produit seront-ils utilisés pour les éléments suivants ?</span><span class="sxs-lookup"><span data-stu-id="81537-195">Which revenue accounts will be used for the following?</span></span>

    - <span data-ttu-id="81537-196">Produit facturé</span><span class="sxs-lookup"><span data-stu-id="81537-196">Invoiced revenue</span></span>
    - <span data-ttu-id="81537-197">Produit à recevoir - Prix de vente</span><span class="sxs-lookup"><span data-stu-id="81537-197">Accrued revenue-sales value</span></span>
    - <span data-ttu-id="81537-198">Travaux en cours - prix de vente</span><span class="sxs-lookup"><span data-stu-id="81537-198">WIP-sales value</span></span>
    - <span data-ttu-id="81537-199">Produit à recevoir - production</span><span class="sxs-lookup"><span data-stu-id="81537-199">Accrued revenue-production</span></span>
    - <span data-ttu-id="81537-200">Travaux en cours - production</span><span class="sxs-lookup"><span data-stu-id="81537-200">WIP-production</span></span>
    - <span data-ttu-id="81537-201">Produit à recevoir - profit</span><span class="sxs-lookup"><span data-stu-id="81537-201">Accrued revenue-profit</span></span>
    - <span data-ttu-id="81537-202">Travaux en cours - Profit</span><span class="sxs-lookup"><span data-stu-id="81537-202">WIP-profit</span></span>
    - <span data-ttu-id="81537-203">Produit à recevoir - abonnement</span><span class="sxs-lookup"><span data-stu-id="81537-203">Accrued revenue-subscription</span></span>
    - <span data-ttu-id="81537-204">Travaux en cours - Abonnement</span><span class="sxs-lookup"><span data-stu-id="81537-204">WIP-subscription</span></span>

### <a name="taxes"></a><span data-ttu-id="81537-205">Taxes</span><span class="sxs-lookup"><span data-stu-id="81537-205">Taxes</span></span>

<span data-ttu-id="81537-206">Pour les taxes relatives aux dépenses, vous devez déterminer ce qui est inclus ou activé dans les états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="81537-206">For expense-related taxes, you must determine what is included or enabled on expense reports.</span></span>

<span data-ttu-id="81537-207">**Décisions :**</span><span class="sxs-lookup"><span data-stu-id="81537-207">**Decisions:**</span></span>

- <span data-ttu-id="81537-208">La taxe est-elle inclue aux montants des dépenses.</span><span class="sxs-lookup"><span data-stu-id="81537-208">Is sales tax included in the expense amounts?</span></span>
- <span data-ttu-id="81537-209">Le recouvrement fiscal doit-il être activé pour les dépenses ?</span><span class="sxs-lookup"><span data-stu-id="81537-209">Should tax recovery be enabled on expenses?</span></span>

    > [!NOTE]
    > <span data-ttu-id="81537-210">Lorsque vous avez planifié la comptabilité, si vous avez décidé d'appliquer la taxe américaine et les règles de taxe d'utilisation, vous ne pourrez pas activer le recouvrement fiscal sur les dépenses.</span><span class="sxs-lookup"><span data-stu-id="81537-210">When you were planning the general ledger, if you decided to apply U.S. sales tax and use tax rules, you can’t enable tax recovery on expenses.</span></span> <span data-ttu-id="81537-211">(Pour appliquer la taxe américaine et les règles de taxe d'utilisation, définissez l'option **Appliquer les règles de taxe** sur **Oui**.)</span><span class="sxs-lookup"><span data-stu-id="81537-211">(To apply U.S. sales tax and use tax rules, set the **Apply sales tax taxations rules** option to **Yes**.)</span></span>

## <a name="policies"></a><span data-ttu-id="81537-212">Stratégies</span><span class="sxs-lookup"><span data-stu-id="81537-212">Policies</span></span>

<span data-ttu-id="81537-213">En créant des stratégies d'état de dépenses, vous pouvez aider votre organisation à gagner du temps et à économiser de l'argent lorsque les employés engagent des dépenses en son nom.</span><span class="sxs-lookup"><span data-stu-id="81537-213">By creating expense report policies, you can help your organization save time and money when employees incur expenses on its behalf.</span></span> <span data-ttu-id="81537-214">Les stratégies garantissent que les employés ne dépassent pas le budget, fournissent toutes les informations requises, et dépensent de l'argent uniquement lorsque cela est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="81537-214">Policies help guarantee that employees stay in budget, provide all required information, and spend money only as they require it.</span></span> <span data-ttu-id="81537-215">Vous devez prendre les décisions suivantes pour chaque stratégie d'état de dépenses et chaque stratégie d'approbation d'état de dépenses que vous créez.</span><span class="sxs-lookup"><span data-stu-id="81537-215">You must make the following decisions for each expense report policy and each expense report approval policy that you create.</span></span>

<span data-ttu-id="81537-216">**Décisions :**</span><span class="sxs-lookup"><span data-stu-id="81537-216">**Decisions:**</span></span>

- <span data-ttu-id="81537-217">Quel est le nom de la stratégie ?</span><span class="sxs-lookup"><span data-stu-id="81537-217">What is the name of the policy?</span></span>
- <span data-ttu-id="81537-218">À quoi sert la stratégie de dépenses ?</span><span class="sxs-lookup"><span data-stu-id="81537-218">What is the expense policy for?</span></span>
- <span data-ttu-id="81537-219">Si vous avez précédemment décidé d'activer les dépenses intersociétés, à quelles sociétés de votre organisation cette stratégie s'applique-t-elle ?</span><span class="sxs-lookup"><span data-stu-id="81537-219">If you previously decided to enable intercompany expenses, which companies in your organization will this policy apply to?</span></span>
- <span data-ttu-id="81537-220">Quand la stratégie entre-t-elle en vigueur ?</span><span class="sxs-lookup"><span data-stu-id="81537-220">When does the policy become effective?</span></span>
- <span data-ttu-id="81537-221">Quand la stratégie arrive-t-elle à expiration ?</span><span class="sxs-lookup"><span data-stu-id="81537-221">When does the policy expire?</span></span>
- <span data-ttu-id="81537-222">Quelle est la règle de stratégie ?</span><span class="sxs-lookup"><span data-stu-id="81537-222">What is the policy rule?</span></span>
- <span data-ttu-id="81537-223">Quel est le résultat de la règle de stratégie ?</span><span class="sxs-lookup"><span data-stu-id="81537-223">What is the outcome of the policy rule?</span></span>

