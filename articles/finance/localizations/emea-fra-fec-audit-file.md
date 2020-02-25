---
title: Génération du fichier d'audit standard pour la France (FEC)
description: Cette rubrique décrit le processus de génération du fichier d'audit standard pour la France (FEC) dans Microsoft Dynamics 365 Finance.
author: anasyash
manager: AnnBe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 30b2688f45aaf60df306f1c291771b0f148ff3d0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003697"
---
# <a name="generate-the-standard-audit-file-for-france-fec"></a><span data-ttu-id="6df44-103">Génération du fichier d'audit standard pour la France (FEC)</span><span class="sxs-lookup"><span data-stu-id="6df44-103">Generate the Standard Audit File for France (FEC)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6df44-104">Cette procédure vous montre comment générer le fichier d'audit standard (FEC) pour la France dans le format de fichier électronique.</span><span class="sxs-lookup"><span data-stu-id="6df44-104">This procedure walks you through generating the Standard Audit File (FEC) for France in the electronic file format.</span></span> <span data-ttu-id="6df44-105">L'administration fiscale française a besoin de fichiers d'audit générés au format FEC.</span><span class="sxs-lookup"><span data-stu-id="6df44-105">French tax authorities require audit files that are generated in the FEC format.</span></span>

<span data-ttu-id="6df44-106">Avant de générer un fichier d'audit FEC, vous devez :</span><span class="sxs-lookup"><span data-stu-id="6df44-106">Before you can generate a FEC audit file, you must:</span></span>

1. <span data-ttu-id="6df44-107">Définir les souches des N° documents.</span><span class="sxs-lookup"><span data-stu-id="6df44-107">Set up number sequences for vouchers.</span></span> <span data-ttu-id="6df44-108">Chaque souche de N° documents doit contenir une partie du texte considérée comme **JournalCode** dans l'état **Audit FEC**.</span><span class="sxs-lookup"><span data-stu-id="6df44-108">Each voucher series must contain a portion of text which is considered the **JournalCode** in the **FEC audit** report.</span></span> <span data-ttu-id="6df44-109">Par exemple, configurez une souche de N° documents pour les journaux de facture fournisseur comme **FRSIFACF-########** pour obtenir le **JournalCode**, « FRSIFACF » dans le fichier FEC.txt.</span><span class="sxs-lookup"><span data-stu-id="6df44-109">For example, configure a voucher series for vendor invoice journals as **FRSIFACF-########** to get the **JournalCode**, "FRSIFACF" in the FEC.txt file.</span></span>
2. <span data-ttu-id="6df44-110">Importer la dernière version du **Fichier d'audit FEC français** de la configuration de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="6df44-110">Import the latest version of the Electronic reporting configuration **French FEC audit file**.</span></span> <span data-ttu-id="6df44-111">Pour plus d'informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)</span><span class="sxs-lookup"><span data-stu-id="6df44-111">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)</span></span>
3. <span data-ttu-id="6df44-112">Sur la page **Configurations**, développez **Modèle d'exportation des données**, sélectionnez **Mise en correspondance de modèle FEC français**, et paramétrez **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6df44-112">On the **Configurations** page, expand **Data export model**, select **French FEC model mapping**, and set **Default for model mapping** to **Yes**.</span></span>

## <a name="generate-the-standard-audit-file-for-france"></a><span data-ttu-id="6df44-113">Générer le fichier d'audit standard pour la France</span><span class="sxs-lookup"><span data-stu-id="6df44-113">Generate the Standard audit file for France</span></span>
1. <span data-ttu-id="6df44-114">Accédez à **Comptabilité générale** > **Tâches périodiques** > **Exportation de données** pour ouvrir la page **Exportation de données**.</span><span class="sxs-lookup"><span data-stu-id="6df44-114">Go to **General Ledger** > **Periodic tasks** > **Data export** to open the **Data export** page.</span></span>
2. <span data-ttu-id="6df44-115">Dans le champ **Mise en correspondance des formats**, sélectionnez **Fichier d'audit FEC français**.</span><span class="sxs-lookup"><span data-stu-id="6df44-115">In the **Format mapping** field, select **French FEC audit file**.</span></span>
3. <span data-ttu-id="6df44-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6df44-116">Select **OK**.</span></span>
4. <span data-ttu-id="6df44-117">Dans la page **Paramètres de génération d'états électroniques**, entrez les dates de début et de fin pour la période dans les champs **Période - date de début** et **Période - Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="6df44-117">On the **Electronic report parameters** page, enter start and end dates for the period in the **Period - date from** and **Period - date to** fields.</span></span> <span data-ttu-id="6df44-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6df44-118">Select **OK**.</span></span>
5. <span data-ttu-id="6df44-119">Examinez le fichier généré.</span><span class="sxs-lookup"><span data-stu-id="6df44-119">Review the generated file.</span></span>

## <a name="review-the-standard-audit-file"></a><span data-ttu-id="6df44-120">Consultez le fichier d'audit standard</span><span class="sxs-lookup"><span data-stu-id="6df44-120">Review the Standard audit file</span></span>
<span data-ttu-id="6df44-121">Lorsque le fichier d'audit standard est généré, un fichier d'archive avec les cinq rapports suivants est également généré.</span><span class="sxs-lookup"><span data-stu-id="6df44-121">When the Standard audit file is generated, an archive file with the following five reports is also generated.</span></span>

- <span data-ttu-id="6df44-122">FEC.txt</span><span class="sxs-lookup"><span data-stu-id="6df44-122">FEC.txt</span></span>
- <span data-ttu-id="6df44-123">Fournisseur Stock en entrée.txt</span><span class="sxs-lookup"><span data-stu-id="6df44-123">Vendor incoming.txt</span></span>
- <span data-ttu-id="6df44-124">Client Stock en entrée.txt</span><span class="sxs-lookup"><span data-stu-id="6df44-124">Customer incoming.txt</span></span>
- <span data-ttu-id="6df44-125">Solde fournisseur.txt</span><span class="sxs-lookup"><span data-stu-id="6df44-125">Vendor balance.txt</span></span>
- <span data-ttu-id="6df44-126">Solde client.txt</span><span class="sxs-lookup"><span data-stu-id="6df44-126">Customer balance.txt</span></span>

<span data-ttu-id="6df44-127">Envisagez les informations suivantes pour certains champs suivants dans les états :</span><span class="sxs-lookup"><span data-stu-id="6df44-127">Consider the following information for select fields in the reports:</span></span>

- <span data-ttu-id="6df44-128">**JournalCode** : contient la partie texte du N° document.</span><span class="sxs-lookup"><span data-stu-id="6df44-128">**JournalCode**: Contains the text portion of the voucher.</span></span> <span data-ttu-id="6df44-129">Si la souche de N° documents n'a pas de partie texte, la valeur sera vide.</span><span class="sxs-lookup"><span data-stu-id="6df44-129">If the voucher series doesn't have a text portion, the value will be blank.</span></span> <span data-ttu-id="6df44-130">Assurez-vous de configurer correctement la souche de N° documents afin d'avoir la valeur correcte dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="6df44-130">Be sure to correctly set up the voucher series in order to have the correct value in this field.</span></span>
- <span data-ttu-id="6df44-131">**JournalLib** :</span><span class="sxs-lookup"><span data-stu-id="6df44-131">**JournalLib**:</span></span> 

   - <span data-ttu-id="6df44-132">Dans les états **Solde fournisseur.txt** et **Solde client.txt**, cela doit être la valeur constante **Système**.</span><span class="sxs-lookup"><span data-stu-id="6df44-132">In the **Vendor balance.txt** and **Customer balance.txt** reports, this needs to be the constant value **System**.</span></span>
   - <span data-ttu-id="6df44-133">Dans les états **Fournisseur Stock en entrée.txt** et **Client Stock en entrée.txt**, c'est la valeur du champ **Type de transaction** des états, **Transaction fournisseur** ou **Transaction client**.</span><span class="sxs-lookup"><span data-stu-id="6df44-133">In the **Vendor incoming.txt** and **Customer incoming.txt** reports, this is the value of the **Transaction type** field from the reports, **Vendor transaction** or **Customer transaction**.</span></span> <span data-ttu-id="6df44-134">Les valeurs possibles peuvent être **Commande fournisseur** ou **Paiement**.</span><span class="sxs-lookup"><span data-stu-id="6df44-134">Possible values could be **Purchase order** or **Payment**.</span></span>
   - <span data-ttu-id="6df44-135">Dans l'état **FEC.txt**, c'est la valeur du champ **Type de transaction** de l'état **Transaction de documents**.</span><span class="sxs-lookup"><span data-stu-id="6df44-135">In the **FEC.txt** report, this is the value of the **Transaction type** field from the **Voucher transaction** report.</span></span> <span data-ttu-id="6df44-136">Si le **Type de transaction** équivaut à **Fuille comptabilité**, c'est la valeur dans le champ **Description** du journal comptable qui est la source de la transaction de documents.</span><span class="sxs-lookup"><span data-stu-id="6df44-136">If the **Transaction type** equals **General journal**, this is the value in the **Description** field of the ledger journal, which is the source of the voucher transaction.</span></span> <span data-ttu-id="6df44-137">Vérifiez en consultant la valeur sur la page **Noms de journal**.</span><span class="sxs-lookup"><span data-stu-id="6df44-137">Verify by checking the value on the **Journal names** page.</span></span>
