---
title: Réception de contenant mixte
description: Cette rubrique décrit comment utiliser la réception de contenant mixte pour enregistrer et créer le travail pour plusieurs articles avec un appareil mobile.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15c058887da33b522c5d9a1a8d2c45a5d1566a5d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215767"
---
# <a name="mixed-license-plate-receiving"></a><span data-ttu-id="e4886-103">Réception de contenant mixte</span><span class="sxs-lookup"><span data-stu-id="e4886-103">Mixed license plate receiving</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4886-104">La réception de contenant mixte vous permet de générer un contenant composé de plusieurs articles avant d'enregistrer et de créer le travail de rangement.</span><span class="sxs-lookup"><span data-stu-id="e4886-104">Mixed license plate receiving allows you to build a license plate consisting of multiple items before you register and create put-away work.</span></span> 

<span data-ttu-id="e4886-105">Un contenant composé de plusieurs articles ne doit pas être réparti au niveau du quai de réception pour que vous puissiez enregistrer chaque article.</span><span class="sxs-lookup"><span data-stu-id="e4886-105">A license plate that consists of multiple items does not have to be split at the receiving dock for you to register each item.</span></span> 

<span data-ttu-id="e4886-106">Lorsque vous utilisez un flux relatif aux articles pour identifier les lignes du document source, vous pouvez lire les codes-barres sur le contrôle de l'article.</span><span class="sxs-lookup"><span data-stu-id="e4886-106">When using an item-related flow to identify the source document lines, you can scan bar codes on the item control.</span></span> <span data-ttu-id="e4886-107">Si le code-barres présente une quantité et une unité de mesure (UOM) configurés dessus, l'article et la quantité seront automatiquement ajoutés au contenant mixte, et vous serez renvoyé à l'écran permettant de lire un autre article.</span><span class="sxs-lookup"><span data-stu-id="e4886-107">If the bar code has a quantity and a unit of measure (UOM) configured on it, the item and quantity will automatically be added to the mixed license plate, and you will be returned to the screen to scan another item.</span></span> <span data-ttu-id="e4886-108">Cela vous permet d'analyser rapidement tous les articles sans devoir apporter une confirmation à chaque étape.</span><span class="sxs-lookup"><span data-stu-id="e4886-108">This allows you to quickly scan all the items without having to make a confirmation at each step.</span></span> 

<span data-ttu-id="e4886-109">Dans le flux de la réception du contenant mixte, vous pouvez afficher la liste des articles qui sont déjà lus dans le contenant et de là, vous pourrez modifier ou corriger la quantité d'un article.</span><span class="sxs-lookup"><span data-stu-id="e4886-109">In the flow for mixed license plate receiving, you can display the list of items that are already scanned to the license plate and from here you can modify or correct the quantity of an item.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="e4886-110">Dans ce cas</span><span class="sxs-lookup"><span data-stu-id="e4886-110">Where it applies</span></span>

<span data-ttu-id="e4886-111">La réception du contenant mixte correspond à un appareil mobile recevant un flux pour enregistrer et créer du travail pour plusieurs lignes/articles en même temps.</span><span class="sxs-lookup"><span data-stu-id="e4886-111">Mixed license plate receiving is a mobile device receiving flow to register and create work for multiple lines/items at the same time.</span></span> <span data-ttu-id="e4886-112">Cela est utile si vous recevez des contenants entrants avec plusieurs articles.</span><span class="sxs-lookup"><span data-stu-id="e4886-112">This is useful if you receive inbound license plates with multiple items.</span></span> 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a><span data-ttu-id="e4886-113">Comment configurer une réception de contenant mixte</span><span class="sxs-lookup"><span data-stu-id="e4886-113">How to set up mixed license plate receiving</span></span>
<span data-ttu-id="e4886-114">Une réception de contenant mixte est paramétré en tant qu'option de menu d'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="e4886-114">Mixed license plate receiving is set up as a mobile device menu item.</span></span>

<span data-ttu-id="e4886-115">Vous devez créer une option de menu avec le mode de travail qui n'utilise pas le travail existant, mais l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4886-115">You need to create a new menu item with mode work that does not use existing work and use one of the following methods:</span></span>

- <span data-ttu-id="e4886-116">Réception de contenant mixte</span><span class="sxs-lookup"><span data-stu-id="e4886-116">Mixed license plate receiving</span></span>
- <span data-ttu-id="e4886-117">Réception et rangement de contenant mixte</span><span class="sxs-lookup"><span data-stu-id="e4886-117">Mixed license plate receiving and put away</span></span>

<span data-ttu-id="e4886-118">Les options permettant d'identifier les lignes du document source sont Article de commande fournisseur, Ligne de commande fournisseur, Ordre de retour, Article d'ordre de transfert et Ligne d'ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="e4886-118">The options to identify the source document lines are purchase order item, purchase order line, return order, transfer order item, and transfer order line.</span></span> <span data-ttu-id="e4886-119">Ces options peuvent modifier l'ordre de réception dans un contenant unique.</span><span class="sxs-lookup"><span data-stu-id="e4886-119">These options can change the receiving order on a single license plate.</span></span> <span data-ttu-id="e4886-120">La dernière option concerne le chargement d'articles.</span><span class="sxs-lookup"><span data-stu-id="e4886-120">The last option is by load item.</span></span> <span data-ttu-id="e4886-121">Vous pouvez ajouter plusieurs articles à un contenant, mais vous ne pouvez pas basculer entre plusieurs chargements.</span><span class="sxs-lookup"><span data-stu-id="e4886-121">You can add multiple items to a license plate, but you cannot switch between multiple loads.</span></span>
