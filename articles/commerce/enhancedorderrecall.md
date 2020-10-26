---
title: Rappeler l'opération de commande dans le PDV
description: Cette rubrique explique les fonctionnalités disponibles pour les pages de rappel de commande améliorées dans le PDV.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 41944fb7819b5527f6bc023a60acd9450d9e43c2
ms.sourcegitcommit: 25909c6ad3616e4f75a2fe006057dda18d7cc856
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/09/2020
ms.locfileid: "3974836"
---
# <a name="recall-order-operation-in-pos"></a><span data-ttu-id="13a43-103">Rappeler l'opération de commande dans le PDV</span><span class="sxs-lookup"><span data-stu-id="13a43-103">Recall order operation in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="13a43-104">L'opération de rappel de commande dans le point de vente (PDV) Commerce fournit des fonctionnalités de recherche et de filtre de commande mises à jour ainsi que des informations spécifiques à la commande.</span><span class="sxs-lookup"><span data-stu-id="13a43-104">The Recall order operation in the Commerce point of sale (POS) provides updated order search and filtering features and order-specific information.</span></span> <span data-ttu-id="13a43-105">Cette fonctionnalité est disponible dans les versions de Commerce 10.0.15 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="13a43-105">This feature is available in Commerce versions 10.0.15 and later.</span></span>

<span data-ttu-id="13a43-106">Pour activer cette fonctionnalité, activez la fonctionnalité **Rappeler l'opération de commande dans le PDV améliorée** dans l'espace de travail **Gestion des fonctionnalités** au siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="13a43-106">To enable this functionality, turn the **Improved Recall order operation in POS** feature on in **Feature management** workspace in Commerce headquarters.</span></span> <span data-ttu-id="13a43-107">Après avoir activé la fonctionnalité, pensez à mettre à jour les [dispositions de l'écran](pos-screen-layouts.md) dans PDV pour profiter de certaines des fonctionnalités modifiées.</span><span class="sxs-lookup"><span data-stu-id="13a43-107">After you enable the feature, consider updating your [screen layouts](pos-screen-layouts.md) in POS to take advantage of some of the changed  capabilities.</span></span>

<span data-ttu-id="13a43-108">La configuration du bouton de l'opération **Rappeler la commande** permet aux organisations de déployer l'opération avec un affichage prédéfini.</span><span class="sxs-lookup"><span data-stu-id="13a43-108">The configuration of the **Recall order** operation button allows organizations to deploy the operation with a pre-defined display.</span></span>

![Configuration de la grille de boutons](media/recallorderbuttongrid.png)

<span data-ttu-id="13a43-110">Les options d'affichage sont les suivantes.</span><span class="sxs-lookup"><span data-stu-id="13a43-110">The display options are as follows.</span></span>
- <span data-ttu-id="13a43-111">**Aucun** - Cette option déploie l'opération sans affichage spécifique.</span><span class="sxs-lookup"><span data-stu-id="13a43-111">**None** – This option deploys the operation with no specific display.</span></span> <span data-ttu-id="13a43-112">Lorsqu'un utilisateur ouvre l'opération avec cette configuration, il sera invité à rechercher et trouver des commandes ou à choisir un filtre de commande prédéfini.</span><span class="sxs-lookup"><span data-stu-id="13a43-112">When a user opens the operation with this configuration, they will be prompted to search and find orders or choose from a pre-defined order filter.</span></span>
- <span data-ttu-id="13a43-113">**Commandes à traiter** - Lorsqu'un utilisateur lance l'opération, une requête s'exécute automatiquement pour rechercher et afficher une liste des commandes qui doivent être traitées par le magasin.</span><span class="sxs-lookup"><span data-stu-id="13a43-113">**Orders to fulfill** – When a user launches the operation, a query will run automatically to search and display a list of orders that are to be fulfilled by the store.</span></span> <span data-ttu-id="13a43-114">Ces commandes sont configurées pour un retrait en magasin ou une expédition en magasin, et les lignes de ces commandes n'ont pas encore été prélevées ou emballées.</span><span class="sxs-lookup"><span data-stu-id="13a43-114">These orders are configured for in-store pickup or store shipment and the lines of these orders have not yet been picked or packed.</span></span>
- <span data-ttu-id="13a43-115">**Commandes à prélever** - Lorsqu'un utilisateur lance l'opération, une requête s'exécute automatiquement pour rechercher et afficher une liste des commandes qui doivent être configurées pour un retrait en magasin dans le magasin actuel de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="13a43-115">**Orders to pick up** – When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for in-store pickup at the user's current store.</span></span>
- <span data-ttu-id="13a43-116">**Commandes à expédier** - Lorsqu'un utilisateur lance l'opération, une requête s'exécute automatiquement pour rechercher et afficher une liste des commandes qui doivent être configurées pour être expédiées depuis le magasin actuel de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="13a43-116">**Orders to ship** - When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for shipment from the user's current store.</span></span>

<span data-ttu-id="13a43-117">Lors du lancement de l'opération **Rappel de la commande** à partir du PDV, si l'écran est configuré pour **Aucun**, un utilisateur pourra rechercher et récupérer des commandes de l'une des manières suivantes.</span><span class="sxs-lookup"><span data-stu-id="13a43-117">When launching the **Recall order** operation from POS, if the display is configured to **None**, a user will be able to search and retrieve orders in one of the following ways.</span></span>
- <span data-ttu-id="13a43-118">Numérisez les codes-barres des commandes.</span><span class="sxs-lookup"><span data-stu-id="13a43-118">Scan order barcodes.</span></span> <span data-ttu-id="13a43-119">Cette opération effectue une recherche de correspondances dans les champs du numéro de commande, de la référence de canal et d'ID de ticket de caisse.</span><span class="sxs-lookup"><span data-stu-id="13a43-119">This will search order number, channel reference, and receipt ID fields for matches.</span></span>
- <span data-ttu-id="13a43-120">Sélectionnez l'icône **Rechercher les commandes** ou **Rechercher et filtrer** sur la barre des applications pour utiliser le mécanisme de filtre afin de localiser les commandes qui répondent aux critères de filtre.</span><span class="sxs-lookup"><span data-stu-id="13a43-120">Select **Search orders** or **Search and filter** icon on the AppBar to use the filtering mechanism to locate orders that meet the filter criteria.</span></span>
- <span data-ttu-id="13a43-121">Choisissez un filtre prédéfini dans le menu déroulant **Afficher les commandes** (commandes à traiter, commandes à prélever ou commandes à expédier).</span><span class="sxs-lookup"><span data-stu-id="13a43-121">Choose from a pre-defined filter from the **Show Orders** drop-down menu (orders to fulfill, orders to pick up, or orders to ship).</span></span>

![RecallOrderMainMenu](media/recallordermain.png)

<span data-ttu-id="13a43-123">Après application des critères de recherche, l'application affichera une liste des commandes client correspondantes.</span><span class="sxs-lookup"><span data-stu-id="13a43-123">After search criteria are applied, the application will display a list of matching sales orders.</span></span>

![RecallOrderDetail](media/orderrecalldetail.png)

<span data-ttu-id="13a43-125">Un utilisateur peut sélectionner une commande dans la liste pour afficher des détails supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="13a43-125">A user can select an order on the list to view additional details.</span></span> <span data-ttu-id="13a43-126">Le panneau d'informations situé sur le côté droit de l'écran affiche les détails de la commande sélectionnée, y compris les détails de la ligne de commande, les détails de livraison et les détails d'exécution.</span><span class="sxs-lookup"><span data-stu-id="13a43-126">The information panel on the right side of the screen displays specifics on the selected order, including order line details, delivery details, and fulfillment details.</span></span>

<span data-ttu-id="13a43-127">Dans la barre des applications, un utilisateur peut sélectionner une opération.</span><span class="sxs-lookup"><span data-stu-id="13a43-127">From the AppBar, a user can select an operation.</span></span> <span data-ttu-id="13a43-128">Selon l'état de la commande, certaines opérations peuvent ne pas être activées.</span><span class="sxs-lookup"><span data-stu-id="13a43-128">Depending on the status of the order, certain operations may not be enabled.</span></span>

- <span data-ttu-id="13a43-129">**Retourner** - Exécute un retour pour une ou plusieurs factures liées à la commande client sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13a43-129">**Return** – Executes a return for one or more invoices related to the selected customer order.</span></span>

- <span data-ttu-id="13a43-130">**Annuler** - Émet une annulation complète de la commande client sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13a43-130">**Cancel** – Issue a full cancellation of the selected sales order.</span></span>

- <span data-ttu-id="13a43-131">**Traiter** - Transfère l'utilisateur vers la page de traitement de la commande, qui sera pré-filtrée pour la commande sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13a43-131">**Fulfill** – Transfers the user to the order fulfillment page, which will be pre-filtered for the selected order.</span></span> <span data-ttu-id="13a43-132">Seules seront affichées les lignes de commande ouvertes pour le traitement par le magasin de l'utilisateur pour la commande sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13a43-132">Only order lines that are open for fulfillment by the user's store for the selected order will be displayed.</span></span>

- <span data-ttu-id="13a43-133">**Modifier** - Permet aux utilisateurs d'apporter des modifications à la commande client sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13a43-133">**Edit** – Allows users to make changes to the selected customer order.</span></span>

- <span data-ttu-id="13a43-134">**Prélever** - Lance le flux de prélèvement, qui permet à l'utilisateur de choisir les produits à prélever et crée la transaction de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="13a43-134">**Pick up** – Launches the pickup flow, which allows the user to choose the products to be picked up and creates the pickup sales transaction.</span></span>
