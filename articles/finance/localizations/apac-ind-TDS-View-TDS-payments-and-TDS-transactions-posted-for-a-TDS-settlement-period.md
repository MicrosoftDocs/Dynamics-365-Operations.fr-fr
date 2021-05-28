---
title: Afficher les paiements et les transactions TDS validés pour une période de règlement TDS
description: Cette rubrique explique comment afficher les paiements et les transactions de taxe déduite à la source (TDS) qui ont été comptabilisés pour une période de règlement.
author: kailiang
ms.date: 03/12/2021
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
ms.openlocfilehash: 2bada42073e46c69101e6d31f3328a2eeb95f880
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023231"
---
# <a name="view-posted-tds-payments-and-transactions-for-a-tds-settlement-period"></a><span data-ttu-id="e241f-103">Afficher les paiements et les transactions TDS validés pour une période de règlement TDS</span><span class="sxs-lookup"><span data-stu-id="e241f-103">View posted TDS payments and transactions for a TDS settlement period</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e241f-104">Cette rubrique explique comment afficher les paiements et les transactions de taxe déduite à la source (TDS) qui ont été comptabilisés pour une période de règlement.</span><span class="sxs-lookup"><span data-stu-id="e241f-104">This topic explains how to view the Tax Deducted at Source (TDS) payments and transactions that were posted for a settlement period.</span></span>

1. <span data-ttu-id="e241f-105">Accédez à **Taxes \> Taxes indirectes \> Retenue à la source \> Périodes de règlement de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="e241f-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax settlement periods**.</span></span>

    <span data-ttu-id="e241f-106">[![Page Périodes de règlement de la retenue à la source](./media/apac-ind-TDS-50.png)](./media/apac-ind-TDS-50.png)</span><span class="sxs-lookup"><span data-stu-id="e241f-106">[![Withholding tax settlement periods page](./media/apac-ind-TDS-50.png)](./media/apac-ind-TDS-50.png)</span></span>

2. <span data-ttu-id="e241f-107">Sur la page **Périodes de règlement de la retenue à la source**, sélectionnez **Paiements de retenue à la source** pour ouvrir la page **Paiements de retenue à la source**, où vous pouvez afficher les décomptes TDS qui ont été effectués pour une période de décompte TDS spécifique.</span><span class="sxs-lookup"><span data-stu-id="e241f-107">On the **Withholding tax settlement periods** page, select **Withholding tax payments** to open the **Withholding tax payments** page, where you can view the TDS settlements that were made for a specific TDS settlement period.</span></span>

    <span data-ttu-id="e241f-108">L'onglet **Vue d'ensemble** affiche les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e241f-108">The **Overview** tab shows the following information:</span></span>

    - <span data-ttu-id="e241f-109">**Date** – Date de règlement de la taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="e241f-109">**Date** – The date of TDS settlement.</span></span>
    - <span data-ttu-id="e241f-110">**Justificatif** – Numéro de document de la transaction de règlement TDS.</span><span class="sxs-lookup"><span data-stu-id="e241f-110">**Voucher** – The voucher number of the TDS settlement transaction.</span></span>
    - <span data-ttu-id="e241f-111">**Type de taxe** - Le type de taxe pour lequel le processus de règlement est exécuté.</span><span class="sxs-lookup"><span data-stu-id="e241f-111">**Tax type** – The tax type that the settlement process is run for.</span></span>
    - <span data-ttu-id="e241f-112">**Numéro de compte fiscal (TAN)** - Le numéro de compte fiscal (TAN) de la transaction TDS réglée.</span><span class="sxs-lookup"><span data-stu-id="e241f-112">**Tax Account Number (TAN)** – The Tax Account Number (TAN) of the settled TDS transaction.</span></span>
    - <span data-ttu-id="e241f-113">**Période de règlement** - La période de décompte pour laquelle le processus de règlement TDS est exécuté.</span><span class="sxs-lookup"><span data-stu-id="e241f-113">**Settlement period** – The settlement period that the TDS settlement process is run for.</span></span>
    - <span data-ttu-id="e241f-114">**Date de début** – Permet d'entrer la date de début de la période de règlement.</span><span class="sxs-lookup"><span data-stu-id="e241f-114">**From date** – The start date of the settlement period.</span></span>
    - <span data-ttu-id="e241f-115">**Date de fin** – Permet d'entrer la date de fin de la période de règlement.</span><span class="sxs-lookup"><span data-stu-id="e241f-115">**To date** – The end date of the settlement period.</span></span>
    - <span data-ttu-id="e241f-116">**Version de paiement de la retenue à la source** - La version du paiement de la retenue à la source : **Original**, **Dernières corrections** ou **Liste totale**.</span><span class="sxs-lookup"><span data-stu-id="e241f-116">**Withholding tax payment version** – The version of the withholding tax payment: **Original**, **Latest corrections**, or **Total list**.</span></span>

5. <span data-ttu-id="e241f-117">Sélectionnez **Justificatif** pour afficher les entrées de justificatif pour la transaction TDS.</span><span class="sxs-lookup"><span data-stu-id="e241f-117">Select **Voucher** to view the voucher entries for the TDS transaction.</span></span>
6. <span data-ttu-id="e241f-118">Sélectionnez **Transactions de retenue à la source** pour afficher les détails des transactions TDS qui ont été réglées pour une période spécifique au cours d'une période de règlement.</span><span class="sxs-lookup"><span data-stu-id="e241f-118">Select **Withholding tax transactions** to view the details of the TDS transactions that were settled for a specific period during a settlement period.</span></span> <span data-ttu-id="e241f-119">Sélectionnez **Justificatif** pour afficher les entrées de justificatif pour la transaction TDS.</span><span class="sxs-lookup"><span data-stu-id="e241f-119">Select **Voucher** to view the voucher entries for the TDS transaction.</span></span> <span data-ttu-id="e241f-120">Sélectionnez **Composants de retenue à la source** pour afficher le TDS qui a été calculé par composant de taxe TDS pour un code de taxe TDS spécifique.</span><span class="sxs-lookup"><span data-stu-id="e241f-120">Select **Withholding tax components** to view the TDS that was calculated per TDS tax component for a specific TDS tax code.</span></span>
7. <span data-ttu-id="e241f-121">Fermez la page **Paiements de retenue à la source** pour revenir à la page **Périodes de règlement de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="e241f-121">Close the **Withholding tax payments** page to return to the **Withholding tax settlement periods** page.</span></span>
8. <span data-ttu-id="e241f-122">Sélectionnez **Transactions de retenue à la source** pour afficher les détails des transactions TDS qui ont été réglées pour la période de règlement.</span><span class="sxs-lookup"><span data-stu-id="e241f-122">Select **Withholding tax transactions** to view the details of the TDS transactions that were settled for the settlement period.</span></span>
