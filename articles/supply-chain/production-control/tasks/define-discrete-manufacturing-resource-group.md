---
title: Définir un groupe de ressources pour la fabrication discrète
description: Un groupe de ressources est un ensemble de ressources opérationnelles correspondant généralement à l’organisation physique des cellules de travail, définie par des lignes jaunes dans l’atelier de production.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 24097cbb6f0ffae7b1b52bd3c70b7e054b3ce86c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257313"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="a5a5b-103">Définir un groupe de ressources pour la fabrication discrète</span><span class="sxs-lookup"><span data-stu-id="a5a5b-103">Define discrete manufacturing resource group</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a5a5b-104">Un groupe de ressources est un ensemble de ressources opérationnelles correspondant généralement à l’organisation physique des cellules de travail, définie par des lignes jaunes dans l’atelier de production.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="a5a5b-105">Cette procédure vous indique comment définir un groupe de ressources pour une utilisation dans la production discrète.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="a5a5b-106">Vous pouvez parcourir cette procédure dans la société USMF fictive ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="a5a5b-107">Allez dans Groupes de ressources.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="a5a5b-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-108">Click New.</span></span>
3. <span data-ttu-id="a5a5b-109">Tapez une valeur dans le champ Groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="a5a5b-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a5a5b-111">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="a5a5b-112">Saisissez ou sélectionnez une valeur dans le champ Unité de production.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="a5a5b-113">Définissez les paramètres opérationnels par défaut</span><span class="sxs-lookup"><span data-stu-id="a5a5b-113">Define default operational parameters</span></span>
1. <span data-ttu-id="a5a5b-114">Développez la section Opération.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="a5a5b-115">Entrez un nombre dans le champ Pourcentage de rebut.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="a5a5b-116">Saisissez ou sélectionnez une valeur dans le champ Catégorie de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="a5a5b-117">Saisissez ou sélectionnez une valeur dans le champ Catégorie de temps d’exécution.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="a5a5b-118">Entrez un nombre dans le champ Pourcentage d’ordonnancement.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="a5a5b-119">Définir les heures de fonctionnement</span><span class="sxs-lookup"><span data-stu-id="a5a5b-119">Define operating hours</span></span>
1. <span data-ttu-id="a5a5b-120">Développez la section Calendriers.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="a5a5b-121">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-121">Click Add.</span></span>
3. <span data-ttu-id="a5a5b-122">Saisissez ou sélectionnez une valeur dans le champ Calendrier.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="a5a5b-123">Ajouter des ressources opérationnelles</span><span class="sxs-lookup"><span data-stu-id="a5a5b-123">Add operations resources</span></span>
1. <span data-ttu-id="a5a5b-124">Développez la section Ressources.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="a5a5b-125">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-125">Click Add.</span></span>
3. <span data-ttu-id="a5a5b-126">Saisissez ou sélectionnez une valeur dans le champ Ressources.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="a5a5b-127">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-127">Click Add.</span></span>
5. <span data-ttu-id="a5a5b-128">Saisissez ou sélectionnez une valeur dans le champ Ressources.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="a5a5b-129">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="a5a5b-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a5a5b-130">In the list, click the link in the selected row.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]