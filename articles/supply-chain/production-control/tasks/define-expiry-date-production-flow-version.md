---
title: Définir une date d’expiration pour une version de flux de production
description: Pour terminer la validité et le traitement d’une version de flux de production à une date donnée, entier ou pour planifier le remplacement d’une version active par une nouvelle version, vous devez définir la date d’expiration de la version.
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
ms.openlocfilehash: 87063653eb78209caaefd3fafa7783f425e710b7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257289"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a><span data-ttu-id="41662-103">Définir une date d’expiration pour une version de flux de production</span><span class="sxs-lookup"><span data-stu-id="41662-103">Define an expiry date for a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="41662-104">Pour terminer la validité et le traitement d’une version de flux de production à une date donnée, entier ou pour planifier le remplacement d’une version active par une nouvelle version, vous devez définir la date d’expiration de la version.</span><span class="sxs-lookup"><span data-stu-id="41662-104">To end the validity and the processing of a production flow version on a given date, or to plan replacement of an active version with a new version, you have to set an expiry date on the version.</span></span> <span data-ttu-id="41662-105">Il n’est pas nécessaire de désactiver la version.</span><span class="sxs-lookup"><span data-stu-id="41662-105">It is not necessary to deactivate the version.</span></span>


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a><span data-ttu-id="41662-106">Définir une date d’expiration pour mettre fin à une version de flux de production</span><span class="sxs-lookup"><span data-stu-id="41662-106">Set an expiration date to end a production flow version</span></span>
1. <span data-ttu-id="41662-107">Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.</span><span class="sxs-lookup"><span data-stu-id="41662-107">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="41662-108">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="41662-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="41662-109">Sélectionnez un flux de production qui a une version déjà définie.</span><span class="sxs-lookup"><span data-stu-id="41662-109">Select any production flow that has a version that is already defined.</span></span>  
3. <span data-ttu-id="41662-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="41662-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="41662-111">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="41662-111">Click Edit.</span></span>
5. <span data-ttu-id="41662-112">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="41662-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="41662-113">Entrez une date et une heure dans le champ Date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="41662-113">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="41662-114">Pour la date d’expiration, une nouvelle version ne démarre pas ni n’est activée.</span><span class="sxs-lookup"><span data-stu-id="41662-114">For the expiration date, a new version will not start or become activated.</span></span> <span data-ttu-id="41662-115">Il n’est également plus possible de créer ou de démarrer des tâches pour ce flux de production.</span><span class="sxs-lookup"><span data-stu-id="41662-115">It will also no longer be possible to create or start jobs for this production flow.</span></span> <span data-ttu-id="41662-116">Vous pouvez toujours exécuter les tâches commencées après la date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="41662-116">You can still complete started jobs after the expiration date.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]