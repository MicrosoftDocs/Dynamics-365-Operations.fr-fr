---
title: Joindre les codes de taxe TDS aux groupes de taxes TDS et définir la formule de calcul du TDS
description: Cette rubrique explique comment configurer les groupes de taxes TDS (Tax Deduced at Source) et associer les codes de taxe TDS aux groupes de taxe TDS. Pour calculer le TDS pour un groupe de taxes TDS, vous devez définir la formule des codes de taxe TDS qui lui sont attachés.
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
ms.openlocfilehash: ec0d683153bd5ab731035159d32881fbdb352d70
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023247"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a><span data-ttu-id="76b0a-104">Joindre les codes de taxe TDS aux groupes de taxes TDS et définir la formule de calcul du TDS</span><span class="sxs-lookup"><span data-stu-id="76b0a-104">Attach TDS tax codes to TDS tax groups and define the formula for calculating TDS</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76b0a-105">Cette rubrique explique comment configurer les groupes de taxes TDS (Tax Deduced at Source) et associer les codes de taxe TDS aux groupes de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="76b0a-105">This topic explains how to set up Tax Deducted at Source (TDS) tax groups and attach TDS tax codes to TDS tax groups.</span></span> <span data-ttu-id="76b0a-106">Pour calculer le TDS pour un groupe de taxes TDS, vous devez définir la formule des codes de taxe TDS qui lui sont attachés.</span><span class="sxs-lookup"><span data-stu-id="76b0a-106">To calculate TDS for a TDS tax group, you must define the formula for TDS tax codes that are attached to it.</span></span>

<span data-ttu-id="76b0a-107">Suivez ces étapes pour configurer un groupe de taxes TDS, y associer des codes de taxe TDS et définir la formule de calcul de TDS.</span><span class="sxs-lookup"><span data-stu-id="76b0a-107">Follow these steps to set up a TDS tax group, attach TDS tax codes to it, and define the formula for calculating TDS.</span></span>

1. <span data-ttu-id="76b0a-108">Accédez à **Taxe \> > Taxes indirectes \> Retenue à la source \> Groupes de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-108">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax groups**.</span></span>

    <span data-ttu-id="76b0a-109">[![Page Groupes de retenue à la source](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span><span class="sxs-lookup"><span data-stu-id="76b0a-109">[![Withholding tax groups page](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span></span>

2. <span data-ttu-id="76b0a-110">Dans le volet Actions, sélectionnez **Nouveau** pour créer un groupe de retenue à la source pour TDS et entrez les détails requis.</span><span class="sxs-lookup"><span data-stu-id="76b0a-110">On the Action Pane, select **New** to create a withholding tax group for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="76b0a-111">Dans le champ **Type de taxe**, sélectionnez **TDS**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-111">In the **Tax type** field, select **TDS**.</span></span>
4. <span data-ttu-id="76b0a-112">Dans le raccourci **Configurer**, sélectionnez **Ajouter** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="76b0a-112">On the **Setup** FastTab, select **Add** to create a line.</span></span>
5. <span data-ttu-id="76b0a-113">Dans le champ **Code de retenue à la source**, sélectionnez le code de taxe TDS pour le groupe de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="76b0a-113">In the **Withholding tax code** field, select the TDS tax code for the TDS tax group.</span></span> <span data-ttu-id="76b0a-114">Le champ **Nom de la retenue à la source** affiche le nom du code de taxe TDS et le champ **Valeur** affiche la valeur.</span><span class="sxs-lookup"><span data-stu-id="76b0a-114">The **Withholding tax name** field shows the name of the TDS tax code, and the **Value** field shows the value.</span></span>
6. <span data-ttu-id="76b0a-115">Pour ignorer la limite de seuil et la limite de seuil d'exception qui sont définies pour la composant de taxe TDS qui est attachée au code de taxe TDS dans les transactions TDS, cochez la case **Seuil de surplomb**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-115">To ignore the threshold limit and exception threshold limit that are defined for the TDS tax component that is attached to the TDS tax code in TDS transactions, select the **Overlook threshold** check box.</span></span>
7. <span data-ttu-id="76b0a-116">Pour empêcher que le groupe de taxe ne soit calculé dans les transactions, cochez la case **Exempté**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-116">To prevent the tax group from being calculated in transactions, select the **Exempt** check box.</span></span>
8. <span data-ttu-id="76b0a-117">Dans le volet Actions, sélectionnez **Concepteur** pour ouvrir le concepteur de formule, afin de pouvoir définir la formule de calcul de TDS pour le groupe de taxes TDS.</span><span class="sxs-lookup"><span data-stu-id="76b0a-117">On the Action Pane, select **Designer** to open the formula designer, so that you can define the formula for calculating TDS for the TDS tax group.</span></span> <span data-ttu-id="76b0a-118">Sur la page **Concepteur**, l'onglet **Taxes** affiche les codes de taxe TDS qui ont été sélectionnés pour le groupe de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="76b0a-118">On the **Designer** page, the **Taxes** tab shows the TDS tax codes that have been selected for the TDS tax group.</span></span>

    <span data-ttu-id="76b0a-119">[![Page Concepteur](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span><span class="sxs-lookup"><span data-stu-id="76b0a-119">[![Designer page](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span></span>

9. <span data-ttu-id="76b0a-120">Dans l'onglet **Calcul**, sélectionnez **Alt + N** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="76b0a-120">On the **Calculation** tab, select **Alt+N** to create a line.</span></span> <span data-ttu-id="76b0a-121">Le champ **ID** affiche l'ID de priorité généré automatiquement pour le calcul TDS.</span><span class="sxs-lookup"><span data-stu-id="76b0a-121">The **ID** field shows the automatically generated priority ID for TDS calculation.</span></span>
10. <span data-ttu-id="76b0a-122">Dans le champ **Code taxe**, sélectionnez le code de taxe TDS pour laquelle définir la formule.</span><span class="sxs-lookup"><span data-stu-id="76b0a-122">In the **Tax code** field, select the TDS tax code to define the formula for.</span></span> <span data-ttu-id="76b0a-123">Tous les codes de taxe TDS qui ont été sélectionnés pour le groupe de taxe TDS peuvent être sélectionnés dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="76b0a-123">All the TDS tax codes that have been selected for the TDS tax group are available for selection in this field.</span></span>
11. <span data-ttu-id="76b0a-124">Dans le champ **Base imposable**, sélectionnez la base de calcul du TDS :</span><span class="sxs-lookup"><span data-stu-id="76b0a-124">In the **Taxable basis** field, select the basis for calculating TDS:</span></span>

    - <span data-ttu-id="76b0a-125">**Montant brut** - Calculez le TDS en fonction du montant brut de la transaction (c'est-à-dire le montant de la facture) en utilisant l'expression de calcul définie pour le code TVA.</span><span class="sxs-lookup"><span data-stu-id="76b0a-125">**Gross amount** – Calculate TDS based on the gross transaction amount (that is, the invoice amount) by using the calculation expression that is defined for the tax code.</span></span>
    - <span data-ttu-id="76b0a-126">**Hors montant brut** - Calculez le TDS en fonction de l'expression de calcul définie pour le code fiscal.</span><span class="sxs-lookup"><span data-stu-id="76b0a-126">**Excl Gross amount** – Calculate TDS based on the calculation expression that is defined for the tax code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="76b0a-127">Le champ **Base imposable** ne peut pas être défini sur **Hors montant brut** pour le code fiscal TDS dont l'ID de priorité est **1**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-127">The **Taxable basis** field can't be set to **Excl Gross amount** for the TDS tax code that has a priority ID of **1**.</span></span>

12. <span data-ttu-id="76b0a-128">Le calcul TDS est basé sur la formule définie dans le champ **Expression de calcul** pour chaque code de taxe associé au groupe de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="76b0a-128">The TDS calculation is based on the formula that is defined in the **Calculation expression** field for each tax code that is attached to the TDS tax group.</span></span> <span data-ttu-id="76b0a-129">Sélectionnez le signe plus (**+**), signe moins (**-**), signe de multiplication (**\**_) ou le signe de division (_*/**) pour saisir l'expression de calcul du code de taxe TDS sélectionné dans le champ **Expression de calcul**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-129">Select the plus sign (**+**), minus sign (**-**), multiplication sign (**\**_), or division sign (_*/**) button to enter the calculation expression for the selected TDS tax code in the **Calculation expression** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="76b0a-130">Aucune expression de calcul ne peut être définie pour le code TVA TDS dont l'ID de priorité est **1**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-130">No calculation expression can be defined for the TDS tax code that has a priority ID of **1**.</span></span>

13. <span data-ttu-id="76b0a-131">Pour définir l'expression de calcul du code TVA TDS dans le champ **Expression de calcul**, ajoutez les codes de taxe TDS disponibles sur l'onglet **Taxes**. Pour ajouter des codes de taxe TDS dans le champ **Expression de calcul**, vous pouvez utiliser l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="76b0a-131">To define the calculation expression for the TDS tax code in the **Calculation expression** field, add TDS tax codes that are available on the **Taxes** tab. To add TDS tax codes in the **Calculation expression** field, you can use any of the following methods:</span></span>

    - <span data-ttu-id="76b0a-132">Faites glisser le code de taxe requis à partir de l'onglet **Taxes** vers le champ **Expression de calcul**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-132">Drag the required tax code from the **Taxes** tab to the **Calculation expression** field.</span></span>
    - <span data-ttu-id="76b0a-133">Appuyez deux fois (ou double-cliquez) sur le code de taxe requis sur l'onglet **Taxes**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-133">Double-tap (or double-click) the required tax code on the **Taxes** tab.</span></span>
    - <span data-ttu-id="76b0a-134">Sélectionnez et maintenez (ou cliquez avec le bouton droit) le code de taxe requis sur l'onglet **Taxes**, puis sélectionnez **Ajouter un code de taxe**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-134">Select and hold (or right-click) the required tax code on the **Taxes** tab, and then select **Add tax code**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="76b0a-135">Insérez une expression de calcul avant chaque code de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="76b0a-135">Insert a calculation expression before each TDS tax code.</span></span> <span data-ttu-id="76b0a-136">Les codes de taxe TDS qui ont été ajoutés à l'expression de calcul apparaissent entre parenthèses (\[ ...\]).</span><span class="sxs-lookup"><span data-stu-id="76b0a-136">The TDS tax codes that have been added to the calculation expression appear in brackets (\[...\]).</span></span>

14. <span data-ttu-id="76b0a-137">Pour effacer l'expression de calcul définie pour un code TVA dans le champ **Expression de calcul**, sélectionnez le bouton **C**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-137">To clear the calculation expression that is defined for a tax code in the **Calculation expression** field, select the **C** button.</span></span>
15. <span data-ttu-id="76b0a-138">Pour supprimer un enregistrement dans l'onglet **Calcul**, sélectionnez **Effacer**.</span><span class="sxs-lookup"><span data-stu-id="76b0a-138">To delete a record on the **Calculation** tab, select **Delete**.</span></span>
16. <span data-ttu-id="76b0a-139">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="76b0a-139">Close the page.</span></span>
