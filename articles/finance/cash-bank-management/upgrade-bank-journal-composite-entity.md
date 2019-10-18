---
title: Mise à jour de l'entité composite du journal des banques
description: Les étapes suivantes sont requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.
author: ShylaThompson
manager: AnnBe
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
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 974d6b3b11df92debdec26860fd9eea00a9f2313
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188025"
---
# <a name="update-the-bank-journal-composite-entity"></a><span data-ttu-id="ee3a2-103">Mise à jour de l'entité composite du journal des banques</span><span class="sxs-lookup"><span data-stu-id="ee3a2-103">Update the bank journal composite entity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee3a2-104">Les étapes suivantes sont requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.</span><span class="sxs-lookup"><span data-stu-id="ee3a2-104">The following steps are needed in order to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

<span data-ttu-id="ee3a2-105">Les étapes suivantes permettent d'ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.</span><span class="sxs-lookup"><span data-stu-id="ee3a2-105">Use the following steps to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

1.  <span data-ttu-id="ee3a2-106">Compilez et de synchroniser les entités composites de journal des banques, entités, et tables intermédiaires suivantes :</span><span class="sxs-lookup"><span data-stu-id="ee3a2-106">Compile and synchronize the following bank journal composite entities, entities, and staging tables:</span></span>
    -   <span data-ttu-id="ee3a2-107">Composite Entity\\BankJournalEntity</span><span class="sxs-lookup"><span data-stu-id="ee3a2-107">Composite Entity\\BankJournalEntity</span></span>
    -   <span data-ttu-id="ee3a2-108">Entity\\BankJournalHeaderEntity</span><span class="sxs-lookup"><span data-stu-id="ee3a2-108">Entity\\BankJournalHeaderEntity</span></span>
    -   <span data-ttu-id="ee3a2-109">Entity\\BankJournalLineEntity</span><span class="sxs-lookup"><span data-stu-id="ee3a2-109">Entity\\BankJournalLineEntity</span></span>
    -   <span data-ttu-id="ee3a2-110">Table\\BankJournalHeaderStaging</span><span class="sxs-lookup"><span data-stu-id="ee3a2-110">Table\\BankJournalHeaderStaging</span></span>
    -   <span data-ttu-id="ee3a2-111">Table\\BankJournalLineStaging</span><span class="sxs-lookup"><span data-stu-id="ee3a2-111">Table\\BankJournalLineStaging</span></span>

2.  <span data-ttu-id="ee3a2-112">Data management\\data projects</span><span class="sxs-lookup"><span data-stu-id="ee3a2-112">Data management\\data projects</span></span>
    -   <span data-ttu-id="ee3a2-113">Exposez le type **Transaction bancaire** sur la mise en page **Données sources**.</span><span class="sxs-lookup"><span data-stu-id="ee3a2-113">Expose the **Bank Transaction** type on **Source Data** layout.</span></span>
        -   <span data-ttu-id="ee3a2-114">Format de données source = Élément XML</span><span class="sxs-lookup"><span data-stu-id="ee3a2-114">Source data format = XML-Element</span></span>
        -   <span data-ttu-id="ee3a2-115">Nom de l'entité = Journal des banques</span><span class="sxs-lookup"><span data-stu-id="ee3a2-115">Entity name = Bank Journal</span></span>
        -   <span data-ttu-id="ee3a2-116">Télécharger le fichier de données = nouvelle version de SampleBankJournalCompositeEntity.xml</span><span class="sxs-lookup"><span data-stu-id="ee3a2-116">Upload data file = new version SampleBankJournalCompositeEntity.xml</span></span>
        -   <span data-ttu-id="ee3a2-117">Cliquez sur **Oui** pour remplacer le fichier existant.</span><span class="sxs-lookup"><span data-stu-id="ee3a2-117">Click **Yes** to overwrite the existing file.</span></span>
        -   <span data-ttu-id="ee3a2-118">Cliquez sur **Oui** pour générer un mappage à partir du début.</span><span class="sxs-lookup"><span data-stu-id="ee3a2-118">Click **Yes** to generate mapping from scratch.</span></span>
        -   <span data-ttu-id="ee3a2-119">Vérifiez que le type de transaction bancaire en mappé.</span><span class="sxs-lookup"><span data-stu-id="ee3a2-119">Verify that the Bank Transaction Type is mapped.</span></span>
            -   <span data-ttu-id="ee3a2-120">Cliquez sur **Afficher la carte** sur l'entité de ligne.</span><span class="sxs-lookup"><span data-stu-id="ee3a2-120">Click **View map** on Line entity.</span></span>
            -   <span data-ttu-id="ee3a2-121">Vérifiez que le type de transaction bancaire est mappé entre Source et Intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="ee3a2-121">Verify that Bank Transaction type is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="ee3a2-122">Importez le nouveau relevé.</span><span class="sxs-lookup"><span data-stu-id="ee3a2-122">Import the new statement.</span></span>




