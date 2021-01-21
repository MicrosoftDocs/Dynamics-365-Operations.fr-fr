---
title: Statuts sur la gestion du transport
description: Cette rubrique explique comment créer un statut de transport et mapper ce statut sur un statut de transporteur.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 3f7d471771ec2b4703d878fbf395cd90902b6669
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4428351"
---
# <a name="transportation-management-statuses"></a><span data-ttu-id="ae453-103">Statuts sur la gestion du transport</span><span class="sxs-lookup"><span data-stu-id="ae453-103">Transportation management statuses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ae453-104">Paramétrez les codes données principales pour les statuts de transport afin d'interpréter les codes fournis par vos transporteurs.</span><span class="sxs-lookup"><span data-stu-id="ae453-104">Set up master codes for transportation statuses to interpret codes that are provided by your shipping carriers.</span></span> <span data-ttu-id="ae453-105">Cela vous permet de vous intégrer aux transporteurs pour fournir un statut.</span><span class="sxs-lookup"><span data-stu-id="ae453-105">This lets you integrate with shipping carriers to provide a status.</span></span> <span data-ttu-id="ae453-106">Le statut de transport que vous fournissez un pour code données principales de statut de transport peut vous aider à suivre le statut d'une charge, d'une expédition, ou d'un conteneur.</span><span class="sxs-lookup"><span data-stu-id="ae453-106">The transportation status that you provide for a transportation master status code can help you track the status of a load, shipment, or container.</span></span> <span data-ttu-id="ae453-107">Le statut de transport spécifique d'un chargement, d'une expédition ou d'un conteneur ne peut être mis à jour que par le biais de l'intégration des données et non manuellement par le biais de l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ae453-107">The specific transportation status for a load, shipment, or container can only be updated through data integration and not manually through the user interface.</span></span>

## <a name="create-a-transportation-status"></a><span data-ttu-id="ae453-108">Créer un statut de transport</span><span class="sxs-lookup"><span data-stu-id="ae453-108">Create a transportation status</span></span>

<span data-ttu-id="ae453-109">Pour créer un statut de transport, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ae453-109">To create a transportation status, follow these steps:</span></span>

1. <span data-ttu-id="ae453-110">Accédez à **Gestion du transport \> Configurer \> Données principales du statut du transport**.</span><span class="sxs-lookup"><span data-stu-id="ae453-110">Go to **Transportation management \> Setup \> Transportation status masters**.</span></span>
1. <span data-ttu-id="ae453-111">Cliquez sur **Nouveau** pour créer les données principales de statut de transport.</span><span class="sxs-lookup"><span data-stu-id="ae453-111">Select **New** to create a transportation status master.</span></span>
1. <span data-ttu-id="ae453-112">Dans le champ **Données principales de statut de transport**, entrez un code unique pour le statut de transport.</span><span class="sxs-lookup"><span data-stu-id="ae453-112">In the **Transportation status master** field, enter a unique code for the transportation status.</span></span>
1. <span data-ttu-id="ae453-113">Dans le champ **Type de transport**, sélectionnez *Transporteur* ou *Hub* comme type de transport.</span><span class="sxs-lookup"><span data-stu-id="ae453-113">In the **Transportation type** field, select either *Shipping carrier* or *Hub* as the type of transportation.</span></span>
1. <span data-ttu-id="ae453-114">Entrez un nom et un statut de transport.</span><span class="sxs-lookup"><span data-stu-id="ae453-114">Enter a name and transportation status.</span></span>
1. <span data-ttu-id="ae453-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ae453-115">Close the page.</span></span>

## <a name="map-a-transportation-status-to-a-carrier-status"></a><span data-ttu-id="ae453-116">Mapper un statut de transport à un statut de transporteur</span><span class="sxs-lookup"><span data-stu-id="ae453-116">Map a transportation status to a carrier status</span></span>

<span data-ttu-id="ae453-117">Pour mapper un statut de transport à un statut de transporteur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ae453-117">To map a transportation status to a carrier status, follow these steps:</span></span>

1. <span data-ttu-id="ae453-118">Accédez à **Gestion du transport \> Configurer \> Transporteurs \> Statut du transporteur**.</span><span class="sxs-lookup"><span data-stu-id="ae453-118">Go to **Transportation management \> Setup \> Carriers \> Carrier transportation status**.</span></span>
1. <span data-ttu-id="ae453-119">Cliquez sur **Nouveau** pour mettre en correspondance un transporteur et un code données principales de statut de transport.</span><span class="sxs-lookup"><span data-stu-id="ae453-119">Select **New** to map a code from a shipping carrier to a transportation status master code.</span></span>
1. <span data-ttu-id="ae453-120">Sélectionnez l'ID unique pour le transporteur et le service de transporteur.</span><span class="sxs-lookup"><span data-stu-id="ae453-120">Select the unique ID for the shipping carrier and the carrier service.</span></span>
1. <span data-ttu-id="ae453-121">Sélectionnez le code statut de transport que vous souhaitez mettre en correspondance avec le code du transporteur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ae453-121">Select the transportation status code that you want to map to the selected shipping carrier's code.</span></span>
1. <span data-ttu-id="ae453-122">Entrez le code externe utilisé par le transporteur.</span><span class="sxs-lookup"><span data-stu-id="ae453-122">Enter the external code that is used by the shipping carrier.</span></span>
1. <span data-ttu-id="ae453-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ae453-123">Close the page.</span></span>