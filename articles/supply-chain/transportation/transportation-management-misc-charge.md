---
title: Frais divers de gestion du transport
description: Cette rubrique explique comment les frais générés par le transport doivent être associés à un code de facturation.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 4f58db216176832d61bdafbe43831ededd3dd6dc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233413"
---
# <a name="transportation-management-miscellaneous-charges"></a><span data-ttu-id="f8dbb-103">Frais divers de gestion du transport</span><span class="sxs-lookup"><span data-stu-id="f8dbb-103">Transportation management miscellaneous charges</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8dbb-104">Comme pour tous les frais divers, les frais générés par le transport doivent être associés à un code de facturation.</span><span class="sxs-lookup"><span data-stu-id="f8dbb-104">As with all miscellaneous charges, transportation-generated charges must be associated with a charge code.</span></span> <span data-ttu-id="f8dbb-105">Sinon, ils ne seront pas ajoutés à la commande en tant que frais divers.</span><span class="sxs-lookup"><span data-stu-id="f8dbb-105">Otherwise, they won't be added back to the order as a miscellaneous charge.</span></span> <span data-ttu-id="f8dbb-106">Le **Code des frais** détermine la façon dont les frais sont comptabilisés par rapport à la commande et à la ligne de commande où ils sont ajoutés.</span><span class="sxs-lookup"><span data-stu-id="f8dbb-106">The **Charges code** determines how the charge is accounted for in relation to the order and order line where it is added.</span></span>

<span data-ttu-id="f8dbb-107">Aller à **Gestion des transports > Configurer > Classement > Frais divers** pour définir les critères de qualification qui déterminent quand un **Code des frais** est appliqué à des frais.</span><span class="sxs-lookup"><span data-stu-id="f8dbb-107">Go to **Transportation management > Setup > Rating > Miscellaneous charges** to define the qualifying criteria that determine when a specific **Charges code** is applied to a charge.</span></span>

<span data-ttu-id="f8dbb-108">Vous devez avoir au moins une configuration pour chaque paramètre **Module de frais** (*Client* et *Vendeur*) où le **Type de frais divers** est réglé sur *Aucun*.</span><span class="sxs-lookup"><span data-stu-id="f8dbb-108">You should have at least one setup for each relevant **Charges module** setting (*Customer* and *Vendor*) where the **Miscellaneous charge type** is set to *None*.</span></span> <span data-ttu-id="f8dbb-109">S’il manque, les frais divers ne seront *pas* ajouté à la commande.</span><span class="sxs-lookup"><span data-stu-id="f8dbb-109">If this is missing, the miscellaneous charge will *not* be added to the order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]