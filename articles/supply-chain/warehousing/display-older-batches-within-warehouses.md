---
title: "Configuration des lots plus anciens d'affichage dans l'entrepôt sur un périphérique mobile"
description: "Cette rubrique décrit la procédure de paramétrage d'un appareil mobile pour afficher une liste des emplacements avec des lots plus anciens que l'emplacement actuel d'une ligne de travail."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4f2dc9221b72600c928db9fd306038725c7af305
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a><span data-ttu-id="ef196-103">Configuration des lots plus anciens d'affichage dans l'entrepôt sur un périphérique mobile</span><span class="sxs-lookup"><span data-stu-id="ef196-103">Configure Display older batches within warehouse on a mobile device</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="ef196-104">La configuration **Lots plus anciens d'affichage dans l'entrepôt** permet d'afficher une liste des emplacements avec des lots plus anciens que l'emplacement actuel de la ligne de travail.</span><span class="sxs-lookup"><span data-stu-id="ef196-104">The **Display older batches within warehouse** configuration lets you display a list of locations with batches older than the current location of the work line.</span></span> <span data-ttu-id="ef196-105">La liste des emplacements affichés inclut des informations sur les lots plus anciens de l'emplacement avec la date d'expiration et le stock physique de chaque lot.</span><span class="sxs-lookup"><span data-stu-id="ef196-105">The list of locations that are displayed includes information about the older batches in the location with the expiration date and the physical inventory of each batch.</span></span> <span data-ttu-id="ef196-106">Vous pouvez choisir de collecter à un nouvel emplacement ou de continuer à collecter à l'emplacement actuel.</span><span class="sxs-lookup"><span data-stu-id="ef196-106">You can choose to pick from a new location or to continue picking from the current location.</span></span> 
- <span data-ttu-id="ef196-107">Collecte à un nouvel emplacement : Si vous sélectionnez un nouvel emplacement de collecte, la ligne de travail actuelle est mise à jour pour utiliser le nouvel emplacement et le travail continuera normalement avec le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="ef196-107">Pick from a new location - If you select a new location to pick from, the  current work line will be updated to use the new location and work will continue as usual with the new location.</span></span> <span data-ttu-id="ef196-108">Pour que le nouvel emplacement soit valide, il doit avoir suffisamment de quantité disponible pour la ligne de travail entière.</span><span class="sxs-lookup"><span data-stu-id="ef196-108">For the new location to be valid, it must have enough available quantity for the whole work line.</span></span> <span data-ttu-id="ef196-109">Si la quantité requise n'est pas disponible, la ligne de travail n'est pas mise à jour, et la liste s'affiche.</span><span class="sxs-lookup"><span data-stu-id="ef196-109">If the required quantity is not available, the work line will not be updated, and the list will display.</span></span> 
- <span data-ttu-id="ef196-110">Continuer de collecter à l'emplacement actuel : Si vous ignorez l'emplacement de la ligne de travail actuelle, les quantités de la ligne de travail continuent à être collectées à l'emplacement d'origine.</span><span class="sxs-lookup"><span data-stu-id="ef196-110">Continue picking from the current location - If you continue with the current work line location, the quantities for the work line will continue to be picked from the original location.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="ef196-111">Dans ce cas</span><span class="sxs-lookup"><span data-stu-id="ef196-111">Where it applies</span></span>
<span data-ttu-id="ef196-112">Lots plus anciens d'affichage dans l'entrepôt est configuré sur les options du menu de l'appareil mobile et affecte le prélèvement pour les articles du lot ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ef196-112">Display older batches within warehouse is configured on mobile device menu items and affects the pick for batch below items.</span></span>

## <a name="set-up-display-older-batches-within-warehouse"></a><span data-ttu-id="ef196-113">Paramétrer des lots plus anciens d'affichage dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="ef196-113">Set up Display older batches within warehouse</span></span>
<span data-ttu-id="ef196-114">La configuration **Lots plus anciens d'affichage dans l'entrepôt** est disponible dans les options du menu d'appareil mobile lorsque l'option **Prélever le traitement par lots le plus ancien** est définie sur **Avertir**.</span><span class="sxs-lookup"><span data-stu-id="ef196-114">The **Display older batches within warehouse** configuration is available on mobile device menu items when the **Pick oldest batch** option is set to **Warn**.</span></span>

- <span data-ttu-id="ef196-115">Sous **Gestion des entrepôts** > **Paramétrage** > **Appareil mobile** > **Options de menu d'appareil mobile**, définissez **Utiliser un travail existant** sur **Oui** pour l'option de menu, et sélectionnez **Avertir** dans le champ **Prélever le traitement par lots le plus ancien**.</span><span class="sxs-lookup"><span data-stu-id="ef196-115">Under **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**, set **Use existing work** to **Yes** for the menu item, and select **Warn** in the **Pick oldest batch** field.</span></span> 


