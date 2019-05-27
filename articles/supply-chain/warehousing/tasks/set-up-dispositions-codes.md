---
title: Paramétrer les codes disposition
description: Cette procédure se concentre sur le paramétrage du code disposition qui peut être utilisé sur un périphérique portable pour l'ordre de retour recevant le processus.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85402e05d55367da5fe89b242ad8eafc727b441e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558005"
---
# <a name="set-up-dispositions-codes"></a><span data-ttu-id="31b73-103">Paramétrer les codes disposition</span><span class="sxs-lookup"><span data-stu-id="31b73-103">Set up dispositions codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="31b73-104">Cette procédure se concentre sur le paramétrage du code disposition qui peut être utilisé sur un périphérique portable pour l'ordre de retour recevant le processus.</span><span class="sxs-lookup"><span data-stu-id="31b73-104">This procedure focuses on the setup of a disposition code that can be used on a mobile device for the return order receiving process.</span></span> <span data-ttu-id="31b73-105">Les codes disposition sont une collection de règles qu'il est possible d'utiliser lorsque des articles endommagés sont reçus.</span><span class="sxs-lookup"><span data-stu-id="31b73-105">Disposition codes are a collection of rules that can be used when items are received.</span></span> <span data-ttu-id="31b73-106">Par exemple, lorsqu'un utilisateur du travail utilise un périphérique portable pour recevoir les articles qui ont été endommagés, l'utilisateur doit numériser un code disposition pour les articles endommagés.</span><span class="sxs-lookup"><span data-stu-id="31b73-106">For example, when a work user uses a mobile device to receive items that were damaged, the user must scan a disposition code for damaged items.</span></span> <span data-ttu-id="31b73-107">Le statut du stock des marchandises reçues, le modèle de travail et la directive d'emplacement peuvent être déterminés à partir du code disposition numérisé.</span><span class="sxs-lookup"><span data-stu-id="31b73-107">The inventory status of the goods received, the work template, and the location directive can be determined from the scanned disposition code.</span></span> <span data-ttu-id="31b73-108">Pour la commande fournisseur recevant le processus et le rapport de l'ordre de fabrication comme étant terminés, l'utilisation de code disposition est facultative.</span><span class="sxs-lookup"><span data-stu-id="31b73-108">For the purchase order receiving process and the production order report as finished process, the use of a disposition code is optional.</span></span> <span data-ttu-id="31b73-109">Pour le processus de réception de retour de commande client, si les articles sont stockés à l'aide d'un périphérique mobile, l'utilisation de code disposition est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="31b73-109">For the sales order return receiving process, if the items are registered using a mobile device, the use of disposition code is mandatory.</span></span>  <span data-ttu-id="31b73-110">Ce guide a été créé à l'aide des données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="31b73-110">This guide was created using the demo data company USMF.</span></span> <span data-ttu-id="31b73-111">Cette procédure est destinée au gestionnaire d'entrepôts.</span><span class="sxs-lookup"><span data-stu-id="31b73-111">This procedure is intended for the warehouse manager.</span></span> 

1. <span data-ttu-id="31b73-112">Accédez à Gestion des entrepôts > Paramétrage > Appareil mobile > Codes disposition.</span><span class="sxs-lookup"><span data-stu-id="31b73-112">Go to Warehouse management > Setup > Mobile device > Disposition codes.</span></span>
2. <span data-ttu-id="31b73-113">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="31b73-113">Click New.</span></span>
    * <span data-ttu-id="31b73-114">Créez un code disposition à utiliser pour les retours client.</span><span class="sxs-lookup"><span data-stu-id="31b73-114">Create a new disposition code to use for customer returns.</span></span>  
3. <span data-ttu-id="31b73-115">Dans le champ Disposition, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b73-115">In the Disposition code field, type a value.</span></span>
4. <span data-ttu-id="31b73-116">Dans la zone Statut du stock, sélectionnez le statut du stock dans lequel il existe blocage du stock.</span><span class="sxs-lookup"><span data-stu-id="31b73-116">In the Inventory status field, select an inventory status where there is inventory blocking.</span></span>
    * <span data-ttu-id="31b73-117">Si vous utilisez le USMF, sélectionnez « Blocage ».</span><span class="sxs-lookup"><span data-stu-id="31b73-117">If you're using USMF, select 'Blocking'.</span></span> <span data-ttu-id="31b73-118">Vous pouvez ajouter un statut de stock au code disposition pour remplacer le statut par défaut basé sur les lignes de commande.</span><span class="sxs-lookup"><span data-stu-id="31b73-118">You can add an inventory status to the disposition code to override the default status that’s on the order lines.</span></span>  
5. <span data-ttu-id="31b73-119">Dans le champ Modèle de travail, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b73-119">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="31b73-120">Facultatif : sélectionnez un code de modèle de travail associé à un ordre de retour.</span><span class="sxs-lookup"><span data-stu-id="31b73-120">Optional: Select a work template code that is associated with a return order.</span></span> <span data-ttu-id="31b73-121">Si aucune valeur n'est fournie, le modèle de travail est résolu à l'aide des règles standard configurées dans votre système.</span><span class="sxs-lookup"><span data-stu-id="31b73-121">If no value is provided, the work template will be resolved using the standard rules configured in your system.</span></span> <span data-ttu-id="31b73-122">La sélection d'un modèle de travail limitera les processus dans lesquels ce code disposition pourra être utilisé.</span><span class="sxs-lookup"><span data-stu-id="31b73-122">Selecting a work template will limit the processes this disposition code can be used with.</span></span> <span data-ttu-id="31b73-123">Par exemple, si le code disposition a un modèle de travail avec un ordre d'entretien de type commande fournisseur, il ne peut pas être utilisé pour enregistrer les retours clients.</span><span class="sxs-lookup"><span data-stu-id="31b73-123">For example, if a disposition code has a work template with a work order of type purchase order, it can’t be used to register items that are returned by customers.</span></span>  
6. <span data-ttu-id="31b73-124">Dans le champ Disposition des retours, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b73-124">In the Return disposition code field, type a value.</span></span>
    * <span data-ttu-id="31b73-125">Le code disposition de retour détermine le reste du processus d'ordre de retour pour les articles enregistrés.</span><span class="sxs-lookup"><span data-stu-id="31b73-125">The return disposition code determines the remainder of the return order process for the items registered.</span></span> <span data-ttu-id="31b73-126">Dans cet exemple, le client doit recevoir un avoir.</span><span class="sxs-lookup"><span data-stu-id="31b73-126">In this example, the customer should receive a credit note.</span></span> <span data-ttu-id="31b73-127">Ajoutez un code disposition de retours qui contient un crédit d'action.</span><span class="sxs-lookup"><span data-stu-id="31b73-127">Add a returns disposition code that contains an action Credit.</span></span>  

