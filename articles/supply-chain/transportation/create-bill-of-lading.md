---
title: Créer une feuille de chargement
description: Cette rubrique décrit la procédure de création d'une feuille de chargement lors de l'utilisation des processus de gestion des entrepôts.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 05ad5d4b49f1fa50bde7df9c835ee99a981420c4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206309"
---
# <a name="create-a-bill-of-lading"></a><span data-ttu-id="7d010-103">Créer une feuille de chargement</span><span class="sxs-lookup"><span data-stu-id="7d010-103">Create a bill of lading</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d010-104">Cette rubrique décrit la procédure de création d'une feuille de chargement lors de l'utilisation des processus de gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="7d010-104">This topic describes how to create a bill of lading when using warehouse management processes.</span></span>  

<span data-ttu-id="7d010-105">Une feuille de chargement est un document juridique entre la société qui expédie les articles et le transporteur.</span><span class="sxs-lookup"><span data-stu-id="7d010-105">A bill of lading is a legal document between the company that ships the items and the carrier.</span></span> <span data-ttu-id="7d010-106">Le document accompagne les articles expédiés, et sert de preuve d'expédition lorsque les articles sont livrés à la destination.</span><span class="sxs-lookup"><span data-stu-id="7d010-106">The document accompanies the shipped items, and it serves as a receipt of shipment when the items are delivered at the destination.</span></span> <span data-ttu-id="7d010-107">Si vous utilisez la gestion des entrepôts, il existe deux manières de générer une feuille de chargement :</span><span class="sxs-lookup"><span data-stu-id="7d010-107">If you're using warehouse management, there are two ways to generate a bill of lading:</span></span>

  -   <span data-ttu-id="7d010-108">Vous pouvez créer l'état manuellement, à l'aide de la page **Feuille de chargement**.</span><span class="sxs-lookup"><span data-stu-id="7d010-108">Create the report manually, using the **Bill of lading** page.</span></span>
  -   <span data-ttu-id="7d010-109">Vous pouvez générer un état à partir de l'option **Atelier de planification des chargements**.</span><span class="sxs-lookup"><span data-stu-id="7d010-109">Generate the report from the **Load planning workbench**.</span></span>

<span data-ttu-id="7d010-110">Si vous générez la feuille de chargement à partir de l'option **Atelier de planification des chargements**, le statut de chargement doit être **Expédié**.</span><span class="sxs-lookup"><span data-stu-id="7d010-110">If you generate the bill of lading from the **Load planning workbench**, the load status must be **Shipped.**</span></span> <span data-ttu-id="7d010-111">S'il y a plus d'une expédition dans le chargement, une feuille de chargement est créée pour chaque expédition.</span><span class="sxs-lookup"><span data-stu-id="7d010-111">If there's more than one shipment in the load, a bill of lading is created for each shipment.</span></span> <span data-ttu-id="7d010-112">Une fois la feuille de chargement créée, vous pouvez y apporter des modifications dans la page **Feuille de chargement**.</span><span class="sxs-lookup"><span data-stu-id="7d010-112">After a bill of lading has been created you can make changes to it on the **Bill of lading** page.</span></span>

## <a name="master-bill-of-lading"></a><span data-ttu-id="7d010-113">Feuille de chargement principale</span><span class="sxs-lookup"><span data-stu-id="7d010-113">Master bill of lading</span></span>
<span data-ttu-id="7d010-114">S'il existe plusieurs expéditions dans un chargement, vous pouvez créer une feuille de chargement principale.</span><span class="sxs-lookup"><span data-stu-id="7d010-114">If there's more than one shipment in the load, you can generate a master bill of lading.</span></span> <span data-ttu-id="7d010-115">La mise en page et les informations sont les mêmes que sur une feuille de chargement, mais elle contient le récapitulatif du contenu de toutes les expéditions.</span><span class="sxs-lookup"><span data-stu-id="7d010-115">This has the same layout and information as a bill of lading, but contains the summarized content for all the shipments.</span></span> <span data-ttu-id="7d010-116">Si l'option **Créer une feuille de chargement principale s'il existe plusieurs expéditions sur un chargement** est définie sur **Oui** sur la page **Paramètres de gestion de transport**, une feuille de chargement principale est générée automatiquement si vous créez une feuille de chargement à partir de **Atelier de planification des chargements**, et il y a plusieurs expéditions.</span><span class="sxs-lookup"><span data-stu-id="7d010-116">If the **Create a master bill of lading when there's more than one shipment on a load** option is set to **Yes** on the **Transportation management parameters** page, a master bill of lading is automatically generated if you create a bill of lading from the **Load planning workbench**, and there's more than one shipment.</span></span> <span data-ttu-id="7d010-117">Vous pouvez également obtenir la liste des feuilles de chargement en cliquant sur **Informations associées** &gt; **Feuille de chargement**.</span><span class="sxs-lookup"><span data-stu-id="7d010-117">You can also get a list of the bills of lading by clicking **Related information** &gt; **Bill of lading**.</span></span> <span data-ttu-id="7d010-118">Si vous créez des feuilles de chargement manuellement, vous pouvez créer une feuille de chargement principale dans la page **Feuille de chargement**.</span><span class="sxs-lookup"><span data-stu-id="7d010-118">If you're creating bills of lading manually, you can create a master bill of lading on the **Bill of lading** page.</span></span>



