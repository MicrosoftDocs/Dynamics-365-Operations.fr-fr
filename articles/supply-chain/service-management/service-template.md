---
title: Modèles de service
description: Vous pouvez définir un accord de service comme modèle et, ultérieurement, copier les lignes du modèle dans un autre accord de service ou dans une commande de service.
author: ShylaThompson
manager: tfehr
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8a92d67afe5fd427d1bc272c59e459cb1547d22
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427569"
---
# <a name="service-templates"></a><span data-ttu-id="d9c8d-103">Modèles de service</span><span class="sxs-lookup"><span data-stu-id="d9c8d-103">Service templates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9c8d-104">Vous pouvez définir un accord de service comme modèle et, ultérieurement, copier les lignes du modèle dans un autre accord de service ou dans une commande de service.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-104">You can define a service agreement as a template and copy the lines of the template later into another service agreement or into a service order.</span></span>

## <a name="example"></a><span data-ttu-id="d9c8d-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="d9c8d-105">Example</span></span>

<span data-ttu-id="d9c8d-106">Un client pour lequel vous fournissez un service possède des ascenseurs de service identiques en cinq endroits différents.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-106">A customer for whom you provide service has identical service elevators at five different locations.</span></span>

<span data-ttu-id="d9c8d-107">Vous souhaitez paramétrer cinq accords de service pour le client, un pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-107">You want to set up five service agreements for the customer, one for each site.</span></span>
<span data-ttu-id="d9c8d-108">Pour un travail répétitif de paramétrage et pour vous assurer que les informations de paramétrage sont identiques dans les accords de services, vous créez un accord de service et le spécifiez comme modèle pour la tâche de service sur les ascenseurs.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-108">To limit repetitive setup work, and to make sure that the setup information in the service agreements is identical, you create a service agreement and specify it as a template for the service work on the elevators.</span></span>

<span data-ttu-id="d9c8d-109">À présent, vous pouvez copier les lignes de modèle dans les cinq nouveaux accords de service pour que chacun d'entre eux contienne les lignes du modèle.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-109">You can now copy the template lines into the five new service agreements, so that each service agreement is populated with the lines from the template.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="d9c8d-110">Créer un modèle</span><span class="sxs-lookup"><span data-stu-id="d9c8d-110">Create a template</span></span>

<span data-ttu-id="d9c8d-111">Lorsque vous créez un modèle de service, créez un accord de service, ainsi que les lignes requises dans celui-ci, puis associez l'accord de service à un groupe de modèles de service.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-111">When you create a service template, you create a service agreement, create the required lines on it, and attach the service agreement to a service-template group.</span></span>

> [!NOTE]
> <span data-ttu-id="d9c8d-112">Un accord de service peut uniquement être défini comme un modèle si aucune commande de service ne lui est associée.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-112">A service agreement can be defined as a template only if it has no service orders attached to it.</span></span> <span data-ttu-id="d9c8d-113">De la même manière, aucune commande de service ne peut être générée à partir d'un accord de service qui est défini comme un modèle.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-113">Also, no service orders can be generated from a service agreement that is defined as a template.</span></span>

## <a name="copy-template-lines"></a><span data-ttu-id="d9c8d-114">Copier les lignes de modèle</span><span class="sxs-lookup"><span data-stu-id="d9c8d-114">Copy template lines</span></span>

<span data-ttu-id="d9c8d-115">Vous pouvez copier des lignes d'un modèle de service dans un autre accord de service ou dans une commande de service.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-115">You can copy template lines from a service template into another service agreement or into a service order.</span></span>

<span data-ttu-id="d9c8d-116">Lorsque vous copiez des lignes de modèle dans vos commandes de service ou accords de service, vos groupes de modèles sont affichés dans une arborescence où chaque groupe peut être développé.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-116">When you copy template lines into your service orders or service agreements, your template groups are displayed in a tree view in which each group can be expanded.</span></span> <span data-ttu-id="d9c8d-117">Cet affichage vous permet de visualiser chaque modèle et ligne de modèle.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-117">This display lets you view each template and template line.</span></span>

<span data-ttu-id="d9c8d-118">Il est plus facile de déterminer les lignes de modèle de service à copier si vous avez regroupé les modèles sous des noms qui reflètent leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="d9c8d-118">It is easier to determine the service-template lines that you want to copy if you have grouped the templates under names that reflect the use of the templates.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9c8d-119">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="d9c8d-119">Related topics</span></span>

[<span data-ttu-id="d9c8d-120">Copie de lignes de modèles de service</span><span class="sxs-lookup"><span data-stu-id="d9c8d-120">Copy service templates lines</span></span>](copy-service-template-lines.md)
