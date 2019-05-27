---
title: États sur le prix de vente au détail
description: Cette rubrique fournit une vue d'ensemble de la fonction d'état de prix qui peut être utilisée pour afficher les changements de prix à venir pour les produits assortis.
author: shajain
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 72f4d248f3ac49bbfd8e5a7a12352d92b89bb0eb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564945"
---
# <a name="retail-price-reports"></a><span data-ttu-id="3f0ab-103">États sur le prix de vente au détail</span><span class="sxs-lookup"><span data-stu-id="3f0ab-103">Retail price reports</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="3f0ab-104">Afin de fournir des prix concurrentiels à leurs clients, les détaillants changent souvent les prix des produits.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-104">In order to provide competitive prices to their customers, retailers often change prices of products.</span></span> <span data-ttu-id="3f0ab-105">Les directeurs de magasins souhaitent pouvoir accéder facilement aux changements de prix récents ou à venir afin de pouvoir planifier les ressources requises pour mettre à jour les étiquettes de prix affichées sur les étagères en boutique.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-105">Store managers want the ability to easily access recent or upcoming price changes so that they can plan for the required resources to update the price labels displayed on the store shelves.</span></span> <span data-ttu-id="3f0ab-106">Avec la version 10.0 de Dynamics 365 for Retail, un directeur de magasin peut ouvrir l'état **Prix** en accédant à **Tous les magasins de vente au détail \> Magasin \> État de prix** et en affichant les prix mis à jour pour les produits associés au magasin.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-106">With release 10.0 of Dynamics 365 for Retail, a store manager can open the **Price** report by navigating to **All retail stores \> Store \> Price report** and viewing the updated prices for the products associated to the store.</span></span> 

<span data-ttu-id="3f0ab-107">Pour activer l'état de prix, le paramètre **Activer l'état de prix pour le magasin de vente au détail** doit être activé.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-107">To enable the price report, the **Enable price report for Retail store** parameter must be turned on.</span></span> <span data-ttu-id="3f0ab-108">Ce paramètre se trouve sous **Paramètres de vente au détail \> Remises \> Divers**. En ouvrant la page **État de prix**, une boîte de dialogue s'affiche avec différentes configurations.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-108">This parameter is located on the **Retail parameters \> Discounts \> Miscellaneous** tab. Opening the **Price report** page displays a dialog box with various configurations.</span></span> <span data-ttu-id="3f0ab-109">Les configurations disponibles sont répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-109">The available configurations are listed below.</span></span>

| <span data-ttu-id="3f0ab-110">Configuration</span><span class="sxs-lookup"><span data-stu-id="3f0ab-110">Configuration</span></span> | <span data-ttu-id="3f0ab-111">Description</span><span class="sxs-lookup"><span data-stu-id="3f0ab-111">Description</span></span> |
|---|---|
| <span data-ttu-id="3f0ab-112">Date de début/de fin</span><span class="sxs-lookup"><span data-stu-id="3f0ab-112">From date / To date</span></span>| <span data-ttu-id="3f0ab-113">La plage de dates pour laquelle l'état de prix doit être généré.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-113">The date range for which the price report should be generated.</span></span> <span data-ttu-id="3f0ab-114">La durée est actuellement limitée à 7 jours.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-114">The duration is currently limited to 7 days.</span></span> |
| <span data-ttu-id="3f0ab-115">Canal</span><span class="sxs-lookup"><span data-stu-id="3f0ab-115">Channel</span></span>| <span data-ttu-id="3f0ab-116">Le magasin de vente au détail pour lequel l'état de prix doit être généré.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-116">The retail store for which the price report should be generated.</span></span> |
| <span data-ttu-id="3f0ab-117">Afficher les produits avec le stock disponible</span><span class="sxs-lookup"><span data-stu-id="3f0ab-117">Display products with available inventory</span></span>| <span data-ttu-id="3f0ab-118">En définissant ce paramètre sur **Oui**, les prix s'affichent uniquement pour les produits avec un stock disponible en magasin.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-118">Setting this to **Yes** will show the prices for only those products which currently have physical inventory available in the store.</span></span> |
| <span data-ttu-id="3f0ab-119">Afficher les prix des variantes</span><span class="sxs-lookup"><span data-stu-id="3f0ab-119">Display prices for variants</span></span> | <span data-ttu-id="3f0ab-120">En définissant ce paramètre sur **Oui**, les prix des variantes s'affichent ainsi que les produits génériques.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-120">Setting this to **Yes** will display the prices of the variants along with the product masters.</span></span> <span data-ttu-id="3f0ab-121">Ce paramètre doit être défini sur **Activé** si vous avez des prix spécifiques aux variantes, car le nombre de lignes grandit de plus en plus.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-121">This should only be turned **On** if you have variant-specific prices, because the number of rows grows very large.</span></span> <span data-ttu-id="3f0ab-122">Dans les versions à venir, nous activerons les prix selon les dimensions, afin que le responsable du magasin puisse choisir les dimensions pour lesquelles les prix doivent être affichés.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-122">In future releases, we will enable the dimensions-based prices so that the store manager can choose the dimensions for which the prices should be displayed.</span></span> |
| <span data-ttu-id="3f0ab-123">Afficher les produits avec les modifications de prix</span><span class="sxs-lookup"><span data-stu-id="3f0ab-123">Display products with price changes</span></span> | <span data-ttu-id="3f0ab-124">En définissant ce paramètre sur **Oui**, les prix s'affichent pour uniquement ces dates auxquelles le prix a été modifié.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-124">Setting this to **Yes** will display the prices for only those dates on which the price has been changed.</span></span> <span data-ttu-id="3f0ab-125">Le prix pour *un jour avant* la **Date de début** sélectionnée sera toujours affichée, de telle sorte que le responsable du magasin peut facilement identifier les produits dont les prix n'ont pas changé pendant l'intégralité de la durée, et peut également visualiser le prix actuel.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-125">The price for *one day before* the selected **From date** will always be displayed, so that the store manager can easily identity the products which have not changed prices for the entire selected duration, and can also view the current price.</span></span> |

<span data-ttu-id="3f0ab-126">Une fois l'état généré, le fichier Excel peut être téléchargé pour tout besoin de filtre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-126">After the report is generated, the Excel file can be downloaded for any additional filtering needs.</span></span> <span data-ttu-id="3f0ab-127">L'état de prix peut être également utilisé pour vérifier les prix historiques des produits pour les dates passées.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-127">The price report can also be used to check the historical prices of products for past dates.</span></span>
