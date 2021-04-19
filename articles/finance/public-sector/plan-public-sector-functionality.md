---
title: Planifier la fonctionnalité Secteur public
description: Cette rubrique suggère les premières étapes pour paramétrer la fonctionnalité Secteur public.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 19851
ms.assetid: 877eabf3-19c7-4897-b33e-c5a8a319cb35
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a18cb26b075a4ed96a15c3e6b49effb4178a7783
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823556"
---
# <a name="plan-for-public-sector-functionality"></a><span data-ttu-id="6341a-103">Planifier la fonctionnalité Secteur public</span><span class="sxs-lookup"><span data-stu-id="6341a-103">Plan for public sector functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6341a-104">Cette rubrique suggère les premières étapes pour paramétrer la fonctionnalité Secteur public.</span><span class="sxs-lookup"><span data-stu-id="6341a-104">This topic suggests the first steps to setting up Public sector functionality.</span></span>

<a name="what-should-i-do-first"></a><span data-ttu-id="6341a-105">Que dois-je faire en premier lieu ?</span><span class="sxs-lookup"><span data-stu-id="6341a-105">What should I do first?</span></span>
-----------------------

<span data-ttu-id="6341a-106">Avant de configurer le secteur public et de commencer à ajouter vos données, réfléchissez à la manière dont vous allez utiliser cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="6341a-106">Before you set up Public sector and begin adding your data, consider how you'll use this capability.</span></span> <span data-ttu-id="6341a-107">Votre considération doit identifier les modules qui doivent être configurés pour utiliser les fonctionnalités du secteur public.</span><span class="sxs-lookup"><span data-stu-id="6341a-107">Your consideration should identify the modules that must be set up to use Public sector functionality.</span></span> <span data-ttu-id="6341a-108">Le secteur public s’intègre aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6341a-108">Public sector integrates with the following:</span></span> 

### <a name="accounts-payable"></a><span data-ttu-id="6341a-109">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="6341a-109">Accounts payable</span></span>

<span data-ttu-id="6341a-110">page de garde de l’état de paiement générer Montants des lignes de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="6341a-110">Cover page for payments report Purchase order line amounts</span></span>

### <a name="accounts-receivable"></a><span data-ttu-id="6341a-111">Module Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6341a-111">Accounts receivable</span></span>

<span data-ttu-id="6341a-112">Classification de facturation Champs personnalisés de code personnalisé de facturation Codes de facturation Champs personnalisés de facture financière Lignes d’intérêt Codes partenaires commerciaux</span><span class="sxs-lookup"><span data-stu-id="6341a-112">Billing classifications Billing code custom fields Billing codes Free text invoice line custom fields Interest lines Trading partner codes</span></span>

### <a name="budgeting"></a><span data-ttu-id="6341a-113">Budget</span><span class="sxs-lookup"><span data-stu-id="6341a-113">Budgeting</span></span>

<span data-ttu-id="6341a-114">Analyse de budget Analyse de budget pour les budgets révisés Analyse de budget pour les dépenses réelles Analyse de budget pour les engagements Analyse de budget pour les engagements préalables</span><span class="sxs-lookup"><span data-stu-id="6341a-114">Budget analysis Budget analysis for revised budgets Budget analysis for actual expenditures Budget analysis for encumbrances Budget analysis for pre-encumbrances</span></span>

### <a name="french-regulatory-options"></a><span data-ttu-id="6341a-115">Options de réglementation française</span><span class="sxs-lookup"><span data-stu-id="6341a-115">French regulatory options</span></span>

<span data-ttu-id="6341a-116">**Remarque** Pour plus d’informations sur les options de réglementation françaises, consultez [Comptabilité du secteur public en France](../localizations/emea-fra-public-sector-accounting.md).</span><span class="sxs-lookup"><span data-stu-id="6341a-116">**Note** For information about French regulatory options, see [Public sector accounting in France](../localizations/emea-fra-public-sector-accounting.md).</span></span> <span data-ttu-id="6341a-117">Les pages suivantes ne sont disponibles que si les trois conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="6341a-117">The following pages are available only if the following conditions are met:</span></span>

-   <span data-ttu-id="6341a-118">La clé de configuration **Secteur public** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6341a-118">The **Public sector** configuration key is selected.</span></span>
-   <span data-ttu-id="6341a-119">La sous-clé de configuration **Réglementation française** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6341a-119">The **French regulatory** configuration subkey is selected.</span></span>
-   <span data-ttu-id="6341a-120">L’option **Utiliser les règles comptables du secteur public français** est sélectionnée sur la page **Paramètres du budget**.</span><span class="sxs-lookup"><span data-stu-id="6341a-120">The **Use French Public sector accounting rules** option is selected on the **Budget parameters** page.</span></span>

<span data-ttu-id="6341a-121">Synthèse de solde Clôture d’engagement Tenir à jour les mandats de paiement Tenir à jour les titres de recette Accès du département au contrat d’achat Arborescence des contrats d’achat Seuils de dépense par catégorie Historique des blocages de paiements de factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="6341a-121">Balance summary Commitment close Maintain mandats de paiement Maintain titres de recette Purchase agreement department access Purchase agreement tree Spending thresholds by category Vendor invoice payment hold history</span></span>

### <a name="general-ledger"></a><span data-ttu-id="6341a-122">Comptabilité</span><span class="sxs-lookup"><span data-stu-id="6341a-122">General ledger</span></span>

<span data-ttu-id="6341a-123">Écritures comptables avancées Associer des hiérarchies financières dérivées Hiérarchies financières Filtrer les résultats Types de fonds Fonds Aperçu des transactions de comptabilité de fin d’exercice</span><span class="sxs-lookup"><span data-stu-id="6341a-123">Advanced ledger entries Associate derived financial hierarchies Derived financial hierarchies Filter results Fund types Funds Preview year end general ledger transactions</span></span>

### <a name="procurement-and-sourcing"></a><span data-ttu-id="6341a-124">Approvisionnements</span><span class="sxs-lookup"><span data-stu-id="6341a-124">Procurement and sourcing</span></span>

<span data-ttu-id="6341a-125">Type de certification Codes commande fournisseur de confirmation Montants des lignes des commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="6341a-125">Certification type Confirming PO codes Purchase order line amounts</span></span>



<a name="additional-resources"></a><span data-ttu-id="6341a-126">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6341a-126">Additional resources</span></span>
--------

[<span data-ttu-id="6341a-127">Page d’accueil Secteur public</span><span class="sxs-lookup"><span data-stu-id="6341a-127">Public sector home page</span></span>](public-sector-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]