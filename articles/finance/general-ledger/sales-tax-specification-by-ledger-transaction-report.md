---
title: Spécification de taxe par écriture comptable
description: Cette rubrique explique comment utiliser la spécification de taxe par écriture comptable afin d’afficher et d’imprimer des informations sur les écritures comptables pour laquelle la taxe est calculée.
author: ericwang
manager: Ann Beebe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b90ae491605bf59b93137936a2804c4b84c6e1b7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204880"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a><span data-ttu-id="52d71-103">Spécification de taxe par écriture comptable</span><span class="sxs-lookup"><span data-stu-id="52d71-103">Sales tax specification by ledger transaction report</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="52d71-104">Cette rubrique explique comment utiliser la **spécification de taxe par écriture comptable** afin d’afficher et d’imprimer des informations sur les écritures comptables pour laquelle la taxe est calculée.</span><span class="sxs-lookup"><span data-stu-id="52d71-104">This topic explains how to use the **Sales tax specification by ledger transaction** report to view and print information about ledger transactions that sales tax is calculated for.</span></span>

## <a name="tax-accounts-vs-non-tax-accounts"></a><span data-ttu-id="52d71-105">Comptes avec taxe vs Comptes hors taxe</span><span class="sxs-lookup"><span data-stu-id="52d71-105">Tax accounts vs. non-tax accounts</span></span>

<span data-ttu-id="52d71-106">L’état **Spécification de taxe par écriture comptable** indique les transactions de taxe pour les comptes avec taxe et les comptes hors taxe.</span><span class="sxs-lookup"><span data-stu-id="52d71-106">The **Sales tax specification by ledger transaction** report shows tax transactions for both tax accounts and non-tax accounts.</span></span> <span data-ttu-id="52d71-107">Ces comptes sont classés de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="52d71-107">These accounts are categorized in the following way:</span></span>

- <span data-ttu-id="52d71-108">**Compte avec taxe** : un compte est considéré comme tel lorsqu’une transaction de taxe est validée, et que le compte principal sur la ligne du journal **Taxe** est un compte de taxe, comme un compte de comptabilité client ou un compte de comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="52d71-108">**Tax account** – An account is considered a tax account when a tax transaction is posted, and the main account on the **Sales Tax** journal line is a tax account, such as a sales tax payable account or a sales tax receivable account.</span></span>
- <span data-ttu-id="52d71-109">**Compte hors taxe** : un compte est considéré comme tel lorsqu’une transaction de taxe est validée, et que le compte principal sur la transaction d’origine est un compte hors taxe, comme un compte de recettes ou un compte de dépenses.</span><span class="sxs-lookup"><span data-stu-id="52d71-109">**Non-tax account** – An account is considered a non-tax account when a tax transaction is posted, and the main account on the original transaction is a non-tax account, such as a revenue account or an expense account.</span></span>

<span data-ttu-id="52d71-110">Pour les comptes avec taxe, les colonnes **Origine**, **Taxe déductible** et **Taxe collectée** sur l’état indiquent **0** (zéro).</span><span class="sxs-lookup"><span data-stu-id="52d71-110">For tax accounts, the **Origin**, **Sales tax receivable**, and **Sales tax payable** columns on the report show **0** (zero).</span></span> <span data-ttu-id="52d71-111">Pour les comptes hors taxe, ces colonnes indiquent des montants.</span><span class="sxs-lookup"><span data-stu-id="52d71-111">For non-tax accounts, those columns show amounts.</span></span>

## <a name="filtering-the-data-on-the-report"></a><span data-ttu-id="52d71-112">Filtrage des données sur l’état</span><span class="sxs-lookup"><span data-stu-id="52d71-112">Filtering the data on the report</span></span>

<span data-ttu-id="52d71-113">Lorsque vous générez l’état, les champs par défaut suivants sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="52d71-113">When you generate the report, the following default fields are available.</span></span> <span data-ttu-id="52d71-114">Ces champs permettent de filtrer les données qui apparaissent sur l’état.</span><span class="sxs-lookup"><span data-stu-id="52d71-114">You can use these fields to filter the data that is shown on the report.</span></span>

| <span data-ttu-id="52d71-115">Champ</span><span class="sxs-lookup"><span data-stu-id="52d71-115">Field</span></span>                      | <span data-ttu-id="52d71-116">Description</span><span class="sxs-lookup"><span data-stu-id="52d71-116">Description</span></span> |
|----------------------------|-------------|
| <span data-ttu-id="52d71-117">Date</span><span class="sxs-lookup"><span data-stu-id="52d71-117">Date</span></span>                       | <span data-ttu-id="52d71-118">Utilisez les champs dans les sections **De** et **À** pour définir une plage de dates pour les transactions de taxe.</span><span class="sxs-lookup"><span data-stu-id="52d71-118">Use the fields in the **From** and **To** sections to define a date range for the tax transactions.</span></span> |
| <span data-ttu-id="52d71-119">Compte principal</span><span class="sxs-lookup"><span data-stu-id="52d71-119">Main account</span></span>               | <span data-ttu-id="52d71-120">Utilisez les champs dans les sections **De** et **À** pour définir une plage de dates des comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="52d71-120">Use the fields in the **From** and **To** sections to define a range of main accounts.</span></span> |
| <span data-ttu-id="52d71-121">Code taxe</span><span class="sxs-lookup"><span data-stu-id="52d71-121">Sales tax code</span></span>             | <span data-ttu-id="52d71-122">Utilisez les champs dans les sections **De** et **À** pour définir une plage de dates des codes de taxe.</span><span class="sxs-lookup"><span data-stu-id="52d71-122">Use the fields in the **From** and **To** sections to define a range of sales tax codes.</span></span> |
| <span data-ttu-id="52d71-123">Regroupement</span><span class="sxs-lookup"><span data-stu-id="52d71-123">Grouping</span></span>                   | <span data-ttu-id="52d71-124">Indiquez si l’état doit être regroupé par compte général ou par code de taxe.</span><span class="sxs-lookup"><span data-stu-id="52d71-124">Select whether the report should be grouped by ledger account or sales tax code.</span></span> |
| <span data-ttu-id="52d71-125">Sous-total par code taxe</span><span class="sxs-lookup"><span data-stu-id="52d71-125">Subtotal by sales tax code</span></span> | <span data-ttu-id="52d71-126">Définissez cette option sur **Oui** pour afficher les sous-totaux par code de taxe.</span><span class="sxs-lookup"><span data-stu-id="52d71-126">Set this option to **Yes** to show subtotals by sales tax code.</span></span> |
| <span data-ttu-id="52d71-127">Totaux uniquement</span><span class="sxs-lookup"><span data-stu-id="52d71-127">Totals only</span></span>                | <span data-ttu-id="52d71-128">Définissez cette option sur **Oui** pour n’afficher que les totaux.</span><span class="sxs-lookup"><span data-stu-id="52d71-128">Set this option to **Yes** to show only totals.</span></span> |
| <span data-ttu-id="52d71-129">Comptes principaux uniquement</span><span class="sxs-lookup"><span data-stu-id="52d71-129">Main accounts only</span></span>         | <span data-ttu-id="52d71-130">Définissez cette option sur **Oui** pour n’inclure que les comptes principaux sur l’état.</span><span class="sxs-lookup"><span data-stu-id="52d71-130">Set this option to **Yes** to include only main accounts on the report.</span></span> |

## <a name="showing-only-non-tax-accounts-on-the-report"></a><span data-ttu-id="52d71-131">Afficher uniquement les comptes hors taxe sur l’état</span><span class="sxs-lookup"><span data-stu-id="52d71-131">Showing only non-tax accounts on the report</span></span>

<span data-ttu-id="52d71-132">Pour afficher uniquement les comptes hors taxe sur l’état, paramétrez une condition de filtre, comme un astérisque (\*), comme le montre l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="52d71-132">To show only non-tax accounts on the report, set up a filter condition, such as an asterisk (\*), as shown in the following illustration.</span></span>

![État affichant des comptes hors taxe](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]