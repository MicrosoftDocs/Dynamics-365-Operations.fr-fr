---
title: Importer des utilisateurs depuis Azure Active Directory
description: Cette procédure peut être utilisée par les administrateurs système pour importer manuellement des utilisateurs sélectionnés ou un grand nombre d’utilisateurs depuis Azure Active Directory.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b6666310309817ff30ccb3902721880b829ee0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679812"
---
# <a name="import-users-from-azure-active-directory"></a><span data-ttu-id="67553-103">Importer des utilisateurs depuis Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="67553-103">Import users from Azure Active Directory</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a><span data-ttu-id="67553-104">Importer les utilisateurs sélectionnés</span><span class="sxs-lookup"><span data-stu-id="67553-104">Import select users</span></span>

<span data-ttu-id="67553-105">Cette procédure peut être utilisée par les administrateurs système pour importer des utilisateurs sélectionnés depuis Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="67553-105">This procedure can be used by system administrators to import select users from Azure Active Directory (Azure AD).</span></span>

1. <span data-ttu-id="67553-106">L’utilisateur sera importé avec la société de session actuelle comme société par défaut.</span><span class="sxs-lookup"><span data-stu-id="67553-106">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="67553-107">Changez la société actuelle le cas échéant avant d’importer des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="67553-107">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="67553-108">Accédez à **Administration système > Utilisateurs > Utilisateur** s.</span><span class="sxs-lookup"><span data-stu-id="67553-108">Go to **System administration > Users > User** s.</span></span>
3. <span data-ttu-id="67553-109">Cliquez sur **Importer des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="67553-109">Click **Import users**.</span></span>
4. <span data-ttu-id="67553-110">Sélectionnez les utilisateurs à importer et sélectionnez **Importer des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="67553-110">Select the users that should be imported and select **Import users**.</span></span>

<span data-ttu-id="67553-111">Une fois l’importation terminée, il sera nécessaire d’attribuer des rôles aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="67553-111">After import is completed it will be required to assign roles to users.</span></span>

## <a name="import-users-in-bulk"></a><span data-ttu-id="67553-112">Importer des utilisateurs en bloc</span><span class="sxs-lookup"><span data-stu-id="67553-112">Import users in bulk</span></span>

<span data-ttu-id="67553-113">Cette procédure peut être utilisée par les administrateurs système pour importer un grand nombre d’utilisateurs depuis Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="67553-113">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>
<span data-ttu-id="67553-114">Notez qu’il n’est pas possible de sélectionner des utilisateurs lors de l’utilisation de l’option d’importation par lots.</span><span class="sxs-lookup"><span data-stu-id="67553-114">Note that it is not possible to select users when using the Batch import option.</span></span>

## <a name="run-the-import-as-a-batch-job"></a><span data-ttu-id="67553-115">Exécutez l’importation comme un traitement par lots</span><span class="sxs-lookup"><span data-stu-id="67553-115">Run the import as a batch job</span></span>
1. <span data-ttu-id="67553-116">L’utilisateur sera importé avec la société de session actuelle comme société par défaut.</span><span class="sxs-lookup"><span data-stu-id="67553-116">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="67553-117">Changez la société actuelle le cas échéant avant d’importer des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="67553-117">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="67553-118">Accédez à **Administration système > Utilisateurs > Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="67553-118">Go to **System administration > Users > Users**.</span></span>
3. <span data-ttu-id="67553-119">Cliquez sur **Importation par lots**.</span><span class="sxs-lookup"><span data-stu-id="67553-119">Click **Batch import**.</span></span>
4. <span data-ttu-id="67553-120">Développez la section **Exécuter à l’arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="67553-120">Expand the **Run in the background** section.</span></span>
4. <span data-ttu-id="67553-121">Sélectionnez \*\*Oui dans le champ **Traitement par lots**.</span><span class="sxs-lookup"><span data-stu-id="67553-121">Select \*\*Yes in the **Batch processing** field.</span></span>
6. <span data-ttu-id="67553-122">Dans le champ **Groupe de traitement par lots**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="67553-122">In the **Batch group** field, enter or select a value.</span></span> <span data-ttu-id="67553-123">Cette étape est facultative.</span><span class="sxs-lookup"><span data-stu-id="67553-123">This is an optional step.</span></span>  
7. <span data-ttu-id="67553-124">Sélectionnez **Oui** dans le champ **Privé**.</span><span class="sxs-lookup"><span data-stu-id="67553-124">Select **Yes** in the **Private** field.</span></span> <span data-ttu-id="67553-125">Cette étape est facultative.</span><span class="sxs-lookup"><span data-stu-id="67553-125">This is an optional step.</span></span>  
8. <span data-ttu-id="67553-126">Sélectionnez **Oui** dans le champ **Tâche critique**.</span><span class="sxs-lookup"><span data-stu-id="67553-126">Select **Yes** in the **Critical job** field.</span></span> <span data-ttu-id="67553-127">Cette étape est facultative.</span><span class="sxs-lookup"><span data-stu-id="67553-127">bThis is an optional step.</span></span>  
9. <span data-ttu-id="67553-128">Dans le champ \*\*Catégorie de surveillance, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="67553-128">In the \*\*Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="67553-129">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="67553-129">Click **OK**.</span></span>

<span data-ttu-id="67553-130">Une fois l’importation terminée, il sera nécessaire d’attribuer des rôles aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="67553-130">After import is completed, it will be required to assign roles to users.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="67553-131">Exécuter dans un environnement de bac à sable</span><span class="sxs-lookup"><span data-stu-id="67553-131">Run in a sandbox environment</span></span>
1. <span data-ttu-id="67553-132">Sélectionner **Importation par lots**.</span><span class="sxs-lookup"><span data-stu-id="67553-132">Select **Batch import**.</span></span>
2. <span data-ttu-id="67553-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="67553-133">Select **OK**.</span></span>
