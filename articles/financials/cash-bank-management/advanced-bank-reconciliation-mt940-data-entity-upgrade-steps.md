---
title: Importation avancée du rapprochement bancaire MT940 – Mise à niveau de l'entité de données composite
description: Un numéro de souche doit être ajouté à l'entité d'importation des relevés bancaires pour prendre en charge le format MT940.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6c0eeb59726422177ed1122767b9d3142a1311a2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "343786"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="7dabd-103">Importation avancée du rapprochement bancaire MT940 – Mise à niveau de l'entité de données composite</span><span class="sxs-lookup"><span data-stu-id="7dabd-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7dabd-104">Un numéro de souche doit être ajouté à l'entité d'importation des relevés bancaires pour prendre en charge le format MT940.</span><span class="sxs-lookup"><span data-stu-id="7dabd-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="7dabd-105">Les étapes suivantes vous permettent d'ajouter l'entité d'importation des relevés bancaires pour prendre en charge le format MT940.</span><span class="sxs-lookup"><span data-stu-id="7dabd-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="7dabd-106">Compilez et synchronisez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7dabd-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="7dabd-107">Composite Entity\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="7dabd-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="7dabd-108">Entity\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="7dabd-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="7dabd-109">Entity\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="7dabd-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="7dabd-110">Entity\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="7dabd-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="7dabd-111">Entity\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="7dabd-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="7dabd-112">Tables\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="7dabd-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="7dabd-113">Data management\\data projects.</span><span class="sxs-lookup"><span data-stu-id="7dabd-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="7dabd-114">Projets d'importation de la charge MT940</span><span class="sxs-lookup"><span data-stu-id="7dabd-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="7dabd-115">Modifiez XSLT.</span><span class="sxs-lookup"><span data-stu-id="7dabd-115">Change XSLT.</span></span>
            -   <span data-ttu-id="7dabd-116">Cliquez sur **Afficher la carte**.</span><span class="sxs-lookup"><span data-stu-id="7dabd-116">Click **View map**.</span></span>
            -   <span data-ttu-id="7dabd-117">Cliquez sur **Afficher la carte** sur le document de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="7dabd-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="7dabd-118">Cliquez sur **Transformations**</span><span class="sxs-lookup"><span data-stu-id="7dabd-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="7dabd-119">Supprimez le fichier BankReconiliation-to-Composite.xslt.</span><span class="sxs-lookup"><span data-stu-id="7dabd-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="7dabd-120">Ajoutez la nouvelle version de BankReconiliation-to-Composite.xslt.</span><span class="sxs-lookup"><span data-stu-id="7dabd-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="7dabd-121">Exposez le **Numéro de souche** dans la mise en page **Données sources**.</span><span class="sxs-lookup"><span data-stu-id="7dabd-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="7dabd-122">Format de données source = Élément XML.</span><span class="sxs-lookup"><span data-stu-id="7dabd-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="7dabd-123">Nom de l'entité = Relevés bancaires.</span><span class="sxs-lookup"><span data-stu-id="7dabd-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="7dabd-124">Télécharger le fichier de données = nouvelle version de SampleBankCompositeEntity.xml.</span><span class="sxs-lookup"><span data-stu-id="7dabd-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="7dabd-125">Cliquez sur **Oui** pour remplacer le fichier existant.</span><span class="sxs-lookup"><span data-stu-id="7dabd-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="7dabd-126">Cliquez sur **Oui** pour générer un nouveau mappage.</span><span class="sxs-lookup"><span data-stu-id="7dabd-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="7dabd-127">Vérifiez que S**equenceNumber** est mappé.</span><span class="sxs-lookup"><span data-stu-id="7dabd-127">Verify that S**equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="7dabd-128">Cliquez sur **Afficher la carte** sur l'entité de relevé.</span><span class="sxs-lookup"><span data-stu-id="7dabd-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="7dabd-129">Vérifiez que **SequenceNumber** est mappé entre Source et Intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="7dabd-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="7dabd-130">Importez le nouveau relevé.</span><span class="sxs-lookup"><span data-stu-id="7dabd-130">Import the new statement.</span></span>




