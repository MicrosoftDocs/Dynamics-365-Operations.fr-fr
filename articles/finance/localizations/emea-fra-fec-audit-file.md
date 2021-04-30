---
title: Génération du fichier d’audit standard pour la France (FEC)
description: Cette rubrique décrit le processus de génération du fichier d’audit standard pour la France (FEC) dans Microsoft Dynamics 365 Finance.
author: anasyash
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df928687b0ffa8f73eca8627437fcb8b84071045
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892387"
---
# <a name="generate-the-standard-audit-file-for-france-fec"></a><span data-ttu-id="46d08-103">Génération du fichier d’audit standard pour la France (FEC)</span><span class="sxs-lookup"><span data-stu-id="46d08-103">Generate the Standard Audit File for France (FEC)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46d08-104">Cette procédure vous montre comment générer le fichier d’audit standard (FEC) pour la France dans le format de fichier électronique.</span><span class="sxs-lookup"><span data-stu-id="46d08-104">This procedure walks you through generating the Standard Audit File (FEC) for France in the electronic file format.</span></span> <span data-ttu-id="46d08-105">L’administration fiscale française a besoin de fichiers d’audit générés au format FEC.</span><span class="sxs-lookup"><span data-stu-id="46d08-105">French tax authorities require audit files that are generated in the FEC format.</span></span>

<span data-ttu-id="46d08-106">Avant de générer un fichier d’audit FEC, vous devez :</span><span class="sxs-lookup"><span data-stu-id="46d08-106">Before you can generate a FEC audit file, you must:</span></span>

1. <span data-ttu-id="46d08-107">Définir les souches des N° documents.</span><span class="sxs-lookup"><span data-stu-id="46d08-107">Set up number sequences for vouchers.</span></span> <span data-ttu-id="46d08-108">Chaque souche de N° de justificatif doit contenir une partie du texte considérée comme une valeur pour **JournalCode** dans l’état **Audit FEC**.</span><span class="sxs-lookup"><span data-stu-id="46d08-108">Each voucher series must contain a portion of text which is considered as value for the **JournalCode** in the **FEC audit** report.</span></span> <span data-ttu-id="46d08-109">Par exemple, configurez une souche de N° de justificatif pour les journaux de facture fournisseur comme **FRSIFACF-########** pour obtenir la valeur « FRSIFACF » dans **JournalCode** dans le fichier FEC.txt.</span><span class="sxs-lookup"><span data-stu-id="46d08-109">For example, configure a voucher series for vendor invoice journals as **FRSIFACF-########** to get the value "FRSIFACF" in **JournalCode** in the FEC.txt file.</span></span>
2. <span data-ttu-id="46d08-110">Importer la dernière version du **Fichier d’audit FEC français** de la configuration de génération d’états électroniques.</span><span class="sxs-lookup"><span data-stu-id="46d08-110">Import the latest version of the Electronic reporting configuration **French FEC audit file**.</span></span> <span data-ttu-id="46d08-111">Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)</span><span class="sxs-lookup"><span data-stu-id="46d08-111">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)</span></span>
3. <span data-ttu-id="46d08-112">Sur la page **Configurations**, développez **Modèle d’exportation des données**, sélectionnez **Mise en correspondance de modèle FEC français**, et paramétrez **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="46d08-112">On the **Configurations** page, expand **Data export model**, select **French FEC model mapping**, and set **Default for model mapping** to **Yes**.</span></span>

## <a name="generate-the-standard-audit-file-for-france"></a><span data-ttu-id="46d08-113">Générer le fichier d’audit standard pour la France</span><span class="sxs-lookup"><span data-stu-id="46d08-113">Generate the Standard audit file for France</span></span>
1. <span data-ttu-id="46d08-114">Accédez à **Comptabilité générale** > **Tâches périodiques** > **Exportation de données** pour ouvrir la page **Exportation de données**.</span><span class="sxs-lookup"><span data-stu-id="46d08-114">Go to **General Ledger** > **Periodic tasks** > **Data export** to open the **Data export** page.</span></span>
2. <span data-ttu-id="46d08-115">Dans le champ **Mise en correspondance des formats**, sélectionnez **Fichier d’audit FEC français**.</span><span class="sxs-lookup"><span data-stu-id="46d08-115">In the **Format mapping** field, select **French FEC audit file**.</span></span>
3. <span data-ttu-id="46d08-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="46d08-116">Select **OK**.</span></span>
4. <span data-ttu-id="46d08-117">Dans la page **Paramètres de génération d’états électroniques**, entrez les dates de début et de fin pour la période dans les champs **Période – date de début** et **Période – Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="46d08-117">On the **Electronic report parameters** page, enter start and end dates for the period in the **Period - date from** and **Period - date to** fields.</span></span> <span data-ttu-id="46d08-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="46d08-118">Select **OK**.</span></span>
5. <span data-ttu-id="46d08-119">Examinez le fichier généré.</span><span class="sxs-lookup"><span data-stu-id="46d08-119">Review the generated file.</span></span>

## <a name="review-the-standard-audit-file"></a><span data-ttu-id="46d08-120">Consultez le fichier d’audit standard</span><span class="sxs-lookup"><span data-stu-id="46d08-120">Review the Standard audit file</span></span>
<span data-ttu-id="46d08-121">Lorsque le fichier d’audit standard est généré, un fichier d’archive avec les cinq rapports suivants est également généré.</span><span class="sxs-lookup"><span data-stu-id="46d08-121">When the Standard audit file is generated, an archive file with the following five reports is also generated.</span></span>

- <span data-ttu-id="46d08-122">FEC.txt</span><span class="sxs-lookup"><span data-stu-id="46d08-122">FEC.txt</span></span>
- <span data-ttu-id="46d08-123">Fournisseur Stock en entrée.txt</span><span class="sxs-lookup"><span data-stu-id="46d08-123">Vendor incoming.txt</span></span>
- <span data-ttu-id="46d08-124">Client Stock en entrée.txt</span><span class="sxs-lookup"><span data-stu-id="46d08-124">Customer incoming.txt</span></span>
- <span data-ttu-id="46d08-125">Solde fournisseur.txt</span><span class="sxs-lookup"><span data-stu-id="46d08-125">Vendor balance.txt</span></span>
- <span data-ttu-id="46d08-126">Solde client.txt</span><span class="sxs-lookup"><span data-stu-id="46d08-126">Customer balance.txt</span></span>

<span data-ttu-id="46d08-127">Envisagez les informations suivantes pour certains champs suivants dans les états :</span><span class="sxs-lookup"><span data-stu-id="46d08-127">Consider the following information for select fields in the reports:</span></span>

- <span data-ttu-id="46d08-128">**JournalCode** : contient la partie texte du N° document.</span><span class="sxs-lookup"><span data-stu-id="46d08-128">**JournalCode**: Contains the text portion of the voucher.</span></span> <span data-ttu-id="46d08-129">Si la souche de N° documents n’a pas de partie texte, la valeur sera vide.</span><span class="sxs-lookup"><span data-stu-id="46d08-129">If the voucher series doesn't have a text portion, the value will be blank.</span></span> <span data-ttu-id="46d08-130">Assurez-vous de configurer correctement la souche de N° documents afin d’avoir la valeur correcte dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="46d08-130">Be sure to correctly set up the voucher series in order to have the correct value in this field.</span></span>
- <span data-ttu-id="46d08-131">**JournalLib** :</span><span class="sxs-lookup"><span data-stu-id="46d08-131">**JournalLib**:</span></span> 

   - <span data-ttu-id="46d08-132">Dans les états **Solde fournisseur.txt** et **Solde client.txt**, cela doit être la valeur constante **Système**.</span><span class="sxs-lookup"><span data-stu-id="46d08-132">In the **Vendor balance.txt** and **Customer balance.txt** reports, this is the constant value **System**.</span></span>
   - <span data-ttu-id="46d08-133">Dans les états **Fournisseur Stock en entrée.txt** et **Client Stock en entrée.txt**, c’est la valeur du champ **Type de transaction des états** à partir de la transaction fournisseur ou transaction client rapportée.</span><span class="sxs-lookup"><span data-stu-id="46d08-133">In the **Vendor incoming.txt** and **Customer incoming.txt** reports, this is the value of the **Transaction type** field from the  vendor transaction or customer transaction which is reported.</span></span> <span data-ttu-id="46d08-134">Par exemple, les valeurs possibles peuvent être **Commande fournisseur** ou **Paiement**.</span><span class="sxs-lookup"><span data-stu-id="46d08-134">Possible values could be for example, **Purchase order** or **Payment**.</span></span>
   - <span data-ttu-id="46d08-135">Dans l’état **FEC.txt**, c’est la valeur du champ **Type de transaction** de l’état Transaction de documents.</span><span class="sxs-lookup"><span data-stu-id="46d08-135">In the **FEC.txt** report, this is the value of the **Transaction type** field from the voucher transaction that is reported.</span></span> <span data-ttu-id="46d08-136">Si le **Type de transaction** équivaut à **Feuille comptabilité**, c’est la valeur dans le champ **Description** du journal comptable qui est la source de la transaction de documents.</span><span class="sxs-lookup"><span data-stu-id="46d08-136">If the **Transaction type** equals **General journal**, this is the value from the **Description** field of the ledger journal, which is the source of the voucher transaction.</span></span> <span data-ttu-id="46d08-137">Vérifiez en consultant la valeur sur la page **Noms de journal**.</span><span class="sxs-lookup"><span data-stu-id="46d08-137">Verify by checking the value on the **Journal names** page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]