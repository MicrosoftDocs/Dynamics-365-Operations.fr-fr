---
title: Calcul TDS sur les factures à partir de la page Facture financière
description: Cette rubrique explique comment calculer la taxe déduite à la source (TDS) sur les factures à l'aide de la page Facture financière.
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
ms.openlocfilehash: 7d551a8ba6ba9ca282fd9de3fa7d7c7303e394ed
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023244"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a><span data-ttu-id="91359-103">Calcul TDS sur les factures à partir de la page Facture financière</span><span class="sxs-lookup"><span data-stu-id="91359-103">TDS calculation on invoices from the Free text invoice page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91359-104">Cette rubrique explique comment calculer la taxe déduite à la source (TDS) sur les factures à l'aide de la page **Facture financière**.</span><span class="sxs-lookup"><span data-stu-id="91359-104">This topic explains how to calculate Tax Deducted at Source (TDS) on invoices by using the **Free text invoice** page.</span></span>

1. <span data-ttu-id="91359-105">Allez dans **Comptabilité client \> Factures \> Toutes factures financières**.</span><span class="sxs-lookup"><span data-stu-id="91359-105">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>

    <span data-ttu-id="91359-106">[![Page Facture financière](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span><span class="sxs-lookup"><span data-stu-id="91359-106">[![Free text invoice page](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span></span>

2. <span data-ttu-id="91359-107">Sélectionnez **Nouveau** pour créer une facture financière, puis entrez les informations requises.</span><span class="sxs-lookup"><span data-stu-id="91359-107">Select **New** to create a free text invoice, and enter the required details.</span></span>
3. <span data-ttu-id="91359-108">Sélectionnez l'onglet **Facture**. Dans la section **Retenue à la source**, le champ **Nature de la personne évaluée** affiche la nature de la catégorie du fournisseur ou du client.</span><span class="sxs-lookup"><span data-stu-id="91359-108">Select the **Invoice** tab. In the **Withholding tax group** section, the **Nature of assessee** field shows the nature of assessee category of the customer.</span></span>
4. <span data-ttu-id="91359-109">Dans le champ **Groupe TDS**, révisez ou modifiez le groupe TDS par défaut défini pour le client.</span><span class="sxs-lookup"><span data-stu-id="91359-109">In the **TDS group** field, review or change the default TDS group that is defined for the customer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="91359-110">Lorsque vous sélectionnez une valeur dans le champ **Groupe TDS**, le champ **Groupe TCS** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="91359-110">When you select a value in the **TDS group** field, the **TCS group** field becomes unavailable.</span></span> <span data-ttu-id="91359-111">TDS est calculé uniquement si l'option **Calcul de la retenue à la source** est définie sur **Oui** pour le client sur la page **Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="91359-111">TDS is calculated only if the **Calculate withholding tax** option is set to **Yes** for the customer on the **All customers** page.</span></span>

5. <span data-ttu-id="91359-112">Dans l'onglet **Informations fiscales**, dans la section **Informations sur la société**, dans le champ **Nom**, vous pouvez sélectionner un nom de société pour une adresse alternative configurée pour la société.</span><span class="sxs-lookup"><span data-stu-id="91359-112">On the **Tax information** tab, in the **Company information** section, in the **Name** field, select the company name for an alternate address that has been set up for the company.</span></span>

    <span data-ttu-id="91359-113">Dans la section **Retenue à la source**, le champ **Numéro de compte fiscal (TAN)** affiche le numéro de compte fiscal (TAN) de la société sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="91359-113">In the **Withholding tax** section, the **Tax Account Number (TAN)** field shows the tax account number (TAN) for the selected company.</span></span>

6. <span data-ttu-id="91359-114">Dans l'onglet **Lignes de facture**, créez des lignes de facture, puis entrez les détails requis.</span><span class="sxs-lookup"><span data-stu-id="91359-114">On the **Invoice lines** tab, create invoice lines, and enter the required details.</span></span>

    <span data-ttu-id="91359-115">Dans la section **Groupe de retenue à la source**, le champ **Numéro de compte fiscal (TAN)** affiche le TAN, et le champ **Groupe TDS** affiche le groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="91359-115">In the **Withholding tax group** section, the **Tax Account Number (TAN)** field shows the TAN, and the **TDS group** field shows the TDS group.</span></span>

7. <span data-ttu-id="91359-116">Sélectionnez **Retenue à la source** pour ouvrir la page **Opérations de retenue à la source temporaire**.</span><span class="sxs-lookup"><span data-stu-id="91359-116">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="91359-117">La partie supérieure de cette page contient les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="91359-117">The upper part of this page has the following fields:</span></span>

    - <span data-ttu-id="91359-118">**Montant total de la retenue à la source** - Le TDS total qui a été calculé pour la transaction pour le groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="91359-118">**Withholding tax amount in total** – The total TDS that was calculated for the transaction for the TDS group.</span></span>
    - <span data-ttu-id="91359-119">**Valeur** - Le pourcentage total qui a été utilisé pour calculer TDS pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="91359-119">**Value** – The total percentage that was used to calculate TDS for the transaction.</span></span> <span data-ttu-id="91359-120">Le pourcentage total est basé sur la formule définie pour les codes de taxe TDS et attachée au groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="91359-120">The total percentage is based on the formula that is defined for the TDS tax codes and attached to the TDS group.</span></span>
    - <span data-ttu-id="91359-121">**Montant de la retenue à la source ajusté au total** - Le montant total ajusté du TDS pour tous les codes de taxe du groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="91359-121">**Adjusted withholding tax amount in total** – The total adjusted TDS amount for all tax codes in the TDS group.</span></span>
    - <span data-ttu-id="91359-122">**TDS** - Une case cochée indique qu'un groupe TDS est attaché à la transaction.</span><span class="sxs-lookup"><span data-stu-id="91359-122">**TDS** – A selected checkbox indicates that a TDS group is attached to the transaction.</span></span>

    <span data-ttu-id="91359-123">Les champs des onglets **Aperçu**, **Général** et **Ajustement** affichent le montant TDS calculé et les détails du montant TDS ajusté pour chaque code de taxe TDS associé au groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="91359-123">The fields on the **Overview**, **General**, and **Adjustment** tabs show the calculated TDS amount and details of the adjusted TDS amount for each TDS tax code that is attached to the TDS group.</span></span>

8. <span data-ttu-id="91359-124">Sélectionnez **Seuil** pour ouvrir la page **Seuil** dans laquelle vous pouvez consulter la limite de seuil définie pour la composant de taxe TDS associée à un code de taxe TDS spécifique.</span><span class="sxs-lookup"><span data-stu-id="91359-124">Select **Threshold** to open the **Threshold** page, where you can review the threshold limit that is defined for the TDS tax component that is attached to a specific TDS tax code.</span></span>
9. <span data-ttu-id="91359-125">Sélectionnez **Concepteur de formule** pour ouvrir la page **Concepteur de formule**, où vous pouvez consulter la formule définie pour un code de taxe TDS spécifique.</span><span class="sxs-lookup"><span data-stu-id="91359-125">Select **Formula designer** to open the **Formula designer** page, where you can review the formula that is defined for a specific TDS tax code.</span></span>
10. <span data-ttu-id="91359-126">Validez la facture financière.</span><span class="sxs-lookup"><span data-stu-id="91359-126">Post the free text invoice.</span></span> <span data-ttu-id="91359-127">Le montant TDS qui est calculé pour la facture financière est imputé au compte fournisseur défini pour chaque code TVA TDS du groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="91359-127">The TDS amount that is calculated for the free text invoice is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="91359-128">Les comptes clients pour les codes TVA TDS sont définis sur la page **Codes de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="91359-128">The receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>
11. <span data-ttu-id="91359-129">Sélectionnez **Retenue à la source validée** pour ouvrir la page **Opérations de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="91359-129">Select **Posted withholding tax** to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="91359-130">Le champ **Valeur** affiche le pourcentage total qui a été utilisé pour calculer TDS pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="91359-130">The **Value** field shows the total percentage that was used to calculate TDS for the transaction.</span></span>

    <span data-ttu-id="91359-131">Les champs sur les onglets **Aperçu**, **Général** et **Montant** affichent les montants TDS qui ont été calculés sur les lignes de facture.</span><span class="sxs-lookup"><span data-stu-id="91359-131">The fields on the **Overview**, **General**, and **Amount** tabs show the TDS amounts that were calculated on the invoice lines.</span></span>

12. <span data-ttu-id="91359-132">Vérifiez les informations de calcul TDS pour chaque code de taxe TDS associé au groupe TDS.</span><span class="sxs-lookup"><span data-stu-id="91359-132">Review the TDS calculation information for each TDS tax code that is attached to the TDS group.</span></span>
