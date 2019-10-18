---
title: Canada GST/GIFT (HST Internet File Transfer)
description: Cette rubrique explique comment configurer et utiliser la fonction GIFT (Internet File Transfer) sur les biens et services ou de taxe harmonisée (GST/HST) du Canada.
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
ms.author: vstehman
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 056d2e145a0d819bc200a4792fd3ad7ee5db465c
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250354"
---
# <a name="canada-gsthst-internet-file-transfer-gift"></a><span data-ttu-id="5e897-103">Canada GST/GIFT (HST Internet File Transfer)</span><span class="sxs-lookup"><span data-stu-id="5e897-103">Canada GST/HST Internet File Transfer (GIFT)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="5e897-104">Les contribuables canadiens utilisent le formulaire GST 34 pour remplir manuellement les déclarations fiscales sur les biens et services ou de taxe harmonisée (GST/HST) et pour effectuer les paiements auprès de l'Agence du revenu du Canada (ARC).</span><span class="sxs-lookup"><span data-stu-id="5e897-104">Taxpayers in Canada use form GST 34 to manually file Goods and Services Tax or Harmonized Sales Tax (GST/HST) returns, and to remit payments to the Canada Revenue Agency (CRA).</span></span> <span data-ttu-id="5e897-105">Toutefois, cette dernière leur permet de remplir électroniquement les déclarations et de verser les taxes calculées sur les immobilisations acquises par voie électronique.</span><span class="sxs-lookup"><span data-stu-id="5e897-105">However, the CRA allows taxpayers to electronically file and remit taxes that are calculated on acquired fixed assets.</span></span> <span data-ttu-id="5e897-106">Vous pouvez remplir électroniquement les déclarations GST/HST par voie électronique à l'aide de l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e897-106">You can electronically file GST/HST returns by using any of the following methods:</span></span>

- <span data-ttu-id="5e897-107">**Transfert de fichiers via Internet** : service Internet de déclaration qui permet aux contribuables de remplir leurs déclarations directement via Internet.</span><span class="sxs-lookup"><span data-stu-id="5e897-107">**Net file transfer** – An internet-based filing service that taxpayers can use to file their returns directly over the internet.</span></span>
- <span data-ttu-id="5e897-108">**Échange de données informatisé (EDI)**  : méthode de transfert de données qui permet aux contribuables de remplir leurs déclarations directement auprès de l'ARC ou d'un fournisseur de services tiers.</span><span class="sxs-lookup"><span data-stu-id="5e897-108">**Electronic Data Interchange (EDI)** – A data transfer method that taxpayers can use to file their returns either directly with the CRA or through a third-party service provider.</span></span>
- <span data-ttu-id="5e897-109">**GST/HST Internet File Transfer (GIFT)**  : outil de téléchargement qui permet aux contribuables d'envoyer des fichiers texte au site Web de l'ARC à des fins de déclarations GST/HST et de règlement des paiements.</span><span class="sxs-lookup"><span data-stu-id="5e897-109">**GST/HST Internet File Transfer (GIFT)** – An upload tool that taxpayers can use to submit text files to the CRA website to file GST/HST returns and remit payments.</span></span>

<span data-ttu-id="5e897-110">Avant de générer un fichier GIFT, vous devez configurer le code identification du logiciel, le code taxe et le groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="5e897-110">Before you generate a GIFT file, you have to set up your software identification code, sales tax code, and sales tax group.</span></span>

<span data-ttu-id="5e897-111">Les procédures suivantes permettent d'entrer des informations sur l'entité juridique, le code taxe et les groupes de taxe pour GIFT, ainsi que de créer des entrées de taxe réglée pour les taxes sur l'acquisition.</span><span class="sxs-lookup"><span data-stu-id="5e897-111">Use the following procedures to enter legal entity details, a sales tax code, and a sales tax group for GIFT, and to create sales tax entries for taxes that were paid on fixed asset acquisition.</span></span>

## <a name="set-up-legal-entities-for-gift"></a><span data-ttu-id="5e897-112">Paramétrage d'entités juridiques pour GIFT</span><span class="sxs-lookup"><span data-stu-id="5e897-112">Set up legal entities for GIFT</span></span>

<span data-ttu-id="5e897-113">Lorsque vous envoyez une requête de transfert de fichiers via Internet à l'ARC, celle-ci fournit un code identification du logiciel,</span><span class="sxs-lookup"><span data-stu-id="5e897-113">When you submit a request to the CRA to do an internet file transfer, the CRA provides a software identification code.</span></span> <span data-ttu-id="5e897-114">composé de deux caractères alphabétiques et de six caractères numériques.</span><span class="sxs-lookup"><span data-stu-id="5e897-114">The first two characters are alphabetical, and the last six characters are numerical.</span></span> <span data-ttu-id="5e897-115">Pour traiter vos déclarations, vous devez entrer correctement ce code identification sur la page **Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="5e897-115">To process your returns, you must enter this code on the **Legal entities** page.</span></span>

1. <span data-ttu-id="5e897-116">Accédez à **Administration d'organisation** \> **Paramétrage** \> **Organisation** \> **Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="5e897-116">Go to **Organization administration** \> **Setup** \> **Organization** \> **Legal entities**.</span></span>
2. <span data-ttu-id="5e897-117">Sur l'organisateur **Génération d'état statutaire**, puis dans le champ **Numéro d'enregistrement**, entrez le numéro d'enregistrement fourni par l'ARC lors de votre enregistrement à des fins de déclaration GST/HST.</span><span class="sxs-lookup"><span data-stu-id="5e897-117">On the **Statutory reporting** FastTab, in the **Registration number** field, enter the registration number that the CRA provided when you registered for GST/HST.</span></span>
3. <span data-ttu-id="5e897-118">Dans le champ **Code identification du logiciel**, entrez **AX030003** pour transférer les déclarations.</span><span class="sxs-lookup"><span data-stu-id="5e897-118">In the **Software identification code** field, enter **AX030003** to transfer the returns.</span></span>
4. <span data-ttu-id="5e897-119">Sélectionnez **Identificateurs du compte** pour ouvrir la page **Identificateurs du compte**.</span><span class="sxs-lookup"><span data-stu-id="5e897-119">Select **Account identifiers** to open the **Account identifiers** page.</span></span>
5. <span data-ttu-id="5e897-120">Sous l'onglet **Vue d'ensemble**, dans le champ **Identificateur du programme**, sélectionnez **GST/HST**.</span><span class="sxs-lookup"><span data-stu-id="5e897-120">On the **Overview** tab, in the **Program identifier** field, select **GST/HST**.</span></span>
6. <span data-ttu-id="5e897-121">Dans le champ **Numéro de référence**, entrez le numéro de référence fourni par l'ARC.</span><span class="sxs-lookup"><span data-stu-id="5e897-121">In the **Reference number** field, enter the reference number that the CRA provided.</span></span>
7. <span data-ttu-id="5e897-122">Fermez les pages pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="5e897-122">Close the pages to save your changes.</span></span>

## <a name="set-up-tax-codes-for-gift"></a><span data-ttu-id="5e897-123">Définition des codes taxe pour GIFT</span><span class="sxs-lookup"><span data-stu-id="5e897-123">Set up tax codes for GIFT</span></span>

<span data-ttu-id="5e897-124">La page **Codes taxe** permet de définir des codes taxe pour calculer le montant des taxes GST/HST pour le fichier GIFT.</span><span class="sxs-lookup"><span data-stu-id="5e897-124">Use the **Sales tax codes** page to set up tax codes to calculate GST/HST for the GIFT file.</span></span>

1. <span data-ttu-id="5e897-125">Accédez à **Comptabilité** \> **Paramétrage** \> **Taxe** \> **Codes de taxe**.</span><span class="sxs-lookup"><span data-stu-id="5e897-125">Go to **General ledger** \> **Setup** \> **Sales tax** \> **Sales tax codes**.</span></span>
2. <span data-ttu-id="5e897-126">Appuyez sur **Ctrl+N** pour créer un code taxe.</span><span class="sxs-lookup"><span data-stu-id="5e897-126">Press **Ctrl+N** to create a tax code.</span></span>
3. <span data-ttu-id="5e897-127">Dans le champ **Code de taxe**, entrez un code, tel que **GST/HST**, puis entrez des informations générales sur le code taxe.</span><span class="sxs-lookup"><span data-stu-id="5e897-127">In the **Sales tax code** field, enter a code, such as **GST/HST**, and then enter general information about the sales tax code.</span></span>
4. <span data-ttu-id="5e897-128">Cliquez sur l'onglet **Calcul** et entrez les détails du calcul du montant des taxes GST/HST.</span><span class="sxs-lookup"><span data-stu-id="5e897-128">On the **Calculation** tab, enter the calculation details that should be used to calculate the GST/HST amount.</span></span>
5. <span data-ttu-id="5e897-129">Sélectionnez **Valeurs** pour ouvrir la page **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="5e897-129">Select **Values** to open the **Values** page.</span></span>
6. <span data-ttu-id="5e897-130">Entrez les dates auxquelles le code taxe prend effet.</span><span class="sxs-lookup"><span data-stu-id="5e897-130">Enter the dates when the tax code is in effect.</span></span>
7. <span data-ttu-id="5e897-131">Dans le champ **Valeur**, entrez le pourcentage utilisé pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="5e897-131">In the **Value** field, enter the percentage for the calculation.</span></span>
8. <span data-ttu-id="5e897-132">Fermez les pages pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="5e897-132">Close the pages to save your changes.</span></span>

## <a name="set-up-tax-groups-for-gift"></a><span data-ttu-id="5e897-133">Paramétrage des groupes de taxe pour GIFT</span><span class="sxs-lookup"><span data-stu-id="5e897-133">Set up tax groups for GIFT</span></span>

<span data-ttu-id="5e897-134">Utilisez la page **Groupes de taxe** pour configurer les groupes de taxe.</span><span class="sxs-lookup"><span data-stu-id="5e897-134">Use the **Sales tax groups** page to set up sales tax groups.</span></span> <span data-ttu-id="5e897-135">Vous pouvez affecter des groupes de taxe aux sociétés.</span><span class="sxs-lookup"><span data-stu-id="5e897-135">You can assign the sales tax groups to companies.</span></span> <span data-ttu-id="5e897-136">Les taxes seront ensuite calculées en fonction des codes taxe en vigueur au moment de l'exécution des transactions.</span><span class="sxs-lookup"><span data-stu-id="5e897-136">Taxes will then be calculated based on the tax codes that were in effect when the transactions occurred.</span></span>

1. <span data-ttu-id="5e897-137">Accédez à **Comptabilité** \> **Paramétrage** \> **Taxe** \> **Groupes de taxe**.</span><span class="sxs-lookup"><span data-stu-id="5e897-137">Go to **General ledger** \> **Setup** \> **Sales tax** \> **Sales tax groups**.</span></span>
2. <span data-ttu-id="5e897-138">Appuyez sur **Ctrl+N** pour créer un groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="5e897-138">Press **Ctrl+N** to create a sales tax group.</span></span>
3. <span data-ttu-id="5e897-139">Dans le champ **Code de groupe de taxe**, entrez un nom, tel que **GST/HST**, puis entrez des informations générales sur le groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="5e897-139">In the **Sales tax group** field, enter a name, such as **GST/HST**, and then enter general information about the sales tax group.</span></span>
4. <span data-ttu-id="5e897-140">Sur l'onglet **Configuration**, puis dans le champ **Code de taxe**, sélectionnez un code taxe à ajouter au groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="5e897-140">On the **Setup** tab, in the **Sales tax code** field, select a sales tax code to add to the sales tax group.</span></span>
5. <span data-ttu-id="5e897-141">Fermez la page pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="5e897-141">Close the page to save your changes.</span></span>

## <a name="generate-a-gift-file"></a><span data-ttu-id="5e897-142">Génération d'un fichier GIFT</span><span class="sxs-lookup"><span data-stu-id="5e897-142">Generate a GIFT file</span></span>

<span data-ttu-id="5e897-143">Pour faire vos déclarations GST/HST et effectuer les paiements, vous pouvez générer un fichier GIFT et le télécharger le site Web de l'ARC.</span><span class="sxs-lookup"><span data-stu-id="5e897-143">To file your GST/HST returns and remit payments, you can generate a GIFT file and upload it to the CRA website.</span></span>

1. <span data-ttu-id="5e897-144">Accédez à **Comptabilité générale** \> **Périodique** \> **GST/HST Internet File Transfer (GIFT)**.</span><span class="sxs-lookup"><span data-stu-id="5e897-144">Go to **General ledger** \> **Periodic** \> **GST/HST Internet File Transfer (GIFT)**.</span></span>
2. <span data-ttu-id="5e897-145">Dans les champs **Date de début** et **Date de fin**, entrez les dates de début et de fin de la période de déclaration.</span><span class="sxs-lookup"><span data-stu-id="5e897-145">In the **From date** and **To date** fields, select the start and end dates of the reporting period.</span></span>
3. <span data-ttu-id="5e897-146">Dans le champ **Nom du fichier**, sélectionnez le chemin et saisissez le nom du fichier d'exportation de l'état Déclaration européenne de services.</span><span class="sxs-lookup"><span data-stu-id="5e897-146">In the **File name** field, select the path and enter the name of the GIFT file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e897-147">Pour faciliter l'identification du fichier GIFT, utilisez le format *GSTAAAAMMJJ.tax* pour le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="5e897-147">For easy identification of the GIFT file, use the format *GSTYYYYMMDD.tax* for the file name.</span></span> <span data-ttu-id="5e897-148">(Autrement dit, entrez **GST** suivi de la date de déclaration, puis ajoutez l'extension de nom de fichier **.tax** .) Par exemple, si la date de génération d'états est le 28 juillet 2010, entrez **GST20100728.tax** comme nom du fichier GIFT.</span><span class="sxs-lookup"><span data-stu-id="5e897-148">(In other words, enter **GST** followed by the reporting date, and then add the **.tax** file name extension.) For example, if the reporting date is July 28, 2010, enter **GST20100728.tax** as the name of the GIFT file.</span></span>

4. <span data-ttu-id="5e897-149">Sélectionnez **OK** pour exporter le fichier GIFT vers le chemin spécifié.</span><span class="sxs-lookup"><span data-stu-id="5e897-149">Select **OK** to export the GIFT file to the specified path.</span></span>
