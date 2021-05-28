---
title: Paramétrer les périodes de règlement de retenue pour le type de taxe TDS
description: Cette rubrique explique comment configurer des périodes de configuration pour la fonction Taxe déduite à la source (TDS).
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
ms.openlocfilehash: 9430bc1386f127d02b598d6cad1b53f66e0cf2ba
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023225"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a><span data-ttu-id="870e8-103">Paramétrer les périodes de règlement de retenue pour le type de taxe TDS</span><span class="sxs-lookup"><span data-stu-id="870e8-103">Set up withholding tax settlement periods for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="870e8-104">Cette rubrique explique comment configurer des périodes de configuration pour la fonction Taxe déduite à la source (TDS).</span><span class="sxs-lookup"><span data-stu-id="870e8-104">This topic explains how to set up settlement periods for Tax Deducted at Source (TDS) settlement periods.</span></span>

1. <span data-ttu-id="870e8-105">Accédez à **Taxes \> Taxes indirectes \> Retenue à la source \> Périodes de règlement de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="870e8-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax settlement periods**.</span></span>

    <span data-ttu-id="870e8-106">[![Page Périodes de règlement de la retenue à la source](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span><span class="sxs-lookup"><span data-stu-id="870e8-106">[![Withholding tax settlement periods page](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span></span>

2. <span data-ttu-id="870e8-107">Dans le champ **Type de taxe**, sélectionnez **TDS** pour configurer des périodes de décompte de la retenue à la source pour le type de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="870e8-107">In the **Tax type** field, select **TDS** to set up withholding tax settlement periods for the TDS tax type.</span></span>
3. <span data-ttu-id="870e8-108">Sélectionnez **Nouveau** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="870e8-108">Select **New** to create a line.</span></span>
4. <span data-ttu-id="870e8-109">Dans le champ **Période de règlement**, entrez un nom pour la période de règlement TDS.</span><span class="sxs-lookup"><span data-stu-id="870e8-109">In the **Settlement period** field, enter a name for the TDS settlement period.</span></span>
5. <span data-ttu-id="870e8-110">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="870e8-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="870e8-111">Dans le champ **Administration fiscale**, sélectionnez l'autorité TDS pour laquelle vous définissez la période de décompte TDS.</span><span class="sxs-lookup"><span data-stu-id="870e8-111">In the **Withholding tax authority** field, select the TDS authority that you're defining the TDS settlement period for.</span></span>
7. <span data-ttu-id="870e8-112">Sur le raccourci **Général**, dans le champ **Intervalle de période**, sélectionnez le type d'intervalle de période pour la période de décompte TDS.</span><span class="sxs-lookup"><span data-stu-id="870e8-112">On the **General** FastTab, in the **Period interval** field, select the type of period interval for the TDS settlement period.</span></span>
8. <span data-ttu-id="870e8-113">Dans le champ **Nombre d'unités**, spécifiez le nombre d'unités pour le type d'intervalle de période.</span><span class="sxs-lookup"><span data-stu-id="870e8-113">In the **Number of units** field, specify the number of units for the period interval type.</span></span>
9. <span data-ttu-id="870e8-114">Sur le raccourci **Périodes**, dans le champ **Date de début**, sélectionnez la date de début de la période de règlement TDS.</span><span class="sxs-lookup"><span data-stu-id="870e8-114">On the **Periods** FastTab, in the **From date** field, select the start date for the TDS settlement period.</span></span> <span data-ttu-id="870e8-115">Dans le champ **Date de fin**, sélectionnez la date de fin.</span><span class="sxs-lookup"><span data-stu-id="870e8-115">In the **To date** field, select the end date.</span></span>
10. <span data-ttu-id="870e8-116">Pour créer une période de décompte TDS ultérieure pour une période existante, en fonction de l'intervalle de période et des unités de période, sélectionnez **Nouvelle période**.</span><span class="sxs-lookup"><span data-stu-id="870e8-116">To create a subsequent TDS settlement period for an existing period, based on the period interval and period units, select **New period**.</span></span>
11. <span data-ttu-id="870e8-117">Pour afficher les détails du décompte TDS périodique exécuté pour une période de décompte spécifique, sélectionnez **Paiements de retenue à la source** pour ouvrir la page **Paiement de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="870e8-117">To view the details of the periodic TDS settlement that is run for a specific settlement period, select **Withholding tax payments** to open the **Withholding tax payment** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="870e8-118">Pour exécuter le processus de règlement TDS périodique, accédez à **Comptabilité \> Périodique \> Retenue à la source \> Paiement de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="870e8-118">To run the periodic TDS settlement process, go to **General ledger \> Periodic \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="870e8-119">[![Page Paiement de la retenue à la source](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span><span class="sxs-lookup"><span data-stu-id="870e8-119">[![Withholding tax payment page](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span></span>

12. <span data-ttu-id="870e8-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="870e8-120">Close the page.</span></span>
