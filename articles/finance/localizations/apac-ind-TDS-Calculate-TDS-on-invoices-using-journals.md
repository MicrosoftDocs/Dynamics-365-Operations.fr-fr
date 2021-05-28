---
title: Calculer le TDS sur les factures à l'aide de journaux
description: Cette rubrique répertorie les étapes de calcul de la taxe déduite à la source (TDS) relatives aux journaux.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: d68e1b3a4dc31823ec56a525149f16bdc23c0883
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023252"
---
# <a name="calculate-tds-on-invoices-using-journals"></a><span data-ttu-id="26f00-103">Calculer le TDS sur les factures à l'aide de journaux</span><span class="sxs-lookup"><span data-stu-id="26f00-103">Calculate TDS on invoices using journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26f00-104">Cette rubrique répertorie les étapes de calcul de la taxe déduite à la source (TDS) relatives aux journaux.</span><span class="sxs-lookup"><span data-stu-id="26f00-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on journals.</span></span>

<span data-ttu-id="26f00-105">Commencez par ouvrir la page **Journaux des opérations diverses** (**Comptabilité > Entrées de journal > Journaux des opérations**).</span><span class="sxs-lookup"><span data-stu-id="26f00-105">Begin by opening the **General journals** page (**General ledger > Journal entries > General journals**).</span></span>

<span data-ttu-id="26f00-106">[![Journaux des opérations diverses](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span><span class="sxs-lookup"><span data-stu-id="26f00-106">[![General journals](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span></span>

1. <span data-ttu-id="26f00-107">Créez des lignes de journal à l'aide des formulaires de journal répertoriés dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="26f00-107">Create journal lines using the journal forms that are listed in the table.</span></span> <span data-ttu-id="26f00-108">Sélectionnez le type de compte et le type de compte de compensation et saisissez le montant de la transaction.</span><span class="sxs-lookup"><span data-stu-id="26f00-108">Select the account type and offset account type and enter the amount for the transaction.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="26f00-109">Sur la page **Journal des approbations de facture**, sélectionnez **Rechercher des N° documents** et sélectionnez les factures sur lesquelles calculer le TDS.</span><span class="sxs-lookup"><span data-stu-id="26f00-109">On the **Invoice approval journal** page, select **Find vouchers** and select invoices to calculate TDS on.</span></span> <span data-ttu-id="26f00-110">Consultez les factures créées dans la page **Registre des factures** ou la page **Rechercher des N° documents**.</span><span class="sxs-lookup"><span data-stu-id="26f00-110">View the invoices created in the **Invoice register** page or the **Find vouchers** page.</span></span>  

2. <span data-ttu-id="26f00-111">Dans l'onglet **Général** de la page **N° document de journal**, affichez ou modifiez le groupe TDS par défaut défini pour le fournisseur ou le client, dans le champ **Groupe TDS**.</span><span class="sxs-lookup"><span data-stu-id="26f00-111">On the **General** tab of the **Journal voucher** page, view or modify the default TDS group defined for the vendor or customer, in the **TDS group** field.</span></span> <span data-ttu-id="26f00-112">Le montant TDS calculé sur les lignes de journal est basé sur la formule définie pour les codes TVA TDS dans le champ **Groupe TDS**.</span><span class="sxs-lookup"><span data-stu-id="26f00-112">The TDS amount that's calculated on journal lines is based on the formula defined for the TDS tax codes listed in the **TDS group** field.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="26f00-113">Le champ **Groupe de retenue à la source** et le champ **Groupe TCS** deviennent indisponibles lorsque vous sélectionnez un groupe TDS dans le champ **Groupe TDS**.</span><span class="sxs-lookup"><span data-stu-id="26f00-113">The **Withholding tax group**  field and the **TCS group** field become unavailable when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="26f00-114">Le champ **Groupe de retenue à la source** est disponible uniquement sur la page **Journal des opérations diverses**.</span><span class="sxs-lookup"><span data-stu-id="26f00-114">The **Withholding tax group** field is available only on the **General journal** page.</span></span> <span data-ttu-id="26f00-115">TDS est calculé uniquement si la case **Calcul de la retenue à la source** est cochée pour le fournisseur ou le client sur les pages **Tous les fournisseurs** et **Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="26f00-115">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** pages.</span></span>   

3. <span data-ttu-id="26f00-116">Sélectionnez l'onglet **Informations fiscales**. Sélectionnez les adresses alternatives d'une société configurées pour le nom de la société affiché dans ce champ, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="26f00-116">Select the **Tax information** tab. Select the alternate addresses of a company that's set up for the company in this field, if required.</span></span> <span data-ttu-id="26f00-117">Vous pouvez afficher le nom de la société dans le champ **Nom**, qui est sous le groupe de champs **Informations sur la société**.</span><span class="sxs-lookup"><span data-stu-id="26f00-117">You can view the company name in the **Name** field, which is under the **Company information** field group.</span></span> 

4. <span data-ttu-id="26f00-118">Affichez la nature de la catégorie du fournisseur ou du client dans le champ **Nature de la personne évaluée**, figurant sous le groupe de champs **Retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="26f00-118">View the nature of assessee category of the vendor or customer in the **Nature of assessee** field, which is under the **Withholding tax** field group.</span></span> <span data-ttu-id="26f00-119">Dans le **Numéro de compte fiscal** (**TAN**), affichez le TAN du nom de la société sélectionnée qui est affiché.</span><span class="sxs-lookup"><span data-stu-id="26f00-119">In the **Tax Account Number** (**TAN**) field, view the TAN of the selected company name that's displayed.</span></span>  

5. <span data-ttu-id="26f00-120">Sélectionnez **Retenue à la source** dans le menu **Retenue à la source** pour ouvrir la page **Opérations de retenue à la source temporaire**.</span><span class="sxs-lookup"><span data-stu-id="26f00-120">Select **Withholding tax** in **Withholding tax** menu to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="26f00-121">Les champs suivants s'affichent dans le volet supérieur de la page **Opérations de retenue à la source temporaire**.</span><span class="sxs-lookup"><span data-stu-id="26f00-121">The following fields are displayed on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="26f00-122">**Montant total de la retenue à la source** - TDS total calculé pour la transaction pour le groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="26f00-122">**Withholding tax amount in total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="26f00-123">**Valeur** - Pourcentage total utilisé pour calculer TDS pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="26f00-123">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="26f00-124">Le pourcentage total est basé sur la formule définie pour les codes de taxe TDS et attachée au groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="26f00-124">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="26f00-125">**Montant de la retenue à la source ajusté au total** - Le montant total ajusté du TDS pour tous les codes de taxe du groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="26f00-125">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="26f00-126">**TDS** - Si cette option est sélectionnée, un groupe TDS est attaché à la transaction.</span><span class="sxs-lookup"><span data-stu-id="26f00-126">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

  <span data-ttu-id="26f00-127">Les champs des onglets **Aperçu**, **Général** et **Ajustement** dans la page **Opérations de retenue à la source temporaire** affichent le montant TDS calculé et les détails du montant TDS ajusté pour chaque code de taxe TDS associé au groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="26f00-127">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

6. <span data-ttu-id="26f00-128">Sélectionnez **Seuil** pour ouvrir la page **Seuil**.</span><span class="sxs-lookup"><span data-stu-id="26f00-128">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="26f00-129">Consultez la limite de seuil et la limite de seuil d'exception définis pour le composant de taxe TDS associé à un code de taxe TDS spécifique sur cette page.</span><span class="sxs-lookup"><span data-stu-id="26f00-129">View the threshold limit and exception threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

   <span data-ttu-id="26f00-130">Sélectionnez **Concepteur de formule** pour ouvrir l'écran **Concepteur de formule**.</span><span class="sxs-lookup"><span data-stu-id="26f00-130">Select **Formula designer** to open the **Formula designer** form.</span></span> <span data-ttu-id="26f00-131">Consultez la formule définie pour un code de taxe TDS spécifique sur cette page.</span><span class="sxs-lookup"><span data-stu-id="26f00-131">View the formula defined for a specific TDS tax code in this page.</span></span> <span data-ttu-id="26f00-132">Fermez les pages **Concepteur de formule** et **Opérations de retenue à la source temporaire** pour revenir à la page **Justificatif de journal**.</span><span class="sxs-lookup"><span data-stu-id="26f00-132">Close the **Formula designer** and **Temporary withholding tax transactions** pages to return to the **Journal voucher** page.</span></span>

8. <span data-ttu-id="26f00-133">Renseignez les informations demandées.</span><span class="sxs-lookup"><span data-stu-id="26f00-133">Enter the other required details.</span></span> <span data-ttu-id="26f00-134">Contrôlez et validez le journal.</span><span class="sxs-lookup"><span data-stu-id="26f00-134">Validate and post the journal.</span></span> <span data-ttu-id="26f00-135">Le montant TDS calculé sur les factures d'achat est imputé au compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="26f00-135">The TDS amount that's calculated on purchase invoices is posted to the payable account.</span></span> <span data-ttu-id="26f00-136">Le montant TDS qui a été calculé en fonction des factures client est imputé au compte fournisseur défini pour chaque code TVA TDS du groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="26f00-136">The TDS amount that's calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="26f00-137">Les comptes clients et fournisseurs pour les codes TVA TDS sont définis sur la page **Codes de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="26f00-137">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

9. <span data-ttu-id="26f00-138">Sélectionnez **Retenue à la source validée** pour ouvrir la page **Opérations** **de retenue** **à la source**.</span><span class="sxs-lookup"><span data-stu-id="26f00-138">Select **Posted withholding tax** to open the **Withholding** **tax** **transactions** page.</span></span> <span data-ttu-id="26f00-139">Dans le champ **Valeur**, le pourcentage total qui a été utilisé pour calculer TDS pour la transaction s'affiche.</span><span class="sxs-lookup"><span data-stu-id="26f00-139">In the **Value** field, the total percentage used to calculate TDS for the transaction is displayed.</span></span>

   <span data-ttu-id="26f00-140">Les champs des onglets **Aperçu**, **Général** et **Montant** dans la page Opérations de retenue à la source temporaire affichent le montant TDS calculé et les détails du montant TDS ajusté pour chaque code de taxe TDS associé au groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="26f00-140">The fields on the **Overview**, **General**, and **Amount** tabs in the Withholding tax transactions page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>
