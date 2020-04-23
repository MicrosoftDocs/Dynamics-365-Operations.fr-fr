---
title: Annuler le travail d'entrepôt pour le traitement des exceptions
description: Cette rubrique décrit la fonctionnalité Annuler le travail qui permet aux superviseurs d'entrepôt de gérer le travail bloqué.
author: omulvad
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cb725885fb48293a08915f13a4fb14085e930444
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205803"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a><span data-ttu-id="33949-103">Annuler le travail d'entrepôt pour le traitement des exceptions</span><span class="sxs-lookup"><span data-stu-id="33949-103">Cancel warehouse work for exception handling</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33949-104">La fonctionnalité Annuler le travail dans Microsoft Dynamics 365 Supply Chain Management permet à l'utilisateur administrateur d'annuler un travail d'entrepôt spécifique en cours, mais qui est bloqué par le système ou ne peut pas être exécuté en raison de les circonstances exceptionnelles.</span><span class="sxs-lookup"><span data-stu-id="33949-104">The Cancel work functionality in Microsoft Dynamics 365 Supply Chain Management lets the admin user cancel specific warehouse work that is currently in progress, but that is blocked by the system or can't be completed because of exceptional circumstances.</span></span> <span data-ttu-id="33949-105">Cette fonctionnalité est une offre attractive et sécurisée autre que les scripts correctifs SQL qui résolvent des données incohérentes.</span><span class="sxs-lookup"><span data-stu-id="33949-105">This functionality is an attractive and secure alternative to SQL corrective scripts that fix inconsistent data.</span></span> <span data-ttu-id="33949-106">Toutefois, alors que ces scripts sont généralement demandés par des professionnels de l'informatique, la fonctionnalité Annuler le travail peut être utilisée par les utilisateurs de la société disposant de droits d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="33949-106">However, whereas these scripts are typically requested from IT professionals, the Cancel work functionality can be used by users in the company who have admin rights.</span></span>

<span data-ttu-id="33949-107">Vous pouvez accéder à la fonctionnalité Annuler le travail dans **Gestion des entrepôts** \> **Tâches périodiques** \> **Nettoyer \> Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="33949-107">You can access the Cancel work functionality at **Warehouse management** \> **Periodic tasks** \> **Clean up \> Cancel work**.</span></span> <span data-ttu-id="33949-108">Dans la boîte de dialogue **Annuler le travail**, spécifiez l'ID travail du travail à annuler, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="33949-108">In the **Cancel work** dialog box, specify the work ID of the work to cancel, and then select **OK**.</span></span>

## <a name="warehouse-work-that-can-be-canceled"></a><span data-ttu-id="33949-109">Travail d'entrepôt pouvant être annulé</span><span class="sxs-lookup"><span data-stu-id="33949-109">Warehouse work that can be canceled</span></span>

<span data-ttu-id="33949-110">Au cours des opérations de prélèvement d'entrepôt, un collaborateur peut rencontrer des situations où ils ont enregistré des quantités comme prélevées à un emplacement de stockage et rangé dans leur emplacement utilisateur, mais ils ne peuvent pas enregistrer l'opération de rangement.</span><span class="sxs-lookup"><span data-stu-id="33949-110">During warehouse picking operations, a worker might encounter situations where they have registered quantities as picked from a storage location to their user location, but then they can't register the put operation.</span></span> <span data-ttu-id="33949-111">Les données d'entrepôt incohérentes sont souvent, mais pas toujours, la raison pour laquelle le travail est bloqué.</span><span class="sxs-lookup"><span data-stu-id="33949-111">Inconsistent warehouse data is often, but not always, the reason why work is blocked.</span></span>

<span data-ttu-id="33949-112">Contrairement à une fonctionnalité Annuler standard à laquelle on accède via le bouton **Annuler** dans l'en-tête du travail, la fonctionnalité Annuler le travail ne nécessite pas que la dernière ligne de travail terminé soit une ligne de travail du type **rangement**.</span><span class="sxs-lookup"><span data-stu-id="33949-112">Unlike the regular Cancel functionality that can be accessed by using the **Cancel** button on the work header, the Cancel work functionality doesn't require that the last completed work line be a work line of the **put** type.</span></span> <span data-ttu-id="33949-113">En d'autres termes, pour la fonctionnalité Annuler le travail, la logique d'annulation peut être exécutée même si la quantité d'article sur une ligne de travail est à un emplacement utilisateur.</span><span class="sxs-lookup"><span data-stu-id="33949-113">In other words, for the Cancel work functionality, cancellation logic can be run even if the item quantity on a work line is in a user location.</span></span>

> [!NOTE]
> <span data-ttu-id="33949-114">Pour le travail qui doit être annulé pour des raisons opérationnelles, les utilisateurs d'entrepôts doivent continuer à utiliser la fonctionnalité Annuler standard sur la page de travail.</span><span class="sxs-lookup"><span data-stu-id="33949-114">For work that must be canceled for operational reasons, warehouse users must continue to use the regular Cancel functionality on the work page.</span></span>

<span data-ttu-id="33949-115">Seul le travail de type **Ventes**, **Sortie de transfert**, **Prélèvement de matières premières** ou **Réapprovisionnement** peut être annulé à l'aide de la fonctionnalité Annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="33949-115">Only work of the **Sales**, **Transfer issue**, **Raw material picking**, or **Replenishment** type can be canceled by using the Cancel work functionality.</span></span> <span data-ttu-id="33949-116">La logique d'annulation n'est pas exécutée sur le travail de prélèvement de matières premières surgelées ou le travail qui peut être annulé en utilisant la fonctionnalité Annuler standard (voir la note précédente).</span><span class="sxs-lookup"><span data-stu-id="33949-116">Cancellation logic won't be run for frozen raw material picking work or work that can be canceled by using the regular Cancel functionality (see the preceding note).</span></span>

<span data-ttu-id="33949-117">Pour débloquer le travail, le système annule toutes les lignes de travail restantes et corrige les données d'entrepôt associées à l'ID travail que l'utilisateur a spécifié.</span><span class="sxs-lookup"><span data-stu-id="33949-117">To unblock the work, the system cancels any remaining work lines and fixes the warehouse data that is associated with the work ID that the user specified.</span></span> <span data-ttu-id="33949-118">Toutes les opérations de gestion en entrepôt standard qui impliquent la quantité d'article affectée peuvent alors continuer.</span><span class="sxs-lookup"><span data-stu-id="33949-118">Any regular warehouse-handling operations that involve the affected item quantity can then resume.</span></span>

<span data-ttu-id="33949-119">Pour ranger l'article affecté à un emplacement spécifique une fois le travail annulé, l'utilisateur doit utiliser une opération de mouvement de stock ou d'ajustement de quantité sur un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="33949-119">To put the affected item in a specific location after the work is canceled, the user must use an inventory movement or quantity adjustment operation on a mobile device.</span></span>
