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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: c06dfa697e3e0eab7a7f4183da9f178af818a6d7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206156"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a><span data-ttu-id="1231d-103">Masquer les modes de livraison hors transporteur dans les options d'expédition dans PDV</span><span class="sxs-lookup"><span data-stu-id="1231d-103">Hide non-carrier delivery modes from the shipping options in POS</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="1231d-104">Cette rubrique décrit une option de configuration disponible pour l'application de point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="1231d-104">This topic describes a configuration option that is available for the point of sale (POS) application.</span></span> <span data-ttu-id="1231d-105">Cette option de configuration modifie le comportement de la sélection d'un mode de livraison lorsque des ordres d'expédition sont créés dans PDV.</span><span class="sxs-lookup"><span data-stu-id="1231d-105">This configuration option changes the behavior for the selection of a mode of delivery when shipment orders are created in POS.</span></span>

<span data-ttu-id="1231d-106">Lorsque les utilisateurs créent des ordres d'expédition client dans PDV, ils peuvent sélectionner un mode de livraison pour l'expédition.</span><span class="sxs-lookup"><span data-stu-id="1231d-106">When users create customer shipment orders in POS, they can select a mode of delivery for the shipment.</span></span> <span data-ttu-id="1231d-107">Cette fonctionnalité est disponible, que la commande soit expédiée dans son ensemble ou uniquement les lignes sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1231d-107">This functionality is available regardless of whether the whole order is being shipped or only selected lines.</span></span>

<span data-ttu-id="1231d-108">Par défaut, la boîte de dialogue dans laquelle un mode de livraison est sélectionné affiche tous les modes de livraison valides pour la combinaison d'un canal, d'un article et d'une adresse de livraison.</span><span class="sxs-lookup"><span data-stu-id="1231d-108">By default, the dialog box where a mode of delivery is selected shows all the valid modes of delivery for the combination of a channel, an item, and a delivery address.</span></span> <span data-ttu-id="1231d-109">Ces modes de livraison sont définis sur la page **Modes de livraison** de Headquarters (**Ventes et marketing \> Paramétrage \> Distribution \> Modes de livraison**).</span><span class="sxs-lookup"><span data-stu-id="1231d-109">These modes of delivery are defined on the **Modes of delivery** page in Headquarters (**Sales and marketing \> Setup \> Distribution \> Modes of delivery**).</span></span> <span data-ttu-id="1231d-110">Les modes de livraison « hors transporteur », tels que **À emporter** ou **Prélèvement**, peuvent également être affichés pour la sélection dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="1231d-110">"Non-carrier" modes of delivery, such as **Carryout** or **Pickup**, might also appear for selection in the dialog box.</span></span>

<span data-ttu-id="1231d-111">Toutefois, une fonctionnalité a été ajoutée pour vous permettre de masquer les modes de livraison hors transporteur dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="1231d-111">However, a feature has been added that lets you hide non-carrier modes of delivery in the dialog box.</span></span> <span data-ttu-id="1231d-112">Pour activer cette fonctionnalité, sur la page **Paramètres de commerce**, sous l'onglet **Commandes client**, définissez l'option **Afficher uniquement les options de mode transporteur pour les ordres d'expédition** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1231d-112">To turn on this feature, on the **Commerce parameters** page, on the **Customer orders** tab, set the **Show only carrier mode options for ship orders** option to **Yes**.</span></span> <span data-ttu-id="1231d-113">Après avoir activé cette fonctionnalité et exécuté les tâches de distribution appropriées pour synchroniser les informations avec la base de données du canal, les modes de livraison hors porteur n'apparaissent pas pour la sélection au cours du processus de créer des ordres d'expédition dans PDV.</span><span class="sxs-lookup"><span data-stu-id="1231d-113">After you turn on this feature and run the appropriate distribution jobs to sync the information to the channel database, non-carrier modes of delivery won't appear for selection during the process of creating shipment orders in POS.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]