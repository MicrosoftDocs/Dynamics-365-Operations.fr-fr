---
title: Désactiver la collecte d'événements d'activité Web
description: Cette rubrique explique comment vous pouvez autoriser les visiteurs de votre site Web à désactiver la collecte d'événements d'activité Web dans Microsoft Dynamics 365 Commerce.
author: aamiral
manager: AnnBe
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2c396060017db6d7ce830b350f242d3097876e50
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012311"
---
# <a name="opt-out-of-web-activity-event-collection"></a><span data-ttu-id="4f283-103">Désactiver la collecte d'événements d'activité Web</span><span class="sxs-lookup"><span data-stu-id="4f283-103">Opt out of web activity event collection</span></span>
[!include [banner](includes/banner.md)]

<span data-ttu-id="4f283-104">Cette rubrique explique comment vous pouvez laisser les clients désactiver la collecte d'événements d'activité Web dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4f283-104">This topic explains how you can let customers opt out of web activity event collection in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4f283-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="4f283-105">Overview</span></span>

<span data-ttu-id="4f283-106">Dynamics 365 Commerce permet aux administrateurs de site d'analyser l'activité Web des utilisateurs de leurs sites de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="4f283-106">Dynamics 365 Commerce lets site administrators analyze the web activity of users of their e-commerce sites.</span></span> <span data-ttu-id="4f283-107">De cette façon, ils peuvent mieux comprendre comment leurs sites sont utilisés et les optimiser pour offrir une expérience utilisateur améliorée et répondre aux objectifs commerciaux.</span><span class="sxs-lookup"><span data-stu-id="4f283-107">In that way, they can better understand how their sites are used, and they can optimize the sites to provide an improved user experience and meet business objectives.</span></span>


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a><span data-ttu-id="4f283-108">Méthodes de mise en œuvre d'une expérience de désinscription côté administrateurs</span><span class="sxs-lookup"><span data-stu-id="4f283-108">Ways for administrators to implement an opt-out experience</span></span>

<span data-ttu-id="4f283-109">Les administrateurs disposent de 3 méthodes pour mettre en œuvre d'une expérience de désinscription.</span><span class="sxs-lookup"><span data-stu-id="4f283-109">Administrators have three ways to implement an opt-out experience.</span></span>

### <a name="opt-out-on-behalf-of-users"></a><span data-ttu-id="4f283-110">Refus pour le compte des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4f283-110">Opt out on behalf of users</span></span>

<span data-ttu-id="4f283-111">Dans la gestion de compte dans Commerce Headquarters (HQ), les administrateurs peuvent refuser au nom des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4f283-111">In Account management in Commerce headquarters (HQ), administrators can opt out on behalf of users.</span></span>

1. <span data-ttu-id="4f283-112">Dans le client HQ, sur la page **Tous les clients**, recherchez et sélectionnez un client.</span><span class="sxs-lookup"><span data-stu-id="4f283-112">In the HQ client, on the **All customers** page, search for and select a customer.</span></span>
1. <span data-ttu-id="4f283-113">Sur la page des détails du client, sur le raccourci **Retail**, dans la section **Confidentialité**, définissez l'option **Ne pas suivre l'activité Web** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="4f283-113">On the customer details page, on the **Retail** FastTab, in the **Privacy** section, set the **Do not track web activity** option to **Yes**.</span></span>

    ![Paramètres de confidentialité](media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="4f283-115">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4f283-115">Select **Save**, and then close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="4f283-116">Expérience de désinscription basée sur les modules</span><span class="sxs-lookup"><span data-stu-id="4f283-116">Module-based opt-out experience</span></span>

<span data-ttu-id="4f283-117">Les administrateurs peuvent laisser les utilisateurs authentifiés désactiver eux-mêmes la collecte d'événements d'activité Web.</span><span class="sxs-lookup"><span data-stu-id="4f283-117">Administrators can let authenticated users opt out of web activity event collection by themselves.</span></span> <span data-ttu-id="4f283-118">Pour proposer cette expérience de désinscription, ajoutez le module de refus utilisateur aux pages du profil de compte client.</span><span class="sxs-lookup"><span data-stu-id="4f283-118">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="4f283-119">Extensions personnalisées</span><span class="sxs-lookup"><span data-stu-id="4f283-119">Custom extensions</span></span>

<span data-ttu-id="4f283-120">Les administrateurs peuvent créer leurs propres extensions pour gérer l'expérience de désinscription pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4f283-120">Administrators can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="4f283-121">Pour plus d'informations, voir [Appeler les API Retail Server](e-commerce-extensibility/call-retail-server-apis.md) et [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="4f283-121">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
