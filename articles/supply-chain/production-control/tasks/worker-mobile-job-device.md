---
title: Configurer un collaborateur à l’aide du périphérique mobile
description: Cette rubrique explique comment affecter des rôles corrects au compte utilisateur d’un collaborateur, puis autoriser ce collaborateur à effectuer des enregistrements d’atelier.
author: ShylaThompson
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6210cdeed99f26a6b58b75d9f5405c0e1ee5aef1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213328"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="0b57b-103">Configurer un collaborateur à l’aide du périphérique mobile</span><span class="sxs-lookup"><span data-stu-id="0b57b-103">Configure a worker using the mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0b57b-104">Cette rubrique explique comment affecter des rôles corrects au compte utilisateur d’un collaborateur, puis autoriser ce collaborateur à effectuer des enregistrements d’atelier.</span><span class="sxs-lookup"><span data-stu-id="0b57b-104">This topic explains how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a><span data-ttu-id="0b57b-105">Vérifier qu’un certain rôle est affecté à un collaborateur</span><span class="sxs-lookup"><span data-stu-id="0b57b-105">Verify that a worker is assigned a certain role</span></span>

<span data-ttu-id="0b57b-106">Pour cet exemple, vérifiez que le rôle Opérateur est affecté à l’utilisateur « SHANNON » avant de configurer le compte du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="0b57b-106">For this example, verify that user "SHANNON" is assigned the machine operator role before you configure the worker account.</span></span>

1. <span data-ttu-id="0b57b-107">Accédez à **Volet de navigation > Modules > Administration système > Utilisateurs > Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="0b57b-108">Recherchez un utilisateur dans le filtre rapide.</span><span class="sxs-lookup"><span data-stu-id="0b57b-108">Search for a user in the quick filter.</span></span> <span data-ttu-id="0b57b-109">Pour cet exemple, entrez `shannon`.</span><span class="sxs-lookup"><span data-stu-id="0b57b-109">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="0b57b-110">Sélectionnez le lien dans la colonne **ID utilisateur** du compte d’utilisateur qui s’affiche.</span><span class="sxs-lookup"><span data-stu-id="0b57b-110">Select the link in the **User ID** column of the user account that appears.</span></span>
4. <span data-ttu-id="0b57b-111">Dans l’arborescence **Rôles de l’utilisateur**, sélectionnez **Rôles > Opérateur**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-111">In the **User's roles** tree, select **Roles > Machine operator**.</span></span>
5. <span data-ttu-id="0b57b-112">Fermez les pages **détails sur l’utilisateur** et **utilisateurs** pour revenir à la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="0b57b-112">Close the **user details** and **users** pages to return to the home page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="0b57b-113">Paramétrer le compte du collaborateur</span><span class="sxs-lookup"><span data-stu-id="0b57b-113">Configure worker account</span></span>
1. <span data-ttu-id="0b57b-114">Allez dans **Volet de navigation > Modules > Ressources humaines > Collaborateurs > Collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-114">Go to **Navigation pane > Modules > Human resources > Workers > Workers**.</span></span>
2. <span data-ttu-id="0b57b-115">Recherchez un utilisateur dans le filtre rapide.</span><span class="sxs-lookup"><span data-stu-id="0b57b-115">Search for a user in the quick filter.</span></span> <span data-ttu-id="0b57b-116">Pour cet exemple, entrez `shannon`.</span><span class="sxs-lookup"><span data-stu-id="0b57b-116">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="0b57b-117">Sélectionnez le lien dans la colonne **Nom** du compte d’utilisateur qui s’affiche.</span><span class="sxs-lookup"><span data-stu-id="0b57b-117">Select the link in the **Name** column of the user account that appears.</span></span>
4. <span data-ttu-id="0b57b-118">Sélectionnez l’onglet **Enregistrement du temps**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-118">Select the **Time registration** tab.</span></span>
5. <span data-ttu-id="0b57b-119">Sélectionnez **Activer sur les terminaux d’enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-119">Select **Activate on registration terminals**.</span></span>
6. <span data-ttu-id="0b57b-120">Entrez ou sélectionnez des valeurs dans les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="0b57b-120">Enter or select values in the following fields:</span></span>  

    - <span data-ttu-id="0b57b-121">**Groupe de calcul**</span><span class="sxs-lookup"><span data-stu-id="0b57b-121">**Calculation group**</span></span>  
    - <span data-ttu-id="0b57b-122">**Groupe de calcul par défaut**</span><span class="sxs-lookup"><span data-stu-id="0b57b-122">**Default calculation group**</span></span>  
    - <span data-ttu-id="0b57b-123">**Groupe d’approbation**</span><span class="sxs-lookup"><span data-stu-id="0b57b-123">**Approval group**</span></span>  
    - <span data-ttu-id="0b57b-124">**Profil standard**</span><span class="sxs-lookup"><span data-stu-id="0b57b-124">**Standard profile**</span></span>  
    - <span data-ttu-id="0b57b-125">**Groupe de profils**</span><span class="sxs-lookup"><span data-stu-id="0b57b-125">**Profile group**</span></span>  

7. <span data-ttu-id="0b57b-126">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-126">Select **OK**.</span></span>
8. <span data-ttu-id="0b57b-127">Sélectionnez **Modifier** pour saisir un numéro de badge pour le nouveau collaborateur qualifié pour l’enregistrement des heures.</span><span class="sxs-lookup"><span data-stu-id="0b57b-127">Select **Edit** to enter a badge number for the new time registration worker.</span></span> <span data-ttu-id="0b57b-128">Entrez une valeur dans le champ **ID badge**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-128">Enter a value in the **Badge ID** field.</span></span>
9. <span data-ttu-id="0b57b-129">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-129">Select **Save**.</span></span>
10. <span data-ttu-id="0b57b-130">Fermez les pages **Détails du collaborateur** et **Collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-130">Close the **Worker details** and **Workers** pages.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="0b57b-131">Affecter le collaborateur au groupe de périphériques</span><span class="sxs-lookup"><span data-stu-id="0b57b-131">Assign worker to device group</span></span>
1. <span data-ttu-id="0b57b-132">Accédez à **Contrôle de la production > Paramétrage > Contrôle et suivi de la production > Configurer le bon de travail pour les périphériques**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-132">Go to **Production control > Setup > Manufacturing execution > Configure job card for devices**.</span></span>
2. <span data-ttu-id="0b57b-133">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-133">Select **Add**.</span></span>
3. <span data-ttu-id="0b57b-134">Dans la liste, sélectionnez le collaborateur souhaité.</span><span class="sxs-lookup"><span data-stu-id="0b57b-134">In the list, select the desired worker.</span></span> <span data-ttu-id="0b57b-135">Pour cet exemple, sélectionnez **SHANNON**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-135">For this example, select **SHANNON**.</span></span>
4. <span data-ttu-id="0b57b-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-136">Select **OK**.</span></span>
5. <span data-ttu-id="0b57b-137">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0b57b-137">Select **Edit**.</span></span>
6. <span data-ttu-id="0b57b-138">Dans le champ **Unité de production**, vous pouvez définir le filtre par défaut pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="0b57b-138">In the **Production unit** field, you can set the default filter for the worker.</span></span> <span data-ttu-id="0b57b-139">Cela garantit que seules les tâches de production pour l’unité de production sélectionnée sont affichées lorsque le collaborateur se connecte au périphérique.</span><span class="sxs-lookup"><span data-stu-id="0b57b-139">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span> <span data-ttu-id="0b57b-140">Entrez la valeur souhaitée.</span><span class="sxs-lookup"><span data-stu-id="0b57b-140">Enter the desired value.</span></span>
7. <span data-ttu-id="0b57b-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0b57b-141">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]