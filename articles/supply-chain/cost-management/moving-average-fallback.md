---
title: Moyenne mobile, séquence de coût de secours
description: Cette rubrique fournit des informations sur les séquences de coût de secours pour déplacer les calculs de moyenne dans Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
manager: tfehr
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 1f5b1307f039bb9e921d50aed411b3dc603ada65
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263612"
---
# <a name="moving-average-fallback-cost-sequence"></a><span data-ttu-id="831ed-103">Moyenne mobile, séquence de coût de secours</span><span class="sxs-lookup"><span data-stu-id="831ed-103">Moving average fallback cost sequence</span></span>

<span data-ttu-id="831ed-104">Vous pouvez calculer le coût de votre stock en utilisant une _moyenne mobile_.</span><span class="sxs-lookup"><span data-stu-id="831ed-104">One way that you can calculate the cost of your inventory is by using a _moving average_.</span></span> <span data-ttu-id="831ed-105">Jusqu’à trois valeurs de coût peuvent être associées à chaque article en stock :</span><span class="sxs-lookup"><span data-stu-id="831ed-105">Up to three cost values can be associated with each inventory item:</span></span>

- <span data-ttu-id="831ed-106">**Dernière sortie** - Le dernier coût d’émission attribué avant que le stock ne devienne négatif</span><span class="sxs-lookup"><span data-stu-id="831ed-106">**Last issue** – The last issue cost that was assigned before inventory went negative</span></span>
- <span data-ttu-id="831ed-107">**Coût actif** - Le dernier coût qui a été activé dans une version d’évaluation des coûts</span><span class="sxs-lookup"><span data-stu-id="831ed-107">**Active cost** – The latest cost that was activated in a costing version</span></span>
- <span data-ttu-id="831ed-108">**Prix de l’article** - Le coût spécifié pour le produit lancé</span><span class="sxs-lookup"><span data-stu-id="831ed-108">**Item price** – The cost that is specified for the released product</span></span>

<span data-ttu-id="831ed-109">Pour déterminer laquelle de ces valeurs de coût doit être utilisée dans les calculs de moyenne mobile, le système utilise une _séquence de coût de secours_ pour établir l’ordre de préférence des valeurs.</span><span class="sxs-lookup"><span data-stu-id="831ed-109">To determine which of these cost values should be used in moving average calculations, the system uses a _fallback cost sequence_ to establish the order of preference for the values.</span></span> <span data-ttu-id="831ed-110">Si la valeur de coût préférée n’est pas disponible, le système utilise la valeur préférée suivante, etc.</span><span class="sxs-lookup"><span data-stu-id="831ed-110">If the preferred cost value isn't available, the system uses the next-preferred value, and so on.</span></span>

<span data-ttu-id="831ed-111">Dans les versions précédentes de Microsoft Dynamics 365 Supply Chain Management, le système a utilisé une séquence de coûts de secours fixe (_Dernière sortie - Coût actif - Prix de l’article_).</span><span class="sxs-lookup"><span data-stu-id="831ed-111">In previous versions of Microsoft Dynamics 365 Supply Chain Management, the system used a fixed fallback cost sequence (_Last issue – Active cost – Item price_).</span></span> <span data-ttu-id="831ed-112">Dans la version 10.0.11, cette séquence est toujours la séquence par défaut.</span><span class="sxs-lookup"><span data-stu-id="831ed-112">In version 10.0.11, this sequence is still the default sequence.</span></span> <span data-ttu-id="831ed-113">Cependant, vous pouvez également activer une fonctionnalité qui vous permet de sélectionner parmi trois séquences de coût de secours disponibles.</span><span class="sxs-lookup"><span data-stu-id="831ed-113">However, you can also turn on a feature that lets you select among three available fallback cost sequences.</span></span> <span data-ttu-id="831ed-114">Cette fonctionnalité peut être particulièrement utile pour les organisations qui utilisent régulièrement des valeurs de stock négatives.</span><span class="sxs-lookup"><span data-stu-id="831ed-114">This feature can be especially useful for organizations that regularly use negative inventory values.</span></span>

<span data-ttu-id="831ed-115">Pour rendre le sélecteur de la séquence de coût de secours disponible, vous (ou un administrateur) devez utiliser [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer la fonction nommée _Moyenne mobile, séquence de coût de secours_.</span><span class="sxs-lookup"><span data-stu-id="831ed-115">To make the selector for the fallback cost sequence available, you (or an admin) must use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named _Moving average fallback cost sequence_.</span></span>

<span data-ttu-id="831ed-116">Pour sélectionner la séquence de coût de secours pour les calculs de moyenne mobile, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="831ed-116">To select the fallback cost sequence for moving average calculations, follow these steps.</span></span>

1. <span data-ttu-id="831ed-117">Ouvrez la page **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="831ed-117">Open the **Parameters** page.</span></span>
2. <span data-ttu-id="831ed-118">Sur l’onglet **Comptabilité de stock**, dans la section **Moyenne mobile**, définissez le champ **Séquence de coût de secours** sur l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="831ed-118">On the **Inventory accounting** tab, in the **Moving average** section, set the **Fallback cost sequence** field to one of the following values:</span></span>

    - <span data-ttu-id="831ed-119">**Dernière sortie - Coût actif - Prix de l’article** - Cette séquence est la séquence par défaut.</span><span class="sxs-lookup"><span data-stu-id="831ed-119">**Last issue – Active cost – Item price** – This sequence is the default sequence.</span></span> <span data-ttu-id="831ed-120">C’est la même séquence qui est utilisée si la fonctionnalité _Moyenne mobile, séquence de coût de secours_ n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="831ed-120">It's the same sequence that is used if the _Moving average fallback cost sequence_ feature isn't turned on.</span></span>
    - <span data-ttu-id="831ed-121">**Coût actif - Dernière sortie**</span><span class="sxs-lookup"><span data-stu-id="831ed-121">**Active cost – Last issue**</span></span>
    - <span data-ttu-id="831ed-122">**Coût actif - Prix de l’article** - Les organisations peuvent rencontrer des problèmes de performances si elles utilisent des processus métier où le stock devient régulièrement négatif et si, en même temps, le volume de transactions est élevé.</span><span class="sxs-lookup"><span data-stu-id="831ed-122">**Active cost – Item price** – Organizations might experience performance issues if they use business processes where inventory regularly goes negative and, at the same time, the transaction volume is high.</span></span> <span data-ttu-id="831ed-123">Ce paramètre peut aider à atténuer ces problèmes de performances.</span><span class="sxs-lookup"><span data-stu-id="831ed-123">This setting can help mitigate those performance issues.</span></span>

<span data-ttu-id="831ed-124">![Paramètres de comptabilité de stock](media/inventory-accounting-parameters.png "Paramètres de comptabilité de stock")</span><span class="sxs-lookup"><span data-stu-id="831ed-124">![Inventory accounting parameters](media/inventory-accounting-parameters.png "Inventory accounting parameters")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]