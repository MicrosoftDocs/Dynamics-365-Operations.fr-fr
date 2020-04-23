---
title: Renseignements sur l'emplacement des disponibilités
description: Cette rubrique fournit des informations sur la façon de déterminer les emplacements de disponibilités correspondants pour les ensembles de dimensions financières contenant des dimensions en équilibre.
author: velofog
manager: AnnBe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-alpavk
ms.search.validFrom: 2019-10-24
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 0f08f5af1617c2d69c2ed025b6716546b59e8a85
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249080"
---
# <a name="cash-position-inquiry"></a><span data-ttu-id="204e3-103">Renseignements sur l'emplacement des disponibilités</span><span class="sxs-lookup"><span data-stu-id="204e3-103">Cash position inquiry</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="204e3-104">Les renseignements **Emplacement des disponibilités** vous permet de déterminer les emplacements de disponibilités correspondants pour les ensembles de dimensions financières contenant des dimensions en équilibre.</span><span class="sxs-lookup"><span data-stu-id="204e3-104">The **Cash position** inquiry allows you to determine the corresponding cash positions for financial dimension sets that contain self-balancing dimensions.</span></span> <span data-ttu-id="204e3-105">Les renseignements affiche le solde des disponibilités de début, ainsi que l'effet de l'addition des rentrées de fonds, de la soustraction des remboursements de disponibilités, et la soustraction des transferts interfonds pour obtenir un solde de fin.</span><span class="sxs-lookup"><span data-stu-id="204e3-105">The inquiry shows the beginning cash balance, and the effect of the addition of cash receipts, the subtraction of cash disbursements, and the subtraction of interfund transfers to arrive at an ending balance.</span></span> <span data-ttu-id="204e3-106">Ensuite, les réservations budgétaires générales, les engagements ou les engagements préalables sont soustraits du solde de clôture pour obtenir à un solde non engagé.</span><span class="sxs-lookup"><span data-stu-id="204e3-106">Then, from the ending balance, general budget reservations, encumbrances, or pre-encumbrances are subtracted to arrive at an unencumbered balance.</span></span>

<span data-ttu-id="204e3-107">Ces renseignements sont uniques, car ils permettent aux utilisateurs de personnaliser la terminologie pour les noms de colonne et pour les comptes principaux utilisés pour fournir des montants aux colonnes.</span><span class="sxs-lookup"><span data-stu-id="204e3-107">This inquiry is unique in that it allows users to customize the terminology for column names and for the main accounts that are used to derive amounts for the columns.</span></span> <span data-ttu-id="204e3-108">Dans la page **Paramètres de l'emplacement des disponibilités**, les colonnes affichées dans les renseignements sont numérotées à compter de la colonne de données à l'extrême gauche comme première colonne.</span><span class="sxs-lookup"><span data-stu-id="204e3-108">On the **Cash position parameters** page, the columns that appear in the inquiry are numbered starting with the left-most data column as column one.</span></span>

## <a name="cash-position-inquiry-setup"></a><span data-ttu-id="204e3-109">Configuration des renseignements sur l'emplacement des disponibilités</span><span class="sxs-lookup"><span data-stu-id="204e3-109">Cash position inquiry setup</span></span>

1. <span data-ttu-id="204e3-110">Accédez à **Comptabilité générale** > **Paramétrage de la comptabilité** > **Paramètres de l'emplacement des disponibilités**.</span><span class="sxs-lookup"><span data-stu-id="204e3-110">Go to **General ledger** > **Ledger setup** > **Cash position parameters**.</span></span>
2. <span data-ttu-id="204e3-111">Dans la page **Paramètres de l'emplacement des disponibilités**, dans la section **Première colonne** :</span><span class="sxs-lookup"><span data-stu-id="204e3-111">In the **Cash position parameters** page, in the **Column one** section:</span></span>

- <span data-ttu-id="204e3-112">Dans le champ **Nom de la colonne**, tapez une étiquette à utiliser comme en-tête pour la première colonne de la recherche (par exemple, « Solde d'ouverture »).</span><span class="sxs-lookup"><span data-stu-id="204e3-112">In the **Column name** field, type a label to use as the header for the inquiry’s first column (for example, "Beginning balance").</span></span>
- <span data-ttu-id="204e3-113">Dans le champ **Comptes principaux de solde d'ouverture**, sélectionnez les comptes que vous souhaitez référencer pour lancer une recherche sur le solde d'ouverture.</span><span class="sxs-lookup"><span data-stu-id="204e3-113">In the **Opening balance main accounts** field, select the account(s) that you want to reference for inquiring on the opening balance.</span></span>

3. <span data-ttu-id="204e3-114">Dans la section **Deuxième colonne** :</span><span class="sxs-lookup"><span data-stu-id="204e3-114">In the **Column two** section:</span></span> 

- <span data-ttu-id="204e3-115">Spécifiez un libellé pour la deuxième colonne dans la recherche (par exemple, « Rentrées de fonds »).</span><span class="sxs-lookup"><span data-stu-id="204e3-115">Specify a label for the second column in the inquiry (for example, "Cash receipts").</span></span>
- <span data-ttu-id="204e3-116">Dans la liste **Comptes principaux de débit et de crédit**, sélectionnez les comptes principaux à partir desquels utiliser uniquement la somme de tous les montants de transactions de débit et de crédit pour les données de la recherche.</span><span class="sxs-lookup"><span data-stu-id="204e3-116">In the **Debit and credit main accounts** list, select the main accounts from which to use only the sum of all debit and credit transaction amounts for the inquiry's data.</span></span> 

> [!NOTE]
> <span data-ttu-id="204e3-117">La recherche ajoute le net des comptes débiteurs et créditeurs ainsi que le montant de débit et les montants de crédit des comptes principaux dans les autres champs du groupe.</span><span class="sxs-lookup"><span data-stu-id="204e3-117">The inquiry will add the net of the debit and credit accounts plus the debit amount and credit amounts from the main accounts in the other fields in the group.</span></span>

- <span data-ttu-id="204e3-118">Dans la liste **Comptes principaux de débit uniquement**, sélectionnez les comptes principaux à partir desquels utiliser uniquement la somme de tous les montants de transactions de débit pour les données de la recherche.</span><span class="sxs-lookup"><span data-stu-id="204e3-118">In the **Debit-only main accounts** list, select the main accounts from which to use only the sum of all debit transaction amounts for the inquiry's data.</span></span>
- <span data-ttu-id="204e3-119">Dans la liste **Comptes principaux de crédit uniquement**, sélectionnez les comptes principaux à partir desquels utiliser uniquement la somme de tous les montants de transactions de crédit pour les données de la recherche.</span><span class="sxs-lookup"><span data-stu-id="204e3-119">In the **Credit-only main accounts** list, select the main accounts from which to use only the sum of all credit transaction amounts for the inquiry's data.</span></span>

4. <span data-ttu-id="204e3-120">Dans les sections **Troisième colonne** et **Quatrième colonne** :</span><span class="sxs-lookup"><span data-stu-id="204e3-120">In the **Column three** and **Column four** sections:</span></span> 

- <span data-ttu-id="204e3-121">Spécifiez un libellé pour la troisième colonne (par exemple, « Déboursements de disponibilités ») et la quatrième colonne (par exemple, « Transferts interfonds »).</span><span class="sxs-lookup"><span data-stu-id="204e3-121">Specify a label for the third column (for example, "Cash disbursements") and fourth column (for example, "Interfund transfers").</span></span>
- <span data-ttu-id="204e3-122">Pour les deux colonnes, spécifiez les numéros de compte des comptes principaux de débit et de crédit, des comptes principaux réservés au débit et des comptes principaux réservés au crédit.</span><span class="sxs-lookup"><span data-stu-id="204e3-122">For both columns, specify account numbers for the debit and credit main accounts, debit-only main accounts, and credit-only main accounts.</span></span>

5. <span data-ttu-id="204e3-123">Dans la section de groupe **Cinquième colonne**, spécifiez un libellé pour la cinquième colonne (par exemple, « Solde de clôture »).</span><span class="sxs-lookup"><span data-stu-id="204e3-123">In the **Column five** groupsection, specify a label for the fifth column (for example, ""Ending balance"").</span></span> 

> [!NOTE]
> <span data-ttu-id="204e3-124">Dynamics 365 Finance calcule automatiquement une somme à partir des comptes spécifiés pour les quatre premières colonnes : Solde d'ouverture plus les rentrées de fonds, moins les déboursements de disponibilités, moins les transferts interfonds.</span><span class="sxs-lookup"><span data-stu-id="204e3-124">Dynamics 365 Finance automatically calculates a sum from the accounts you specified for the first four columns: Beginning balance plus cash receipts, minus cash disbursements, minus interfund transfers.</span></span>

6. <span data-ttu-id="204e3-125">Dans les sections **Sixième colonne** et **Septième colonne** :</span><span class="sxs-lookup"><span data-stu-id="204e3-125">In the **Column six** and **Column seven** sections:</span></span> 

- <span data-ttu-id="204e3-126">Spécifiez une étiquette pour la colonne six (par exemple, Réservations budgétaires générales ou Non engagements ») et la colonne sept (par exemple, « Engagements préalables »).</span><span class="sxs-lookup"><span data-stu-id="204e3-126">Specify a label for column six (for example, General budget reservations or Encunbrances") and column seven (for example, "Pre-encumbrances").</span></span>
- <span data-ttu-id="204e3-127">Pour les deux colonnes, spécifiez les numéros de compte des **Comptes principaux de débit et de crédit**, des **Comptes principaux réservés au débit** et des **Comptes principaux réservés au crédit**.</span><span class="sxs-lookup"><span data-stu-id="204e3-127">For both columns, specify account numbers for the **Debit and credit main accounts**, **Debit-only main accounts**, and **Credit-only main accounts**.</span></span>

7. <span data-ttu-id="204e3-128">Dans la section **Huitième colonne**, spécifiez une étiquette de colonne (par exemple, « Solde non engagé »).</span><span class="sxs-lookup"><span data-stu-id="204e3-128">In the **Column eight** section, specify a column label (for example, "Unencumbered balance").</span></span> 

> [!NOTE]
> <span data-ttu-id="204e3-129">Dynamics 365 Finance calcule automatiquement un résultat à partir des comptes spécifiés pour les colonnes cinq à sept : Solde de clôture moins Engagements, moins Engagements préalables.</span><span class="sxs-lookup"><span data-stu-id="204e3-129">Dynamics 365 Finance automatically calculates a result from the accounts you specified for columns five through seven: Ending balance minus Encumbrances, minus Pre-encumbrances.</span></span>

8. <span data-ttu-id="204e3-130">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="204e3-130">Click **Save**.</span></span>

## <a name="running-the-inquiry"></a><span data-ttu-id="204e3-131">Exécuter la recherche</span><span class="sxs-lookup"><span data-stu-id="204e3-131">Running the inquiry</span></span>

1. <span data-ttu-id="204e3-132">Accédez à **Comptabilité générale** > **Recherches et états** > **Emplacement des disponibilités**.</span><span class="sxs-lookup"><span data-stu-id="204e3-132">Go to **General ledger** > **Inqiuries and reports** > **Cash position**.</span></span>
2. <span data-ttu-id="204e3-133">Dans la section **Paramètres** :</span><span class="sxs-lookup"><span data-stu-id="204e3-133">In the **Parameters** section:</span></span> 

- <span data-ttu-id="204e3-134">Sélectionnez le code **Intervalle de dates**, ou **Date de début** et **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="204e3-134">Select the **Date interval** code, or the **From date** and **To date**.</span></span>
- <span data-ttu-id="204e3-135">Sélectionnez **Ensemble de dimensions financières**.</span><span class="sxs-lookup"><span data-stu-id="204e3-135">Select the **Financial dimension set**.</span></span>
- <span data-ttu-id="204e3-136">Sélectionnez **Calculer les soldes** pour exécuter la recherche.</span><span class="sxs-lookup"><span data-stu-id="204e3-136">Select **Calculate balances** to run the inquiry.</span></span>

<span data-ttu-id="204e3-137">(facultatif)</span><span class="sxs-lookup"><span data-stu-id="204e3-137">Optional:</span></span> 

- <span data-ttu-id="204e3-138">Définissez l'option **Supprimer les comptes avec des zéros** sur **Oui** pour exclure les comptes comportant tous des montants nuls issus de la recherche.</span><span class="sxs-lookup"><span data-stu-id="204e3-138">Set the **Suppress accounts with all zeroes** option to **Yes** to exclude accounts that ahve all zero balances from the inquiry.</span></span>
- <span data-ttu-id="204e3-139">Définissez l'option **Afficher les segments dans des colonnes distinctes** sur **Oui** pour afficher les noms du compte pour chaque dimension en tant que colonnes distinctes dans la grille.</span><span class="sxs-lookup"><span data-stu-id="204e3-139">Set the **Display segments in seperate columns** option to **Yes** to show the account names for each dimension as seperate columns in the grid.</span></span>
- <span data-ttu-id="204e3-140">Pour filtrer les valeurs d'une dimension spécifique sélectionnée, sélectionnez les dimensions que vous souhaitez dans les champs sous le champ **Ensemble de dimensions financières**.</span><span class="sxs-lookup"><span data-stu-id="204e3-140">If you want to filter the values for a specific dimension selected, select the dimensions you want in the fields below the **Financial dimension set** field.</span></span> <span data-ttu-id="204e3-141">Les choix parmi lesquels choisir dépendent de l'ensemble de dimensions financières sélectionné.</span><span class="sxs-lookup"><span data-stu-id="204e3-141">The choices you have to select from depend on which financial dimension set you selected.</span></span>

