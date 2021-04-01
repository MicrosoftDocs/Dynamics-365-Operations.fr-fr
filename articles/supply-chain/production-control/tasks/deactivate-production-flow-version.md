---
title: Désactiver la version d’un flux de production
description: Lorsqu’une version de flux de production active n’est plus nécessaire, elle peut être désactivée.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b062bcab17a708be0cd40f2cc6451707d6993a4b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257337"
---
# <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="27bb5-103">Désactiver la version d’un flux de production</span><span class="sxs-lookup"><span data-stu-id="27bb5-103">Deactivate a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="27bb5-104">Lorsqu’une version de flux de production active n’est plus nécessaire, elle peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="27bb5-104">When an active production flow version is no longer needed, it can be deactivated.</span></span> <span data-ttu-id="27bb5-105">Vous devez uniquement utiliser cette option si toutes les règles de kanban et activités sont terminées et ne sont pas réactivées.</span><span class="sxs-lookup"><span data-stu-id="27bb5-105">You should only use this option if all kanban rules and activities have ended and will not be activated again.</span></span> <span data-ttu-id="27bb5-106">Notez que la date d’expiration de toutes les règles de kanban associées à cette version de flux de production est mise à jour sur la date et l’heure actuelles.</span><span class="sxs-lookup"><span data-stu-id="27bb5-106">Note that the expiry date of all kanban rules related to this production flow version will be updated with the current date and time.</span></span> 

<span data-ttu-id="27bb5-107">Pour modifier une version de flux de production active, définissez une date d’expiration pour la version active et créez une nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="27bb5-107">To modify an active production flow version, consider setting an expiry date for the active version and create a new version.</span></span> <span data-ttu-id="27bb5-108">Cela vous permet de continuer vos opérations de production tout en préparant la nouvelle version et les règles de kanban associées.</span><span class="sxs-lookup"><span data-stu-id="27bb5-108">This will allow you to continue your production operations while preparing the new version and related kanban rules.</span></span> 

<span data-ttu-id="27bb5-109">Pour faire expirer une version de flux de production active, vous devez définir une date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="27bb5-109">To expire an active production flow version, you need to set an expiry date.</span></span> <span data-ttu-id="27bb5-110">Dans ce sens, la désactivation s’apparente à une exception plutôt qu’à une règle.</span><span class="sxs-lookup"><span data-stu-id="27bb5-110">In that sense, deactivation is more like an exception than a rule.</span></span> 

<span data-ttu-id="27bb5-111">Pour cette procédure, vous avez besoin d’un flux de production avec une version qui peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="27bb5-111">For this procedure you need a production flow with a version that can be deactivated.</span></span> <span data-ttu-id="27bb5-112">Ne tentez pas d’effectuer cette procédure dans un environnement de production à moins que vous soyez sûr à 100 % que la version est entièrement obsolète.</span><span class="sxs-lookup"><span data-stu-id="27bb5-112">Do not try this in a production environment unless you are 100% positive that the version is fully obsolete.</span></span>


## <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="27bb5-113">Désactiver la version d’un flux de production</span><span class="sxs-lookup"><span data-stu-id="27bb5-113">Deactivate a production flow version</span></span>
1. <span data-ttu-id="27bb5-114">Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.</span><span class="sxs-lookup"><span data-stu-id="27bb5-114">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="27bb5-115">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="27bb5-115">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="27bb5-116">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="27bb5-116">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="27bb5-117">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="27bb5-117">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="27bb5-118">Cliquez sur Désactiver.</span><span class="sxs-lookup"><span data-stu-id="27bb5-118">Click Deactivate.</span></span>
    * <span data-ttu-id="27bb5-119">Ne continuez pas si vous n’êtes pas sûr à 100 % que cette version de flux de production est obsolète.</span><span class="sxs-lookup"><span data-stu-id="27bb5-119">Do not proceed if you are not 100% positive that this production flow version is obsolete.</span></span> <span data-ttu-id="27bb5-120">Lorsque vous cliquez sur OK, toutes les règles de kanban actives expirent et toutes les activités de production et de réapprovisionnement de cette version de flux de production sont immédiatement arrêtées.</span><span class="sxs-lookup"><span data-stu-id="27bb5-120">Clicking Ok will expire all active kanban rules and put an immediate stop to all production and replenishment activities of this production flow version.</span></span>  
6. <span data-ttu-id="27bb5-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="27bb5-121">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]