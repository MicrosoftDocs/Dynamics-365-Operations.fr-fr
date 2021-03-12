---
title: Calculer l’amortissement des immobilisations dans les entités juridiques
description: L’amortissement d’immobilisation peut être exécuté dans les entités juridiques en une seule étape.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b09bbe4d0143aa521ca0a4cf67e86b7165b0f4f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968952"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="a13ed-103">Calculer l’amortissement des immobilisations dans les entités juridiques</span><span class="sxs-lookup"><span data-stu-id="a13ed-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a13ed-104">L’amortissement d’immobilisation peut être exécuté dans les entités juridiques en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="a13ed-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="a13ed-105">Cette procédure décrit comment paramétrer et exécuter le processus pour plusieurs entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="a13ed-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="a13ed-106">Elle utilise le rôle de comptable et les données de démonstration de l’entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="a13ed-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="a13ed-107">Paramétrer les journaux d’exécution de l’amortissement entre sociétés</span><span class="sxs-lookup"><span data-stu-id="a13ed-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="a13ed-108">Accédez à Immobilisations > Paramétrage > Paramètres des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a13ed-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="a13ed-109">Développez la section de propositions d’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a13ed-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="a13ed-110">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="a13ed-110">Click Add.</span></span>
4. <span data-ttu-id="a13ed-111">Dans le champ Couche de validation, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a13ed-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="a13ed-112">Dans le champ Nom de journal, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a13ed-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="a13ed-113">Répétez le paramétrage de journal sur la page Paramètres d’immobilisation dans chaque entité juridique.</span><span class="sxs-lookup"><span data-stu-id="a13ed-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="a13ed-114">Exécution de l’amortissement</span><span class="sxs-lookup"><span data-stu-id="a13ed-114">Depreciation run</span></span>
1. <span data-ttu-id="a13ed-115">Accédez à Immobilisations > Entrées de journal > Créer une proposition d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="a13ed-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="a13ed-116">Dans le champ Couche de validation, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a13ed-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="a13ed-117">Le nom du journal sera issu par défaut des paramètres d’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a13ed-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="a13ed-118">Il peut être remplacé ici pour l’entité juridique actuelle.</span><span class="sxs-lookup"><span data-stu-id="a13ed-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="a13ed-119">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="a13ed-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="a13ed-120">Sélectionnez les entités juridiques à inclure dans l’exécution d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="a13ed-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="a13ed-121">Seules les entités juridiques avec les journaux paramétrés pour les propositions d’immobilisation sur la page Paramètres d’immobilisation sont affichées dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a13ed-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="a13ed-122">Sélectionnez Oui dans le champ Valider les journaux.</span><span class="sxs-lookup"><span data-stu-id="a13ed-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="a13ed-123">Les champs de filtrage incluent les immobilisations, les groupes, et les registres des entités juridiques sélectionnées pour cette exécution d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="a13ed-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="a13ed-124">L’option de traitement par lots est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="a13ed-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="a13ed-125">Lorsque cette option est activée, la création et la validation du journal d’amortissement est exécutée en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="a13ed-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="a13ed-126">Cliquez sur Créer un journal.</span><span class="sxs-lookup"><span data-stu-id="a13ed-126">Click Create journal.</span></span>
6. <span data-ttu-id="a13ed-127">Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a13ed-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

