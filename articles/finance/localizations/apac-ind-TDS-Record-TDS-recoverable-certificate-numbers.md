---
title: Enregistrer les numéros de certificat récupérables
description: Cette rubrique explique comment utiliser la page Certificats récupérables pour enregistrer les numéros de certificat et les dates des certificats TDS (Tax Deduced at Source) reçus pour un fournisseur, un client ou un compte général spécifique.
author: kailiang
mms.date: 02/12/2021
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
ms.openlocfilehash: b501c331cccc6d030f36d0a13ba0a6a13c08c733
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023224"
---
# <a name="record-tds-recoverable-certificate-numbers"></a><span data-ttu-id="a7345-103">Enregistrer les numéros de certificat récupérables</span><span class="sxs-lookup"><span data-stu-id="a7345-103">Record TDS recoverable certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7345-104">Cette rubrique explique comment utiliser la page **Certificats récupérables** pour enregistrer les numéros de certificat et les dates des certificats TDS (Tax Deduced at Source) reçus pour un fournisseur, un client ou un compte général spécifique.</span><span class="sxs-lookup"><span data-stu-id="a7345-104">This topic explains how to use the **Recoverable certificates** page to record the certificate numbers and dates for Tax Deducted at Source (TDS) certificates that are received for a specific vendor, customer, or ledger.</span></span> <span data-ttu-id="a7345-105">Pour mettre à jour les numéros et dates de certificat TDS enregistrés pour les transactions TDS sur cette page, utilisez la page **Mettre à jour le certificat** (**Comptabilité \> Périodique \> Retenue à la source \> Mettre à jour le certificat**).</span><span class="sxs-lookup"><span data-stu-id="a7345-105">To update the TDS certificate numbers and dates that are recorded for TDS transactions on this page, use the **Update certificate** page (**General ledger \> Periodic \> Withholding tax \> Update certificate**).</span></span> <span data-ttu-id="a7345-106">Une fois la mise à jour des numéros de certificat TDS terminée, fermez-les.</span><span class="sxs-lookup"><span data-stu-id="a7345-106">After you've finished updating TDS certificate numbers, close them.</span></span>

<span data-ttu-id="a7345-107">Suivez ces étapes pour enregistrer les numéros et les dates des certificats TDS.</span><span class="sxs-lookup"><span data-stu-id="a7345-107">Follow these steps to record the TDS certificate numbers and dates.</span></span>

1. <span data-ttu-id="a7345-108">Accédez à **Taxe \> > Taxes indirectes \> Retenue à la source \> Certificats récupérables**.</span><span class="sxs-lookup"><span data-stu-id="a7345-108">Go to **Tax \> Indirect tax \> Withholding tax \> Recoverable certificates**.</span></span>

    <span data-ttu-id="a7345-109">[![Page des certificats récupérables](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span><span class="sxs-lookup"><span data-stu-id="a7345-109">[![Recoverable certificates page](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span></span> 

2. <span data-ttu-id="a7345-110">Sur la page **Certificats récupérables**, dans le champ **Type de taxe**, sélectionnez **TDS**.</span><span class="sxs-lookup"><span data-stu-id="a7345-110">On the **Recoverable certificates** page, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="a7345-111">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="a7345-111">Select **New** to create a record.</span></span>
4. <span data-ttu-id="a7345-112">Dans le champ **Numéro de certificat**, entrez le numéro de certificat TDS.</span><span class="sxs-lookup"><span data-stu-id="a7345-112">In the **Certificate number** field, enter the TDS certificate number.</span></span>
5. <span data-ttu-id="a7345-113">Dans le cham p **Type de compte**, sélectionnez le type de compte pour lequel le certificat TDS est reçu : **Fournisseur**, **Client** ou **Registre**.</span><span class="sxs-lookup"><span data-stu-id="a7345-113">In the **Account type** field, select the type of account that the TDS certificate is received for: **Vendor**, **Customer**, or **Ledger**.</span></span>
6. <span data-ttu-id="a7345-114">Dans le champ **Compte**, sélectionnez le numéro de compte fournisseur, compte client ou compte général, selon le type de compte que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a7345-114">In the **Account** field, select the vendor, customer, or ledger account number, depending on the account type that you selected.</span></span> <span data-ttu-id="a7345-115">Le champ **Nom** affiche le nom du fournisseur, du client ou du compte général.</span><span class="sxs-lookup"><span data-stu-id="a7345-115">The **Name** field shows the name of the vendor, customer, or ledger account.</span></span>
7. <span data-ttu-id="a7345-116">Dans le champ **Montant du certificat**, entrez le montant du certificat TDS.</span><span class="sxs-lookup"><span data-stu-id="a7345-116">In the **Certificate amount** field, enter the amount of the TDS certificate.</span></span>
8. <span data-ttu-id="a7345-117">Dans le champ **Date**, saisissez la date du certificat pour le numéro de certificat.</span><span class="sxs-lookup"><span data-stu-id="a7345-117">In the **Date** field, enter the certificate date for the certificate number.</span></span>
9. <span data-ttu-id="a7345-118">Sélectionnez **Demandes de renseignements** pour ouvrir la page **Transactions de certificat**, dans laquelle vous pouvez afficher les transactions TDS pour lesquelles le numéro et la date du certificat TDS sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="a7345-118">Select **Inquiries** to open the **Certificate transactions** page, where you can view the TDS transactions that the TDS certificate number and date are updated for.</span></span> <span data-ttu-id="a7345-119">Ces informations peuvent être mises à jour sur la page **Mettre à jour le certificat** (**Impôt \> Déclarations \> Retenue d'impôt \> Mettre à jour le certificat**).</span><span class="sxs-lookup"><span data-stu-id="a7345-119">This information can be updated on the **Update certificate** page (**Tax \> Declarations \> Withholding tax \> Update certificate**).</span></span>

    <span data-ttu-id="a7345-120">La page **Mettre à jour le certificat** affiche les informations suivantes pour chaque transaction TDS :</span><span class="sxs-lookup"><span data-stu-id="a7345-120">The **Update certificate** page shows the following information for each TDS transaction:</span></span>

    - <span data-ttu-id="a7345-121">**Date** – Date de validation de la transaction TDS.</span><span class="sxs-lookup"><span data-stu-id="a7345-121">**Date** – The posting date of the TDS transaction.</span></span>
    - <span data-ttu-id="a7345-122">**Justificatif** – Numéro de document de la transaction TDS.</span><span class="sxs-lookup"><span data-stu-id="a7345-122">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="a7345-123">**Source** - Le module dans lequel la transaction TDS a été créée.</span><span class="sxs-lookup"><span data-stu-id="a7345-123">**Source** – The module that the TDS transaction was created in.</span></span>
    - <span data-ttu-id="a7345-124">**Compte** - Le numéro de compte fournisseur, compte client ou compte général pour lequel la transaction TDS a été créée.</span><span class="sxs-lookup"><span data-stu-id="a7345-124">**Account** – The vendor, customer, or ledger account number that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="a7345-125">**Nom** - Le nom du compte fournisseur, compte client ou compte général pour lequel la transaction TDS a été créée.</span><span class="sxs-lookup"><span data-stu-id="a7345-125">**Name** – The name of the vendor, customer, or ledger account that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="a7345-126">**Montant** – Le montant de la facture à partir duquel la transaction TDS a été calculée.</span><span class="sxs-lookup"><span data-stu-id="a7345-126">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="a7345-127">**Montant de la taxe** – Le montant de la taxe TDS qui a été calculé pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="a7345-127">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>
    - <span data-ttu-id="a7345-128">**Date du certificat** - La date du certificat TDS qui a été mise à jour pour la transaction TDS.</span><span class="sxs-lookup"><span data-stu-id="a7345-128">**Certificate date** – The TDS certificate date that was updated for the TDS transaction.</span></span>
    - <span data-ttu-id="a7345-129">**Numéro du certificat** - Le numéro du certificat TDS qui a été mis à jour pour la transaction TDS.</span><span class="sxs-lookup"><span data-stu-id="a7345-129">**Certificate number** – TDS certificate number that was updated for the TDS transaction.</span></span>

10. <span data-ttu-id="a7345-130">Sur la page **Certificats récupérables**, sélectionnez la case à cocher **Fermé** pour fermer le numéro de certificat TDS une fois que vous avez fini de le mettre à jour pour les transactions TDS sur la page **Mettre à jour le certificat**.</span><span class="sxs-lookup"><span data-stu-id="a7345-130">On the **Recoverable certificates** page, select the **Closed** check box to close the TDS certificate number after you've finished updating it for TDS transactions on the **Update certificate** page.</span></span>

    <span data-ttu-id="a7345-131">Pour cocher la case **Fermé** pour tous les enregistrements de la page, sélectionnez **Marquer tout**.</span><span class="sxs-lookup"><span data-stu-id="a7345-131">To select the **Closed** check box for all records on the page, select **Mark all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a7345-132">Les numéros de certificat TDS pour lesquels la case à cocher **Fermé** est cochée pour cause de non-disponibilité sur la page **Mettre à jour le certificat**.</span><span class="sxs-lookup"><span data-stu-id="a7345-132">TDS certificate numbers that the **Closed** check box is selected for aren't available on the **Update certificate** page.</span></span>
