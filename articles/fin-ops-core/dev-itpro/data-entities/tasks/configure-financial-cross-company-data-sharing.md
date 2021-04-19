---
title: Configurer le partage de données financières entre sociétés
description: Cette procédure indique comment configurer, activer, valider, et résoudre des conflits en partageant des données entre des sociétés.
author: aprilolson
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportRnr, DMFExecutionHistoryWorkspace, DMFExecutionHistorySummary, DMFExecutionHistoryEntities,  SysDataSharingConfiguration, SysDataSharingDiscrepencies
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35ec8fc809841c0830224646fb57b0e4e4d40ef4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752290"
---
# <a name="configure-financial-cross-company-data-sharing"></a><span data-ttu-id="88ad1-103">Configurer le partage de données financières entre sociétés</span><span class="sxs-lookup"><span data-stu-id="88ad1-103">Configure financial cross-company data sharing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="88ad1-104">Cette procédure indique comment configurer, activer, valider, et résoudre des conflits en partageant des données entre des sociétés.</span><span class="sxs-lookup"><span data-stu-id="88ad1-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="88ad1-105">Elle utilise la société USMF et le modèle de partage de données financières.</span><span class="sxs-lookup"><span data-stu-id="88ad1-105">It uses the USMF company and the Financial data sharing template.</span></span>

<span data-ttu-id="88ad1-106">La plateforme Dynamics AX 7.1 ou ultérieure est requise pour ce guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="88ad1-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="88ad1-107">Accédez à **Volet de navigation pane > Modules > Administration système> Espaces de travail > Gestion des données**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-107">Go to **Navigation pane > Modules > System administration > Workspaces > Data management**.</span></span>
2. <span data-ttu-id="88ad1-108">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-108">Click **Import**.</span></span>
3. <span data-ttu-id="88ad1-109">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-109">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="88ad1-110">Dans le champ **Format des données source**, sélectionnez le type de package.</span><span class="sxs-lookup"><span data-stu-id="88ad1-110">In the **Source data format** field, select the 'Package' type.</span></span> <span data-ttu-id="88ad1-111">Cliquez sur **Charger**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-111">Click **Upload**.</span></span> <span data-ttu-id="88ad1-112">Allez dans l’emplacement du fichier de package du modèle de partage de données financières et sélectionnez ce fichier.</span><span class="sxs-lookup"><span data-stu-id="88ad1-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>
5. <span data-ttu-id="88ad1-113">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-113">Click **Save**.</span></span>
6. <span data-ttu-id="88ad1-114">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="88ad1-114">In the list, mark the selected row.</span></span> <span data-ttu-id="88ad1-115">Sélectionnez la stratégie de partage de données qui vient d’être créée.</span><span class="sxs-lookup"><span data-stu-id="88ad1-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="88ad1-116">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-116">Click **Import**.</span></span>
8. <span data-ttu-id="88ad1-117">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-117">Click **Close**.</span></span>
9. <span data-ttu-id="88ad1-118">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="88ad1-118">Refresh the page.</span></span>
10. <span data-ttu-id="88ad1-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="88ad1-119">Close the page.</span></span>
11. <span data-ttu-id="88ad1-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="88ad1-120">Close the page.</span></span>
12. <span data-ttu-id="88ad1-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="88ad1-121">Close the page.</span></span>
13. <span data-ttu-id="88ad1-122">Accédez à **Volet de navigation > Modules > Administration système > Paramétrage > Configurer le partage de données entre sociétés**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-122">Go to **Navigation pane > Modules > System administration > Setup > Configure cross-company data sharing**.</span></span>
14. <span data-ttu-id="88ad1-123">Dans la liste, recherchez et sélectionnez **Jours de paiement**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-123">In the list, find and select **Payment days**.</span></span>
15. <span data-ttu-id="88ad1-124">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-124">Click **Add**.</span></span>
16. <span data-ttu-id="88ad1-125">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="88ad1-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="88ad1-126">Dans le champ **Société**, saisissez ’USSI’.</span><span class="sxs-lookup"><span data-stu-id="88ad1-126">In the **Company** field, type 'USSI'.</span></span>
18. <span data-ttu-id="88ad1-127">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-127">Click **Add**.</span></span>
19. <span data-ttu-id="88ad1-128">Dans le champ **Société**, saisissez ’USMF’.</span><span class="sxs-lookup"><span data-stu-id="88ad1-128">In the **Company** field, type 'USMF'.</span></span>
20. <span data-ttu-id="88ad1-129">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-129">Click **Save**.</span></span>
21. <span data-ttu-id="88ad1-130">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-130">Click **Enable**.</span></span>
22. <span data-ttu-id="88ad1-131">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-131">Click **Yes**.</span></span>
23. <span data-ttu-id="88ad1-132">Cliquez sur **Rechercher les problèmes de partage**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-132">Click **Find sharing issues**.</span></span>
24. <span data-ttu-id="88ad1-133">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-133">Click **Yes**.</span></span>
25. <span data-ttu-id="88ad1-134">Cliquez sur **Mettre à jour la valeur du champ**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-134">Click **Update field value**.</span></span>
26. <span data-ttu-id="88ad1-135">Cliquez sur **Utiliser la valeur depuis la Société 1**.</span><span class="sxs-lookup"><span data-stu-id="88ad1-135">Click **Use value from company 1**.</span></span>
27. <span data-ttu-id="88ad1-136">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="88ad1-136">Refresh the page.</span></span>
28. <span data-ttu-id="88ad1-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="88ad1-137">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]