---
title: Masquer les modes de livraison hors transporteur dans les options d'expédition dans PDV
description: Cette rubrique décrit une option de configuration qui peut empêcher les modes de livraison hors transporteur de s'afficher pour la sélection lorsque des ordres d'expédition sont créés dans l'application de point de vente (PDV).
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 09ea83b3336b208f8af0a91025c2e6c50d64c385
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2019
ms.locfileid: "2659019"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a><span data-ttu-id="c168a-103">Masquer les modes de livraison hors transporteur dans les options d'expédition dans PDV</span><span class="sxs-lookup"><span data-stu-id="c168a-103">Hide non-carrier delivery modes from the shipping options in POS</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="c168a-104">Cette rubrique décrit une option de configuration disponible pour l'application de point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="c168a-104">This topic describes a configuration option that is available for the point of sale (POS) application.</span></span> <span data-ttu-id="c168a-105">Cette option de configuration modifie le comportement de la sélection d'un mode de livraison lorsque des ordres d'expédition sont créés dans PDV.</span><span class="sxs-lookup"><span data-stu-id="c168a-105">This configuration option changes the behavior for the selection of a mode of delivery when shipment orders are created in POS.</span></span>

<span data-ttu-id="c168a-106">Lorsque les utilisateurs créent des ordres d'expédition client dans PDV, ils peuvent sélectionner un mode de livraison pour l'expédition.</span><span class="sxs-lookup"><span data-stu-id="c168a-106">When users create customer shipment orders in POS, they can select a mode of delivery for the shipment.</span></span> <span data-ttu-id="c168a-107">Cette fonctionnalité est disponible, que la commande soit expédiée dans son ensemble ou uniquement les lignes sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="c168a-107">This functionality is available regardless of whether the whole order is being shipped or only selected lines.</span></span>

<span data-ttu-id="c168a-108">Par défaut, la boîte de dialogue dans laquelle un mode de livraison est sélectionné affiche tous les modes de livraison valides pour la combinaison d'un canal, d'un article et d'une adresse de livraison.</span><span class="sxs-lookup"><span data-stu-id="c168a-108">By default, the dialog box where a mode of delivery is selected shows all the valid modes of delivery for the combination of a channel, an item, and a delivery address.</span></span> <span data-ttu-id="c168a-109">Ces modes de livraison sont définis sur la page **Modes de livraison** de Retail Headquarters (**Ventes et marketing \> Paramétrage \> Distribution \> Modes de livraison**).</span><span class="sxs-lookup"><span data-stu-id="c168a-109">These modes of delivery are defined on the **Modes of delivery** page in Retail Headquarters (**Sales and marketing \> Setup \> Distribution \> Modes of delivery**).</span></span> <span data-ttu-id="c168a-110">Les modes de livraison « hors transporteur », tels que **À emporter** ou **Prélèvement**, peuvent également être affichés pour la sélection dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="c168a-110">"Non-carrier" modes of delivery, such as **Carryout** or **Pickup**, might also appear for selection in the dialog box.</span></span>

<span data-ttu-id="c168a-111">Toutefois, une fonctionnalité a été ajoutée pour vous permettre de masquer les modes de livraison hors transporteur dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="c168a-111">However, a feature has been added that lets you hide non-carrier modes of delivery in the dialog box.</span></span> <span data-ttu-id="c168a-112">Pour activer cette fonctionnalité, sur la page **Paramètres des ventes au détail**, sous l'onglet **Commandes client**, définissez l'option **Afficher uniquement les options de mode transporteur pour les ordres d'expédition** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c168a-112">To turn on this feature, on the **Retail parameters** page, on the **Customer orders** tab, set the **Show only carrier mode options for ship orders** option to **Yes**.</span></span> <span data-ttu-id="c168a-113">Après avoir activé cette fonctionnalité et exécuté les tâches de distribution appropriées pour synchroniser les informations avec la base de données du canal, les modes de livraison hors porteur n'apparaissent pas pour la sélection au cours du processus de créer des ordres d'expédition dans PDV.</span><span class="sxs-lookup"><span data-stu-id="c168a-113">After you turn on this feature and run the appropriate distribution jobs to sync the information to the channel database, non-carrier modes of delivery won't appear for selection during the process of creating shipment orders in POS.</span></span>
