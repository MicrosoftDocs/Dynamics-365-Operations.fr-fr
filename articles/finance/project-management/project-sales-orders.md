---
title: Commandes client de projet pour les projets en régie
description: Cette rubrique explique comment créer des commandes client basées sur un projet pour les projets en régie.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: 2f27e3e0a2d6aadc4c5224b55f8a416cbe4e83aa
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551200"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a><span data-ttu-id="7bf7b-103">Commandes client de projet pour les projets en régie</span><span class="sxs-lookup"><span data-stu-id="7bf7b-103">Project sales orders for time and material projects</span></span>

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

<span data-ttu-id="7bf7b-104">Cette rubrique décrit comment créer une commande client pour un projet.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-104">This topic describes how to create a sales order for a project.</span></span> <span data-ttu-id="7bf7b-105">Les commandes client ne peuvent être créées que pour les projets du type **régie**.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-105">Sales orders can only be created for projects of type **time and material**.</span></span>

<span data-ttu-id="7bf7b-106">Si un projet en régie a plusieurs sources de financement dans le contrat de projet, vous devez activer le paramètre **Autoriser les commandes client pour les projets avec plusieurs sources de financement** dans la page **Paramètres de gestion de projets et de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-106">If a time and material project has multiple funding sources on the project contract, you must enable the **Allow sales orders for projects with multiple funding sources** parameter on the **Project management and accounting parameters** page.</span></span> 

> [!NOTE]
> - <span data-ttu-id="7bf7b-107">La prise en charge des commandes client de projets avec plusieurs sources de financement est disponible depuis la version de l'application 10.0.2.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-107">Support for project sales orders with multiple funding sources is available starting with application release 10.0.2 and higher.</span></span>
> - <span data-ttu-id="7bf7b-108">Le paramètre permettant d'activer la prise en charge des commandes client de projet avec plusieurs sources de financement sera supprimé dans la vague de publications d'avril 2020, après quoi la fonctionnalité sera toujours activée.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-108">The parameter to enable the support for project sales orders with multiple funding sources will be removed in the April 2020 release wave, after which the functionality will always be enabled.</span></span>

<span data-ttu-id="7bf7b-109">Vous pouvez créer des commandes client basée sur un projet de deux manières :</span><span class="sxs-lookup"><span data-stu-id="7bf7b-109">You can create project-based sales orders in two ways:</span></span>

- <span data-ttu-id="7bf7b-110">Accédez au projet lui-même.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-110">Go to the project itself.</span></span> <span data-ttu-id="7bf7b-111">Dans le volet Actions, sélectionnez **Gestion > Tâches d'article > Commandes client**.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-111">On the Action Pane, select **Manage > Item tasks > Sales order**.</span></span> <span data-ttu-id="7bf7b-112">Les informations du projet passent par défaut sur les commandes client du projet.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-112">The project information will default to the sales order from the project.</span></span> <span data-ttu-id="7bf7b-113">Si le contrat de projet comporte plusieurs sources de financement, vous devez sélectionner la source de financement pour définir le client pour la commande client.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-113">If the project contract has more than one funding source, you will need to select the funding source to set the customer for the sales order.</span></span> <span data-ttu-id="7bf7b-114">S'il n'y a qu'une source de financement pour le projet, le client est automatiquement défini.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-114">If there is only one funding source for the project, the customer will be automatically set.</span></span>
- <span data-ttu-id="7bf7b-115">Accédez à la page de liste **Toutes les commandes client** et créez une commande client.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-115">Go to the **All sales order** list page and create a new sales order.</span></span> <span data-ttu-id="7bf7b-116">Vous devez sélectionner le projet pour la commande client.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-116">You will need to select the project for the sales order.</span></span> <span data-ttu-id="7bf7b-117">Une fois le projet sélectionnée, le client est défini à partir de la source de financement, ou vous devez sélectionner la source de financement si le contrat de projet en inclut plusieurs.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-117">After the project is selected, the customer will be set from the funding source or you will need to select the funding source if the project contract has multiple funding sources.</span></span>

