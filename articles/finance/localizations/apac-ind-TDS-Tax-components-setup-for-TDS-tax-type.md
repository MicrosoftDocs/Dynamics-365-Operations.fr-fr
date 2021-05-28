---
title: Configurer des composants de taxe pour le type de taxe TDS
description: Cette rubrique explique comment configurer des composants de retenue à la source pour le type de taxe Déduite à la Source (TDS). Il explique également comment définir la limite de seuil utilisée pour calculer le TDS pour chaque composant TDS.
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
ms.openlocfilehash: 6e0a6a05fcb4afb8c8965e25c3089bc1b3d98431
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023233"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a><span data-ttu-id="36b58-104">Configurer des composants de taxe pour le type de taxe TDS</span><span class="sxs-lookup"><span data-stu-id="36b58-104">Set up tax components for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36b58-105">Cette rubrique explique comment configurer des composants de retenue à la source pour le type de taxe Déduite à la Source (TDS).</span><span class="sxs-lookup"><span data-stu-id="36b58-105">This topic explains how to set up withholding tax components for the Tax Deducted at Source (TDS) tax type.</span></span> <span data-ttu-id="36b58-106">Les composants TDS sont TDS, surtaxe, PE-Cess et SHE Cess.</span><span class="sxs-lookup"><span data-stu-id="36b58-106">The TDS components are TDS, surcharge, PE-Cess, and SHE Cess.</span></span> <span data-ttu-id="36b58-107">Cette rubrique explique également comment définir le seuil utilisé pour calculer le TDS pour chaque composant TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-107">This topic also explains how to define the threshold that is used to calculate TDS for each TDS component.</span></span> <span data-ttu-id="36b58-108">En outre, vous pouvez définir un seuil d'exception utilisé pour calculer TDS pour chaque composant TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-108">Additionally, you can define an exception threshold that is used to calculate TDS for each TDS component.</span></span>

<span data-ttu-id="36b58-109">Procédez comme suit pour configurer des composants TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-109">Follow these steps to set up TDS components.</span></span>

1. <span data-ttu-id="36b58-110">Accédez à **Taxe \> Configuration \> Retenue à la source \> Composants de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="36b58-110">Go to **Tax \> Setup \> Withholding tax \> Withholding tax components**.</span></span>

    <span data-ttu-id="36b58-111">[![Page Composants de retenue à la source](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span><span class="sxs-lookup"><span data-stu-id="36b58-111">[![Withholding tax components page](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span></span>

2. <span data-ttu-id="36b58-112">Dans le champ **Type de taxe**, sélectionnez **TDS** pour configurer des composants pour le type de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-112">In the **Tax type** field, select **TDS** to set up withholding tax components for the TDS tax type.</span></span>
3. <span data-ttu-id="36b58-113">Dans le volet Actions, sélectionnez **Nouveau** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="36b58-113">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="36b58-114">Dans le champ **Composant de retenue à la source**, entrez un nom pour le composant TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-114">In the **Withholding tax component** field, enter a name for the TDS component.</span></span>
5. <span data-ttu-id="36b58-115">Dans le champ **Groupe de composants de retenue à la source**, sélectionnez le groupe de composants de retenue d'impôt TDS auquel attacher le composant TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-115">In the **Withholding tax component group** field, select the TDS withholding tax component group to attach the TDS component to.</span></span>
6. <span data-ttu-id="36b58-116">Dans le raccourci **Général**, dans le champ **Description**, saisissez une description du composant TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-116">On the **General** FastTab, in the **Description** field, enter a description of  the TDS component.</span></span>
7. <span data-ttu-id="36b58-117">Dans le volet Actions, sélectionnez **Seuil** pour ouvrir la page **Seuil**, afin que vous puissiez définir le seuil utilisé pour calculer TDS pour le composant TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-117">On the Action Pane, select **Threshold** to open **Threshold** page, so that you can define the threshold that is used to calculate TDS for the TDS component.</span></span>
8. <span data-ttu-id="36b58-118">Utilisez les champs **Date de début** et **Date de fin** pour définir la période à laquelle le seuil est applicable.</span><span class="sxs-lookup"><span data-stu-id="36b58-118">Use the **From date** and **To date** fields to define the period that the threshold is applicable to.</span></span>
9. <span data-ttu-id="36b58-119">Sur le raccourci **Général**, dans le champ **Seuil**, entrez le montant seuil utilisé pour calculer le TDS pour le composant TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-119">On the **General** FastTab, in the **Threshold** field, enter the threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="36b58-120">La taxe ne sera déduite à la source que lorsque le montant cumulé de la facture franchira le seuil.</span><span class="sxs-lookup"><span data-stu-id="36b58-120">The tax will be deducted at the source only when the cumulative invoice amount crosses the threshold.</span></span>

    <span data-ttu-id="36b58-121">Par exemple, si le montant du seuil est de 10 000, TDS est calculé après que le montant de la facture cumulée dépasse 10 000 (en d'autres termes, lorsqu'il est de 10 001 ou plus).</span><span class="sxs-lookup"><span data-stu-id="36b58-121">For example, if the threshold amount is 10,000, TDS is calculated after the cumulative invoice amount exceeds 10,000 (in other words, when it's 10,001 or more).</span></span>

10. <span data-ttu-id="36b58-122">Dans le champ **Seuil d'exception**, entrez le montant seuil d'exception utilisé pour calculer le TDS pour le composant TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-122">In the **Exception threshold** field, enter the exception threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="36b58-123">La taxe sur une ligne de facture ne sera déduite à la source que lorsque le montant cumulé de la facture franchira le seuil d'exception.</span><span class="sxs-lookup"><span data-stu-id="36b58-123">The tax on an invoice line will be deducted at the source only when the amount crosses the exception threshold.</span></span>

    <span data-ttu-id="36b58-124">Par exemple, si le montant du seuil d'exception est de 5 000 TDS est calculé sur une ligne de facture spécifique si le montant de la ligne de facture dépasse 5 000 (en d'autres termes, s'il est de 5 001 ou plus).</span><span class="sxs-lookup"><span data-stu-id="36b58-124">For example, if the exception threshold amount is 5,000, TDS is calculated on a specific invoice line if the invoice line amount exceeds 5,000 (in other words, if it's 5,001 or more).</span></span>

    <span data-ttu-id="36b58-125">[![Page Seuil](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span><span class="sxs-lookup"><span data-stu-id="36b58-125">[![Threshold page](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="36b58-126">Le montant du seuil d'exception doit être inférieur ou égal au montant du seuil.</span><span class="sxs-lookup"><span data-stu-id="36b58-126">The exception threshold amount must be less than or equal to the threshold amount.</span></span>
    >
    > <span data-ttu-id="36b58-127">La taxe est déduite pour une transaction si le montant de la transaction dépasse le seuil d'exception, même si le montant cumulé de la facture ne dépasse pas le seuil spécifié dans le champ **Seuil**.</span><span class="sxs-lookup"><span data-stu-id="36b58-127">The tax is deducted for a transaction if the transaction amount crosses the exception threshold, even if the cumulative invoice amount doesn't cross the threshold that is specified in the **Threshold** field.</span></span>

11. <span data-ttu-id="36b58-128">Fermez la page **Seuil** pour revenir à la page **Composants de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="36b58-128">Close the **Threshold** page to return to the **Withholding tax components** page.</span></span>
12. <span data-ttu-id="36b58-129">Dans le volet Actions, sélectionnez **Copier** pour ouvrir la boîte de dialogue **Copier les composants de la retenue à la source**, afin que vous puissiez copier les composants TDS qui ont été configurés pour un groupe de composants TDS dans un autre groupe de composants TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-129">On the Action Pane, select **Copy** to open the **Copy withholding tax components** dialog box, so that you can copy the TDS components that were set up for one TDS component group to another TDS component group.</span></span>
13. <span data-ttu-id="36b58-130">Dans le champ **De**, sélectionnez le groupe de composants TDS à partir duquel copier les composants TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-130">In the **From** field, select the TDS component group to copy the TDS components from.</span></span> <span data-ttu-id="36b58-131">Dans le champ **À**, sélectionnez le groupe de composant de retenue à la source pour y copier les composants TDS.</span><span class="sxs-lookup"><span data-stu-id="36b58-131">In the **To** field, select the withholding tax component group to copy the TDS components to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36b58-132">Les composants TDS communs associés aux deux groupes de composants TDS ne sont pas copiés.</span><span class="sxs-lookup"><span data-stu-id="36b58-132">Common TDS components that are attached to both TDS component groups aren't copied.</span></span>

14. <span data-ttu-id="36b58-133">Sélectionnez **OK** pour copier et créer des composants TDS pour l'autre groupe de composants TDS sur la page **Composants de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="36b58-133">Select **OK** to copy and create TDS components for the other TDS component group on the **Withholding tax components** page.</span></span>

    <span data-ttu-id="36b58-134">[![Boîte de dialogue Copier les composants de la retenue à la source](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span><span class="sxs-lookup"><span data-stu-id="36b58-134">[![Copy withholding tax components dialog box](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span></span>

15. <span data-ttu-id="36b58-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="36b58-135">Close the page.</span></span>
