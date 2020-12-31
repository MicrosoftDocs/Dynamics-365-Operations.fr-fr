---
title: Configurer les registres des baux
description: Cette rubrique décrit les informations gérées dans les registres de location. Les registres de location contiennent les méthodes comptables qui déterminent la façon dont une location est comptabilisé dans le système.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 28518341544327f1983e563b719b0f455b6e1c43
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4443370"
---
# <a name="set-up-lease-books"></a><span data-ttu-id="87aa2-104">Configurer les registres des baux</span><span class="sxs-lookup"><span data-stu-id="87aa2-104">Set up lease books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87aa2-105">Les registres de location contiennent les méthodes comptables qui déterminent la façon dont une location est comptabilisé dans le système.</span><span class="sxs-lookup"><span data-stu-id="87aa2-105">Lease books contain the accounting policies that determine how a lease is accounted for in the system.</span></span> <span data-ttu-id="87aa2-106">En plus de la comptabilité de caisse, la location d’actifs prend en charge les normes suivantes :</span><span class="sxs-lookup"><span data-stu-id="87aa2-106">In addition to cash basis accounting, Asset leasing supports the following standards:</span></span>

- <span data-ttu-id="87aa2-107">Principes comptables généraux des États-Unis (GAAP)</span><span class="sxs-lookup"><span data-stu-id="87aa2-107">Generally Accepted Accounting Principles in the United States (US GAAP)</span></span>
- <span data-ttu-id="87aa2-108">Article 842 sur la codification des normes comptables (ASC 842)</span><span class="sxs-lookup"><span data-stu-id="87aa2-108">Accounting Standards Codification Topic 842 (ASC 842)</span></span>
- <span data-ttu-id="87aa2-109">ASC 840</span><span class="sxs-lookup"><span data-stu-id="87aa2-109">ASC 840</span></span>
- <span data-ttu-id="87aa2-110">Norme internationale d’information financière 16 (IFRS 16)</span><span class="sxs-lookup"><span data-stu-id="87aa2-110">International Financial Reporting Standard 16 (IFRS 16)</span></span>
- <span data-ttu-id="87aa2-111">Norme comptable internationale 17 (IAS 17)</span><span class="sxs-lookup"><span data-stu-id="87aa2-111">International Accounting Standard 17 (IAS 17)</span></span>

<span data-ttu-id="87aa2-112">Pour créer un registre de location, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="87aa2-112">To create a lease book, follow these steps.</span></span>

1. <span data-ttu-id="87aa2-113">Accédez à **Location d’actifs \> Configuration \> registres de baux**.</span><span class="sxs-lookup"><span data-stu-id="87aa2-113">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="87aa2-114">Sélectionnez **Nouveau** pour ajouter un registre.</span><span class="sxs-lookup"><span data-stu-id="87aa2-114">Select **New** to add a book.</span></span>
3. <span data-ttu-id="87aa2-115">Définisse les champs suivants.</span><span class="sxs-lookup"><span data-stu-id="87aa2-115">Set the following fields.</span></span>

    | <span data-ttu-id="87aa2-116">Nom</span><span class="sxs-lookup"><span data-stu-id="87aa2-116">Name</span></span>                                     | <span data-ttu-id="87aa2-117">Description</span><span class="sxs-lookup"><span data-stu-id="87aa2-117">Description</span></span> |
    |------------------------------------------|-------------|
    | <span data-ttu-id="87aa2-118">Couche de validation</span><span class="sxs-lookup"><span data-stu-id="87aa2-118">Posting layer</span></span>                            | <span data-ttu-id="87aa2-119">Sélectionnez la couche de validation à utiliser.</span><span class="sxs-lookup"><span data-stu-id="87aa2-119">Select the posting layer to use.</span></span> <span data-ttu-id="87aa2-120">Chaque registre associé à un bail est configuré pour une couche de validation spécifique.</span><span class="sxs-lookup"><span data-stu-id="87aa2-120">Each book that is attached to a lease is set up for a specific posting layer.</span></span> <span data-ttu-id="87aa2-121">Chaque couche de validation a des objectifs de publication différents.</span><span class="sxs-lookup"><span data-stu-id="87aa2-121">Each posting layer has different posting purposes.</span></span> |
    | <span data-ttu-id="87aa2-122">Type de bail</span><span class="sxs-lookup"><span data-stu-id="87aa2-122">Lease type</span></span>                               | <span data-ttu-id="87aa2-123">Sélectionnez si la location doit être classé automatiquement ou s’il doit être prédéfini en tant que location-financement ou location simple.</span><span class="sxs-lookup"><span data-stu-id="87aa2-123">Select whether the lease should be classified automatically, or whether it should be predefined as a finance or operating lease.</span></span> |
    | <span data-ttu-id="87aa2-124">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="87aa2-124">Accounting framework</span></span>                     | <span data-ttu-id="87aa2-125">Sélectionnez le cadre associé au registre.</span><span class="sxs-lookup"><span data-stu-id="87aa2-125">Select the framework that is associated with the book.</span></span> |
    | <span data-ttu-id="87aa2-126">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="87aa2-126">Lease term/Useful life Set Up</span></span>          | <span data-ttu-id="87aa2-127">Le système classera le bail comme contrat de location-financement si le type de bail est défini sur **automatique** et si la durée du bail sur la durée de vie utile de l’actif est supérieure ou égale au pourcentage défini dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="87aa2-127">The system will classify the lease as a finance lease if the lease type is set to **Automatic**, and if the lease term over useful life of the asset is greater than or equal to the percentage entered in this field.</span></span>  |
    | <span data-ttu-id="87aa2-128">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="87aa2-128">Present value / Asset fair value setup</span></span>   | <span data-ttu-id="87aa2-129">Entrez un nombre entier pour définir le seuil qui déterminera le type de bail.</span><span class="sxs-lookup"><span data-stu-id="87aa2-129">Enter a whole number to define the threshold that will determine the lease type.</span></span> <span data-ttu-id="87aa2-130">Si la valeur actuelle des futurs paiements minimaux au titre de la location est supérieure à la valeur définie par l’utilisateur à partir de la configuration comptable et si la classification des contrats de location du registre est définie sur automatique, le système classera le contrat de location comme contrat de location-financement.</span><span class="sxs-lookup"><span data-stu-id="87aa2-130">If the present value of future minimum lease payments is more than the user-defined value from the book setup, and if the book's lease classification is set to automatic, the system will classify the lease as a finance lease.</span></span> |
    | <span data-ttu-id="87aa2-131">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="87aa2-131">Short-term threshold</span></span>                     | <span data-ttu-id="87aa2-132">Saisissez le nombre de mois à utiliser comme seuil pour les baux à court terme.</span><span class="sxs-lookup"><span data-stu-id="87aa2-132">Enter the number of months to use as a threshold for short-term leases.</span></span> <span data-ttu-id="87aa2-133">Si la durée du bail est inférieure ou égale au nombre de mois que vous entrez ici, le système classera le bail comme un bail à court terme et le traitement du loyer différé sera appliqué.</span><span class="sxs-lookup"><span data-stu-id="87aa2-133">If the lease term is less than or equal to the number of months that you enter here, the system will classify the lease as a short-term lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="87aa2-134">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="87aa2-134">Low value threshold</span></span>                      | <span data-ttu-id="87aa2-135">Saisissez un montant à utiliser comme seuil pour les baux de faible valeur.</span><span class="sxs-lookup"><span data-stu-id="87aa2-135">Enter an amount to use as a threshold for low-value leases.</span></span> <span data-ttu-id="87aa2-136">Si la juste valeur de l’actif est inférieure ou égale ou la valeur que vous entrez ici, le système classera le bail comme un bail de faible valeur et le traitement du loyer différé sera appliqué.</span><span class="sxs-lookup"><span data-stu-id="87aa2-136">If the fair value of the asset is less than or equal or the value that you enter here, the system will classify the lease as a low-value lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="87aa2-137">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="87aa2-137">Pay to vendor</span></span>                            | <span data-ttu-id="87aa2-138">Définissez cette option sur **Oui** pour permettre que les paiements de location soient imputés, sous forme de facture, sur le compte fournisseur spécifié sur chaque contrat de location.</span><span class="sxs-lookup"><span data-stu-id="87aa2-138">Set this option to **Yes** to allow lease payments to be posted, as an invoice, to the vendor account that is specified on each lease.</span></span> <span data-ttu-id="87aa2-139">Lorsqu’un paiement de location est validé, le compte fournisseur est crédité.</span><span class="sxs-lookup"><span data-stu-id="87aa2-139">When a lease payment is posted, the vendor account will be credited.</span></span> <span data-ttu-id="87aa2-140">Si cette option est définie sur **Non**, le compte spécifié pour le type de validation **Paiement de location** sur la page **Paramètres d’affichage du bail** sera créditée à la place.</span><span class="sxs-lookup"><span data-stu-id="87aa2-140">If this option is set to **No**, the account that is specified for the **Lease payment** posting type on the **Lease posting parameters** page will be credited instead.</span></span> |
