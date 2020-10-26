---
title: Canada GST/GIFT (HST Internet File Transfer)
description: Cet article décrit la configuration et utiliser la fonctionnalité de transfert de fichiers via Internet Canada GST/GIFT (HST Internet File Transfer).
author: ericwang
manager: Ann Beebe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GST/HST, GIFT
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Canada
ms.author: kfend
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 8c3a60449e202b270ed0ee77b620320d58f98cce
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981883"
---
# <a name="canada-gsthst-internet-file-transfer"></a><span data-ttu-id="fca76-103">Canada GST/GIFT (HST Internet File Transfer)</span><span class="sxs-lookup"><span data-stu-id="fca76-103">Canada GST/HST Internet File Transfer</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fca76-104">Les contribuables canadiens utilisent le formulaire GST 34 pour remplir manuellement les déclarations fiscales sur les biens et services ou de taxe harmonisée (GST/HST) et pour effectuer les paiements auprès de l'Agence du revenu du Canada (ARC).</span><span class="sxs-lookup"><span data-stu-id="fca76-104">Taxpayers in Canada use form GST 34 to manually file Goods and Services Tax or Harmonized Sales Tax (GST/HST) returns and to remit payments to the Canada Revenue Agency (CRA).</span></span> <span data-ttu-id="fca76-105">Toutefois, cette dernière leur permet de remplir les déclarations et de verser les taxes calculées sur les immobilisations acquises par voie électronique.</span><span class="sxs-lookup"><span data-stu-id="fca76-105">However, the CRA allows taxpayers to file and remit taxes calculated on acquired fixed assets electronically.</span></span> <span data-ttu-id="fca76-106">Vous pouvez remplir les déclarations GST/HST par voie électronique à l'aide de l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="fca76-106">You can file GST/HST returns electronically using any of the following methods:</span></span>

  - <span data-ttu-id="fca76-107">transfert de fichiers via Internet : service Web de déclaration qui permet aux contribuables de remplir leurs déclarations directement via Internet ;</span><span class="sxs-lookup"><span data-stu-id="fca76-107">Net file transfer – An Internet-based filing service that allows taxpayers to file their returns directly over the Internet.</span></span>

  - <span data-ttu-id="fca76-108">échange de données informatisé (EDI) : méthode de transfert de données qui permet aux contribuables de remplir leurs déclarations directement auprès de l'ARC ou d'un fournisseur de services tiers ;</span><span class="sxs-lookup"><span data-stu-id="fca76-108">Electronic Data Interchange (EDI) – A data transfer method that taxpayers can use to file their returns directly with the CRA or through a third-party service provider.</span></span>

  - <span data-ttu-id="fca76-109">GST/HST Internet File Transfer (GIFT) : outil de téléchargement qui permet d'envoyer des fichiers texte au site Web de l'ARC à des fins de déclarations GST/HST et de règlement des paiements.</span><span class="sxs-lookup"><span data-stu-id="fca76-109">GST/HST Internet File Transfer (GIFT) – An uploading tool used to submit text files to the CRA website for filing GST/HST returns and remitting payments.</span></span>

<span data-ttu-id="fca76-110">Avant de générer un fichier GIFT, vous devez configurer le code identification du logiciel, le code taxe et le groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="fca76-110">Before you generate a GIFT file, you should set up your software identification code, sales tax code, and sales tax group.</span></span> 

<span data-ttu-id="fca76-111">Les procédures suivantes permettent d'entrer des informations sur l'entité juridique, le code taxe et les groupes de taxe pour GIFT, ainsi que de créer des entrées de taxe pour les taxes sur l'acquisition.</span><span class="sxs-lookup"><span data-stu-id="fca76-111">Use the following procedures to enter legal entity details, sales tax code, and sales tax group for GIFT, and to create sales tax entries for taxes paid on acquisition.</span></span>

## <a name="set-up-legal-entities-for-gift"></a><span data-ttu-id="fca76-112">Paramétrage d'entités juridiques pour GIFT</span><span class="sxs-lookup"><span data-stu-id="fca76-112">Set up legal entities for GIFT</span></span>

<span data-ttu-id="fca76-113">Lorsque vous envoyez une requête de transfert de fichiers via Internet à l'ARC, celle-ci fournit un code identification du logiciel,</span><span class="sxs-lookup"><span data-stu-id="fca76-113">When you submit a request to CRA to perform an Internet file transfer, CRA provides a software identification code.</span></span> <span data-ttu-id="fca76-114">composé de deux caractères alphabétiques et de six caractères numériques.</span><span class="sxs-lookup"><span data-stu-id="fca76-114">The first two characters are alphabetical and the last six characters are numerical.</span></span> <span data-ttu-id="fca76-115">Vous devez entrer correctement ce code identification dans l'écran **Entités juridiques** pour traiter vos déclarations.</span><span class="sxs-lookup"><span data-stu-id="fca76-115">You must enter this identification code in the **Legal entities** form correctly to process your returns.</span></span>

1.  <span data-ttu-id="fca76-116">Cliquez sur **Administration d'organisation** \> **Paramétrage** \> **Organisation** \> **Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="fca76-116">Click **Organization administration** \> **Setup** \> **Organization** \> **Legal entities**.</span></span>

2.  <span data-ttu-id="fca76-117">Cliquez sur l'organisateur **Génération d'état statutaire**, puis dans le champ **Numéro d'enregistrement**, entrez le numéro d'enregistrement fourni par l'ARC lors de votre enregistrement à des fins de déclaration GST/HST.</span><span class="sxs-lookup"><span data-stu-id="fca76-117">Click the **Statutory reporting** FastTab, and in the **Registration number** field, enter the registration number that the CRA provided to you when you registered for GST/HST.</span></span>

3.  <span data-ttu-id="fca76-118">Dans le champ **Code identification du logiciel**, entrez AX030003 pour transférer les déclarations.</span><span class="sxs-lookup"><span data-stu-id="fca76-118">In the **Software identification code** field, enter AX030003 to transfer the returns.</span></span>

4.  <span data-ttu-id="fca76-119">Cliquez sur **Identificateurs du compte** pour ouvrir l'écran **Identificateurs du compte**.</span><span class="sxs-lookup"><span data-stu-id="fca76-119">Click **Account identifiers** to open the **Account identifiers** form.</span></span>

5.  <span data-ttu-id="fca76-120">Sous l'onglet **Vue d'ensemble**, dans le champ **Identificateur du programme**, sélectionnez **GST/HST**.</span><span class="sxs-lookup"><span data-stu-id="fca76-120">On the **Overview** tab, in the **Program identifier** field, select **GST/HST**.</span></span>

6.  <span data-ttu-id="fca76-121">Dans le champ **Numéro de référence**, entrez le numéro de référence fourni par l'ARC.</span><span class="sxs-lookup"><span data-stu-id="fca76-121">In the **Reference number** field, enter the reference number provided by the CRA.</span></span>

7.  <span data-ttu-id="fca76-122">Fermez les écrans pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="fca76-122">Close the forms to save your changes.</span></span>

## <a name="set-up-tax-codes-for-gift"></a><span data-ttu-id="fca76-123">Définition des codes taxe pour GIFT</span><span class="sxs-lookup"><span data-stu-id="fca76-123">Set up tax codes for GIFT</span></span>

<span data-ttu-id="fca76-124">L'écran **Codes taxe** permet de définir des codes taxe pour calculer le montant des taxes GST/HST pour le fichier GIFT.</span><span class="sxs-lookup"><span data-stu-id="fca76-124">Use the **Sales tax codes** form to set up tax codes to calculate GST/HST for the GIFT file.</span></span>

1.  <span data-ttu-id="fca76-125">Cliquez sur **Comptabilité** \> **Paramétrage** \> **Taxe** \> **Codes de taxe**.</span><span class="sxs-lookup"><span data-stu-id="fca76-125">Click **General ledger** \> **Setup** \> **Sales tax** \> **Sales tax codes**.</span></span>

2.  <span data-ttu-id="fca76-126">Appuyez sur Ctrl+N pour créer un code taxe.</span><span class="sxs-lookup"><span data-stu-id="fca76-126">Press CTRL+N to create a new tax code.</span></span>

3.  <span data-ttu-id="fca76-127">Dans le champ **Code de taxe**, entrez un code, tel que GST/HST, puis entrez des informations générales sur le code taxe.</span><span class="sxs-lookup"><span data-stu-id="fca76-127">In the **Sales tax code** field, enter a code, such as GST/HST, and then enter general information about the sales tax code.</span></span>

4.  <span data-ttu-id="fca76-128">Cliquez sur l'onglet **Calcul** et entrez les détails du calcul du montant des taxes GST/HST.</span><span class="sxs-lookup"><span data-stu-id="fca76-128">Click the **Calculation** tab and enter the calculation details to calculate the GST/HST amount.</span></span>

5.  <span data-ttu-id="fca76-129">Cliquez sur **Valeurs** pour ouvrir l'écran **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="fca76-129">Click **Values** to open the **Values** form.</span></span> <span data-ttu-id="fca76-130">Entrez les dates auxquelles le code taxe prend effet.</span><span class="sxs-lookup"><span data-stu-id="fca76-130">Enter the dates during which the tax code is in effect.</span></span>

6.  <span data-ttu-id="fca76-131">Dans le champ **Valeur**, entrez le pourcentage utilisé pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="fca76-131">In the **Value** field, enter the percentage for the calculation.</span></span>

7.  <span data-ttu-id="fca76-132">Fermez les écrans pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="fca76-132">Close the forms to save your changes.</span></span>

## <a name="set-up-tax-groups-for-gift"></a><span data-ttu-id="fca76-133">Paramétrage des groupes de taxe pour GIFT</span><span class="sxs-lookup"><span data-stu-id="fca76-133">Set up tax groups for GIFT</span></span>

<span data-ttu-id="fca76-134">Utilisez l'écran **Groupes de taxe** pour configurer les groupes de taxe.</span><span class="sxs-lookup"><span data-stu-id="fca76-134">Use the **Sales tax groups** form to set up sales tax groups.</span></span> <span data-ttu-id="fca76-135">Vous pouvez affecter des groupes de taxe à des sociétés et les taxes sont calculées en fonction des codes taxe en vigueur au moment de l'exécution des transactions.</span><span class="sxs-lookup"><span data-stu-id="fca76-135">You can assign the sales tax groups to companies, and the taxes will be calculated based on the tax codes that were in effect when the transactions took place.</span></span>

1.  <span data-ttu-id="fca76-136">Cliquez sur **Comptabilité** \> **Paramétrage** \> **Taxe** \> **Groupes de taxe**.</span><span class="sxs-lookup"><span data-stu-id="fca76-136">Click **General ledger** \> **Setup** \> **Sales tax** \> **Sales tax groups**.</span></span>

2.  <span data-ttu-id="fca76-137">Appuyez sur Ctrl+N pour créer un groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="fca76-137">Press CTRL+N to create a new sales tax group.</span></span>

3.  <span data-ttu-id="fca76-138">Dans le champ **Code de groupe de taxe**, entrez un nom, tel que GST/HST, puis entrez des informations générales sur le groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="fca76-138">In the **Sales tax group** field, enter a name, such as GST/HST, and then enter general information about the sales tax group.</span></span>

4.  <span data-ttu-id="fca76-139">Cliquez sur l'onglet **Configuration**, puis dans le champ **Code de taxe**, sélectionnez un code taxe à ajouter au groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="fca76-139">Click the **Setup** tab, and in the **Sales tax code** field, select a sales tax code to add to the sales tax group.</span></span>

5.  <span data-ttu-id="fca76-140">Fermez l'écran pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="fca76-140">Close the form to save your changes.</span></span>

## <a name="generate-a-gift-file"></a><span data-ttu-id="fca76-141">Génération d'un fichier GIFT</span><span class="sxs-lookup"><span data-stu-id="fca76-141">Generate a GIFT file</span></span>

<span data-ttu-id="fca76-142">Vous pouvez générer un fichier GST/GIFT (HST Internet File Transfer) de déclaration de taxe sur les biens et services ou de taxe harmonisée et charger celui-ci sur le site de l'Agence du revenu du Canada (ARC) afin de remplir vos déclarations GST/HST et effectuer des paiements.</span><span class="sxs-lookup"><span data-stu-id="fca76-142">You can generate a Goods and Services Tax or Harmonized Sales Tax (GST/HST) Internet File Transfer (GIFT) file and upload it to the Canadian Revenue Agency (CRA) website to file your GST/HST returns and remit payments.</span></span>

1. <span data-ttu-id="fca76-143">Cliquez sur **Comptabilité générale** > **Périodique** > **GST/GIFT (HST Internet File Transfer)**.</span><span class="sxs-lookup"><span data-stu-id="fca76-143">Click **General ledger** > **Periodic** > **GST/HST Internet File Transfer (GIFT)**.</span></span>

2. <span data-ttu-id="fca76-144">Dans les champs **Date de début** et **Date de fin**, entrez les dates de début et de fin de la période de déclaration.</span><span class="sxs-lookup"><span data-stu-id="fca76-144">In the **From date** and **To date** fields, select the starting and ending dates of the reporting period.</span></span>

3. <span data-ttu-id="fca76-145">Dans le champ **Nom du fichier**, sélectionnez le chemin et saisissez le nom du fichier d'exportation de l'état Déclaration européenne de services.</span><span class="sxs-lookup"><span data-stu-id="fca76-145">In the **File name** field, select the path and enter the name for the GIFT file.</span></span>

    <span data-ttu-id="fca76-146">Note</span><span class="sxs-lookup"><span data-stu-id="fca76-146">Note</span></span>

   <span data-ttu-id="fca76-147">Pour faciliter l'identification, utilisez le format GSTAAAAMMJJ.tax (GST, suivi de la date de déclaration, puis de l'extension .tax) ; par exemple : GST20100728.tax.</span><span class="sxs-lookup"><span data-stu-id="fca76-147">For easy identification, use the format GSTYYYYMMDD.tax (GST, followed by the reporting date, with a .tax extension) as in this example: GST20100728.tax.</span></span>

4. <span data-ttu-id="fca76-148">Cliquez sur **OK** pour exporter le fichier GIFT vers le chemin spécifié.</span><span class="sxs-lookup"><span data-stu-id="fca76-148">Click **OK** to export the GIFT file to the specified path.</span></span>
