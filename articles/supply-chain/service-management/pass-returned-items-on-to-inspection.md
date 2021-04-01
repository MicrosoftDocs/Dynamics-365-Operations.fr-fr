---
title: Transmission d’articles retournés pour inspection
description: Lorsque vous enregistrez un retour marchandises, déterminez qu’un article doit être envoyé pour inspection avant son retour en stock ou sa cession.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04b27a5560b6126fde3028f653a89059bb765844
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254963"
---
# <a name="pass-returned-items-on-to-inspection"></a><span data-ttu-id="580a0-103">Transmission d’articles retournés pour inspection</span><span class="sxs-lookup"><span data-stu-id="580a0-103">Pass returned items on to inspection</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="580a0-104">Lorsque vous enregistrez un retour marchandises, vous pouvez déterminer qu’un article doit être envoyé pour inspection avant son retour en stock ou sa cession.</span><span class="sxs-lookup"><span data-stu-id="580a0-104">When registering a returned item, you may determine that an item should be sent for inspection before it is returned to inventory or disposed of in some other way.</span></span>

1.  <span data-ttu-id="580a0-105">Cliquez sur **Gestion des stocks** \> **Journaux** \> **Arrivée d’articles** \> **Arrivée d’articles**.</span><span class="sxs-lookup"><span data-stu-id="580a0-105">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>
    
    <span data-ttu-id="580a0-106">\-ou-</span><span class="sxs-lookup"><span data-stu-id="580a0-106">\-or-</span></span>
    
    <span data-ttu-id="580a0-107">Cliquez sur **Gestion des stocks** \> **Journaux** \> **Arrivée d’articles** \> **Entrée en production**.</span><span class="sxs-lookup"><span data-stu-id="580a0-107">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Production input**.</span></span>

2.  <span data-ttu-id="580a0-108">Dans l’écran **Journal des emplacements**, enregistrez la réception d’un article normalement.</span><span class="sxs-lookup"><span data-stu-id="580a0-108">On the **Location journal** form, register the receipt of an item as usual.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="580a0-109">Pour plus d’informations sur l’enregistrement de la réception des retours marchandises, voir <A href="register-the-receipt-of-returned-items.md">Enregistrement de la réception d’articles retournés</A></span><span class="sxs-lookup"><span data-stu-id="580a0-109">For information about registering the receipt of returned items, see <A href="register-the-receipt-of-returned-items.md">Register the receipt of returned items</A></span></span></P>



3.  <span data-ttu-id="580a0-110">Sous l’onglet **Valeurs par défaut**, dans la zone **Mode de traitement**, cochez la case **Gestion des contrôles**.</span><span class="sxs-lookup"><span data-stu-id="580a0-110">On the **Default values** tab, in the **Mode of handling** area, select the **Quarantine management** box.</span></span>

<span data-ttu-id="580a0-111">Cela entraîne la création par le système d’un ordre de contrôle. La personne ou le département chargé(e) des inspections répond à cet ordre à l’aide de l’écran **Ordre de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="580a0-111">This will prompt the system to create a quarantine order, and the person or department that performs inspections will respond to this order using the **Quarantine order** form.</span></span>

## <a name="see-also"></a><span data-ttu-id="580a0-112">Voir également :</span><span class="sxs-lookup"><span data-stu-id="580a0-112">See also</span></span>

[<span data-ttu-id="580a0-113">Inspection des articles retournés</span><span class="sxs-lookup"><span data-stu-id="580a0-113">Take returned items through inspection</span></span>](take-returned-items-through-inspection.md)

[<span data-ttu-id="580a0-114">Spécification de la procédure de cession des articles retournés</span><span class="sxs-lookup"><span data-stu-id="580a0-114">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]