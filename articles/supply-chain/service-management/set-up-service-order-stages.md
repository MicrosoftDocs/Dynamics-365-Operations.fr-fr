---
title: Paramétrer des stades de commande de service
description: Paramétrer des stades de commande de service.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9774d5f4e97d3f768366ba552e5928929bacf508
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470927"
---
# <a name="set-up-service-order-stages"></a><span data-ttu-id="4a9c5-103">Paramétrer des stades de commande de service</span><span class="sxs-lookup"><span data-stu-id="4a9c5-103">Set up service order stages</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="4a9c5-104">Accédez à **Gestion des services** \> **Paramétrage** \> **Commandes de service** \> **Stades du service**.</span><span class="sxs-lookup"><span data-stu-id="4a9c5-104">Go to **Service management** \> **Setup** \> **Service orders** \> **Service stages**.</span></span>

2.  <span data-ttu-id="4a9c5-105">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="4a9c5-105">Select **New** to create a new record.</span></span>

3.  <span data-ttu-id="4a9c5-106">Dans les champs **Stade du service** et **Description**, entrez l’ID et la description du stade de service.</span><span class="sxs-lookup"><span data-stu-id="4a9c5-106">In the **Service stage** and **Description** fields, specify a service stage ID and description.</span></span>

4.  <span data-ttu-id="4a9c5-107">Sélectionnez les paramètres appropriés pour le stade.</span><span class="sxs-lookup"><span data-stu-id="4a9c5-107">Select the appropriate parameters for the stage.</span></span>

5.  <span data-ttu-id="4a9c5-108">Sélectionnez le stade parent du stade actif ou laissez le champ **Parent** vide si le stade actif correspond au stade initial du paramétrage de stade.</span><span class="sxs-lookup"><span data-stu-id="4a9c5-108">Select the parent stage for the current stage or leave the **Parent** field blank if the stage is the initial stage in the stage setup.</span></span>


> [!NOTE]
> <P><span data-ttu-id="4a9c5-109">Une fois le stade enregistré, il n’est plus possible de modifier le champ <STRONG>Parent</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4a9c5-109">You cannot modify the <STRONG>Parent</STRONG> field after you save the stage.</span></span> <span data-ttu-id="4a9c5-110">Vous pouvez supprimer l’enregistrement et le créer à nouveau en sélectionnant un autre élément dans le champ <STRONG>Parent</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4a9c5-110">Instead, you can delete the record and create the record again with a different selection in the <STRONG>Parent</STRONG> field.</span></span></P>
> <P><span data-ttu-id="4a9c5-111">En outre, vous ne pouvez créer qu’un seul stade avec un champ <STRONG>Parent</STRONG> vide.</span><span class="sxs-lookup"><span data-stu-id="4a9c5-111">Also, you can only create one stage with a blank <STRONG>Parent</STRONG> field.</span></span> <span data-ttu-id="4a9c5-112">Cela signifie qu’un seul stade initial est autorisé.</span><span class="sxs-lookup"><span data-stu-id="4a9c5-112">That is, only one initial stage is permitted.</span></span></P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]