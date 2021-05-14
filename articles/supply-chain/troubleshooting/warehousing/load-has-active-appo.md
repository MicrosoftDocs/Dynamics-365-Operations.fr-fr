---
title: Vous ne pouvez pas confirmer une expédition en raison d'un problème avec le calendrier
description: Vous ne pouvez pas confirmer une expédition en raison d'un problème avec le calendrier
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f1fccd10d8867252f32b37c77f9a3bad54157bdd
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938471"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a><span data-ttu-id="9495b-103">Vous ne pouvez pas confirmer une expédition en raison d'un problème avec le calendrier</span><span class="sxs-lookup"><span data-stu-id="9495b-103">You can't confirm a shipment because of an issue with the calendar</span></span>

<span data-ttu-id="9495b-104">Code d’erreur : TRX2716</span><span class="sxs-lookup"><span data-stu-id="9495b-104">Error code: TRX2716</span></span>

## <a name="symptoms"></a><span data-ttu-id="9495b-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="9495b-105">Symptoms</span></span>

<span data-ttu-id="9495b-106">Lorsque vous essayez de confirmer une expédition, le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="9495b-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="9495b-107">Le type de calendrier %1 nécessite le pointage à l'arrivée et au départ du rendez-vous %2.</span><span class="sxs-lookup"><span data-stu-id="9495b-107">The calendar type %1 requires the appointment %2 to be checked in and out.</span></span>

<span data-ttu-id="9495b-108">Par conséquent, vous ne pouvez pas confirmer l'expédition pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="9495b-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="9495b-109">Cause</span><span class="sxs-lookup"><span data-stu-id="9495b-109">Cause</span></span>

<span data-ttu-id="9495b-110">Il existe des rendez-vous actifs pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="9495b-110">Active appointments for the load exist.</span></span> <span data-ttu-id="9495b-111">Par exemple, il existe une règle qui exige l'enregistrement de l'arrivée du conducteur.</span><span class="sxs-lookup"><span data-stu-id="9495b-111">For example, there is a rule that requires driver check-in.</span></span> <span data-ttu-id="9495b-112">Par conséquent, le chargement est actuellement dans un état où la confirmation d'expédition échoue.</span><span class="sxs-lookup"><span data-stu-id="9495b-112">Therefore, the load is currently in a state where shipment confirmation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="9495b-113">Résolution</span><span class="sxs-lookup"><span data-stu-id="9495b-113">Resolution</span></span>

<span data-ttu-id="9495b-114">Vous devez rechercher et résoudre tous les problèmes liés aux rendez-vous actifs liés au chargement.</span><span class="sxs-lookup"><span data-stu-id="9495b-114">You must investigate and fix any issues with the active appointments that are linked to the load.</span></span>

1. <span data-ttu-id="9495b-115">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="9495b-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="9495b-116">Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.</span><span class="sxs-lookup"><span data-stu-id="9495b-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="9495b-117">Dans le volet Actions, sous l’onglet **Transport**, dans le groupe **Rendez-vous**, sélectionnez **Planification de rendez-vous**.</span><span class="sxs-lookup"><span data-stu-id="9495b-117">On the Action Pane, on the **Transportation** tab, in the **Appointments** group, select **Appointment scheduling**.</span></span>
1. <span data-ttu-id="9495b-118">Utilisez l’une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="9495b-118">Follow one of these steps:</span></span>

    - <span data-ttu-id="9495b-119">Assurez-vous que l'arrivée/le départ du chauffeur a bien été effectué pour le rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9495b-119">Make sure that driver check-in/check-out is completed for the appointment.</span></span>
    - <span data-ttu-id="9495b-120">Terminez ou annulez le rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9495b-120">Complete or cancel the appointment.</span></span>
    - <span data-ttu-id="9495b-121">Désactivez l'option **Arrivée du chauffeur obligatoire** pour la règle de rendez-vous associée.</span><span class="sxs-lookup"><span data-stu-id="9495b-121">Disable the **Driver check-in required** option for the related appointment rule.</span></span>
