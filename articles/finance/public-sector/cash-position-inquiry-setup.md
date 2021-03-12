---
title: Configurer et exécuter les renseignements sur l’emplacement des disponibilités
description: Cette rubrique fournit des informations sur les renseignements sur l’emplacement des disponibilités. Ces renseignements vous permettent de déterminer les emplacements de disponibilités correspondants pour les ensembles de dimensions financières contenant des dimensions en équilibre.
author: velofog
manager: AnnBe
ms.date: 10/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: public sector
ms.author: roschlom
ms.search.validFrom: 2019-10-07
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 62a3986e6a1aa5d4af9b829b07a0b3a2486b28ba
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971182"
---
# <a name="set-up-and-run-the-cash-position-inquiry"></a><span data-ttu-id="93581-104">Configurer et exécuter les renseignements sur l’emplacement des disponibilités</span><span class="sxs-lookup"><span data-stu-id="93581-104">Set up and run the Cash position inquiry</span></span>
[!include [banner](../includes/banner.md)]


<span data-ttu-id="93581-105">Cette rubrique fournit des informations sur les renseignements sur l’emplacement des disponibilités.</span><span class="sxs-lookup"><span data-stu-id="93581-105">This topic provides information about the Cash position inquiry.</span></span> <span data-ttu-id="93581-106">Ces renseignements vous permettent de déterminer les emplacements de disponibilités correspondants pour les ensembles de dimensions financières contenant des dimensions en équilibre.</span><span class="sxs-lookup"><span data-stu-id="93581-106">This inquiry lets you determine the corresponding cash positions for financial dimension sets that contain self-balancing dimensions.</span></span> <span data-ttu-id="93581-107">Ils montrent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="93581-107">It shows the following items:</span></span>

- <span data-ttu-id="93581-108">Le solde des disponibilités d’ouverture</span><span class="sxs-lookup"><span data-stu-id="93581-108">The beginning cash balance</span></span>
- <span data-ttu-id="93581-109">L’effet de l’ajout de rentrées de fonds</span><span class="sxs-lookup"><span data-stu-id="93581-109">The effect of the addition of cash receipts</span></span>
- <span data-ttu-id="93581-110">La soustraction des décaissements en espèces</span><span class="sxs-lookup"><span data-stu-id="93581-110">The subtraction of cash disbursements</span></span>
- <span data-ttu-id="93581-111">La soustraction des transferts interfonds pour arriver à un solde final</span><span class="sxs-lookup"><span data-stu-id="93581-111">The subtraction of interfund transfers to arrive at an ending balance</span></span>
- <span data-ttu-id="93581-112">La soustraction des réservations budgétaires générales, des engagements ou des engagements préalables du solde de clôture pour obtenir à un solde non engagé.</span><span class="sxs-lookup"><span data-stu-id="93581-112">The subtraction of general budget reservations, encumbrances, or pre-encumbrances from the ending balance to arrive at an unencumbered balance</span></span>

<span data-ttu-id="93581-113">Ces renseignements diffèrent des autres renseignements, car ils permettent aux utilisateurs de personnaliser la terminologie pour les noms de colonne et pour les comptes principaux utilisés pour fournir des montants aux colonnes.</span><span class="sxs-lookup"><span data-stu-id="93581-113">This inquiry differs from other inquiries because you can customize the terminology for column names and for the main accounts that are used to derive the amounts that appear in the columns.</span></span> <span data-ttu-id="93581-114">Sur la page **Paramètres de l’emplacement des disponibilités**, les colonnes qui apparaissent dans les renseignements sont numérotées séquentiellement de gauche à droite.</span><span class="sxs-lookup"><span data-stu-id="93581-114">On the **Cash position parameters** page, the columns that appear in the inquiry are numbered sequentially from left to right.</span></span> <span data-ttu-id="93581-115">La colonne la plus à gauche est la **Colonne Une**.</span><span class="sxs-lookup"><span data-stu-id="93581-115">The left-most column is **Column one**.</span></span>

## <a name="set-up-the-cash-position-inquiry"></a><span data-ttu-id="93581-116">Configurer les renseignements sur l’emplacement des disponibilités</span><span class="sxs-lookup"><span data-stu-id="93581-116">Set up the Cash position inquiry</span></span>

1. <span data-ttu-id="93581-117">Accédez à **Comptabilité générale \> Paramétrage de la comptabilité \> Paramètres de l’emplacement des disponibilités**.</span><span class="sxs-lookup"><span data-stu-id="93581-117">Go to **General ledger \> Ledger setup \> Cash position parameters**.</span></span>
2. <span data-ttu-id="93581-118">Dans le groupe **Paramètres de l’emplacement des disponibilités**, dans la **Colonne Une** procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="93581-118">On the **Cash position parameters** page, in the **Column one** group, follow these steps:</span></span>

    - <span data-ttu-id="93581-119">Dans le champ **Nom de la colonne**, entrez une étiquette à utiliser comme en-tête pour la première colonne de la recherche (par exemple, **Solde d’ouverture**).</span><span class="sxs-lookup"><span data-stu-id="93581-119">In the **Column name** field, enter a label for the heading of the first column in the inquiry (for example, **Beginning balance**).</span></span>
    - <span data-ttu-id="93581-120">Dans le champ **Comptes principaux de solde d’ouverture**, sélectionnez les comptes que vous souhaitez référencer pour lancer des recherches sur le solde d’ouverture.</span><span class="sxs-lookup"><span data-stu-id="93581-120">In the **Opening balance main accounts** field, select the accounts that you want to reference for inquiries about the opening balance.</span></span>

3. <span data-ttu-id="93581-121">Dans le groupe **Colonne Deux**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="93581-121">In the **Column two** group, follow these steps:</span></span>

    - <span data-ttu-id="93581-122">Entrez un libellé pour l’en-tête de la deuxième colonne (par exemple, **Rentrées de fonds**).</span><span class="sxs-lookup"><span data-stu-id="93581-122">Enter a label for the heading of the second column (for example, **Cash receipts**).</span></span>
    - <span data-ttu-id="93581-123">Pour utiliser uniquement la somme de tous les montants de transactions de débit et de crédit pour les données incluses dans la recherche, sélectionnez les comptes principaux dans la liste **Comptes principaux de débit et de crédit**.</span><span class="sxs-lookup"><span data-stu-id="93581-123">To use only the sum of all debit and credit transaction amounts for the data that is included in the inquiry, select the main accounts in the **Debit and credit main accounts** list.</span></span>
    
        <span data-ttu-id="93581-124">La recherche ajoute le montant net des comptes débiteurs et créditeurs ainsi que les montants de débit et de crédit des comptes principaux spécifiés dans les autres champs du groupe.</span><span class="sxs-lookup"><span data-stu-id="93581-124">The inquiry will add the net amount of the debit and credit accounts, plus the debit and credit amounts from the main accounts that are specified in the other fields in the group.</span></span>

    - <span data-ttu-id="93581-125">Pour utiliser uniquement la somme de tous les montants de transactions de débit pour les données de la recherche, sélectionnez les comptes principaux dans la liste **Comptes principaux de débit uniquement**.</span><span class="sxs-lookup"><span data-stu-id="93581-125">To use only the sum of all debit transaction amounts for the inquiry's data, select the main accounts in the **Debit-only main accounts** list.</span></span>
    - <span data-ttu-id="93581-126">Pour utiliser uniquement la somme de tous les montants de transactions de crédit pour les données de la recherche, sélectionnez les comptes principaux dans la liste **Comptes principaux de crédit uniquement**.</span><span class="sxs-lookup"><span data-stu-id="93581-126">To use only the sum of all credit transaction amounts for the inquiry's data, select the main accounts in the **Credit-only main accounts** list.</span></span>

4. <span data-ttu-id="93581-127">Dans les groupes **Colonne Trois** et **Colonne Quatre**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="93581-127">In the **Column three** and **Column four** groups, follow these steps:</span></span>

    - <span data-ttu-id="93581-128">Entrez un libellé pour l’en-tête de la troisième colonne (par exemple, **Déboursements de disponibilités**) et la quatrième colonne (par exemple, **Transferts interfonds**).</span><span class="sxs-lookup"><span data-stu-id="93581-128">Enter a label for the heading of the third column (for example, **Cash disbursements**) and the fourth column (for example, **Interfund transfers**).</span></span>
    - <span data-ttu-id="93581-129">Pour les deux colonnes, spécifiez les comptes principaux pour distribuer les entrées de débit et de crédit.</span><span class="sxs-lookup"><span data-stu-id="93581-129">For both columns, specify the main accounts to distribute debit and credit entries.</span></span> <span data-ttu-id="93581-130">Spécifiez également les comptes principaux de débit uniquement et les comptes principaux de crédit uniquement.</span><span class="sxs-lookup"><span data-stu-id="93581-130">Also specify the debit-only main accounts and credit-only main accounts.</span></span>

5. <span data-ttu-id="93581-131">Dans le groupe **Colonne Cinq**, entrez un libellé pour l’en-tête de la cinquième colonne (par exemple, **Solde de clôture**).</span><span class="sxs-lookup"><span data-stu-id="93581-131">In the **Column five** group, enter a label for the heading of the fifth column (for example, **Ending balance**).</span></span>

    <span data-ttu-id="93581-132">Un résultat est automatiquement calculé à partir des comptes que vous avez spécifiés dans les quatre premières colonnes.</span><span class="sxs-lookup"><span data-stu-id="93581-132">A result is automatically calculated from the accounts that you specified in the first four columns.</span></span> <span data-ttu-id="93581-133">Pour cet exemple, le calcul est Solde de départ + Encaissements - Décaissements - Transferts interfonds.</span><span class="sxs-lookup"><span data-stu-id="93581-133">For this example, the calculation is Beginning balance + Cash receipts – Cash disbursements – Interfund transfers.</span></span>

6. <span data-ttu-id="93581-134">Dans les groupes **Colonne Six** et **Colonne Sept**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="93581-134">In the **Column six** and **Column seven** groups, follow these steps:</span></span>

    - <span data-ttu-id="93581-135">Entrez une étiquette pour l’en-tête de la sixième colonne (par exemple, **Réservations budgétaires générales** ou **Non engagements**) et la septième colonne (par exemple, **Engagements préalables**).</span><span class="sxs-lookup"><span data-stu-id="93581-135">Enter a label for the heading of the sixth column (for example, **General budget reservations** or **Encumbrances**) and the seventh column (for example, **Pre-encumbrances**).</span></span>
    - <span data-ttu-id="93581-136">Pour les deux colonnes, spécifiez les numéros de compte des comptes principaux de débit et de crédit, et pour les comptes principaux réservés au débit et des comptes principaux réservés au crédit.</span><span class="sxs-lookup"><span data-stu-id="93581-136">For both columns, specify account numbers for the debit and credit main accounts, and for the debit-only main accounts and credit-only main accounts.</span></span>

7. <span data-ttu-id="93581-137">Dans le groupe **Colonne Huit**, entrez un libellé pour l’en-tête de la huitième colonne (par exemple, **Solde non engagé**).</span><span class="sxs-lookup"><span data-stu-id="93581-137">In the **Column eight** group, enter a label for the heading of the eighth column (for example, **Unencumbered balance**).</span></span>

    <span data-ttu-id="93581-138">Un résultat est automatiquement calculé à partir des comptes que vous avez spécifiés dans les colonnes cinq à sept.</span><span class="sxs-lookup"><span data-stu-id="93581-138">A result is automatically calculated from the accounts that you specified in the fifth through seventh columns.</span></span> <span data-ttu-id="93581-139">Pour cet exemple, le calcul est Solde final - Engagements - Pré-engagements.</span><span class="sxs-lookup"><span data-stu-id="93581-139">For this example, the calculation is Ending balance – Encumbrances – Pre-encumbrances.</span></span>

8. <span data-ttu-id="93581-140">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="93581-140">Select **Save**.</span></span>

## <a name="run-the-cash-position-inquiry"></a><span data-ttu-id="93581-141">Exécutez les renseignements sur l’emplacement des disponibilités</span><span class="sxs-lookup"><span data-stu-id="93581-141">Run the Cash position inquiry</span></span>

1. <span data-ttu-id="93581-142">Accédez à **Comptabilité générale \> Recherches et états \> Emplacement des disponibilités**.</span><span class="sxs-lookup"><span data-stu-id="93581-142">Go to **General ledger \> Inquiries and reports \> Cash position**.</span></span>
2. <span data-ttu-id="93581-143">Dans la section **Paramètres**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="93581-143">In the **Parameters** section, follow these steps:</span></span>

    - <span data-ttu-id="93581-144">Dans le champ **Intervalle de dates**, sélectionnez le code de l’intervalle de dates.</span><span class="sxs-lookup"><span data-stu-id="93581-144">In the **Date interval** field, select the code for the date interval.</span></span> <span data-ttu-id="93581-145">Sinon, dans les champs **Date de début** et **Date de fin**, définissez l’intervalle de dates.</span><span class="sxs-lookup"><span data-stu-id="93581-145">Alternatively, in the **From date** and **To date** fields, define the date interval.</span></span>
    - <span data-ttu-id="93581-146">Dans le champ **Ensemble de dimensions financières**, sélectionnez l’ensemble de dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="93581-146">In the **Financial dimension set** field, select the financial dimension set.</span></span>
    - <span data-ttu-id="93581-147">Facultatif : Définissez l’option **Supprimer les comptes avec des zéros** sur **Oui** pour exclure les comptes comportant tous des soldes nuls issus de la recherche.</span><span class="sxs-lookup"><span data-stu-id="93581-147">Optional: Set the **Suppress accounts with all zeroes** option to **Yes** to exclude accounts from the inquiry if they have all 0 (zero) balances.</span></span>
    - <span data-ttu-id="93581-148">Facultatif : Définissez l’option **Afficher les segments dans des colonnes distinctes** sur **Oui** pour afficher les noms du compte pour chaque dimension en tant que colonnes distinctes dans la grille.</span><span class="sxs-lookup"><span data-stu-id="93581-148">Optional: Set the **Display segments in separate columns** option to **Yes** to show the account names for each dimension as separate columns in the grid.</span></span>
    - <span data-ttu-id="93581-149">Facultatif : Pour filtrer les valeurs d’une dimension spécifique sélectionnée, dans les champs sous le champ **Ensemble de dimensions financières**, sélectionnez les dimensions que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="93581-149">Optional: To filter the values for a specific dimension, in the fields below the **Financial dimension set** field, select the dimensions to include.</span></span> <span data-ttu-id="93581-150">Les options disponibles varient en fonction de l’ensemble de dimensions financières que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="93581-150">The options that are available vary, depending on the financial dimension set that you selected.</span></span>

3. <span data-ttu-id="93581-151">Sélectionnez **Calculer les soldes** pour exécuter la recherche.</span><span class="sxs-lookup"><span data-stu-id="93581-151">Select **Calculate balances** to run the inquiry.</span></span>
