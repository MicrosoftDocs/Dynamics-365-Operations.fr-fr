---
title: Gestion améliorée des articles suivis par lots
description: Cette rubrique décrit les améliorations qui ont été apportées à la gestion des lots pour les articles suivis par lots pendant le processus de validation des relevés de vente au détail.
author: josaw1
manager: AnnBe
ms.date: 05/28/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4456fc3d5bc4547fa8211642b11ca6df455fa187
ms.sourcegitcommit: aec1dcd44274e9b8d0770836598fde5533b7b569
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2019
ms.locfileid: "1617387"
---
# <a name="improved-handling-of-batch-tracked-items"></a><span data-ttu-id="fe489-103">Gestion améliorée des articles suivis par lots</span><span class="sxs-lookup"><span data-stu-id="fe489-103">Improved handling of batch-tracked items</span></span>

<span data-ttu-id="fe489-104">Dans le point de vente (PDV) Microsoft Dynamics 365 for Retail, les numéros de lot ne peuvent pas être capturés pour les articles suivis par lots au moment de la vente.</span><span class="sxs-lookup"><span data-stu-id="fe489-104">In Microsoft Dynamics 365 for Retail Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</span></span> <span data-ttu-id="fe489-105">Toutefois, pour des configurations spécifiques, lorsque les ventes sont validées dans le siège par le biais des commandes client ou de la validation des relevés, le système Microsoft Dynamics s'attend à ce que des numéros de lot valides soient disponibles pour les articles suivis par lots et qu'ils soient utilisés pendant le processus de facturation.</span><span class="sxs-lookup"><span data-stu-id="fe489-105">However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</span></span>

<span data-ttu-id="fe489-106">Si des numéros de lot valides sont disponibles pour les produits, le processus de facturation des commandes client et le processus de facturation des commandes client par le biais de la validation des relevés les utilisent.</span><span class="sxs-lookup"><span data-stu-id="fe489-106">If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</span></span> <span data-ttu-id="fe489-107">Sinon, le processus de facturation des commandes client ne peut pas être validé et l'utilisateur POS reçoit un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="fe489-107">Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</span></span> <span data-ttu-id="fe489-108">La validation des relevés passe ensuite à l'état d'erreur.</span><span class="sxs-lookup"><span data-stu-id="fe489-108">Statement posting then goes into an error state.</span></span> <span data-ttu-id="fe489-109">Cet état d'erreur se produit même si un stock négatif a été activé pour les produits.</span><span class="sxs-lookup"><span data-stu-id="fe489-109">This error state occurs even when negative inventory has been turned on for the products.</span></span>

<span data-ttu-id="fe489-110">Les améliorations qui ont été apportées dans Microsoft Dynamics for Retail version 10.0.4 et ultérieure garantissent qu'en cas d'activation d'un stock négatif pour les articles suivis par lots, la facturation des commandes client et la facturation des commandes client par le biais de la validation des relevés ne sont pas bloquées pour ces articles si le stock est égal à 0 (zéro) ou un numéro de lot n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="fe489-110">Improvements that have been made in Microsoft Dynamics for Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</span></span> <span data-ttu-id="fe489-111">La nouvelle fonctionnalité utilise un ID de lot par défaut pour les lignes de vente lorsque les numéros de lot ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="fe489-111">The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</span></span>

<span data-ttu-id="fe489-112">Pour définir l'ID de lot par défaut utilisé pour les commandes client, dans la page **Paramètres des ventes au détail**, sous l'onglet **Commandes client**, dans le raccourci **Commande**, définissez le champ **ID de lot par défaut**.</span><span class="sxs-lookup"><span data-stu-id="fe489-112">To define the default batch ID that is used for customer orders, on the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, set the **Default batch id** field.</span></span>

<span data-ttu-id="fe489-113">Pour définir l'ID de lot par défaut utilisé pour la facturation des commandes client par le biais de la validation des relevés, dans la page **Paramètres des ventes au détail**, sous l'onglet **Validation**, dans le raccourci **Mise à jour du stock**, définissez le champ **ID de lot par défaut**.</span><span class="sxs-lookup"><span data-stu-id="fe489-113">To define the default batch ID that is used for sales order invoicing through statement posting, on the **Retail parameters** page, on the **Posting** tab, on the **Inventory update** FastTab, set the **Default batch id** field.</span></span>

> [!NOTE]
> <span data-ttu-id="fe489-114">Cette fonctionnalité est disponible uniquement lorsque l'entreposage avancé est activé pour l'entrepôt et les articles spécifiques.</span><span class="sxs-lookup"><span data-stu-id="fe489-114">This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</span></span> <span data-ttu-id="fe489-115">Dans une version ultérieure, la fonctionnalité sera également prise en charge pour les scénarios où la gestion avancée des entrepôts n'est pas utilisée.</span><span class="sxs-lookup"><span data-stu-id="fe489-115">In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</span></span>
