---
title: Paramétrer des modèles de valeur
description: Cette procédure indique comment créer un nouveau registre d’immobilisations et l’associer à un groupe d’immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a59bafe3099b50d34bdd9e125cfb7f43d219dcc6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443233"
---
# <a name="set-up-value-models"></a><span data-ttu-id="d395e-103">Paramétrer des modèles de valeur</span><span class="sxs-lookup"><span data-stu-id="d395e-103">Set up value models</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d395e-104">Cette procédure indique comment créer un nouveau registre d’immobilisations et l’associer à un groupe d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="d395e-104">This procedure shows you to how create a new fixed asset book and associate it with a fixed asset group.</span></span> <span data-ttu-id="d395e-105">Elle utilise le rôle de comptable et les données de démonstration de l’entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="d395e-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-book"></a><span data-ttu-id="d395e-106">Créer un registre</span><span class="sxs-lookup"><span data-stu-id="d395e-106">Create a book</span></span>
1. <span data-ttu-id="d395e-107">Accédez à Immobilisations > Configuration > Registres.</span><span class="sxs-lookup"><span data-stu-id="d395e-107">Go to Fixed assets > Setup > Books.</span></span>
2. <span data-ttu-id="d395e-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d395e-108">Click New.</span></span>
3. <span data-ttu-id="d395e-109">Dans le champ Registre, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d395e-109">In the Book field, type a value.</span></span>
4. <span data-ttu-id="d395e-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d395e-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="d395e-111">Si Calculer l’amortissement est sélectionné, le registre d’actifs associé est inclus dans les propositions d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="d395e-111">If Calculate depreciation is selected, the associated asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="d395e-112">Si cette option n’est pas sélectionnée, le registre d’actifs n’est pas automatiquement amorti.</span><span class="sxs-lookup"><span data-stu-id="d395e-112">If it is not selected, the asset book will not be automatically depreciated.</span></span>  
5. <span data-ttu-id="d395e-113">Sélectionnez Oui dans le champ Calculer l’amortissement.</span><span class="sxs-lookup"><span data-stu-id="d395e-113">Select Yes in the Calculate depreciation field.</span></span>
6. <span data-ttu-id="d395e-114">Dans le champ Profil d’amortissement, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d395e-114">In the Depreciation profile field, enter or select a value.</span></span>
    * <span data-ttu-id="d395e-115">L’autre profil d’amortissement est également appelé : méthode de basculement d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="d395e-115">An alternative depreciation profile is also known as a switchover method of depreciation.</span></span> <span data-ttu-id="d395e-116">La proposition d’amortissement bascule sur ce profil lorsque l’autre profil calcule un montant d’amortissement égal ou supérieur au profil d’amortissement par défaut.</span><span class="sxs-lookup"><span data-stu-id="d395e-116">The depreciation proposal will switch to this profile when the alternative profile calculates a depreciation amount that is equal to or greater than the default depreciation profile.</span></span>  
    * <span data-ttu-id="d395e-117">Le profil d’amortissement exceptionnel est utilisé pour l’amortissement supplémentaire d’un actif dans des circonstances peu courantes.</span><span class="sxs-lookup"><span data-stu-id="d395e-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="d395e-118">Par exemple, vous pouvez utiliser cette opération pour enregistrer l’amortissement résultant d’une catastrophe naturelle.</span><span class="sxs-lookup"><span data-stu-id="d395e-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
    * <span data-ttu-id="d395e-119">Si l’option Créer des ajustements d’amortissement avec des amortissements de base est sélectionnée, les ajustements d’amortissement sont automatiquement créés lorsque la valeur de l’actif est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d395e-119">If Create depreciation adjustments with basis adjustments is selected, depreciation adjustments will be automatically created when the value of the asset is updated.</span></span> <span data-ttu-id="d395e-120">Si elle n’est pas activée, la valeur d’immobilisation mise à jour affecte uniquement les prochains calculs d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="d395e-120">If it is not selected, the updated asset value will only affect depreciation calculations going forward.</span></span>  
7. <span data-ttu-id="d395e-121">Sélectionnez Oui dans le champ Créer des ajustements d’amortissement avec des amortissements de base.</span><span class="sxs-lookup"><span data-stu-id="d395e-121">Select Yes in the Create depreciation adjustments with basis adjustments field.</span></span>
    * <span data-ttu-id="d395e-122">Par défaut, les transactions du registre des immobilisations sont validées dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="d395e-122">By default, fixed asset book transactions will post to the general ledger.</span></span> <span data-ttu-id="d395e-123">Vous pouvez désactiver la validation dans la comptabilité pour le registre en définissant le champ Valider dans la comptabilité sur Non.</span><span class="sxs-lookup"><span data-stu-id="d395e-123">You can disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="d395e-124">Les registres qui ne sont pas validés dans la comptabilité sont généralement utilisés à des fins de déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="d395e-124">Books that do not post to the general ledger are typically used for tax reporting purposes.</span></span> <span data-ttu-id="d395e-125">Cela vous donne une flexibilité supplémentaire pour supprimer les transactions historiques du registre des actifs, car elles n’ont pas été validées dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="d395e-125">This gives you additional flexibility to delete historical transactions for the asset book because they have not been committed to the general ledger.</span></span>  
    * <span data-ttu-id="d395e-126">La couche de validation est définie par défaut sur la couche actuelle si le registre est validé dans la comptabilité, et sur Aucun s’il n’est pas validé dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="d395e-126">The Posting layer defaults to the Current layer if the book posts to general ledger, and None if it does not post to general ledger.</span></span> <span data-ttu-id="d395e-127">Mettez la couche de validation à jour si des transactions de ce registre doivent être validées sur une couche de validation différente.</span><span class="sxs-lookup"><span data-stu-id="d395e-127">Update Posting layer if you need transactions for this book to be posted to a different layer.</span></span>  
8. <span data-ttu-id="d395e-128">Saisissez ou sélectionnez une valeur dans le champ Calendrier.</span><span class="sxs-lookup"><span data-stu-id="d395e-128">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="d395e-129">Les registres dérivés valident simultanément les transactions sur des registres différents.</span><span class="sxs-lookup"><span data-stu-id="d395e-129">Derived books will post transactions to different books at the same time.</span></span> <span data-ttu-id="d395e-130">Vous créez les transactions avec le registre principal et pendant la validation, une copie exacte de la transaction est validée dans le registre dérivé.</span><span class="sxs-lookup"><span data-stu-id="d395e-130">You create the transactions with the primary book and during posting, an exact copy of the transaction is posted to the derived book.</span></span> <span data-ttu-id="d395e-131">Aucun recalcul n’est nécessaire avec les transactions du registre dérivé ; il ne doit donc pas être utilisé pour les transactions d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="d395e-131">There is no recalculation with derived book transactions, so it should not be used for depreciation transactions.</span></span>  

## <a name="associate-the-book-with-a-fixed-asset-group"></a><span data-ttu-id="d395e-132">Associer le registre à un groupe d’immobilisations</span><span class="sxs-lookup"><span data-stu-id="d395e-132">Associate the book with a fixed asset group</span></span>
1. <span data-ttu-id="d395e-133">Cliquez sur Groupes d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="d395e-133">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="d395e-134">Saisissez ou sélectionnez une valeur dans le champ Groupe d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="d395e-134">In the Fixed asset group field, enter or select a value.</span></span>
3. <span data-ttu-id="d395e-135">Entrez un nombre dans le champ Durée de vie.</span><span class="sxs-lookup"><span data-stu-id="d395e-135">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="d395e-136">Notez que les périodes d’amortissement sont calculées après la définition de la durée de vie.</span><span class="sxs-lookup"><span data-stu-id="d395e-136">Note that Depreciation periods is calculated after setting the Service life.</span></span>  
    * <span data-ttu-id="d395e-137">Vous pouvez définir la convention d’amortissement comme requis pour les besoins fiscaux.</span><span class="sxs-lookup"><span data-stu-id="d395e-137">You are able to set the depreciation convention as required for tax purposes.</span></span>  

