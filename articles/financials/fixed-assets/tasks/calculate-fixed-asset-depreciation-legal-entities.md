--- 
title: "Calculer l'amortissement des immobilisations dans les entités juridiques"
description: "Cette procédure décrit comment paramétrer et exécuter le processus d'amortissement pour plusieurs entités juridiques."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 662554b1b6bed63e5017aad3a292dad7a2f0bcea
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="5c28e-103">Calculer l'amortissement des immobilisations dans les entités juridiques</span><span class="sxs-lookup"><span data-stu-id="5c28e-103">Calculate fixed asset depreciation across legal entities</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5c28e-104">L'amortissement d'immobilisation peut être exécuté dans les entités juridiques en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="5c28e-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="5c28e-105">Cette procédure décrit comment paramétrer et exécuter le processus pour plusieurs entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="5c28e-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="5c28e-106">Elle utilise le rôle de comptable.</span><span class="sxs-lookup"><span data-stu-id="5c28e-106">It uses the accountant role.</span></span>  

<span data-ttu-id="5c28e-107">La société fictive USMF sert d'exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="5c28e-107">This recording uses the USMF demo company.</span></span>


<span data-ttu-id="5c28e-108">Étapes (16) sous-tâche : Paramétrer des journaux d'exécution d'amortissement de société croisée.</span><span class="sxs-lookup"><span data-stu-id="5c28e-108">Steps (16) Sub-task: Set up cross company depreciation run journals.</span></span> 

1. <span data-ttu-id="5c28e-109">Commencez par paramétrer les journaux à utiliser dans l'exécution de l'amortissement de société croisée dans chaque entité juridique.</span><span class="sxs-lookup"><span data-stu-id="5c28e-109">First, you must set up the journals to be used in the cross company depreciation run in each legal entity.</span></span> <span data-ttu-id="5c28e-110">Accédez à Immobilisations > Paramétrage > Paramètres des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="5c28e-110">Go to Fixed assets > Setup > Fixed assets parameters.</span></span> 
2. <span data-ttu-id="5c28e-111">Développez la section de propositions d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="5c28e-111">Expand the Fixed asset proposals section.</span></span> 
3. <span data-ttu-id="5c28e-112">Créez un enregistrement avec le nom de journal à utiliser pour chaque couche de validation dans l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="5c28e-112">Create a record with the journal name to be used for each posting layer in the legal entity.</span></span> <span data-ttu-id="5c28e-113">Si les registres ne sont pas validés dans la comptabilité, Aucun couche de validation doit être sélectionné avec le journal associé.</span><span class="sxs-lookup"><span data-stu-id="5c28e-113">If books do not post to the general ledger, then the None posting layer should be selected with the associated journal.</span></span> <span data-ttu-id="5c28e-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="5c28e-114">Click Add.</span></span> 
4. <span data-ttu-id="5c28e-115">Dans le champ Couche de validation, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5c28e-115">In the Posting layer field, enter or select a value.</span></span> 
5. <span data-ttu-id="5c28e-116">Dans le champ Nom de journal, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5c28e-116">In the Journal name field, enter or select a value.</span></span> 
6. <span data-ttu-id="5c28e-117">Répétez le paramétrage de journal sur la page Paramètres d'immobilisation dans chaque entité juridique.</span><span class="sxs-lookup"><span data-stu-id="5c28e-117">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span> 

<span data-ttu-id="5c28e-118">Sous-tâche : calculer l'amortissement</span><span class="sxs-lookup"><span data-stu-id="5c28e-118">Sub-task: Calculate depreciation</span></span>

1. <span data-ttu-id="5c28e-119">Utilisez la page Créer une proposition d'amortissement pour commencer l'exécution de l'amortissement dans les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="5c28e-119">Use the Create depreciation proposal page to start your depreciation run across legal entities.</span></span> <span data-ttu-id="5c28e-120">Accédez à Immobilisations > Entrées de journal > Créer une proposition d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="5c28e-120">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span> 
2. <span data-ttu-id="5c28e-121">Dans le champ Couche de validation, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5c28e-121">In the Posting layer field, enter or select a value.</span></span> 
3. <span data-ttu-id="5c28e-122">Le nom du journal sera issu par défaut des paramètres d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="5c28e-122">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="5c28e-123">Il peut être remplacé ici pour l'entité juridique actuelle.</span><span class="sxs-lookup"><span data-stu-id="5c28e-123">It can be changed here for the current legal entity.</span></span> 
4. <span data-ttu-id="5c28e-124">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="5c28e-124">In the To date field, enter a date.</span></span> 
5. <span data-ttu-id="5c28e-125">Sélectionnez les entités juridiques à inclure dans l'exécution d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="5c28e-125">Select the legal entities to be included in the depreciation run.</span></span> <span data-ttu-id="5c28e-126">Seules les entités juridiques avec les journaux paramétrés pour les propositions d'immobilisation sur la page Paramètres d'immobilisation sont affichées dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5c28e-126">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span> 
6. <span data-ttu-id="5c28e-127">Si elle est activée, l'option Valider les journaux valide automatiquement les journaux d'amortissement lors de leur création.</span><span class="sxs-lookup"><span data-stu-id="5c28e-127">When enabled, the Post journals option will automatically post the depreciation journals when they are created.</span></span> <span data-ttu-id="5c28e-128">Si elle n'est pas sélectionnée, les journaux sont créés, mais pas validés, afin que vous puissiez vérifier les détails avant la validation.</span><span class="sxs-lookup"><span data-stu-id="5c28e-128">When not selected, the journals will be created, but not posted, so you can review the details before posting.</span></span> <span data-ttu-id="5c28e-129">Sélectionnez Oui dans le champ Valider les journaux.</span><span class="sxs-lookup"><span data-stu-id="5c28e-129">Select Yes in the Post journals field.</span></span> 
7. <span data-ttu-id="5c28e-130">Les champs de filtrage incluent les immobilisations, les groupes, et les registres des entités juridiques sélectionnées pour cette exécution d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="5c28e-130">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span> 
8. <span data-ttu-id="5c28e-131">L'option de traitement par lots est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="5c28e-131">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="5c28e-132">Lorsque cette option est activée, la création et la validation du journal d'amortissement est exécutée en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="5c28e-132">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span> 
9. <span data-ttu-id="5c28e-133">Cliquez sur Créer un journal.</span><span class="sxs-lookup"><span data-stu-id="5c28e-133">Click Create journal.</span></span> 
10. <span data-ttu-id="5c28e-134">Vous devez afficher les journaux d'amortissement créés dans les entités juridiques appropriées.</span><span class="sxs-lookup"><span data-stu-id="5c28e-134">You must view the depreciation journals created in the respective legal entities.</span></span> <span data-ttu-id="5c28e-135">Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="5c28e-135">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

