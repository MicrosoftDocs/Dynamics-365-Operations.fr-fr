---
title: " Créer, calculer et valider un relevé pour un magasin de vente au détail"
description: Cette procédure décrit les étapes manuelles pour créer, calculer et valider un relevé pour un magasin.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9ea30e7e008bfcce77a7ee2f4d7d01a6cf1ababc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "354389"
---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a><span data-ttu-id="7bd4c-103"> Créer, calculer et valider un relevé pour un magasin de vente au détail</span><span class="sxs-lookup"><span data-stu-id="7bd4c-103">Create, calculate, and post a statement for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="7bd4c-104">Cette procédure décrit les étapes manuelles pour créer, calculer et valider un relevé pour un magasin.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="7bd4c-105">Des traitements par lots peuvent également être configurés pour les mêmes tâches.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="7bd4c-106">Les étapes de configuration et d'exécution des traitements par lots sont disponibles dans d'autres rubriques.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="7bd4c-107">Pour effectuer cette procédure, vous devez disposer des transactions effectuées dans le PDV et extraites dans Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="7bd4c-108">Cet enregistrement utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="7bd4c-109">Cette procédure peut faire référence à Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="7bd4c-110">Notez que Dynamics AX est maintenant appelé Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="7bd4c-111">Accédez à Tous les espaces de travail > ..</span><span class="sxs-lookup"><span data-stu-id="7bd4c-111">Go to All workspaces > ..</span></span> <span data-ttu-id="7bd4c-112">> Finances du magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-112">> Retail store financials.</span></span>
2. <span data-ttu-id="7bd4c-113">Cliquez sur Nouveau relevé.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-113">Click New statement.</span></span>
3. <span data-ttu-id="7bd4c-114">Dans le champ Numéro de magasin, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7bd4c-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7bd4c-116">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-116">Click OK.</span></span>
    * <span data-ttu-id="7bd4c-117">Le groupe Paramétrage contient les paramètres qui contrôlent les transactions incluses dans le relevé et leur regroupement en lignes de relevé.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="7bd4c-118">Vous pouvez ouvrir le groupe Paramétrage et modifier ces paramètres, ou vous pouvez utiliser les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="7bd4c-119">Le champ Méthode de relevé définit la manière dont les lignes de relevé sont regroupées.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="7bd4c-120">Sélectionnez un membre du personnel ou une caisse enregistreuse si vous souhaitez calculer un relevé uniquement pour ce membre du personnel ou cette caisse enregistreuse spécifique.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="7bd4c-121">Dans le champ Méthode de clôture, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="7bd4c-122">Cliquez sur Calcul du relevé.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="7bd4c-123">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-123">Click Yes.</span></span>
    * <span data-ttu-id="7bd4c-124">Après le calcul du relevé, des lignes doivent être créées avec les montants totaux pour chaque mode de paiement et chaque méthode de relevé utilisé.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="7bd4c-125">Saisissez un montant compté dans chaque ligne s'il doit être saisi ou mis à jour.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="7bd4c-126">Le champ Compté est renseigné avec les montants des comptages de caisse effectués dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="7bd4c-127">Cliquez sur Validation du relevé.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-127">Click Post statement.</span></span>
10. <span data-ttu-id="7bd4c-128">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-128">Click Close.</span></span>
11. <span data-ttu-id="7bd4c-129">Accédez à Commerce et vente au détail > Canaux > Finances du magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="7bd4c-130">Cliquez sur l'onglet Relevés validés.</span><span class="sxs-lookup"><span data-stu-id="7bd4c-130">Click the Posted statements tab.</span></span>

