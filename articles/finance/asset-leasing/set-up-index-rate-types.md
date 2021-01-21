---
title: Configurer les taux d’indexation
description: Cette rubrique explique comment paramétrer des taux d’indexation. Les taux d’indexation sont requis si votre organisation associe les montants des paiements de location à un ensemble de taux d’indexation.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 16b83102aa76f46473138f89ea487e71668a188c
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4443368"
---
# <a name="set-up-index-rates"></a><span data-ttu-id="aeadb-104">Configurer les taux d’indexation</span><span class="sxs-lookup"><span data-stu-id="aeadb-104">Set up index rates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aeadb-105">Si les paiements de location dépendent d’un indice, les types de taux d’indexation peuvent être ajoutés et gérés dans le système.</span><span class="sxs-lookup"><span data-stu-id="aeadb-105">If lease payments depend on an index, the index rate types can be added and maintained in the system.</span></span> <span data-ttu-id="aeadb-106">Pour réévaluer les paiements de location de la page **Type de taux d’indexation**, le processus de réévaluation du taux d’indexation utilise le taux d’indexation le plus récent à partir de la date de réévaluation.</span><span class="sxs-lookup"><span data-stu-id="aeadb-106">To revalue the lease payments from the **Index rate type** page, the index rate revaluation process uses the most recent index rate from the date of revaluation.</span></span>

<span data-ttu-id="aeadb-107">Pour ajouter des types de taux d’indexation et des taux d’indexation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="aeadb-107">To add index rate types and index rates, follow these steps.</span></span>

1. <span data-ttu-id="aeadb-108">Accédez à **Location d’actifs \> Configuration \> Types de taux d’indexation**.</span><span class="sxs-lookup"><span data-stu-id="aeadb-108">Go to **Asset leasing \> Setup \> Index rate type**.</span></span>
2. <span data-ttu-id="aeadb-109">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="aeadb-109">Select **New**.</span></span>
3. <span data-ttu-id="aeadb-110">Dans les champs appropriés, saisissez le type de taux et le nom du taux d’indexation.</span><span class="sxs-lookup"><span data-stu-id="aeadb-110">In the appropriate fields, enter the rate type and the name of the index rate.</span></span>
4. <span data-ttu-id="aeadb-111">Pour ajouter une nouvelle valeur de taux d’indexation, sélectionnez le type de taux d’indexation, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="aeadb-111">To add a new index rate value, select the index rate type, and then select **Add**.</span></span>
5. <span data-ttu-id="aeadb-112">Sélectionnez la date de début effective du taux et sélectionnez la valeur du taux.</span><span class="sxs-lookup"><span data-stu-id="aeadb-112">Select the effective start date of the rate, and select the rate value.</span></span>

<span data-ttu-id="aeadb-113">Vous devez sélectionner soit **Différence de valeur de taux d’indexation** ou **Valeur du taux d’indexation** comme méthode du taux d’indexation.</span><span class="sxs-lookup"><span data-stu-id="aeadb-113">You must select either **Index rate value difference** or **Index rate value** as the index rate method.</span></span>

- <span data-ttu-id="aeadb-114">Sélectionnez la méthode **Différence de valeur de taux d’indexation** pour calculer un nouveau paiement de location, sur la base de la différence entre le taux d’indexation à la date de début et le taux d’indexation le plus récent.</span><span class="sxs-lookup"><span data-stu-id="aeadb-114">Select the **Index rate value difference** method to calculate a new lease payment, based on the difference between the index rate on the start date and the most recent index rate.</span></span> <span data-ttu-id="aeadb-115">Le taux d’indexation est défini dans le champ **Taux d’indexation (%)**.</span><span class="sxs-lookup"><span data-stu-id="aeadb-115">The index rate is defined in the **Index rate (%)** field.</span></span>
- <span data-ttu-id="aeadb-116">Sélectionnez la méthode **Valeur du taux d’indexation** pour calculer le paiement de location en utilisant le pourcentage spécifié dans le champ **Taux d’indexation (%)**.</span><span class="sxs-lookup"><span data-stu-id="aeadb-116">Select the **Index rate value** method to calculate the lease payment by using the percentage that is specified in the **Index rate (%)** field.</span></span>