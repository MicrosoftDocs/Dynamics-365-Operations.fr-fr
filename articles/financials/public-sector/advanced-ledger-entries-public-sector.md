---
title: "Écritures comptables avancées dans le secteur public"
description: "Les organisations du secteur public peuvent utiliser les écritures comptables avancées pour créer, ajuster et contrepasser des écritures comptables. Par exemple, vous pouvez utiliser des écritures comptables avancées pour reclassifier des dépenses si des factures sont validées par erreur dans un compte ou projet inapproprié."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AdvancedLedgerEntry, BudgetControlConfiguration, LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 19511
ms.assetid: 3db0233e-d767-4dc0-b008-733098b6ca70
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 29a67d884eeac2a8dbbbf96f4c4f4d43eba1e879
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="advanced-ledger-entries-in-the-public-sector"></a><span data-ttu-id="ebf4f-104">Écritures comptables avancées dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="ebf4f-104">Advanced ledger entries in the public sector</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ebf4f-105">Les organisations du secteur public peuvent utiliser les écritures comptables avancées pour créer, ajuster et contrepasser des écritures comptables.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-105">Public-sector organizations can use advanced ledger entries to create, adjust, and reverse ledger entries.</span></span> <span data-ttu-id="ebf4f-106">Par exemple, vous pouvez utiliser des écritures comptables avancées pour reclassifier des dépenses si des factures sont validées par erreur dans un compte ou projet inapproprié.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-106">For example, advanced ledger entries can be used to reclassify expenditures if invoices are mistakenly posted to the wrong account or project.</span></span>

<a name="how-do-i-set-up-advanced-ledger-entries"></a><span data-ttu-id="ebf4f-107">Comment paramétrer des écritures comptables avancées ?</span><span class="sxs-lookup"><span data-stu-id="ebf4f-107">How do I set up advanced ledger entries?</span></span>
----------------------------------------

<span data-ttu-id="ebf4f-108">Vérifiez que la clé **Écriture comptable avancée** **Configuration des licences** est sélectionnée sur la page **Configuration des licences**.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-108">Verify that the **Advanced ledger entry** **License configuration** key is selected in the **License configuration** page.</span></span> <span data-ttu-id="ebf4f-109">Les écritures comptables avancées exigent des définitions de validation de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-109">Advanced ledger entries require General ledger posting definitions.</span></span> <span data-ttu-id="ebf4f-110">Ces définitions de validation peuvent être paramétrées pour générer plusieurs écritures comptables équilibrées basées sur le compte général spécifié sur la page **Écritures comptables avancées**.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-110">These posting definitions can be set up to generate multiple, balanced ledger entries based on the ledger account entered in the **Advanced ledger entries** page.</span></span> <span data-ttu-id="ebf4f-111">Pour plus d'informations sur les définitions de validation pour les écritures comptables avancées, voir [Définitions de validation dans le secteur public](posting-definitions-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="ebf4f-111">For more information about posting definitions for advanced ledger entries, see [Posting definitions in the public sector](posting-definitions-public-sector.md).</span></span>

## <a name="can-i-use-budget-control-with-advanced-ledger-entries"></a><span data-ttu-id="ebf4f-112">Puis-je utiliser le contrôle budgétaire avec les écritures comptables avancées ?</span><span class="sxs-lookup"><span data-stu-id="ebf4f-112">Can I use budget control with advanced ledger entries?</span></span>
<span data-ttu-id="ebf4f-113">Oui.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-113">Yes.</span></span> <span data-ttu-id="ebf4f-114">Si votre organisation utilise le contrôle budgétaire, vous pouvez l'activer pour les écritures comptables avancées sur la page **Configuration du contrôle budgétaire**.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-114">If your organization uses budget control, you can enable budget control for advanced ledger entries on the **Budget control configuration** page.</span></span>

## <a name="can-i-use-advanced-ledger-entries-with-projects"></a><span data-ttu-id="ebf4f-115">Puis-je utiliser les écritures comptables avancées avec des projets ?</span><span class="sxs-lookup"><span data-stu-id="ebf4f-115">Can I use advanced ledger entries with projects?</span></span>
<span data-ttu-id="ebf4f-116">Oui.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-116">Yes.</span></span> <span data-ttu-id="ebf4f-117">Si vous souhaitez que les utilisateurs soient en mesure de modifier les dimensions financières pour un projet sur la ligne d'écriture comptable avancée, vous devez sélectionner l'option **Autoriser la modification des dimensions financières dans l'écran d'écriture comptable avancée** sur la page **Paramètres de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-117">If you want users to be able to change the financial dimensions for a project on the advanced ledger entry line, you’ll need to select the **Allow the financial dimensions to be edited on the advanced ledger entry form** option on the **General ledger parameters** page.</span></span> <span data-ttu-id="ebf4f-118">Si vous ne sélectionnez pas cette option, les utilisateurs peuvent modifier les dimensions financières dans le champ **Compte général** uniquement si les dimensions financières ne correspondent pas aux dimensions financières par défaut d'un projet.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-118">If you don’t select this option, users can change the financial dimensions in the **Ledger account** field only if the financial dimensions are not the default financial dimensions for a project.</span></span>

## <a name="how-do-i-use-advanced-ledger-entries-to-record-yearend-accrual-entries"></a><span data-ttu-id="ebf4f-119">Comment utiliser les écritures comptables avancées pour enregistrer les entrées de régularisation de fin d'exercice ?</span><span class="sxs-lookup"><span data-stu-id="ebf4f-119">How do I use advanced ledger entries to record yearend accrual entries?</span></span>
<span data-ttu-id="ebf4f-120">Créez une écriture comptable avancée, sélectionnez l'option **Entrée de contrepassation**, puis entrez une date de contrepassation.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-120">Create an advanced ledger entry, select the **Reversing entry** option, and enter a reversing date.</span></span> <span data-ttu-id="ebf4f-121">L'écriture comptable avancée de contrepassation est créée lors de la validation de l'écriture comptable avancée.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-121">The reversing advanced ledger entry is created when the advanced ledger entry is posted.</span></span> <span data-ttu-id="ebf4f-122">L'écriture comptable avancée de contrepassation aura un nouveau numéro de transaction et le statut de brouillon.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-122">The reversing advanced ledger entry will have a new transaction number and a draft status.</span></span> <span data-ttu-id="ebf4f-123">La date de contrepassation sera utilisée comme date comptable et le montant débiteur ou créditeur de chaque ligne de l'écriture originale sera contrepassé.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-123">The reversing date will be used as the accounting date and the debit or credit amount on each line of the original entry will be reversed.</span></span> <span data-ttu-id="ebf4f-124">La même définition de validation sera utilisée.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-124">The same posting definition will be used.</span></span> <span data-ttu-id="ebf4f-125">Le libellé de transaction de l'en-tête et des lignes contiendra les mots « Entrée de contrepassation de », le numéro de transaction de l'écriture comptable avancée originale, ainsi que son libellé de transaction.</span><span class="sxs-lookup"><span data-stu-id="ebf4f-125">The transaction text for the header and lines will contain the words “Reversing entry from,” the transaction number of the original advanced ledger entry, and the transaction text of the original advanced ledger entry.</span></span>






