---
title: Module d'information sur le retrait
description: Cette rubrique couvre le module d'informations de retrait et décrit comment l’ajouter aux pages de paiement dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 61b97d72b6a397737c10476cd6c02764e60f10b1
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665346"
---
# <a name="pickup-information-module"></a><span data-ttu-id="160ec-103">Module d'information sur le retrait</span><span class="sxs-lookup"><span data-stu-id="160ec-103">Pickup information module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="160ec-104">Cette rubrique couvre le module d'informations de retrait et décrit comment l’ajouter aux pages de paiement dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="160ec-104">This topic covers the pickup information module and describes how to add it to checkout pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="160ec-105">Le module d'informations de retrait peut être utilisé dans un module de paiement pour afficher les informations de retrait de commande.</span><span class="sxs-lookup"><span data-stu-id="160ec-105">The pickup information module can be used in a checkout module to show order pickup information.</span></span> <span data-ttu-id="160ec-106">Les clients peuvent consulter les dates et les plages horaires de retrait disponibles, puis sélectionner une heure appropriée pour récupérer leur commande.</span><span class="sxs-lookup"><span data-stu-id="160ec-106">Customers can view available pickup dates and time slots, and then select a suitable time to pick up their order.</span></span> <span data-ttu-id="160ec-107">Par exemple, un client peut choisir de récupérer une commande à 15 h le 21 mars dans le magasin de San Francisco.</span><span class="sxs-lookup"><span data-stu-id="160ec-107">For example, a customer can choose to pick up an order at 3 PM on March 21 from the San Francisco store.</span></span>

<span data-ttu-id="160ec-108">Les plages horaires de retrait pour les magasins appropriés doivent être configurées au siège social Commerce.</span><span class="sxs-lookup"><span data-stu-id="160ec-108">Pickup time slots for the appropriate stores must be configured in Commerce headquarters.</span></span> <span data-ttu-id="160ec-109">Pour plus d'informations, consultez [Créer et mettre à jour des plages horaires pour le retrait client](dev-itpro/pickup-timeslots.md).</span><span class="sxs-lookup"><span data-stu-id="160ec-109">For more information, see [Create and update time slots for customer pickup](dev-itpro/pickup-timeslots.md).</span></span>

<span data-ttu-id="160ec-110">Si un module d'informations de retrait est créé sur une page de paiement, mais qu'aucune plage horaire n'est définie pour le magasin sélectionné pour la collecte, le module affichera des informations, mais l'utilisateur ne pourra sélectionner aucune plage horaire.</span><span class="sxs-lookup"><span data-stu-id="160ec-110">If a pickup information module is created on a checkout page, but no time slots are defined for the store that is selected for pickup, the module will show information, but the user won't be able to select any time slots.</span></span> <span data-ttu-id="160ec-111">Les plages horaires sont facultatives et ne sont pas nécessaires pour passer une commande.</span><span class="sxs-lookup"><span data-stu-id="160ec-111">Time slots are optional and aren't required to place an order.</span></span>

<span data-ttu-id="160ec-112">Si plusieurs articles sont sélectionnés pour le retrait dans plusieurs magasins, le module d'information de retrait permettra à l'utilisateur de sélectionner un créneau horaire pour chaque magasin, à condition que des créneaux horaires soient disponibles pour celui-ci.</span><span class="sxs-lookup"><span data-stu-id="160ec-112">If multiple items are selected for pickup across multiple stores, the pickup information module will let the user select a time slot for each store, provided that time slots are available for it.</span></span>

> [!NOTE]
> <span data-ttu-id="160ec-113">La prise en charge des créneaux horaires et du module d'informations de retrait à la caisse est disponible dans Dynamics 365 Commerce version 10.0.15 et ultérieure.</span><span class="sxs-lookup"><span data-stu-id="160ec-113">Support for time slots and the checkout pickup information module is available in Dynamics 365 Commerce version 10.0.15 and later.</span></span>

<span data-ttu-id="160ec-114">L'illustration suivante montre un exemple de sélection de créneau horaire via le module d'informations de retrait sur une page de paiement.</span><span class="sxs-lookup"><span data-stu-id="160ec-114">The following illustration shows an example of time slot selection through the pickup information module on a checkout page.</span></span>

![Exemple de module d'informations de retrait sur une page de paiement](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a><span data-ttu-id="160ec-116">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="160ec-116">Module properties</span></span>

- <span data-ttu-id="160ec-117">**En-tête** – Entrez un titre pour le module.</span><span class="sxs-lookup"><span data-stu-id="160ec-117">**Heading** – Enter a heading for the module.</span></span>

## <a name="show-time-slot-information-after-an-order-is-placed"></a><span data-ttu-id="160ec-118">Afficher les informations sur les plages horaires après qu'une commande est passée</span><span class="sxs-lookup"><span data-stu-id="160ec-118">Show time slot information after an order is placed</span></span>

<span data-ttu-id="160ec-119">Une fois la commande passée, les informations sur la plage horaire sélectionnée peuvent être consultées dans le [module de confirmation de commande](order-confirmation-module.md) et le [module de détails de la commande](account-management.md#order-details-page).</span><span class="sxs-lookup"><span data-stu-id="160ec-119">After an order is placed, information about the selected time slot can be viewed in the [order confirmation module](order-confirmation-module.md) and the [order details module](account-management.md#order-details-page).</span></span> <span data-ttu-id="160ec-120">Ces deux modules ont une propriété **Afficher les informations sur les plages horaires**.</span><span class="sxs-lookup"><span data-stu-id="160ec-120">Both these modules have a **Show timeslot information** property.</span></span> <span data-ttu-id="160ec-121">Avant de pouvoir afficher la plage horaire sélectionnée pendant le processus de commande, cette propriété doit être définie sur **Vrai**.</span><span class="sxs-lookup"><span data-stu-id="160ec-121">Before they can show the selected time slot during the order process, this property must be set to **True**.</span></span>

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a><span data-ttu-id="160ec-122">Ajouter un module d'informations de retrait de paiement sur une page</span><span class="sxs-lookup"><span data-stu-id="160ec-122">Add a checkout pickup information module to a page</span></span>

<span data-ttu-id="160ec-123">Pour obtenir des instructions sur la façon d’ajouter un module d'informations sur le retrait à une page de paiement et de définir les propriétés requises, voir [Module de paiement](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="160ec-123">For instructions about how to add a pickup information module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="160ec-124">L'illustration suivante montre un exemple de page de paiement pour l'e-commerce qui comprend des plages horaires pour les éléments de campagne de retrait.</span><span class="sxs-lookup"><span data-stu-id="160ec-124">The following illustration shows an example of an e-Commerce checkout page that includes time slots for pickup line items.</span></span>

![Exemple de page de paiement pour l'e-commerce qui comprend des plages horaires pour les articles de lignes de retrait](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a><span data-ttu-id="160ec-126">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="160ec-126">Additional resources</span></span>

[<span data-ttu-id="160ec-127">Créer et mettre à jour des plages horaires pour le ramassage des clients</span><span class="sxs-lookup"><span data-stu-id="160ec-127">Create and update time slots for customer pickup</span></span>](dev-itpro/pickup-timeslots.md)

[<span data-ttu-id="160ec-128">Module Validation</span><span class="sxs-lookup"><span data-stu-id="160ec-128">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="160ec-129">Module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="160ec-129">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="160ec-130">Module Détails de la commande</span><span class="sxs-lookup"><span data-stu-id="160ec-130">Order details module</span></span>](account-management.md)
