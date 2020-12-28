---
title: Activer l'intégration à Broadbean dans Attract
description: Cette rubrique comment configurer Microsoft Dynamics 365 Talent - Attract pour publier des annonces sur des portails d'emploi externes tels que Broadbean.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 10b612711e81b2b368ed23fdd95ab6a66451f0ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461222"
---
# <a name="enable-broadbean-integration-in-attract"></a><span data-ttu-id="12774-103">Activer l'intégration à Broadbean dans Attract</span><span class="sxs-lookup"><span data-stu-id="12774-103">Enable Broadbean integration in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="12774-104">Vous souhaitez présenter vos postes vacants à autant de candidats qualifiés que possible.</span><span class="sxs-lookup"><span data-stu-id="12774-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="12774-105">Les sites de recrutement comme Broadbean vous aident à y parvenir.</span><span class="sxs-lookup"><span data-stu-id="12774-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="12774-106">Microsoft Dynamics 365 Talent: Attract vous permet désormais de publier des offres sur Broadbean, et Microsoft propose continuellement de nouvelles options dans ce domaine.</span><span class="sxs-lookup"><span data-stu-id="12774-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

> [!NOTE]
> - <span data-ttu-id="12774-107">Pour publier des offres sur des sites externes, vous devez avoir le [Module complémentaire Recrutement complet](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="12774-107">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="12774-108">Pour afficher des missions dans Broadbean via Attract, vous devez avoir un abonnement à Broadbean.</span><span class="sxs-lookup"><span data-stu-id="12774-108">To post jobs to Broadbean through Attract, you must have a Broadbean subscription.</span></span>
> - <span data-ttu-id="12774-109">Cette fonctionnalité est actuellement en mode aperçu.</span><span class="sxs-lookup"><span data-stu-id="12774-109">This feature is currently in preview.</span></span> <span data-ttu-id="12774-110">Si vous souhaitez l'essayer, vous devez [l'activer dans les paramètres administrateur d'Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="12774-110">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

## <a name="configure-broadbean-integration"></a><span data-ttu-id="12774-111">Configurer l'intégration de Broadbean</span><span class="sxs-lookup"><span data-stu-id="12774-111">Configure Broadbean integration</span></span>

1. <span data-ttu-id="12774-112">Connectez-vous à Attract en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="12774-112">Sign in to Attract as an admin.</span></span>

2. <span data-ttu-id="12774-113">Sélectionnez le bouton **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit de la page, puis sélectionnez **Centre d'administration**.</span><span class="sxs-lookup"><span data-stu-id="12774-113">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>

3. <span data-ttu-id="12774-114">Contactez Broadbean, puis entrez vos informations dans les champs **Nom d'utilisateur**, **ID client** et **Jeton de chiffrement**.</span><span class="sxs-lookup"><span data-stu-id="12774-114">Contact Broadbean, and enter your information in the **Username**, **Client ID**, and **Encryption Token** fields.</span></span>

4. <span data-ttu-id="12774-115">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="12774-115">Select **Save**.</span></span>

> [!WARNING]
> <span data-ttu-id="12774-116">Les informations d'identification Broadbean sont précieuses et confidentielles.</span><span class="sxs-lookup"><span data-stu-id="12774-116">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="12774-117">Conservez-les et partagez-les de manière responsable en conséquence.</span><span class="sxs-lookup"><span data-stu-id="12774-117">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="12774-118">Toute personne disposant du rôle Administrateur dans Attract peut afficher ces informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="12774-118">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="12774-119">Microsoft et Attract ne sont pas impliqués dans la création et la conservation de ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="12774-119">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="12774-120">Il est de votre responsabilité de les garder à jour dans Attract et de faire appel à Broadbean pour résoudre éventuels les problèmes impliquant vos informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="12774-120">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>
