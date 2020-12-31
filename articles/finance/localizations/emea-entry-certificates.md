---
title: Certificat d’entrée de l’UE
description: Cet article fournit des informations sur les certificats d’entrée dans l’Union européenne (UE).
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 11464
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 46a4180163adea72e7d8712ed5ce6a3306e477c5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4407979"
---
# <a name="eu-entry-certificates"></a><span data-ttu-id="af1d5-103">Certificat d’entrée dans l’UE</span><span class="sxs-lookup"><span data-stu-id="af1d5-103">EU entry certificates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="af1d5-104">Cet article fournit des informations sur les certificats d’entrée dans l’Union européenne (UE).</span><span class="sxs-lookup"><span data-stu-id="af1d5-104">This article provides information about European Union (EU) entry certificates.</span></span>

<span data-ttu-id="af1d5-105">Vous pouvez effectuer les tâches suivantes pour un certificat d’entrée de l’Union européenne (UE) :</span><span class="sxs-lookup"><span data-stu-id="af1d5-105">You can complete the following tasks for a European Union (EU) entry certificate:</span></span>

-   <span data-ttu-id="af1d5-106">Création et émission d’un certificat d’entrée de l’UE accompagné d’un bon de livraison ou une facture client pour la livraison d’articles ou de services aux pays/régions européens.</span><span class="sxs-lookup"><span data-stu-id="af1d5-106">Create and issue an EU entry certificate together with a packing slip or customer invoice for the delivery of items or services to EU countries/regions.</span></span>
-   <span data-ttu-id="af1d5-107">Acceptation du certificat d’entrée de l’Union européenne signé par un client de l’UE.</span><span class="sxs-lookup"><span data-stu-id="af1d5-107">Receive the EU entry certificate that is signed by an EU customer.</span></span>
-   <span data-ttu-id="af1d5-108">Téléchargement du certificat d’entrée de l’UE signé, reçu du client ou d’un tiers responsable de la livraison des articles au client.</span><span class="sxs-lookup"><span data-stu-id="af1d5-108">Upload the signed EU entry certificate that is received either from the customer or from a third party who is responsible for delivering items to the customer.</span></span>
-   <span data-ttu-id="af1d5-109">Association du certificat d’entrée de l’UE téléchargé avec une facture client.</span><span class="sxs-lookup"><span data-stu-id="af1d5-109">Associate the uploaded EU entry certificate with a customer invoice.</span></span>
-   <span data-ttu-id="af1d5-110">Mise à jour du statut du certificat d’entrée de l’UE téléchargé.</span><span class="sxs-lookup"><span data-stu-id="af1d5-110">Update the status of the uploaded EU entry certificate.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af1d5-111">Logiciels requis</span><span class="sxs-lookup"><span data-stu-id="af1d5-111">Prerequisites</span></span>
<span data-ttu-id="af1d5-112">Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="af1d5-112">The following table shows the prerequisites that must be in place before you start.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af1d5-113">Catégorie</span><span class="sxs-lookup"><span data-stu-id="af1d5-113">Category</span></span></th>
<th><span data-ttu-id="af1d5-114">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="af1d5-114">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="af1d5-115">Pays/Région</span><span class="sxs-lookup"><span data-stu-id="af1d5-115">Country/region</span></span></td>
<td><span data-ttu-id="af1d5-116">L’adresse principale de l’entité juridique doit être dans un pays membre de l’UE.</span><span class="sxs-lookup"><span data-stu-id="af1d5-116">The primary address of the legal entity must be in a EU member state.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="af1d5-117">Tâches associées de paramétrage</span><span class="sxs-lookup"><span data-stu-id="af1d5-117">Related set up tasks</span></span></td>
<td><ul>
<li><span data-ttu-id="af1d5-118">Dans la page <strong>Paramètres des ventes</strong>, sélectionnez les options <strong>Activer la gestion des certificats d’entrée</strong> et <strong>Activer l’émission de certificats d’entrée</strong>.</span><span class="sxs-lookup"><span data-stu-id="af1d5-118">On the <strong>Accounts receivable parameters</strong> page, select the <strong>Enable entry certificate management</strong> and <strong>Enable entry certificate issuing</strong> options.</span></span></li>
<li><span data-ttu-id="af1d5-119">Dans la page <strong>Clients</strong>, sous l’organisateur <strong>Facture et livraison</strong>, sélectionnez l’option <strong>Certificat d’entrée requis</strong> pour indiquer qu’un certificat d’entrée de l’UE est obligatoire pour le client.</span><span class="sxs-lookup"><span data-stu-id="af1d5-119">On the <strong>Customers</strong> page, on the <strong>Invoice and delivery</strong> FastTab, select the <strong>Entry certificate required</strong> option to indicate that an EU entry certificate is mandatory for the customer.</span></span> <span data-ttu-id="af1d5-120">Sélectionnez l’option <strong>Émettre un certificat d’entrée</strong> pour émettre un certificat d’entrée de l’UE de l’entité juridique pour le client.</span><span class="sxs-lookup"><span data-stu-id="af1d5-120">Select the <strong>Issue entry certificate</strong> option to issue an EU entry certificate of the legal entity to the customer.</span></span></li>
<li><span data-ttu-id="af1d5-121">Dans la page <strong>Paramètres des ventes</strong>, sélectionnez un code souche de numéros pour la référence du <strong>Certificat d’entrée</strong>.</span><span class="sxs-lookup"><span data-stu-id="af1d5-121">On the <strong>Accounts receivable parameters</strong> page, select a number sequence code for the <strong>Entry certificate</strong> reference.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="af1d5-122">Transactions liées</span><span class="sxs-lookup"><span data-stu-id="af1d5-122">Related transactions</span></span></td>
<td><ul>
<li><span data-ttu-id="af1d5-123">Créez un compte client.</span><span class="sxs-lookup"><span data-stu-id="af1d5-123">Create a customer account.</span></span></li>
<li><span data-ttu-id="af1d5-124">Créez une commande client.</span><span class="sxs-lookup"><span data-stu-id="af1d5-124">Create a sales order.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a><span data-ttu-id="af1d5-125">Création, enregistrement et téléchargement d’un certificat d’entrée de l’UE</span><span class="sxs-lookup"><span data-stu-id="af1d5-125">Creating, registering, and uploading an EU entry certificate</span></span>
<span data-ttu-id="af1d5-126">Vous pouvez créer un certificat d’entrée de l’UE automatiquement ou manuellement.</span><span class="sxs-lookup"><span data-stu-id="af1d5-126">You can create an EU entry certificate automatically or manually.</span></span> <span data-ttu-id="af1d5-127">Un certificat d’entrée de l’UE est créé et imprimé automatiquement lors de la validation d’un bon de livraison ou d’une facture pour un client à l’aide de la page **Validation du bon de livraison** ou la page **Validation de la facture**.</span><span class="sxs-lookup"><span data-stu-id="af1d5-127">An EU entry certificate is created and printed automatically when you post a packing slip or invoice for a customer by using the **Packing slip posting** page or the **Posting invoice** page.</span></span> <span data-ttu-id="af1d5-128">Pour créer manuellement ou réimprimer un certificat d’entrée de l’UE pour une facture client, utilisez la page **Journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="af1d5-128">To manually create or reprint an EU entry certificate for a customer invoice, use the **Invoice journal** page.</span></span> <span data-ttu-id="af1d5-129">En outre, vous pouvez utiliser la page **Journal des certificats d’entrée** pour entrer des détails sur un certificat d’entrée de l’UE émis par une tierce partie.</span><span class="sxs-lookup"><span data-stu-id="af1d5-129">Additionally, you can use the **Entry certificate journal** page to enter details about an EU entry certificate that is issued by a third party.</span></span>

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a><span data-ttu-id="af1d5-130">Création d’un certificat d’entrée de l’UE automatiquement ou manuellement</span><span class="sxs-lookup"><span data-stu-id="af1d5-130">Creating an EU entry certificate automatically or manually</span></span>

<span data-ttu-id="af1d5-131">Vous pouvez créer un certificat d’entrée de l’UE automatiquement à l’aide d’un bon de livraison dans la page **Toutes les commandes client** ou en utilisant une facture dans la page **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="af1d5-131">You can create an EU entry certificate automatically by using a packing slip on the **All sales orders** page or by using an invoice on the **Sales order** page.</span></span> <span data-ttu-id="af1d5-132">Pour créer manuellement un certificat d’entrée de l’UE, vous pouvez utiliser une facture dans la page **Journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="af1d5-132">To manually create an EU entry certificate, you can use an invoice on the **Invoice journal** page.</span></span> <span data-ttu-id="af1d5-133">Toutefois, vous devez modifier le statut de certification de la facture avant de créer manuellement un certificat d’entrée de l’UE.</span><span class="sxs-lookup"><span data-stu-id="af1d5-133">However, you must change the certification status of the invoice before you manually create an EU entry certificate.</span></span>

### <a name="registering-an-eu-entry-certificate"></a><span data-ttu-id="af1d5-134">Enregistrement d’un certificat d’entrée de l’UE</span><span class="sxs-lookup"><span data-stu-id="af1d5-134">Registering an EU entry certificate</span></span>

<span data-ttu-id="af1d5-135">Si un enregistrement est requis, vous pouvez utiliser la page **Journal des certificats d’entrée** pour enregistrer un certificat d’entrée de l’UE émis par une tierce partie.</span><span class="sxs-lookup"><span data-stu-id="af1d5-135">If registration is required, you can use the **Entry certificate journal** page to register an EU entry certificate that is issued by a third party.</span></span>

### <a name="uploading-a-received-eu-entry-certificate"></a><span data-ttu-id="af1d5-136">Chargement d’un certificat d’entrée de l’UE reçu</span><span class="sxs-lookup"><span data-stu-id="af1d5-136">Uploading a received EU entry certificate</span></span>

<span data-ttu-id="af1d5-137">Utilisez la page **Documents joints** pour télécharger un certificat d’entrée de l’UE reçu, signé par un client européen.</span><span class="sxs-lookup"><span data-stu-id="af1d5-137">Use the **Attachments** page to upload a received EU entry certificate that is signed by an EU customer.</span></span> <span data-ttu-id="af1d5-138">Une fois le certificat téléchargé, vous pouvez l’associer avec une facture comme pièce justificative de livraison des articles.</span><span class="sxs-lookup"><span data-stu-id="af1d5-138">After the certificate is uploaded, you can associate it with an invoice as proof that the items were delivered.</span></span> <span data-ttu-id="af1d5-139">Cette pièce est requise si vous devez délivrer une facture qui n’inclut pas la taxe sur la valeur ajoutée (TVA), elle est également utilisée lors de l’audit.</span><span class="sxs-lookup"><span data-stu-id="af1d5-139">This proof is required if you must issue an invoice that doesn't include value-added tax (VAT), and it's also used during auditing.</span></span>

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a><span data-ttu-id="af1d5-140">Facultatif : mise à jour du statut de certification et d’impression d’une facture</span><span class="sxs-lookup"><span data-stu-id="af1d5-140">Optional: Updating the certification status and printing status of an invoice</span></span>

<span data-ttu-id="af1d5-141">Vous pouvez mettre à jour le statut de certification et d’impression d’une facture client à l’aide de la page **Journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="af1d5-141">You can update the entry certification status and printing status of a customer invoice by using the **Invoice journal** page.</span></span>

## <a name="technical-information-for-system-administrators"></a><span data-ttu-id="af1d5-142">Informations destinées aux administrateurs système</span><span class="sxs-lookup"><span data-stu-id="af1d5-142">Technical information for system administrators</span></span>
<span data-ttu-id="af1d5-143">Si vous n’avez pas accès aux pages qui vous permettent d’effectuer cette tâche, contactez votre administrateur système et fournissez les informations répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="af1d5-143">If you don't have access to the pages that are used to complete this task, contact your system administrator, and provide the information that is shown in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af1d5-144">Catégorie</span><span class="sxs-lookup"><span data-stu-id="af1d5-144">Category</span></span></th>
<th><span data-ttu-id="af1d5-145">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="af1d5-145">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="af1d5-146">Rôles de sécurité et droits</span><span class="sxs-lookup"><span data-stu-id="af1d5-146">Security roles and duties</span></span></td>
<td><span data-ttu-id="af1d5-147">Pour paramétrer et créer des certificats d’entrée de l’UE pour des articles ou des services, vous devez être membre d’un rôle de sécurité qui inclut les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="af1d5-147">To set up and create EU entry certificates for items or services, you must be a member of a security role that includes the following duties:</span></span>
<ul>
<li><span data-ttu-id="af1d5-148"><strong>Commis à la comptabilité client</strong> (CustInvoiceAccountsReceivableClerk)</span><span class="sxs-lookup"><span data-stu-id="af1d5-148"><strong>Accounts receivable clerk</strong> (CustInvoiceAccountsReceivableClerk)</span></span></li>
<li><span data-ttu-id="af1d5-149"><strong>Conseiller du service clientèle</strong> (TradeCustomerServiceRepresentative)</span><span class="sxs-lookup"><span data-stu-id="af1d5-149"><strong>Customer service representative</strong> (TradeCustomerServiceRepresentative)</span></span></li>
<li><span data-ttu-id="af1d5-150"><strong>Commis aux ventes</strong> (TradeSalesClerk)</span><span class="sxs-lookup"><span data-stu-id="af1d5-150"><strong>Sales clerk</strong> (TradeSalesClerk)</span></span></li>
<li><span data-ttu-id="af1d5-151"><strong>Commis à l’expédition</strong> (InventShippingClerk)</span><span class="sxs-lookup"><span data-stu-id="af1d5-151"><strong>Shipping clerk</strong> (InventShippingClerk)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>





