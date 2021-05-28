---
title: Mettre à jour les numéros et les dates de certificat pour les transactions TDS
description: Cette rubrique explique comment mettre à jour les numéros de certificats récupérables et les dates enregistrés pour les comptes fournisseur, client et compte général pour la taxe déduite à la source (TDS).
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
ms.openlocfilehash: 248de8e12703a84482b67d0899857a6efb33531c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023234"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a><span data-ttu-id="2696d-103">Mettre à jour les numéros et les dates de certificat pour les transactions TDS</span><span class="sxs-lookup"><span data-stu-id="2696d-103">Update certificate numbers and dates for TDS transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2696d-104">Cette rubrique explique comment mettre à jour les numéros de certificats récupérables et les dates enregistrés pour les comptes fournisseur, client et compte général pour la taxe déduite à la source (TDS).</span><span class="sxs-lookup"><span data-stu-id="2696d-104">This topic explains how to update the recoverable certificate numbers and dates that were recorded for vendor, customer, and ledger accounts for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="2696d-105">Vous pouvez afficher les certificats des transactions TDS sur la page **Certificats récupérables**.</span><span class="sxs-lookup"><span data-stu-id="2696d-105">You can view the certificates for TDS transactions on the **Recoverable certificates** page.</span></span> <span data-ttu-id="2696d-106">Vous pouvez mettre à jour les certificats en utilisant la page **Mettre à jour les certificats**.</span><span class="sxs-lookup"><span data-stu-id="2696d-106">You can update the certificates by using the **Update Certificates** page.</span></span>

<span data-ttu-id="2696d-107">Suivez ces étapes pour mettre à jour les numéros et les dates des transactions TDS.</span><span class="sxs-lookup"><span data-stu-id="2696d-107">Follow these steps to update certificate numbers and dates for TDS transactions.</span></span>

1. <span data-ttu-id="2696d-108">Accédez à **Taxe \> Déclarations \> Retenue à la source \> Mettre à jour le certificat**.</span><span class="sxs-lookup"><span data-stu-id="2696d-108">Go to **Tax \> Declarations \> Withholding tax \> Update certificate**.</span></span>

    <span data-ttu-id="2696d-109">[![Mettre à jour la page du certificat](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span><span class="sxs-lookup"><span data-stu-id="2696d-109">[![Update certificate page](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span></span>

2. <span data-ttu-id="2696d-110">Sur la page **Mettre à jour le certificat**, dans la section **Sélectionner**, dans le champ **Type de taxe**, sélectionnez **TDS**.</span><span class="sxs-lookup"><span data-stu-id="2696d-110">On the **Update certificate** page, in the **Select** section, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="2696d-111">Dans le champ **Numéro de certificat**, sélectionnez le numéro de certificat TDS du client ou du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2696d-111">In the **Certificate number** field, select the customer's or vendor's TDS certificate number.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2696d-112">Le champ **Numéro de certificat** répertorie uniquement les numéros de certificat TDS que la case à cocher **Fermé** est désactivée sur la page **Certificats récupérables**.</span><span class="sxs-lookup"><span data-stu-id="2696d-112">The **Certificate number** field lists only TDS certificate numbers that the **Closed** check box is cleared for on the **Recoverable certificates** page.</span></span>

    <span data-ttu-id="2696d-113">Le champ **Date du certificat** affiche la date du certificat.</span><span class="sxs-lookup"><span data-stu-id="2696d-113">The **Certificate date** field shows the certificate date.</span></span> <span data-ttu-id="2696d-114">Le champ **Type de compte** indique le type de compte pour lequel le numéro de certificat TDS est reçu et le champ **Nom** affiche le nom du compte.</span><span class="sxs-lookup"><span data-stu-id="2696d-114">The **Account type** field shows the type of account that the TDS certificate number is received for, and the **Name** field shows the name of the account.</span></span>

5. <span data-ttu-id="2696d-115">Dans les champs **Date de début** et **Date de fin**, entrez les dates de début et de fin de la période pour lesquelles afficher les transactions TDS.</span><span class="sxs-lookup"><span data-stu-id="2696d-115">In the **From date** and **To date** fields, select the start and end dates of the period to show the TDS transactions for.</span></span>
6. <span data-ttu-id="2696d-116">Sélectionnez **Afficher les données** pour afficher les transactions TDS qui ont été validées pendant la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2696d-116">Select **Show data** to view the TDS transactions that were posted during the selected period.</span></span>

    <span data-ttu-id="2696d-117">Dans l'onglet **Aperçu**, la grille du volet supérieur affiche les informations suivantes sur chaque transaction TDS qui a été validée pour le fournisseur ou le client au cours de la période sélectionnée :</span><span class="sxs-lookup"><span data-stu-id="2696d-117">On the **Overview** tab, the grid in the upper pane shows the following information about each TDS transaction that was posted for the vendor or customer during the selected period:</span></span>

    - <span data-ttu-id="2696d-118">**Justificatif** – Numéro de document de la transaction TDS.</span><span class="sxs-lookup"><span data-stu-id="2696d-118">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="2696d-119">**Date** – Date de la transaction TDS.</span><span class="sxs-lookup"><span data-stu-id="2696d-119">**Date** – The date of the TDS transaction.</span></span>
    - <span data-ttu-id="2696d-120">**Montant** – Le montant de la facture à partir duquel la transaction TDS a été calculée.</span><span class="sxs-lookup"><span data-stu-id="2696d-120">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="2696d-121">**Montant de la taxe** – Le montant de la taxe TDS qui a été calculé pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="2696d-121">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>

7. <span data-ttu-id="2696d-122">Pour déplacer des transactions TDS spécifiques de la grille supérieure vers la grille inférieure, sélectionnez les transactions, puis sélectionnez **Inclure**.</span><span class="sxs-lookup"><span data-stu-id="2696d-122">To move specific TDS transactions from the upper grid to the lower grid, select the transactions, and then select **Include**.</span></span> <span data-ttu-id="2696d-123">Sinon, sélectionnez **Tout inclure** pour déplacer toutes les transactions TDS de la grille supérieure vers la grille inférieure.</span><span class="sxs-lookup"><span data-stu-id="2696d-123">Alternatively, select **Include all** to move all TDS transactions from the upper grid to the lower grid.</span></span>

    <span data-ttu-id="2696d-124">Pour déplacer des transactions TDS spécifiques ou toutes les transactions TDS de la grille inférieure vers la grille supérieure, utilisez le bouton **Exclure** ou **Tout exclure**.</span><span class="sxs-lookup"><span data-stu-id="2696d-124">To move specific TDS transactions or all TDS transactions from the lower grid to the upper grid, use the **Exclude** or **Exclude all** button.</span></span>

8. <span data-ttu-id="2696d-125">Sélectionnez **Mettre à jour** pour mettre à jour les champs **Numéro de certificat** et **Date du certificat** pour les transactions TDS dans la grille inférieure.</span><span class="sxs-lookup"><span data-stu-id="2696d-125">Select **Update** to update the **Certificate number** and **Certificate date** fields for TDS transactions in the lower grid.</span></span>
10. <span data-ttu-id="2696d-126">Accédez à **Impôt \> Impôts indirects \> Retenue à la source \> Certificat récupérable** et sélectionnez **Enquête** pour afficher les lignes de transaction mises à jour qui ont les nouveaux numéros de certificat sur la page **Transactions de certificat**.</span><span class="sxs-lookup"><span data-stu-id="2696d-126">Go to **Tax \> Indirect taxes \> Withholding tax \> Recoverable certificate**, and select **Inquiry** to view the updated transaction lines that have the new certificate numbers on the **Certificate transactions** page.</span></span>

    <span data-ttu-id="2696d-127">[![Page Transactions de certificat](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span><span class="sxs-lookup"><span data-stu-id="2696d-127">[![Certificate transactions page](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span></span>
