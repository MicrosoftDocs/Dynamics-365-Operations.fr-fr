---
title: Résoudre des problèmes de configurateur de produit
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer avec le configurateur de produit.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e6cfeb6a2b4166dfa9a5a5cc1b7d3d913b865ce2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999604"
---
# <a name="troubleshoot-the-product-configurator"></a><span data-ttu-id="86c1c-103">Résoudre des problèmes de configurateur de produit</span><span class="sxs-lookup"><span data-stu-id="86c1c-103">Troubleshoot the product configurator</span></span>

<span data-ttu-id="86c1c-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer avec le configurateur de produit.</span><span class="sxs-lookup"><span data-stu-id="86c1c-104">This topic describes how to fix issues that you might encounter while you work with the product configurator.</span></span>

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a><span data-ttu-id="86c1c-105">Le texte de l'article est écrasé lorsque je configure un produit sur une ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="86c1c-105">Item text is overwritten when I configure a product on a sales order line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="86c1c-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="86c1c-106">Issue description</span></span>

<span data-ttu-id="86c1c-107">Ce problème se produit lorsque vous créez une ligne de commande client pour un article configurable, puis que vous modifiez le texte de l'article.</span><span class="sxs-lookup"><span data-stu-id="86c1c-107">This issue occurs when you create a sales order line for a configurable item and then modify the item text.</span></span> <span data-ttu-id="86c1c-108">Lorsque vous configurez l'article, puis sélectionnez **OK**, le texte est écrasé par le texte standard.</span><span class="sxs-lookup"><span data-stu-id="86c1c-108">When you configure the item and then select **OK**, the text is overwritten with the standard text.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="86c1c-109">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="86c1c-109">Issue resolution</span></span>

<span data-ttu-id="86c1c-110">Ce comportement est attendu.</span><span class="sxs-lookup"><span data-stu-id="86c1c-110">This behavior is expected.</span></span> <span data-ttu-id="86c1c-111">Le champ de texte comprend le nom de la variante, qui n'est renseigné qu'après avoir configuré la ligne.</span><span class="sxs-lookup"><span data-stu-id="86c1c-111">The text field includes the variant name, which is filled in only after you configure the line.</span></span> <span data-ttu-id="86c1c-112">Par conséquent, vous devez modifier le texte après avoir configuré la ligne, pas avant.</span><span class="sxs-lookup"><span data-stu-id="86c1c-112">Therefore, you must change the text after you've configured the line, not before.</span></span>

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a><span data-ttu-id="86c1c-113">Les attributs entiers ne sont pas arrondis correctement lors du calcul des modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="86c1c-113">Integer attributes are incorrectly rounded when product configuration models are calculated.</span></span>

### <a name="issue-description"></a><span data-ttu-id="86c1c-114">Description du problème</span><span class="sxs-lookup"><span data-stu-id="86c1c-114">Issue description</span></span>

<span data-ttu-id="86c1c-115">Ce problème peut se produire lorsque vous effectuez la série d'actions suivante :</span><span class="sxs-lookup"><span data-stu-id="86c1c-115">This issue can occur when you perform the following series of actions:</span></span>

1. <span data-ttu-id="86c1c-116">Configurez les attributs suivants sur un modèle de configuration de production :</span><span class="sxs-lookup"><span data-stu-id="86c1c-116">Set up the following attributes on a production configuration model:</span></span>

    - <span data-ttu-id="86c1c-117">Entrée (entier)</span><span class="sxs-lookup"><span data-stu-id="86c1c-117">Input (integer)</span></span>
    - <span data-ttu-id="86c1c-118">Pourcentage (décimal)</span><span class="sxs-lookup"><span data-stu-id="86c1c-118">Percent (decimal)</span></span>
    - <span data-ttu-id="86c1c-119">Résultat (entier)</span><span class="sxs-lookup"><span data-stu-id="86c1c-119">Result (integer)</span></span>

2. <span data-ttu-id="86c1c-120">Créez un calcul possédant les expressions suivantes :</span><span class="sxs-lookup"><span data-stu-id="86c1c-120">Create a calculation that has the following expression:</span></span>

    <span data-ttu-id="86c1c-121">*Résultat* = *Entrée* × *Pourcentage* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="86c1c-121">*Result* = *Input* × *Percent* ÷ 100</span></span>

<span data-ttu-id="86c1c-122">Dans ce cas, le résultat entier n'est pas toujours correctement arrondi.</span><span class="sxs-lookup"><span data-stu-id="86c1c-122">In this case, the integer result isn't always correctly rounded.</span></span> <span data-ttu-id="86c1c-123">Par exemple, l'entrée est 1 000 et le pourcentage est 2,40.</span><span class="sxs-lookup"><span data-stu-id="86c1c-123">For example, the input is 1,000, and the percentage is 2.40.</span></span> <span data-ttu-id="86c1c-124">Par conséquent, vous vous attendez à ce que le résultat entier soit 24, car 2,40 pourcent de 1 000 est 24 (ou 24,00 sous forme décimale).</span><span class="sxs-lookup"><span data-stu-id="86c1c-124">Therefore, you expect the integer result to be 24, because 2.40 percent of 1,000 is 24 (or 24.00 in decimal form).</span></span> <span data-ttu-id="86c1c-125">Au lieu de cela, le résultat est affiché comme 23.</span><span class="sxs-lookup"><span data-stu-id="86c1c-125">Instead, the result is shown as 23.</span></span> <span data-ttu-id="86c1c-126">Cependant, lorsque le pourcentage est de 2,39, le calcul est arrondi à 24 au lieu de 23.</span><span class="sxs-lookup"><span data-stu-id="86c1c-126">However, when the percentage is 2.39, the calculation is rounded to 24 instead of 23.</span></span> <span data-ttu-id="86c1c-127">Lorsque le pourcentage est de 2,50, le calcul est arrondi à 25 comme prévu.</span><span class="sxs-lookup"><span data-stu-id="86c1c-127">When the percentage is 2.50, the calculation is rounded to 25, as expected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="86c1c-128">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="86c1c-128">Issue resolution</span></span>

<span data-ttu-id="86c1c-129">Ce problème se produit en raison de la façon dont Microsoft Solver Foundation représente en interne des nombres en utilisant des fractions.</span><span class="sxs-lookup"><span data-stu-id="86c1c-129">This issue occurs because of the way that Microsoft Solver Foundation internally represents numbers by using fractions.</span></span> <span data-ttu-id="86c1c-130">Pour l'exemple précédent, le résultat du calcul où le pourcentage est de 2,40 est représenté par 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375.</span><span class="sxs-lookup"><span data-stu-id="86c1c-130">For the preceding example, the result of the calculation where the percentage is 2.40 is represented as 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375.</span></span> <span data-ttu-id="86c1c-131">Lorsque .NET convertit cette valeur sous forme d'entier, il renvoie 23.</span><span class="sxs-lookup"><span data-stu-id="86c1c-131">When .NET casts this value as an integer, it will return 23.</span></span>

<span data-ttu-id="86c1c-132">Ce comportement ne sera pas modifié, car d'autres scénarios en dépendent.</span><span class="sxs-lookup"><span data-stu-id="86c1c-132">This behavior won't be changed, because other scenarios depend on it.</span></span> <span data-ttu-id="86c1c-133">Pour l'exemple précédent, vous pouvez résoudre le problème en introduisant un attribut décimal supplémentaire et un calcul.</span><span class="sxs-lookup"><span data-stu-id="86c1c-133">For the preceding example, you can fix the issue by introducing an additional decimal attribute and a calculation.</span></span>

<span data-ttu-id="86c1c-134">Par exemple, vous pouvez configurer les attributs suivants sur un modèle de configuration de production :</span><span class="sxs-lookup"><span data-stu-id="86c1c-134">For example, you can set up the following attributes on a production configuration model:</span></span>

- <span data-ttu-id="86c1c-135">Entrée (entier)</span><span class="sxs-lookup"><span data-stu-id="86c1c-135">Input (integer)</span></span>
- <span data-ttu-id="86c1c-136">Pourcentage (décimal)</span><span class="sxs-lookup"><span data-stu-id="86c1c-136">Percent (decimal)</span></span>
- <span data-ttu-id="86c1c-137">ResultDecimal (décimal)</span><span class="sxs-lookup"><span data-stu-id="86c1c-137">ResultDecimal (decimal)</span></span>
- <span data-ttu-id="86c1c-138">ResultInteger (entier)</span><span class="sxs-lookup"><span data-stu-id="86c1c-138">ResultInteger (integer)</span></span>

<span data-ttu-id="86c1c-139">Vous pouvez ensuite ajouter les calculs suivants :</span><span class="sxs-lookup"><span data-stu-id="86c1c-139">You can then add the following calculations:</span></span>

- <span data-ttu-id="86c1c-140">*ResultDecimal* = *Entrée* × *Pourcentage* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="86c1c-140">*ResultDecimal* = *Input* × *Percent* ÷ 100</span></span>
- <span data-ttu-id="86c1c-141">*ResultInteger* = *ResultDecimal*</span><span class="sxs-lookup"><span data-stu-id="86c1c-141">*ResultInteger* = *ResultDecimal*</span></span>
