---
title: Désactiver la collecte d’événements d’activité Web
description: Cette rubrique explique comment vous pouvez autoriser les visiteurs de votre site Web à désactiver la collecte d’événements d’activité Web dans Microsoft Dynamics 365 Commerce.
author: aamiral
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86f475cc0b78c620309301516b6c3b525b640637
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791555"
---
# <a name="opt-out-of-web-activity-event-collection"></a><span data-ttu-id="7871b-103">Refuser les événements liés à l’activité sur le Web</span><span class="sxs-lookup"><span data-stu-id="7871b-103">Opt out of web activity event collection</span></span>
[!include [banner](includes/banner.md)]

<span data-ttu-id="7871b-104">Cette rubrique explique comment vous pouvez laisser les clients désactiver la collecte d’événements d’activité Web dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7871b-104">This topic explains how you can let customers opt out of web activity event collection in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="7871b-105">Dynamics 365 Commerce permet aux administrateurs de site d’analyser l’activité Web des utilisateurs de leurs sites de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="7871b-105">Dynamics 365 Commerce lets site administrators analyze the web activity of users of their e-commerce sites.</span></span> <span data-ttu-id="7871b-106">De cette façon, ils peuvent mieux comprendre comment leurs sites sont utilisés et les optimiser pour offrir une expérience utilisateur améliorée et répondre aux objectifs commerciaux.</span><span class="sxs-lookup"><span data-stu-id="7871b-106">In that way, they can better understand how their sites are used, and they can optimize the sites to provide an improved user experience and meet business objectives.</span></span>


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a><span data-ttu-id="7871b-107">Méthodes de mise en œuvre d’une expérience de désinscription côté administrateurs</span><span class="sxs-lookup"><span data-stu-id="7871b-107">Ways for administrators to implement an opt-out experience</span></span>

<span data-ttu-id="7871b-108">Les administrateurs disposent de 3 méthodes pour mettre en œuvre d’une expérience de désinscription.</span><span class="sxs-lookup"><span data-stu-id="7871b-108">Administrators have three ways to implement an opt-out experience.</span></span>

### <a name="opt-out-on-behalf-of-users"></a><span data-ttu-id="7871b-109">Refus pour le compte des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7871b-109">Opt out on behalf of users</span></span>

<span data-ttu-id="7871b-110">Dans la gestion de compte dans Commerce Headquarters (HQ), les administrateurs peuvent refuser au nom des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7871b-110">In Account management in Commerce headquarters (HQ), administrators can opt out on behalf of users.</span></span>

1. <span data-ttu-id="7871b-111">Dans le client HQ, sur la page **Tous les clients**, recherchez et sélectionnez un client.</span><span class="sxs-lookup"><span data-stu-id="7871b-111">In the HQ client, on the **All customers** page, search for and select a customer.</span></span>
1. <span data-ttu-id="7871b-112">Sur la page des détails du client, sur le raccourci **Retail**, dans la section **Confidentialité**, définissez l’option **Ne pas suivre l’activité Web** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="7871b-112">On the customer details page, on the **Retail** FastTab, in the **Privacy** section, set the **Do not track web activity** option to **Yes**.</span></span>

    ![Paramètres de confidentialité](media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="7871b-114">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7871b-114">Select **Save**, and then close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="7871b-115">Expérience de désinscription basée sur les modules</span><span class="sxs-lookup"><span data-stu-id="7871b-115">Module-based opt-out experience</span></span>

<span data-ttu-id="7871b-116">Les administrateurs peuvent laisser les utilisateurs authentifiés désactiver eux-mêmes la collecte d’événements d’activité Web.</span><span class="sxs-lookup"><span data-stu-id="7871b-116">Administrators can let authenticated users opt out of web activity event collection by themselves.</span></span> <span data-ttu-id="7871b-117">Pour proposer cette expérience de désinscription, ajoutez le module de refus utilisateur aux pages du profil de compte client.</span><span class="sxs-lookup"><span data-stu-id="7871b-117">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="7871b-118">Extensions personnalisées</span><span class="sxs-lookup"><span data-stu-id="7871b-118">Custom extensions</span></span>

<span data-ttu-id="7871b-119">Les administrateurs peuvent créer leurs propres extensions pour gérer l’expérience de désinscription pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7871b-119">Administrators can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="7871b-120">Pour plus d’informations, voir [Appeler les API Retail Server](e-commerce-extensibility/call-retail-server-apis.md) et [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="7871b-120">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
