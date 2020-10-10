---
title: Mise à jour de l'entité composite du journal des banques
description: Les étapes suivantes sont requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.
author: ShylaThompson
manager: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ec196600a54a2aed4565cf422dc386d6646ff524
ms.sourcegitcommit: 74b10104338222a945684d841d60ab4b8e570168
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2020
ms.locfileid: "3899640"
---
# <a name="update-the-bank-journal-composite-entity"></a><span data-ttu-id="78c73-103">Mise à jour de l'entité composite du journal des banques</span><span class="sxs-lookup"><span data-stu-id="78c73-103">Update the bank journal composite entity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78c73-104">Les étapes suivantes sont requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.</span><span class="sxs-lookup"><span data-stu-id="78c73-104">The following steps are needed in order to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

<span data-ttu-id="78c73-105">Les étapes suivantes permettent d'ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.</span><span class="sxs-lookup"><span data-stu-id="78c73-105">Use the following steps to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

1.  <span data-ttu-id="78c73-106">Compilez et de synchroniser les entités composites de journal des banques, entités, et tables intermédiaires suivantes :</span><span class="sxs-lookup"><span data-stu-id="78c73-106">Compile and synchronize the following bank journal composite entities, entities, and staging tables:</span></span>
    -   <span data-ttu-id="78c73-107">Composite Entity\\BankJournalEntity</span><span class="sxs-lookup"><span data-stu-id="78c73-107">Composite Entity\\BankJournalEntity</span></span>
    -   <span data-ttu-id="78c73-108">Entity\\BankJournalHeaderEntity</span><span class="sxs-lookup"><span data-stu-id="78c73-108">Entity\\BankJournalHeaderEntity</span></span>
    -   <span data-ttu-id="78c73-109">Entity\\BankJournalLineEntity</span><span class="sxs-lookup"><span data-stu-id="78c73-109">Entity\\BankJournalLineEntity</span></span>
    -   <span data-ttu-id="78c73-110">Table\\BankJournalHeaderStaging</span><span class="sxs-lookup"><span data-stu-id="78c73-110">Table\\BankJournalHeaderStaging</span></span>
    -   <span data-ttu-id="78c73-111">Table\\BankJournalLineStaging</span><span class="sxs-lookup"><span data-stu-id="78c73-111">Table\\BankJournalLineStaging</span></span>

2.  <span data-ttu-id="78c73-112">Data management\\data projects</span><span class="sxs-lookup"><span data-stu-id="78c73-112">Data management\\data projects</span></span>
    -   <span data-ttu-id="78c73-113">Exposez le type **Transaction bancaire** sur la mise en page **Données sources**.</span><span class="sxs-lookup"><span data-stu-id="78c73-113">Expose the **Bank Transaction** type on **Source Data** layout.</span></span>
        -   <span data-ttu-id="78c73-114">Format de données source = Élément XML</span><span class="sxs-lookup"><span data-stu-id="78c73-114">Source data format = XML-Element</span></span>
        -   <span data-ttu-id="78c73-115">Nom de l'entité = Journal des banques</span><span class="sxs-lookup"><span data-stu-id="78c73-115">Entity name = Bank Journal</span></span>
        -   <span data-ttu-id="78c73-116">Télécharger le fichier de données = nouvelle version de SampleBankJournalCompositeEntity.xml</span><span class="sxs-lookup"><span data-stu-id="78c73-116">Upload data file = new version SampleBankJournalCompositeEntity.xml</span></span>
        -   <span data-ttu-id="78c73-117">Cliquez sur **Oui** pour remplacer le fichier existant.</span><span class="sxs-lookup"><span data-stu-id="78c73-117">Click **Yes** to overwrite the existing file.</span></span>
        -   <span data-ttu-id="78c73-118">Cliquez sur **Oui** pour générer un mappage à partir du début.</span><span class="sxs-lookup"><span data-stu-id="78c73-118">Click **Yes** to generate mapping from scratch.</span></span>
        -   <span data-ttu-id="78c73-119">Vérifiez que le type de transaction bancaire en mappé.</span><span class="sxs-lookup"><span data-stu-id="78c73-119">Verify that the Bank Transaction Type is mapped.</span></span>
            -   <span data-ttu-id="78c73-120">Cliquez sur **Afficher la carte** sur l'entité de ligne.</span><span class="sxs-lookup"><span data-stu-id="78c73-120">Click **View map** on Line entity.</span></span>
            -   <span data-ttu-id="78c73-121">Vérifiez que le type de transaction bancaire est mappé entre Source et Intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="78c73-121">Verify that Bank Transaction type is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="78c73-122">Importez le nouveau relevé.</span><span class="sxs-lookup"><span data-stu-id="78c73-122">Import the new statement.</span></span>




