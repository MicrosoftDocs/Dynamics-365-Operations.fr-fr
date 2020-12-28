---
title: Création d'une demande d'articles à partir d'une commande de service
description: Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d'article en stock pour celle-ci.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18484b637723cef43cad288c08ddfe53cddf9e03
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428012"
---
# <a name="create-item-requirements-for-service-orders"></a><span data-ttu-id="68915-103">Création d'une demande d'articles à partir d'une commande de service</span><span class="sxs-lookup"><span data-stu-id="68915-103">Create item requirements for service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="68915-104">Vous pouvez créer une commande de service pour suivre et gérer les services que vous fournissez à vos clients.</span><span class="sxs-lookup"><span data-stu-id="68915-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="68915-105">Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d'article en stock pour celle-ci.</span><span class="sxs-lookup"><span data-stu-id="68915-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="68915-106">Une demande d'article peut être immédiatement consommée du stock, ou elle peut lancer une commande fournisseur pour l'article.</span><span class="sxs-lookup"><span data-stu-id="68915-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="68915-107">En utilisant une demande d'article au lieu d'une transaction d'article, vous pouvez prévoir la livraison juste avant que l'article soit utilisé, créer une commande fournisseur, inclure l'article dans le cadre d'un accord commercial et inclure la demande d'article dans la planification de la production.</span><span class="sxs-lookup"><span data-stu-id="68915-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="68915-108">Les demandes d'articles pour les commandes de service sont traitées au travers d'un projet.</span><span class="sxs-lookup"><span data-stu-id="68915-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="68915-109">Pour créer une demande d'articles sur une commande de service, cette dernière doit être associée à un projet.</span><span class="sxs-lookup"><span data-stu-id="68915-109">To create an item requirement on a service order, the service order must be assigned to a project.</span></span> <span data-ttu-id="68915-110">Après avoir créé une demande d'articles pour une commande de service, vous pouvez afficher la demande d'articles dans l'écran **Projets** du projet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="68915-110">After you create an item requirement for a service order, you can view the item requirement in the **Projects** form for the selected project.</span></span>

## <a name="create-an-item-requirement-for-a-service-order"></a><span data-ttu-id="68915-111">Création d'une demande d'articles pour une commande de service</span><span class="sxs-lookup"><span data-stu-id="68915-111">Create an item requirement for a service order</span></span>

1.  <span data-ttu-id="68915-112">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="68915-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="68915-113">Sélectionnez la commande de service que vous souhaitez créer pour la demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="68915-113">Select the service order that you want to create an item requirement for.</span></span>

3.  <span data-ttu-id="68915-114">Dans le volet **Actions**, sous l'onglet **Dispatch**, cliquez sur **Demande d'articles**.</span><span class="sxs-lookup"><span data-stu-id="68915-114">On the **Action Pane**, on the **Dispatch** tab, click **Item requirement**.</span></span>

4.  <span data-ttu-id="68915-115">Dans l'écran **Demande d'articles**, entrez les informations pour l'article requis.</span><span class="sxs-lookup"><span data-stu-id="68915-115">In the **Item requirements** form, enter information for the required item.</span></span> <span data-ttu-id="68915-116">Pour plus d'informations sur les champs spécifiques, voir [Demande d'articles (écran)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).</span><span class="sxs-lookup"><span data-stu-id="68915-116">For more information about the specific fields, see [Item requirements (form)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).</span></span>

## <a name="create-an-item-requirement-for-a-service-agreement"></a><span data-ttu-id="68915-117">Création d'une demande d'articles pour un accord de service</span><span class="sxs-lookup"><span data-stu-id="68915-117">Create an item requirement for a service agreement</span></span>

1.  <span data-ttu-id="68915-118">Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.</span><span class="sxs-lookup"><span data-stu-id="68915-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="68915-119">Ouvrez l'accord de service pour lequel vous souhaitez créer une demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="68915-119">Open the service agreement for which you want to create an item requirement.</span></span>

3.  <span data-ttu-id="68915-120">Dans l'organisateur **Lignes**, cliquez sur **Ajouter** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="68915-120">On the **Lines** FastTab, click **Add** to create a new line.</span></span>

4.  <span data-ttu-id="68915-121">Dans le champ **Type de transaction**, sélectionnez **Article**.</span><span class="sxs-lookup"><span data-stu-id="68915-121">In the **Transaction type** field, select **Item**.</span></span>

5.  <span data-ttu-id="68915-122">Dans le champ **Paramétrage de l'article**, sélectionnez **Demande d'articles**.</span><span class="sxs-lookup"><span data-stu-id="68915-122">In the **Item setup** field, select **Item requirement**.</span></span>

6.  <span data-ttu-id="68915-123">Dans le champ **Numéro d'article**, sélectionnez l'article requis pour l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="68915-123">In the **Item number** field, select the item that is required for the service agreement.</span></span>

7.  <span data-ttu-id="68915-124">Dans l'organisateur **Détails de ligne**, sous l'onglet **Dimensions de produit**, dans le champ **Site**, sélectionnez le site de stock pour l'article.</span><span class="sxs-lookup"><span data-stu-id="68915-124">On the **Line details** FastTab, on the **Product dimensions** tab, in the **Site** field, select the inventory site for the item.</span></span>

8.  <span data-ttu-id="68915-125">Pour créer une commande de service à partir de la ligne d'accord, dans l'organisateur **Lignes**, cliquez sur **Créer des commandes de service**, puis entrez les informations appropriées dans l'écran **Créer des commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="68915-125">To create a service order from the agreement line, on the **Lines** FastTab, click **Create service orders**, and then enter the relevant information in the **Create service orders** form.</span></span> 


## <a name="see-also"></a><span data-ttu-id="68915-126">Voir également :</span><span class="sxs-lookup"><span data-stu-id="68915-126">See also</span></span>

<span data-ttu-id="68915-127">[Création de commandes de service automatiquement](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="68915-127">[Create service orders automatically](create-service-orders-automatically.md).</span></span>

  


