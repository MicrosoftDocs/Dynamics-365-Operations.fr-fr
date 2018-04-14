--- 
title: "Paramétrer la déclaration de la balance des paiements (Belgique)"
description: "Utilisez cette procédure pour paramétrer les informations BLWI (Belgisch Luxemburgs Wissel Instituut) pour la Belgique."
author: v-oloski
manager: AnnBe
ms.date: 07/12/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Belgium
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7bee83705d6d27941cd08084710042e8200f40c2
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-payment-balance-reporting-belgium"></a><span data-ttu-id="950c5-103">Paramétrer la déclaration de la balance des paiements (Belgique)</span><span class="sxs-lookup"><span data-stu-id="950c5-103">Set up payment balance reporting (Belgium)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="950c5-104">Utilisez cette procédure pour paramétrer les informations BLWI (Belgisch Luxemburgs Wissel Instituut) pour la Belgique.</span><span class="sxs-lookup"><span data-stu-id="950c5-104">Use this procedure to set up Belgisch Luxemburgs Wissel Instituut (BLWI) information for Belgium.</span></span> <span data-ttu-id="950c5-105">Cette procédure a été créée à l'aide de la société fictive USSI.</span><span class="sxs-lookup"><span data-stu-id="950c5-105">This procedure was created by using the USSI demo data company.</span></span>

<span data-ttu-id="950c5-106">Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en Belgique.</span><span class="sxs-lookup"><span data-stu-id="950c5-106">This functionality is available for legal entities that have their primary address in Belgium.</span></span> <span data-ttu-id="950c5-107">Avant d'exécuter cette procédure, vous devez paramétrer l'ID enregistrement pour la Belgique et entrer le numéro d'enregistrement qui doit être utilisé pour créer la déclaration BLWI.</span><span class="sxs-lookup"><span data-stu-id="950c5-107">Before you can complete this procedure, you must set up the registration ID for Belgium and enter the registration number that should be used to create the BLWI declaration.</span></span>


## <a name="set-up-a-blwi-countryregion-group"></a><span data-ttu-id="950c5-108">Paramétrer un groupe de pays/régions BLWI</span><span class="sxs-lookup"><span data-stu-id="950c5-108">Set up a BLWI country/region group</span></span>
1. <span data-ttu-id="950c5-109">Accédez à Taxe > Paramétrage > Commerce extérieur > Groupes de pays/régions BLWI.</span><span class="sxs-lookup"><span data-stu-id="950c5-109">Go to Tax > Setup > Foreign trade > BLWI country/region groups.</span></span>
2. <span data-ttu-id="950c5-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="950c5-110">Click New.</span></span>
3. <span data-ttu-id="950c5-111">Dans le champ ID groupe, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-111">In the Group ID field, type a value.</span></span>
4. <span data-ttu-id="950c5-112">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="950c5-113">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="950c5-113">Click Add.</span></span>
6. <span data-ttu-id="950c5-114">Dans le champ Pays/Région, sélectionnez ou entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-114">In the Country/region field, enter or select a value.</span></span>
7. <span data-ttu-id="950c5-115">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="950c5-115">In the Description field, type a value.</span></span>
8. <span data-ttu-id="950c5-116">Cliquez sur Traductions.</span><span class="sxs-lookup"><span data-stu-id="950c5-116">Click Translations.</span></span>
9. <span data-ttu-id="950c5-117">Dans le champ Langue, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-117">In the Language field, enter or select a value.</span></span>
10. <span data-ttu-id="950c5-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="950c5-118">Close the page.</span></span>

## <a name="set-up-blwi-currencies"></a><span data-ttu-id="950c5-119">Paramétrer les devises BLWI</span><span class="sxs-lookup"><span data-stu-id="950c5-119">Set up BLWI currencies</span></span>
1. <span data-ttu-id="950c5-120">Accédez à Taxe > Paramétrage > Commerce extérieur > Devises BLWI.</span><span class="sxs-lookup"><span data-stu-id="950c5-120">Go to Tax > Setup > Foreign trade > BLWI currencies.</span></span>
2. <span data-ttu-id="950c5-121">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="950c5-121">Click New.</span></span>
3. <span data-ttu-id="950c5-122">Dans le champ Devise, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-122">In the Currency field, enter or select a value.</span></span>
4. <span data-ttu-id="950c5-123">Activez la case à cocher État dans cette devise.</span><span class="sxs-lookup"><span data-stu-id="950c5-123">Select the Report in this currency check box.</span></span>
5. <span data-ttu-id="950c5-124">Dans le champ Numéro colonne, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-124">In the Column number field, enter a number.</span></span>

## <a name="set-up-blwi-parameters"></a><span data-ttu-id="950c5-125">Définition des paramètres BLWI</span><span class="sxs-lookup"><span data-stu-id="950c5-125">Set up BLWI parameters</span></span>
1. <span data-ttu-id="950c5-126">Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres BLWI.</span><span class="sxs-lookup"><span data-stu-id="950c5-126">Go to Tax > Setup > Foreign trade > BLWI parameters.</span></span>
2. <span data-ttu-id="950c5-127">Sélectionnez Oui dans le champ BLWI.</span><span class="sxs-lookup"><span data-stu-id="950c5-127">Select Yes in the BLWI field.</span></span>
    * <span data-ttu-id="950c5-128">Ce paramètre doit être activé avant de valider les transactions client/fournisseur, afin que les transactions soient transférées vers la balance des paiements.</span><span class="sxs-lookup"><span data-stu-id="950c5-128">This parameter should be activated before you post customer/vendor transactions, so that the transactions are transferred to the payment balance.</span></span>  
3. <span data-ttu-id="950c5-129">Dans le champ E-mail, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-129">In the Email field, type a value.</span></span>
4. <span data-ttu-id="950c5-130">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="950c5-130">In the Name field, type a value.</span></span>
5. <span data-ttu-id="950c5-131">Dans le champ Téléphone, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-131">In the Telephone field, type a value.</span></span>
6. <span data-ttu-id="950c5-132">Dans le champ Télécopie, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-132">In the Fax field, type a value.</span></span>
7. <span data-ttu-id="950c5-133">Dans le champ Vérifier le code BLWI dans les journaux, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="950c5-133">In the Check BLWI code on journals field, select an option.</span></span>
    * <span data-ttu-id="950c5-134">Dans le champ Vérifier le code BLWI, sélectionnez la règle permettant de vérifier qu'un code objectif de paiement est spécifié dans les documents.</span><span class="sxs-lookup"><span data-stu-id="950c5-134">In the Check BLWI code field, select the rule for checking that a payment purpose code is specified in documents.</span></span> <span data-ttu-id="950c5-135">Les options disponibles sont Aucun, Avertissement et Erreur.</span><span class="sxs-lookup"><span data-stu-id="950c5-135">The available options are None, Warning, and Error.</span></span> <span data-ttu-id="950c5-136">Si une transaction a un client/fournisseur situé à l'étranger (autrement dit, le pays/la région du client/fournisseur est différent du pays/de la région de l'entité juridique), la transaction n'a pas de code objectif de paiement affecté et la vérification est définie sur Avertissement ou Erreur, un message d'avertissement ou d'erreur s'affiche lors de la validation.</span><span class="sxs-lookup"><span data-stu-id="950c5-136">If a transaction has a customer/vendor that is located in a foreign country/region (that is, the country/region of the customer/vendor differs from the country/region of the legal entity), the transaction doesn’t have an assigned payment purpose code, and the check is set to Warning or Error, either a warning or error message will be shown during posting.</span></span> <span data-ttu-id="950c5-137">Cette validation est appliquée à toutes les transactions client/fournisseur sauf les transactions de paiement.</span><span class="sxs-lookup"><span data-stu-id="950c5-137">This validation is applied for all customer/vendor transactions except payment transactions.</span></span>  
8. <span data-ttu-id="950c5-138">Saisissez ou sélectionnez une valeur dans le champ Mise en correspondance des formats.</span><span class="sxs-lookup"><span data-stu-id="950c5-138">In the Format mapping field, enter or select a value.</span></span>
    * <span data-ttu-id="950c5-139">Conditions préalables : vous devez télécharger la configuration (BE) du format BLWI pour les états électroniques auprès de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="950c5-139">Prerequisite: You should upload the BLWI format (BE) configuration for Electronic reporting (ER) from Microsoft Dynamics Lifecycle Services (LCS).</span></span>  

## <a name="set-up-payment-survey-codes"></a><span data-ttu-id="950c5-140">Paramétrer des codes étude de paiement</span><span class="sxs-lookup"><span data-stu-id="950c5-140">Set up payment survey codes</span></span>
1. <span data-ttu-id="950c5-141">Accédez à Taxe > Paramétrage > Commerce extérieur > Codes étude de paiement.</span><span class="sxs-lookup"><span data-stu-id="950c5-141">Go to Tax > Setup > Foreign trade > Payment survey codes.</span></span>
2. <span data-ttu-id="950c5-142">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="950c5-142">Click New.</span></span>
3. <span data-ttu-id="950c5-143">Dans le champ Code étude, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-143">In the Survey code field, type a value.</span></span>
4. <span data-ttu-id="950c5-144">Dans le champ Mois/trimestre, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="950c5-144">In the Month/Quarter field, select an option.</span></span>
5. <span data-ttu-id="950c5-145">Dans le champ Type de calcul, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="950c5-145">In the Calculation type field, select an option.</span></span>
    * <span data-ttu-id="950c5-146">Si vous sélectionnez Chiffre d'affaires dans le champ Type de calcul, les transactions client/fournisseur validées au cours de la période de déclaration sont transférées vers la balance des paiements, et le montant déclaré est le montant total de la transaction validée.</span><span class="sxs-lookup"><span data-stu-id="950c5-146">If you select Turnover in the Calculation type field, the customer/vendor transactions that are posted during the reporting period are transferred to the payment balance, and the amount that is reported is the total amount of the posted transaction.</span></span>  <span data-ttu-id="950c5-147">Si vous sélectionnez Solde, les transactions client/fournisseur en cours (partiellement réglées/clôturées) à la fin de la période de déclaration sont transférées vers la balance des paiements, et le montant déclaré est le montant en cours (non réglé) de la transaction validée à la fin de la période de déclaration.</span><span class="sxs-lookup"><span data-stu-id="950c5-147">If you select Balance, the customer/vendor transactions that are open (not fully settled/closed) at the end of the reporting period are transferred to the payment balance, and the amount that is reported is the open (unsettled) amount of the posted transaction as of the end of the reporting period.</span></span>  
6. <span data-ttu-id="950c5-148">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-148">In the Description field, type a value.</span></span>
7. <span data-ttu-id="950c5-149">Dans le champ Synthèse pays/région, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-149">In the Summary country/region field, type a value.</span></span>
8. <span data-ttu-id="950c5-150">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="950c5-150">Click Add.</span></span>
9. <span data-ttu-id="950c5-151">Dans le champ Code objectif de la banque centrale, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="950c5-151">In the Central bank purpose code field, enter or select a value.</span></span>
10. <span data-ttu-id="950c5-152">Activez la case à cocher Inclure le paiement.</span><span class="sxs-lookup"><span data-stu-id="950c5-152">Select the Include payment check box.</span></span>
    * <span data-ttu-id="950c5-153">Notez que les transactions de paiement ne sont pas transférées vers l'étude de la balance des paiements par défaut.</span><span class="sxs-lookup"><span data-stu-id="950c5-153">Note that payment transactions won't be transferred to the payment balance survey by default.</span></span> <span data-ttu-id="950c5-154">L'utilisateur doit activer le champ Inclure le paiement pour les codes objectif.</span><span class="sxs-lookup"><span data-stu-id="950c5-154">The user must activate the Include payment field for purpose codes.</span></span>  


