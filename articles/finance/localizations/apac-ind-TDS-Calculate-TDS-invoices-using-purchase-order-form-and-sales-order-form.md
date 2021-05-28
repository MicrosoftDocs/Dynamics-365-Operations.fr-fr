---
title: Calculer les factures TDS à l'aide du formulaire de commande fournisseur et du formulaire de commande client
description: Cette rubrique répertorie les étapes de calcul de la taxe déduite à la source (TDS) sur différents types de factures.
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
ms.openlocfilehash: e7925206f3c060c6332de9d4972c8a7fb0066be2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023228"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a><span data-ttu-id="b8f15-103">Calculer les factures TDS à l'aide du formulaire de commande fournisseur et du formulaire de commande client</span><span class="sxs-lookup"><span data-stu-id="b8f15-103">Calculate TDS invoices using purchase order form and sales order form</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8f15-104">Cette rubrique répertorie les étapes de calcul de la taxe déduite à la source (TDS) sur différents types de factures à l'aide des pages **Commande fournisseur**, **Journal des achats**, **Commande globale** et **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on various types of invoices using the **Purchase order**, **Purchase journal**, **Blanket order**, and **Sales order** pages.</span></span>

1. <span data-ttu-id="b8f15-105">Créez une commande fournisseur, un journal d'achats, une commande fournisseur globale ou une commande client à l'aide de la page répertoriée.</span><span class="sxs-lookup"><span data-stu-id="b8f15-105">Create a purchase order, purchase journal, purchase blanket order, or a sales order using the page listed.</span></span> <span data-ttu-id="b8f15-106">Entrez les détails requis.</span><span class="sxs-lookup"><span data-stu-id="b8f15-106">Enter the required details.</span></span>

2. <span data-ttu-id="b8f15-107">Sélectionnez l'onglet **Installer** pour afficher la nature de la personne évaluée du fournisseur ou du client.</span><span class="sxs-lookup"><span data-stu-id="b8f15-107">Select the **Setup** tab to view the nature of the assessee of the vendor or customer.</span></span> <span data-ttu-id="b8f15-108">Ces informations sont répertoriées dans le champ **Nature de la personne évaluée**, sous le champ **Groupe de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-108">This information is listed in the **Nature of assessee** field, under the **Withholding tax group** field group.</span></span>

3. <span data-ttu-id="b8f15-109">Dans le champ **Groupe TDS**, affichez ou modifiez le groupe TDS par défaut défini pour le fournisseur ou le client.</span><span class="sxs-lookup"><span data-stu-id="b8f15-109">In the **TDS group** field, view or modify the default TDS group defined for the vendor or customer.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b8f15-110">Le champ **Groupe TCS** n'est pas disponible lorsque vous sélectionnez un groupe TDS dans le champ **Groupe TDS**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-110">The **TCS group** field isn't available when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="b8f15-111">TDS est calculé uniquement si la case **Calcul de la retenue à la source** est cochée pour le fournisseur ou le client sur la page **Tous les fournisseurs** ou **Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-111">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** page.</span></span>  

4. <span data-ttu-id="b8f15-112">Créez des lignes d'articles dans l'onglet **Lignes** et entrez les détails requis.</span><span class="sxs-lookup"><span data-stu-id="b8f15-112">Create item lines on the **Lines** tab and enter the required details.</span></span>

5. <span data-ttu-id="b8f15-113">Sélectionnez l'onglet **Configurer** (au niveau de la ligne) pour afficher ou modifier le groupe TDS défini au niveau de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="b8f15-113">Select the **Setup** tab (line-level) to view or change the TDS group defined at the header-level.</span></span> <span data-ttu-id="b8f15-114">Le groupe TDS s'affiche dans le champ **Groupe TDS**, qui est sous le groupe de champs **Groupe de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-114">The TDS group is displayed in the **TDS group** field, which is under the **Withholding tax group** field group.</span></span>

6. <span data-ttu-id="b8f15-115">Sélectionnez l'onglet **Informations fiscales** et sélectionnez les adresses alternatives configurées pour le nom de la société affiché dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="b8f15-115">Select the **Tax information** tab and select alternate addresses that are set up for the company name that's displayed in this field.</span></span> <span data-ttu-id="b8f15-116">Le nom de l'entreprise s'affiche dans le champ **Nom**, qui est sous le groupe de champs **Informations sur la société**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-116">The company name is displayed in the **Name** field, which is under the **Company information** field group.</span></span> 

   <span data-ttu-id="b8f15-117">Le TAN du nom de l'entreprise sélectionné s'affiche dans le champ **Numéro de compte fiscal** (**TAN**), sous le groupe de champs **Retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-117">The TAN of the selected company name is displayed in the **Tax Account Number** (**TAN**) field, under the **Withholding tax** field group.</span></span> 

7. <span data-ttu-id="b8f15-118">Sélectionnez **Retenue à la source** pour ouvrir la page **Opérations de retenue à la source temporaire**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-118">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="b8f15-119">Affichez les champs suivants dans le volet supérieur de la page **Opérations de retenue à la source temporaire**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-119">View the following fields on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="b8f15-120">**Montant** **total de la** **retenue** **à la** **source** - TDS total calculé pour la transaction pour le groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="b8f15-120">**Withholding** **tax** **amount** **in** **total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="b8f15-121">**Valeur** - Pourcentage total utilisé pour calculer TDS pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="b8f15-121">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="b8f15-122">Le pourcentage total est basé sur la formule définie pour les codes de taxe TDS et attachée au groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="b8f15-122">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="b8f15-123">**Montant de la retenue à la source ajusté au total** - Le montant total ajusté du TDS pour tous les codes de taxe du groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="b8f15-123">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="b8f15-124">**TDS** - Si cette option est sélectionnée, un groupe TDS est attaché à la transaction.</span><span class="sxs-lookup"><span data-stu-id="b8f15-124">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

<span data-ttu-id="b8f15-125">Les champs des onglets **Aperçu**, **Général** et **Ajustement** dans la page **Opérations de retenue à la source temporaire** affichent le montant TDS calculé et les détails du montant TDS ajusté pour chaque code de taxe TDS associé au groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="b8f15-125">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

8. <span data-ttu-id="b8f15-126">Sélectionnez **Seuil** pour ouvrir la page **Seuil**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-126">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="b8f15-127">Consultez la limite de seuil définie pour la composant de taxe TDS associée à un code de taxe TDS spécifique sur cette page.</span><span class="sxs-lookup"><span data-stu-id="b8f15-127">View the threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

9. <span data-ttu-id="b8f15-128">Sélectionnez **Concepteur de formule** pour ouvrir la page **Concepteur de formule**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-128">Select **Formula designer** to open the **Formula designer** page.</span></span> <span data-ttu-id="b8f15-129">Consultez la formule définie pour un code de taxe TDS spécifique sur cette page.</span><span class="sxs-lookup"><span data-stu-id="b8f15-129">View the formula that is defined for a specific TDS tax code on this page.</span></span> 

10. <span data-ttu-id="b8f15-130">Validez la facture.</span><span class="sxs-lookup"><span data-stu-id="b8f15-130">Post the invoice.</span></span> <span data-ttu-id="b8f15-131">Le montant TDS calculé sur les factures d'achat est enregistré sur le compte fournisseur et le montant TDS calculé sur les factures de vente est enregistré sur le compte client défini pour chaque code TVA TDS du groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="b8f15-131">The TDS amount calculated on purchase invoices is posted to the payable account and the TDS amount calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="b8f15-132">Les comptes clients et fournisseurs pour les codes TVA TDS sont définis sur la page **Codes de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-132">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

11. <span data-ttu-id="b8f15-133">Sélectionnez le bouton **Recherche** **> Facture > Retenue à la source validée** pour ouvrir la page **Opérations de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-133">Select **Inquiry** button **> Invoice > Posted withholding tax** button to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="b8f15-134">Vous pouvez afficher le pourcentage total qui a été utilisé pour calculer TDS pour la transaction dans le champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="b8f15-134">You can view the total percentage used to calculate TDS for the transaction in the **Value** field.</span></span>

<span data-ttu-id="b8f15-135">Les onglets **Aperçu**, **Général** et **Montant** sur la page **Opérations de retenue à la source** affichent les informations de TDS calculées pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="b8f15-135">The fields on the **Overview**, **General**, and **Amount** tabs on the **Withholding tax transactions** page display the information of TDS calculated for the transaction.</span></span> <span data-ttu-id="b8f15-136">Affichez les informations de calcul TDS pour chaque code de taxe TDS associé au groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="b8f15-136">View the TDS calculation information for each TDS tax code attached to the TDS group.</span></span>
