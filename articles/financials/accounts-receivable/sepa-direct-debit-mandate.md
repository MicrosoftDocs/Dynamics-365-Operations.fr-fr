---
title: Paramétrer un mandat de débit direct SEPA
description: Un débit direct dans l'Espace unique de paiement en euros (SEPA) permet à un créditeur d'encaisser des fonds à partir du compte bancaire d'un client, à condition que le client ait accordé un mandat signé au créditeur.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 45cabc7d263299763b6ee457063c96cdf384eeeb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843143"
---
# <a name="set-up-sepa-direct-debit-mandate"></a><span data-ttu-id="37432-103">Paramétrer un mandat de débit direct SEPA</span><span class="sxs-lookup"><span data-stu-id="37432-103">Set up SEPA direct debit mandate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="37432-104">Un débit direct dans l'Espace unique de paiement en euros (SEPA) permet à un créditeur d'encaisser des fonds à partir du compte bancaire d'un client, à condition que le client ait accordé un mandat signé au créditeur.</span><span class="sxs-lookup"><span data-stu-id="37432-104">A Single Euro Payment Area (SEPA) direct debit lets a creditor collect funds from a customer's bank account, provided that the customer has granted a signed mandate to the creditor.</span></span> <span data-ttu-id="37432-105">Le mandat que le client signe autorise le créditeur à encaisser un paiement et demande à la banque du client de payer la créance.</span><span class="sxs-lookup"><span data-stu-id="37432-105">The mandate that the customer signs authorizes the creditor to collect a payment and instructs the customer's bank to pay the collection.</span></span> <span data-ttu-id="37432-106">Cette rubrique présente le processus de paramétrage des mandats de débit direct SEPA.</span><span class="sxs-lookup"><span data-stu-id="37432-106">This topic is organized to show the process for setting up SEPA direct debit mandates.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="37432-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="37432-107">Prerequisites</span></span>
<span data-ttu-id="37432-108">Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="37432-108">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="37432-109">Catégorie</span><span class="sxs-lookup"><span data-stu-id="37432-109">Category</span></span>       | <span data-ttu-id="37432-110">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="37432-110">Prerequisite</span></span>                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="37432-111">Pays/Région</span><span class="sxs-lookup"><span data-stu-id="37432-111">Country/region</span></span> | <span data-ttu-id="37432-112">L'adresse principale de l'entité juridique doit être située dans les pays/régions suivants : l'Autriche, la Belgique, l'Allemagne, l'Espagne, la France, l'Italie, ou les Pays-Bas.</span><span class="sxs-lookup"><span data-stu-id="37432-112">The primary address for the legal entity must be in the following countries/regions: Austria, Belgium, Germany, Spain, France, Italy, or the Netherlands.</span></span> |

1. <span data-ttu-id="37432-113">Paramétrez une souche de numéros pour les mandats de débit direct. Chaque mandat de débit direct doit avoir un numéro unique.</span><span class="sxs-lookup"><span data-stu-id="37432-113">Set up a number sequence for direct debit mandates Each direct debit mandate must have a unique number.</span></span> <span data-ttu-id="37432-114">La page **Souches de numéros** vous permet de créer une souche de numéros pour les mandats de débit direct.</span><span class="sxs-lookup"><span data-stu-id="37432-114">Use the **Number sequences** page to create a number sequence for direct debit mandates.</span></span> <span data-ttu-id="37432-115">Vous utiliserez cet identificateur pour affecter la souche de numéros au système de mandat de débit direct sur la page **Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="37432-115">You will use this identifier to assign the number sequence to the direct debit mandate system on the **Accounts receivable parameters** page.</span></span>

2. <span data-ttu-id="37432-116">Définissez les paramètres de la comptabilité client pour les mandats de débit direct. Utilisez la page **Paramètres de la comptabilité client** pour définir les paramètres des mandats de débit direct.</span><span class="sxs-lookup"><span data-stu-id="37432-116">Set up Accounts receivable parameters for direct debit mandates Use the **Accounts receivable parameters** page to set up parameters for direct debit mandates.</span></span> <span data-ttu-id="37432-117">Pour définir les paramètres, sous l'onglet **Débit direct**, modifiez les paramètres par défaut selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="37432-117">To set up the parameters, on the **Direct debit** tab, change the default parameters as you require.</span></span> <span data-ttu-id="37432-118">Ensuite, sous l'onglet **Souches de numéros**, actualisez le champ **ID mandat de débit direct** avec la souche de numéros définie précédemment.</span><span class="sxs-lookup"><span data-stu-id="37432-118">Then, on the **Number sequences** tab, update the **Direct debit mandate ID** field with the number sequence that you set up earlier.</span></span>

3. <span data-ttu-id="37432-119">Paramétrez un mode de paiement pour les mandats de débit direct. Vous devez définir un mode de paiement pour les mandats de débit direct.</span><span class="sxs-lookup"><span data-stu-id="37432-119">Set up a method of payment for direct debit mandates You must set up a method of payment for direct debit mandates.</span></span> <span data-ttu-id="37432-120">Utilisez ce mode de paiement pour rechercher des factures pour lesquelles générer des paiements de débit direct.</span><span class="sxs-lookup"><span data-stu-id="37432-120">You use this method of payment to query for invoices to generate direct debit payments for.</span></span> <span data-ttu-id="37432-121">La page **Modes de paiement** vous permet de paramétrer le mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="37432-121">Use the **Methods of payment** page to set up the method of payment.</span></span> <span data-ttu-id="37432-122">Pour paramétrer un mode de paiement pour les mandats de débit direct, effectuez les étapes supplémentaires suivantes :</span><span class="sxs-lookup"><span data-stu-id="37432-122">To set up a method of payment for direct debit mandates, you must follow these additional steps for a method of payment:</span></span>

-   <span data-ttu-id="37432-123">Dans le champ **Type de paiement**, sélectionnez **Paiement électronique**.</span><span class="sxs-lookup"><span data-stu-id="37432-123">In the **Payment type** field, select **Electronic payment**.</span></span>
-   <span data-ttu-id="37432-124">Facultatif : si vous prévoyez que chacun de vos clients aura plusieurs mandats, dans le champ **Période**, sélectionnez **Facture**.</span><span class="sxs-lookup"><span data-stu-id="37432-124">Optional: If you expect each of your customers to have multiple mandates, in the **Period** field, select **Invoice**.</span></span> <span data-ttu-id="37432-125">Cette opération crée un paiement distinct pour chaque facture, et chaque paiement utilisera le mandat indiqué pour la facture.</span><span class="sxs-lookup"><span data-stu-id="37432-125">A separate payment will be created for each invoice, and each payment will use the mandate that is specified for the invoice.</span></span>
-   <span data-ttu-id="37432-126">Sélectionnez l'option **Demander un mandat** pour créer des paiements par l'intermédiaire des mandats de débit direct.</span><span class="sxs-lookup"><span data-stu-id="37432-126">Select the **Require mandate** option to create payments by using direct debit mandates.</span></span> <span data-ttu-id="37432-127">L'option **Demander un mandat** est uniquement disponible si vous sélectionnez **Paiement électronique** dans le champ **Type de paiement**.</span><span class="sxs-lookup"><span data-stu-id="37432-127">The **Require mandate** option is available only if you select **Electronic payment** in the **Payment type** field.</span></span>

<span data-ttu-id="37432-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="37432-128">Additional resources</span></span>

[<span data-ttu-id="37432-129">Vue d'ensemble du débit direct</span><span class="sxs-lookup"><span data-stu-id="37432-129">Direct debit overview</span></span>](sepa-direct-debit-overview.md) 

[<span data-ttu-id="37432-130">Créer un mandat de débit direct pour un client</span><span class="sxs-lookup"><span data-stu-id="37432-130">Create a direct debit mandate for a customer</span></span>](tasks/create-direct-debit-mandate-customer.md) 

