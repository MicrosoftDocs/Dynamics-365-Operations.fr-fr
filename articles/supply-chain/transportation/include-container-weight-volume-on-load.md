---
title: Inclure le poids et le volume du conteneur dans la charge
description: "Cette rubrique explique comment configurer et appliquer des fonctionnalités pour inclure le poids et le volume du conteneur sur des charges."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: bafd6129dbbf3aff5f4be0cf10a71e9039f879e2
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="include-container-weight-and-volume-on-load"></a><span data-ttu-id="5508f-103">Inclure le poids et le volume du conteneur dans la charge</span><span class="sxs-lookup"><span data-stu-id="5508f-103">Include container weight and volume on load</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="5508f-104">La fonctionnalité permettant d'inclure le poids et le volume du conteneur sur une charge donne une représentation claire du poids total et du volume des conteneurs et des articles en cours de chargement.</span><span class="sxs-lookup"><span data-stu-id="5508f-104">The functionality for including the container weight and volume on a load gives a clear representation of the total weight and volume of containers and items that are going on a load.</span></span>

<span data-ttu-id="5508f-105">Une charge contient une ou plusieurs expéditions, et les expéditions contiennent des articles séparés composant une commande client unique ou plusieurs commandes client.</span><span class="sxs-lookup"><span data-stu-id="5508f-105">A load contains a single shipment or multiple shipments, and these shipments contain distinct items that belong to a single sales order or multiple sales orders.</span></span> <span data-ttu-id="5508f-106">Les articles sont stockés dans un conteneur, et les conteneurs sont chargés sur une charge.</span><span class="sxs-lookup"><span data-stu-id="5508f-106">The items are stored inside a container, and containers are loaded on a load.</span></span> <span data-ttu-id="5508f-107">Les articles hors d'un conteneur peuvent également faire partie d'une charge.</span><span class="sxs-lookup"><span data-stu-id="5508f-107">Items that are outside a container can also be part of a load.</span></span> <span data-ttu-id="5508f-108">Selon ces conditions, le système calcule les valeurs pour le poids et le volume de la charge en considérant le poids et le volume des conteneurs et des articles.</span><span class="sxs-lookup"><span data-stu-id="5508f-108">Based on these conditions, the system calculates values for the weight and volume on the load by considering the weight and volume of both containers and items.</span></span>

<span data-ttu-id="5508f-109">Si les valeurs calculées ne sont pas précises, vous pouvez les modifier en entrant les valeurs réelles du poids et du volume de la charge.</span><span class="sxs-lookup"><span data-stu-id="5508f-109">If the calculated values aren’t precise, you can adjust them by entering the actual values for the weight and volume on the load.</span></span> <span data-ttu-id="5508f-110">Les valeurs pour le poids et le volume sont utilisées dans les processus de gestion du transport.</span><span class="sxs-lookup"><span data-stu-id="5508f-110">The values for the weight and volume are used in transportation management processes.</span></span> <span data-ttu-id="5508f-111">Par exemple, les valeurs sont utilisées dans l'atelier des routes et frais, où elles servent à définir le taux et la gamme pour les charges. Elles sont également utilisées pour les offres de transport et l'enregistrement des arrivées.</span><span class="sxs-lookup"><span data-stu-id="5508f-111">For example, the values are used in the rate route workbench, where they help define the rate and route for loads, and they are also used for transportation tenders and driver check-in.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="5508f-112">Dans ce cas</span><span class="sxs-lookup"><span data-stu-id="5508f-112">Where it applies</span></span>

<span data-ttu-id="5508f-113">La fonctionnalité pour inclure le poids et le volume de conteneur sur une charge s'applique dans les processus de gestion du transport, tels que l'atelier des routes et frais, les offres de transport, et l'enregistrement des arrivées.</span><span class="sxs-lookup"><span data-stu-id="5508f-113">The functionality for including the container weight and volume on a load applies in transportation management processes, such as the rate route workbench, transportation tenders, and driver check-in.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="5508f-114">Comment elle est paramétrée</span><span class="sxs-lookup"><span data-stu-id="5508f-114">How it is set up</span></span>

<span data-ttu-id="5508f-115">Le nombre de conteneurs qui doit être pris en compte pour une charge est calculé en fonction du poids et du volume du conteneur et du pourcentage d'utilisation d'un conteneur.</span><span class="sxs-lookup"><span data-stu-id="5508f-115">The number of containers that should be considered for a load is calculated based on the weight and volume of the container, and on the percentage of the container is used.</span></span>

-   <span data-ttu-id="5508f-116">Pour définir le poids et le volume pour un conteneur, cliquez sur **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Types de conteneur**.</span><span class="sxs-lookup"><span data-stu-id="5508f-116">To set the weight and volume for a container, click **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>

-   <span data-ttu-id="5508f-117">Pour définir le pourcentage d'utilisation d'un conteneur, cliquez sur **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Groupes de conteneur**, puis entrez une valeur dans le champ **Pourcentage d'utilisation du conteneur**.</span><span class="sxs-lookup"><span data-stu-id="5508f-117">To set the container utilization percentage, click **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**, and then enter a value in the **Container utilization percentage** field.</span></span>

