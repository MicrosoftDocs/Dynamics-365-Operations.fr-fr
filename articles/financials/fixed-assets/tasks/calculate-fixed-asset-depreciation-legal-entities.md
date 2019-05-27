---
title: Calculer l'amortissement des immobilisations dans les entités juridiques
description: L'amortissement d'immobilisation peut être exécuté dans les entités juridiques en une seule étape.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2575354af322827972ffa650e9c732170c5a6eb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566538"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="2e93c-103">Calculer l'amortissement des immobilisations dans les entités juridiques</span><span class="sxs-lookup"><span data-stu-id="2e93c-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e93c-104">L'amortissement d'immobilisation peut être exécuté dans les entités juridiques en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="2e93c-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="2e93c-105">Cette procédure décrit comment paramétrer et exécuter le processus pour plusieurs entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="2e93c-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="2e93c-106">Elle utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="2e93c-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="2e93c-107">Paramétrer les journaux d'exécution de l'amortissement entre sociétés</span><span class="sxs-lookup"><span data-stu-id="2e93c-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="2e93c-108">Accédez à Immobilisations > Paramétrage > Paramètres des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="2e93c-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="2e93c-109">Développez la section de propositions d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="2e93c-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="2e93c-110">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="2e93c-110">Click Add.</span></span>
4. <span data-ttu-id="2e93c-111">Dans le champ Couche de validation, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2e93c-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="2e93c-112">Dans le champ Nom de journal, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2e93c-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="2e93c-113">Répétez le paramétrage de journal sur la page Paramètres d'immobilisation dans chaque entité juridique.</span><span class="sxs-lookup"><span data-stu-id="2e93c-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="2e93c-114">Exécution de l'amortissement</span><span class="sxs-lookup"><span data-stu-id="2e93c-114">Depreciation run</span></span>
1. <span data-ttu-id="2e93c-115">Accédez à Immobilisations > Entrées de journal > Créer une proposition d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="2e93c-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="2e93c-116">Dans le champ Couche de validation, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2e93c-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="2e93c-117">Le nom du journal sera issu par défaut des paramètres d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="2e93c-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="2e93c-118">Il peut être remplacé ici pour l'entité juridique actuelle.</span><span class="sxs-lookup"><span data-stu-id="2e93c-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="2e93c-119">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="2e93c-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="2e93c-120">Sélectionnez les entités juridiques à inclure dans l'exécution d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="2e93c-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="2e93c-121">Seules les entités juridiques avec les journaux paramétrés pour les propositions d'immobilisation sur la page Paramètres d'immobilisation sont affichées dans la liste.</span><span class="sxs-lookup"><span data-stu-id="2e93c-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="2e93c-122">Sélectionnez Oui dans le champ Valider les journaux.</span><span class="sxs-lookup"><span data-stu-id="2e93c-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="2e93c-123">Les champs de filtrage incluent les immobilisations, les groupes, et les registres des entités juridiques sélectionnées pour cette exécution d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="2e93c-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="2e93c-124">L'option de traitement par lots est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2e93c-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="2e93c-125">Lorsque cette option est activée, la création et la validation du journal d'amortissement est exécutée en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="2e93c-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="2e93c-126">Cliquez sur Créer un journal.</span><span class="sxs-lookup"><span data-stu-id="2e93c-126">Click Create journal.</span></span>
6. <span data-ttu-id="2e93c-127">Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="2e93c-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

