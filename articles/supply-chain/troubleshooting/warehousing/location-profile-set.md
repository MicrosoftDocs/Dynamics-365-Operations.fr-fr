---
title: Le profil d'emplacement n'autorise pas le stock négatif, mais le stock disponible négatif est autorisé
description: L'option Autoriser le stock négatif pour le profil d'emplacement est définie sur Non, mais le système autorise toujours le stock en stock négatif.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 356d2dd7853bf93250e14eb9bd28a8a145794584
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026505"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a><span data-ttu-id="b5621-103">Le profil d'emplacement n'autorise pas le stock négatif, mais le stock disponible négatif est autorisé</span><span class="sxs-lookup"><span data-stu-id="b5621-103">Location profile disallows negative inventory, but negative on-hand inventory is permitted</span></span>

<span data-ttu-id="b5621-104">Numéro de la base de connaissances : 4613622</span><span class="sxs-lookup"><span data-stu-id="b5621-104">KB number: 4613622</span></span>

## <a name="symptoms"></a><span data-ttu-id="b5621-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="b5621-105">Symptoms</span></span>

<span data-ttu-id="b5621-106">L'option **Autoriser le stock négatif** pour le profil d'emplacement est définie sur *Non*, mais le système autorise toujours le stock en stock négatif.</span><span class="sxs-lookup"><span data-stu-id="b5621-106">The **Allow negative inventory** option for the location profile is set to *No*, but the system still allows negative on-hand inventory.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="b5621-107">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="b5621-107">Example scenario</span></span>

<span data-ttu-id="b5621-108">Pour les transactions réglementées par le gouvernement, le système doit être en mesure d'enregistrer des stocks négatifs pour comptabiliser les pertes.</span><span class="sxs-lookup"><span data-stu-id="b5621-108">For government-regulated transactions, the system must be able to record negative inventory to book losses.</span></span> <span data-ttu-id="b5621-109">Vous voulez qu'un article puisse afficher un stock négatif, mais uniquement dans des emplacements désignés, tels que les réservoirs.</span><span class="sxs-lookup"><span data-stu-id="b5621-109">You want an item to be able to show negative inventory, but only in designated locations, such as tanks.</span></span> <span data-ttu-id="b5621-110">Cependant, si le groupe de modèles d'article autorise le stock négatif, vous constatez que le fait que l'emplacement soit défini pour autoriser le stock négatif n'a pas d'importance.</span><span class="sxs-lookup"><span data-stu-id="b5621-110">However, if the item model group allows negative inventory, you find that it doesn't matter whether the location is set to allow negative inventory.</span></span> <span data-ttu-id="b5621-111">Si l'article est configuré de manière à ce que le stock négatif ne soit pas autorisé, la configuration du profil d'emplacement n'a pas d'importance.</span><span class="sxs-lookup"><span data-stu-id="b5621-111">If the item is set up so that negative inventory isn't allowed, it doesn't matter how the location profile is set up.</span></span>

## <a name="resolution"></a><span data-ttu-id="b5621-112">Résolution</span><span class="sxs-lookup"><span data-stu-id="b5621-112">Resolution</span></span>

<span data-ttu-id="b5621-113">Le paramètre **Autoriser un stock négatif** du profil d'emplacement s'applique uniquement aux processus d'entrepôt, tels que le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="b5621-113">The **Allow negative inventory** setting from the location profile applies only to warehouse processes, such as picking.</span></span> <span data-ttu-id="b5621-114">Cependant, les groupes de modèles d'article définis pour autoriser un stock négatif affectent tous les processus des modules de gestion des stocks et de gestion des entrepôts, et le profil d'emplacement ne remplace pas le paramètre.</span><span class="sxs-lookup"><span data-stu-id="b5621-114">However, item model groups that are set to allow negative inventory affect all processes from the Inventory management and Warehouse management modules, and the location profile won't override the setting.</span></span>

<span data-ttu-id="b5621-115">Vous pouvez contrôler si un entrepôt est autorisé à porter un stock négatif.</span><span class="sxs-lookup"><span data-stu-id="b5621-115">You can control whether a warehouse is allowed to carry negative inventory.</span></span> <span data-ttu-id="b5621-116">Définissez vos groupes de modèles d'articles pour interdire les stocks physiques négatifs et ne définissez que l'entrepôt approprié pour autoriser les stocks négatifs.</span><span class="sxs-lookup"><span data-stu-id="b5621-116">Set your item model groups to disallow negative physical inventory, and set only the relevant warehouse to allow negative inventory.</span></span>
