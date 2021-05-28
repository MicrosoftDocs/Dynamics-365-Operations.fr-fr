---
title: Paramétrer les codes déclaration de retenue à la source pour le type de taxe TDS
description: Cette rubrique explique comment configurer des codes taxes pour la fonction Taxe déduite à la source (TDS).
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
ms.openlocfilehash: d56a23f7af7633e1761a8a7c48f71381d6f14df2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023250"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a><span data-ttu-id="d0047-103">Paramétrer les codes déclaration de retenue à la source pour le type de taxe TDS</span><span class="sxs-lookup"><span data-stu-id="d0047-103">Set up withholding tax codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0047-104">Cette rubrique explique comment configurer des codes taxes pour la fonction Taxe déduite à la source (TDS).</span><span class="sxs-lookup"><span data-stu-id="d0047-104">This topic explains how to set up tax codes for Tax Deducted at Source (TDS).</span></span>

1. <span data-ttu-id="d0047-105">Accédez à **Taxe \> Taxes indirectes \> Retenue à la source \> Codes de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="d0047-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax codes**.</span></span>

    <span data-ttu-id="d0047-106">[![Page Codes de retenue à la source](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span><span class="sxs-lookup"><span data-stu-id="d0047-106">[![Withholding tax codes page](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span></span>

2. <span data-ttu-id="d0047-107">Dans le volet Actions, sélectionnez **Nouveau** pour créer un code de retenue à la source pour TDS et entrez les détails requis.</span><span class="sxs-lookup"><span data-stu-id="d0047-107">On the Action Pane, select **New** to create a withholding tax code for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="d0047-108">Dans le raccourci **Général**, dans le champ **Type de taxe**, sélectionnez **TDS** pour classer le code de taxe comme code de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="d0047-108">On the **General** FastTab, in the **Tax type** field, select **TDS** to categorize the tax code as a TDS tax code.</span></span>
4. <span data-ttu-id="d0047-109">Dans le champ **Période de règlement**, sélectionnez la période de règlement TDS pour le code de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="d0047-109">In the **Settlement period** field, select the TDS settlement period for the TDS tax code.</span></span>
5. <span data-ttu-id="d0047-110">Dans le champ **Compte principal**, sélectionnez le compte général sur lequel le montant TDS doit être imputé.</span><span class="sxs-lookup"><span data-stu-id="d0047-110">In the **Main account** field, select the ledger account that the TDS amount should be posted to.</span></span>
6. <span data-ttu-id="d0047-111">Dans le champ **Compte client**, sélectionnez le compte client sur lequel le montant TDS déduit dans les transactions de vente doit être imputé.</span><span class="sxs-lookup"><span data-stu-id="d0047-111">In the **Receivable account** field, select the receivable account that the TDS amount that is deducted in sales transactions should be posted to.</span></span>

    <span data-ttu-id="d0047-112">Le champ **Origine** est automatiquement défini sur **Pourcentage du montant brut**, et la valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="d0047-112">The **Origin** field is automatically set to **Percentage of gross amount**, and the value can't be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0047-113">Vous ne pouvez pas définir l'origine sur **Pourcentage du montant net** pour les codes de taxe du type de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="d0047-113">You can't set the origin to **Percentage of net amount** for tax codes of the TDS tax type.</span></span>

7. <span data-ttu-id="d0047-114">Dans le champ **Composant de retenue à la source**, sélectionnez le composant de taxe TDS pour le code de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="d0047-114">In the **Withholding tax component** field, select the TDS tax component for the TDS tax code.</span></span>
8. <span data-ttu-id="d0047-115">Dans le volet Actions, sélectionnez **Valeurs** pour ouvrir la page **Valeurs de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="d0047-115">On the Action Pane, select **Values** to open the **Withholding tax values** page.</span></span>
9. <span data-ttu-id="d0047-116">Dans le champ **Date de début**, saisissez la date de début pour la valeur TDS.</span><span class="sxs-lookup"><span data-stu-id="d0047-116">In the **From date** field, enter the start date for the TDS value.</span></span> <span data-ttu-id="d0047-117">Dans le champ **Date de fin**, saisissez la date de fin.</span><span class="sxs-lookup"><span data-stu-id="d0047-117">In the **To date** field, enter the end date.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0047-118">Les champs **Limite minimum**, **Limite supérieure** et **Exclure %** ne sont pas disponibles pour les codes de taxe du type de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="d0047-118">The **Minimum limit**, **Upper limit**, and **Exclude %** fields aren't available for tax codes of the TDS tax type.</span></span>

10. <span data-ttu-id="d0047-119">Dans le champ **Valeur**, entrez le pourcentage de TDS pour le code de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="d0047-119">In the **Value** field, enter the percentage of TDS for the TDS tax code.</span></span>
11. <span data-ttu-id="d0047-120">Fermez la page **Valeurs de retenue à la source** pour revenir à la page **Codes de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="d0047-120">Close the **Withholding tax values** page to return to the **Withholding tax codes** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0047-121">Le bouton **Limites** de la page **Codes de retenue à la source** n'est pas disponible pour les codes de taxe du type de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="d0047-121">The **Limits** button on the **Withholding tax codes** page isn't available for tax codes of the TDS tax type.</span></span>

12. <span data-ttu-id="d0047-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d0047-122">Close the page.</span></span>
