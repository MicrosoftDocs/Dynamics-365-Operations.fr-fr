---
title: Pays d’origine
description: De nombreuses organisations délivrent des certificats à leurs fournisseurs pour garantir que les produits répondent à des normes de certification spécifiques. Ces certificats dépendent souvent du pays d’origine. Cette rubrique fournit des informations sur la fonction du pays d’origine, qui vous permet de lier un produit à son pays d’origine et de suivre ses certifications de produit.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0471785991a307de11147e9773d9abe1e02941d6
ms.sourcegitcommit: 97d4a9bd442fe20f90605d8154c3a947c7645b37
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2020
ms.locfileid: "3895546"
---
# <a name="country-of-origin"></a><span data-ttu-id="8db1d-105">Pays d’origine</span><span class="sxs-lookup"><span data-stu-id="8db1d-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="8db1d-106">De nombreuses organisations délivrent des certificats à leurs fournisseurs pour garantir que les produits répondent à des normes de certification spécifiques.</span><span class="sxs-lookup"><span data-stu-id="8db1d-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="8db1d-107">Ces certificats dépendent souvent du pays d’origine.</span><span class="sxs-lookup"><span data-stu-id="8db1d-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="8db1d-108">La fonction du pays d’origine vous permet de lier un produit à son pays d’origine et de suivre ses certifications de produit.</span><span class="sxs-lookup"><span data-stu-id="8db1d-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="turn-on-the-country-of-origin-feature"></a><span data-ttu-id="8db1d-109">Activer la fonction du pays d’origine</span><span class="sxs-lookup"><span data-stu-id="8db1d-109">Turn on the country of origin feature</span></span>

<span data-ttu-id="8db1d-110">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="8db1d-110">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="8db1d-111">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8db1d-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="8db1d-112">Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="8db1d-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="8db1d-113">**Module :** *Gestion des informations sur les produits*</span><span class="sxs-lookup"><span data-stu-id="8db1d-113">**Module:** *Product information management*</span></span>
- <span data-ttu-id="8db1d-114">**Nom de la fonctionnalité :** *Fonctionnalité de gestion du pays d’origine*</span><span class="sxs-lookup"><span data-stu-id="8db1d-114">**Feature name:** *Country of origin management feature*</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="8db1d-115">Configurer les pays source et de destination</span><span class="sxs-lookup"><span data-stu-id="8db1d-115">Configure source and destination countries</span></span>

<span data-ttu-id="8db1d-116">Avant d’émettre un certificat pour un produit, vous devez lier le produit à son pays de destination et à son pays d’origine.</span><span class="sxs-lookup"><span data-stu-id="8db1d-116">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="8db1d-117">Accédez à **Gestion des informations sur les produits \> Paramétrage \> Conformité des produits \> Pays d’origine \> Règles du pays d’origine**.</span><span class="sxs-lookup"><span data-stu-id="8db1d-117">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="8db1d-118">Sélectionnez une configuration de pays existante à modifier ou sélectionnez **Nouveau** dans le volet Actions pour créer une nouvelle configuration de pays.</span><span class="sxs-lookup"><span data-stu-id="8db1d-118">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="8db1d-119">Définissez les valeurs suivantes pour le pays sélectionné ou le nouveau pays.</span><span class="sxs-lookup"><span data-stu-id="8db1d-119">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="8db1d-120">Champ</span><span class="sxs-lookup"><span data-stu-id="8db1d-120">Field</span></span> | <span data-ttu-id="8db1d-121">Description</span><span class="sxs-lookup"><span data-stu-id="8db1d-121">Description</span></span> |
    |---|---|
    | <span data-ttu-id="8db1d-122">numéro d’article</span><span class="sxs-lookup"><span data-stu-id="8db1d-122">Item number</span></span> | <span data-ttu-id="8db1d-123">Permet de sélectionner le numéro d’article du produit.</span><span class="sxs-lookup"><span data-stu-id="8db1d-123">Select the item number of the product.</span></span> |
    | <span data-ttu-id="8db1d-124">Pays de destination</span><span class="sxs-lookup"><span data-stu-id="8db1d-124">Destination country</span></span> | <span data-ttu-id="8db1d-125">Sélectionnez le pays vers lequel vous envoyez le produit.</span><span class="sxs-lookup"><span data-stu-id="8db1d-125">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="8db1d-126">Pays d’origine</span><span class="sxs-lookup"><span data-stu-id="8db1d-126">Origin country</span></span> | <span data-ttu-id="8db1d-127">Sélectionnez le pays à partir duquel vous expédiez le produit.</span><span class="sxs-lookup"><span data-stu-id="8db1d-127">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="8db1d-128">Le but de cette configuration est de vous aider à générer un rapport de nomenclature (BOM) dans lequel vous pouvez inclure le pays d’origine de chaque pièce pour laquelle les pays d’origine et de destination sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="8db1d-128">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="8db1d-129">Ce rapport vous permet d’obtenir une image globale de l’origine de vos pièces et de leur destination.</span><span class="sxs-lookup"><span data-stu-id="8db1d-129">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="8db1d-130">Garder la trace des certificats des fournisseurs</span><span class="sxs-lookup"><span data-stu-id="8db1d-130">Keep track of vendor certificates</span></span>

<span data-ttu-id="8db1d-131">Vous pouvez utiliser la page **Certificats de fournisseur du pays d’origine** pour garder une trace des certificats que vous délivrez aux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="8db1d-131">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="8db1d-132">Vous devez décider quels documents de certificat vous émettrez et comment vous les transmettrez aux clients.</span><span class="sxs-lookup"><span data-stu-id="8db1d-132">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="8db1d-133">Cette fonctionnalité vous aide à garder une trace de vos certificats.</span><span class="sxs-lookup"><span data-stu-id="8db1d-133">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="8db1d-134">Elle vous permet également de choisir si les numéros de certificat pertinents apparaissent sur les factures, les bons de livraison et/ou les confirmations de commande.</span><span class="sxs-lookup"><span data-stu-id="8db1d-134">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="8db1d-135">Pour paramétrer des informations de certificat, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8db1d-135">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="8db1d-136">Accédez à **Gestion des informations sur les produits \> Paramétrage \> Conformité des produits \> Pays d’origine \> Certificats fournisseur du pays d’origine**.</span><span class="sxs-lookup"><span data-stu-id="8db1d-136">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="8db1d-137">Sélectionnez une configuration de certificat existante à modifier ou sélectionnez **Nouveau** dans le volet Actions pour créer une nouvelle configuration de certificat.</span><span class="sxs-lookup"><span data-stu-id="8db1d-137">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="8db1d-138">Définissez les paramètres suivants pour le certificat sélectionné ou le nouveau certificat.</span><span class="sxs-lookup"><span data-stu-id="8db1d-138">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="8db1d-139">Champ</span><span class="sxs-lookup"><span data-stu-id="8db1d-139">Field</span></span> | <span data-ttu-id="8db1d-140">Description</span><span class="sxs-lookup"><span data-stu-id="8db1d-140">Description</span></span> |
    |---|---|
    | <span data-ttu-id="8db1d-141">Compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="8db1d-141">Vendor account</span></span> | <span data-ttu-id="8db1d-142">Sélectionnez le fournisseur pour lequel vous avez émis le certificat.</span><span class="sxs-lookup"><span data-stu-id="8db1d-142">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="8db1d-143">numéro d’article</span><span class="sxs-lookup"><span data-stu-id="8db1d-143">Item number</span></span> | <span data-ttu-id="8db1d-144">Sélectionnez l’article pour lequel vous avez émis le certificat.</span><span class="sxs-lookup"><span data-stu-id="8db1d-144">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="8db1d-145">Pays/région</span><span class="sxs-lookup"><span data-stu-id="8db1d-145">Country/region</span></span> | <span data-ttu-id="8db1d-146">Le pays ou la région de destination où vous devez utiliser ce certificat.</span><span class="sxs-lookup"><span data-stu-id="8db1d-146">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="8db1d-147">Numéro de certificat</span><span class="sxs-lookup"><span data-stu-id="8db1d-147">Certificate number</span></span> | <span data-ttu-id="8db1d-148">Saisissez le numéro d’identification du certificat que vous avez émis.</span><span class="sxs-lookup"><span data-stu-id="8db1d-148">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="8db1d-149">Effective</span><span class="sxs-lookup"><span data-stu-id="8db1d-149">Effective</span></span> | <span data-ttu-id="8db1d-150">Sélectionnez la date de début de validité du certificat.</span><span class="sxs-lookup"><span data-stu-id="8db1d-150">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="8db1d-151">Expiration</span><span class="sxs-lookup"><span data-stu-id="8db1d-151">Expiration</span></span> | <span data-ttu-id="8db1d-152">Sélectionnez la date de fin de validité du certificat.</span><span class="sxs-lookup"><span data-stu-id="8db1d-152">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="8db1d-153">Imprimer sur la facture</span><span class="sxs-lookup"><span data-stu-id="8db1d-153">Print on invoice</span></span> | <span data-ttu-id="8db1d-154">Cochez cette case pour imprimer le numéro de certificat sur les factures adressées au pays spécifié pendant la plage de dates spécifiée.</span><span class="sxs-lookup"><span data-stu-id="8db1d-154">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="8db1d-155">Imprimer sur le bon de livraison</span><span class="sxs-lookup"><span data-stu-id="8db1d-155">Print on packing slip</span></span> | <span data-ttu-id="8db1d-156">Cochez cette case pour imprimer le numéro de certificat sur les bons de livraison adressés au pays spécifié pendant la plage de dates spécifiée.</span><span class="sxs-lookup"><span data-stu-id="8db1d-156">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="8db1d-157">Imprimer sur la commande client</span><span class="sxs-lookup"><span data-stu-id="8db1d-157">Print on sales order</span></span> | <span data-ttu-id="8db1d-158">Cochez cette case pour imprimer le numéro de certificat sur les commandes client adressées au pays spécifié pendant la plage de dates spécifiée.</span><span class="sxs-lookup"><span data-stu-id="8db1d-158">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="8db1d-159">Inclure le pays d’origine dans les rapports de nomenclature</span><span class="sxs-lookup"><span data-stu-id="8db1d-159">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="8db1d-160">Lorsque vous générez un rapport de nomenclature, vous pouvez inclure le pays d’origine de chaque pièce pour laquelle vous avez spécifié les pays d’origine et de destination dans la page **Règles du pays d’origine**.</span><span class="sxs-lookup"><span data-stu-id="8db1d-160">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="8db1d-161">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="8db1d-161">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="8db1d-162">Sélectionnez ou créez un produit pour ouvrir sa page **Détails des produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="8db1d-162">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="8db1d-163">Dans le volet Actions, sous l’onglet **Ingénieur**, dans le groupe **Nomenclature**, sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="8db1d-163">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="8db1d-164">Sur la page qui s’affiche, dans le volet Actions,, sélectionnez **Nomenclature \> Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="8db1d-164">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="8db1d-165">Dans la boîte de dialogue **Lignes de nomenclature**, définissez le champ **Pays de destination** comme le pays de destination que vous souhaitez afficher sur votre rapport.</span><span class="sxs-lookup"><span data-stu-id="8db1d-165">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="8db1d-166">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8db1d-166">Select **OK**.</span></span>

<span data-ttu-id="8db1d-167">Un rapport contenant des informations sur le pays d’origine de chaque pièce est généré et affiché.</span><span class="sxs-lookup"><span data-stu-id="8db1d-167">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="8db1d-168">Voici un exemple de rapport.</span><span class="sxs-lookup"><span data-stu-id="8db1d-168">Here is an example of the report.</span></span>

<span data-ttu-id="8db1d-169">![Rapport de pays d’origine](media/country-of-origin-report.png "Rapport de pays d’origine")</span><span class="sxs-lookup"><span data-stu-id="8db1d-169">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
