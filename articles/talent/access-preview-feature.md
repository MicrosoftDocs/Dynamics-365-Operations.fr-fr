---
title: Gérer les fonctionnalités
description: Cette rubrique décrit comment un administrateur peut activer les fonctionnalités d'aperçu dans Microsoft Dynamics 365 Talent. Elle répertorie également les fonctionnalités qui sont actuellement activées pour le mode aperçu.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.1.0, Talent
ms.openlocfilehash: d818e9e04ce88e5ab285ef8176334809447fb477
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461213"
---
# <a name="manage-features"></a><span data-ttu-id="6f29d-103">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="6f29d-103">Manage features</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6f29d-104">Dans le cadre de notre lancement continu de fonctionnalités de gestion du capital humain (GCH) pour Microsoft Dynamics 365 Human Resources, nous souhaitons que nos clients expérimentent de nouvelles fonctionnalités dès que possible.</span><span class="sxs-lookup"><span data-stu-id="6f29d-104">As part of our continuous rollout of human capital management (HCM) capabilities for Microsoft Dynamics 365 Human Resources, we want to let customers experience new features as soon as possible.</span></span> <span data-ttu-id="6f29d-105">Les administrateurs peuvent afficher et utiliser les fonctionnalités d'aperçu dans leurs environnements.</span><span class="sxs-lookup"><span data-stu-id="6f29d-105">Administrators can see and use preview features in their environments.</span></span> <span data-ttu-id="6f29d-106">Ces fonctionnalités sont presque prêtes pour la mise à disposition générale et ont fait l'objet de tests étendus.</span><span class="sxs-lookup"><span data-stu-id="6f29d-106">These features are almost ready for general availability and have gone through extensive testing.</span></span> <span data-ttu-id="6f29d-107">Nous attendons les derniers commentaires et validations des clients avant leur publication pour une disponibilité générale.</span><span class="sxs-lookup"><span data-stu-id="6f29d-107">We're just looking for a final round of customer feedback and validation before we release them for general availability.</span></span>

<span data-ttu-id="6f29d-108">Cette rubrique décrit comment vous pouvez activer les fonctionnalités d'aperçu. Elle répertorie également les fonctionnalités qui sont actuellement disponibles en mode aperçu.</span><span class="sxs-lookup"><span data-stu-id="6f29d-108">This topic describes how you can enable preview features, and it lists the features that are currently available for preview.</span></span> <span data-ttu-id="6f29d-109">Cette liste sera mise à jour lorsque les fonctionnalités seront mises à la disposition générale et que de nouvelles fonctionnalités seront disponibles en mode aperçu.</span><span class="sxs-lookup"><span data-stu-id="6f29d-109">This list will be updated as features are released to general availability and as new features are released to preview.</span></span> <span data-ttu-id="6f29d-110">Aucune notification n'est fournie lorsque de nouvelles fonctionnalités sont disponibles en mode aperçu.</span><span class="sxs-lookup"><span data-stu-id="6f29d-110">No notification is given when new features are released to preview.</span></span> <span data-ttu-id="6f29d-111">Les utilisateurs commenceront simplement à voir les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="6f29d-111">Users will just start to see the features.</span></span> <span data-ttu-id="6f29d-112">Pour plus d'informations sur les nouvelles fonctions dans Talent, voir [Nouveautés ou modifications dans Dynamics 365 Talent](./whats-new.md) et [Notes de publication de Dynamics 365 et Power Platform](https://docs.microsoft.com/business-applications-release-notes).</span><span class="sxs-lookup"><span data-stu-id="6f29d-112">For more information about new features in Talent, see [What's new or changed in Dynamics 365 Talent](./whats-new.md) and [Dynamics 365 and Power Platform Release Notes](https://docs.microsoft.com/business-applications-release-notes).</span></span>

## <a name="enable-or-disable-preview-features"></a><span data-ttu-id="6f29d-113">Activer ou désactiver les fonctionnalités d'aperçu</span><span class="sxs-lookup"><span data-stu-id="6f29d-113">Enable or disable preview features</span></span>

<span data-ttu-id="6f29d-114">Pour accéder aux fonctionnalités d'aperçu, vous devez commencer par les activer dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="6f29d-114">To access preview features, you must first enable them in your environment.</span></span> <span data-ttu-id="6f29d-115">L'activation ou la désactivation des fonctionnalités d'aperçu est propre à l'environnement.</span><span class="sxs-lookup"><span data-stu-id="6f29d-115">Enabling or disabling preview features is environment-specific.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f29d-116">En activant le paramètre **Fonctionnalités d'aperçu**, vous activez les fonctionnalités d'aperçu pour tous les utilisateurs de votre organisation qui se trouvent dans cet environnement.</span><span class="sxs-lookup"><span data-stu-id="6f29d-116">When you turn on the **Preview Features** setting, you enable preview features for all users in your organization who are in that environment.</span></span> <span data-ttu-id="6f29d-117">En désactivant le paramètre, vous désactivez les fonctionnalités d'aperçu et les rendez inaccessibles à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6f29d-117">When you turn off the setting, you disable preview features and make them inaccessible to your users.</span></span> <span data-ttu-id="6f29d-118">Les fonctionnalités d'aperçu ont une prise en charge limitée dans Talent.</span><span class="sxs-lookup"><span data-stu-id="6f29d-118">Preview features have limited support in Talent.</span></span> <span data-ttu-id="6f29d-119">Elles peuvent utiliser moins de mesures de confidentialité et de sécurité, et elles ne sont pas incluses dans le contrat de niveau de service de Talent (SLA).</span><span class="sxs-lookup"><span data-stu-id="6f29d-119">They might use fewer privacy and security measures, and they aren't included in the Talent service level agreement (SLA).</span></span> <span data-ttu-id="6f29d-120">Vous ne devez pas utiliser les fonctionnalités d'aperçu pour traiter des données personnelles (c'est-à-dire, toute information susceptible de vous identifier), ou pour traiter d'autres données soumises à des exigences de conformité juridique ou réglementaire.</span><span class="sxs-lookup"><span data-stu-id="6f29d-120">You should not use preview features to process personal data (that is, any information that could identify you), or to process other data that is subject to legal or regulatory compliance requirements.</span></span>

### <a name="attract"></a><span data-ttu-id="6f29d-121">Attract</span><span class="sxs-lookup"><span data-stu-id="6f29d-121">Attract</span></span>

1. <span data-ttu-id="6f29d-122">Connectez-vous à Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="6f29d-122">Sign in to Microsoft Dynamics 365 Talent: Attract.</span></span>
2. <span data-ttu-id="6f29d-123">Dans le menu **Paramétrage** (symbole en forme d'engrenage) dans le coin supérieur droit, sélectionnez **Centre d'administration**.</span><span class="sxs-lookup"><span data-stu-id="6f29d-123">On the **Setup** menu (the gear symbol) in the upper-right corner, select **Admin center**.</span></span>
3. <span data-ttu-id="6f29d-124">Sous l'onglet **Gestion des fonctionnalités**, sélectionnez l'option en regard de **Fonctionnalités d'aperçu** afin qu'elle devienne bleu et indique **Activé**.</span><span class="sxs-lookup"><span data-stu-id="6f29d-124">On the **Feature management** tab, select the option next to **Preview features** so that it turns blue and says **On**.</span></span>

    ![Activer les fonctionnalités d'aperçu dans Attract](./media/attract-enable-preview-features.png)

4. <span data-ttu-id="6f29d-126">Sélectionnez ou annuler la sélection de fonctionnalités d'aperçu individuelles.</span><span class="sxs-lookup"><span data-stu-id="6f29d-126">Select or cancel the selection of individual preview features.</span></span> <span data-ttu-id="6f29d-127">Si vous n'entrez rien, toutes les fonctionnalités d'aperçu disponibles sont activées.</span><span class="sxs-lookup"><span data-stu-id="6f29d-127">If you do nothing, all available preview features are enabled.</span></span>
5. <span data-ttu-id="6f29d-128">Actualisez votre navigateur pour commencer à voir les nouvelles fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="6f29d-128">Refresh your browser to start to see the new features.</span></span> <span data-ttu-id="6f29d-129">Les utilisateurs qui sont déjà connectés verront les fonctionnalités lors de leur prochaine connexion, ou ils peuvent actualiser leur navigateur pour voir les fonctionnalités immédiatement.</span><span class="sxs-lookup"><span data-stu-id="6f29d-129">Any users who are already signed in will see the features the next time they sign in, or they can refresh their browser to see the features immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="6f29d-130">Certaines fonctionnalités d'aperçu peuvent nécessiter une autre configuration.</span><span class="sxs-lookup"><span data-stu-id="6f29d-130">Some preview features might require additional configuration.</span></span> <span data-ttu-id="6f29d-131">Suivez les liens en regard de la fonctionnalité d'aperçu pour compléter le paramétrage pour celui-ci.</span><span class="sxs-lookup"><span data-stu-id="6f29d-131">Follow the links next to the preview feature to complete the setup for it.</span></span>

## <a name="feedback"></a><span data-ttu-id="6f29d-132">Rétroaction</span><span class="sxs-lookup"><span data-stu-id="6f29d-132">Feedback</span></span>

<span data-ttu-id="6f29d-133">Nous voulons connaître votre opinion sur votre expérience avec l'une de ces fonctionnalités d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="6f29d-133">We want to hear from you about your experience with any of these preview features.</span></span> <span data-ttu-id="6f29d-134">Nous vous encourageons à publier régulièrement vos commentaires sur les sites suivants lorsque vous utilisez ces fonctionnalités ou d'autres :</span><span class="sxs-lookup"><span data-stu-id="6f29d-134">We encourage you to regularly post your feedback on the following sites as you use these or any other features:</span></span>

- <span data-ttu-id="6f29d-135">[Communauté](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ce site est une ressource utile où les utilisateurs peuvent discuter de cas d'utilisation, poser des questions et obtenir l'aide de la communauté.</span><span class="sxs-lookup"><span data-stu-id="6f29d-135">[Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – This site is a great resource where users can discuss use cases, ask questions, and get community help.</span></span>
- <span data-ttu-id="6f29d-136">Faites-nous part des fonctionnalités que vous souhaitez voir dans le produit ou des modifications qui, selon vous, doivent être apportées aux fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="6f29d-136">Let us know about features that you want to see in the product, or let us know about any changes you think we should make to existing features.</span></span> <span data-ttu-id="6f29d-137">Proposez des idées de produit pour les sites suivants :</span><span class="sxs-lookup"><span data-stu-id="6f29d-137">Suggest product ideas on the following sites:</span></span>

    - [<span data-ttu-id="6f29d-138">Idées pour Attract</span><span class="sxs-lookup"><span data-stu-id="6f29d-138">Attract ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [<span data-ttu-id="6f29d-139">Idées pour Onboard</span><span class="sxs-lookup"><span data-stu-id="6f29d-139">Onboard ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

<span data-ttu-id="6f29d-140">Assurez-vous de ne pas ajouter de données personnelles (toute information susceptible de vous identifier) dans vos commentaires ou vos demandes d'évaluation du produit.</span><span class="sxs-lookup"><span data-stu-id="6f29d-140">Make sure that you don't include personal data (any information that could identify you) in your feedback or product review submissions.</span></span> <span data-ttu-id="6f29d-141">Les informations collectées peuvent être analysées davantage, et ne sont pas utilisées pour répondre à des demandes aux termes des lois applicables sur la confidentialité.</span><span class="sxs-lookup"><span data-stu-id="6f29d-141">Collected information might be analyzed further and isn't used to answer requests under applicable privacy laws.</span></span> <span data-ttu-id="6f29d-142">Les données personnelles qui sont collectées séparément dans le cadre de ces programmes sont soumises à la [Déclaration de confidentialité Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="6f29d-142">Personal data that is collected separately under these programs is subject to the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span>

> [!TIP]
> <span data-ttu-id="6f29d-143">Marquez cette rubrique et consultez-la régulièrement pour rester informé des nouvelles fonctionnalités d'aperçu dès leur parution.</span><span class="sxs-lookup"><span data-stu-id="6f29d-143">Bookmark this topic, and check back often to stay up to date about new preview features as we release them.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f29d-144">Voir également :</span><span class="sxs-lookup"><span data-stu-id="6f29d-144">See also</span></span>

- [<span data-ttu-id="6f29d-145">Essayer ou acheter des applications Talent</span><span class="sxs-lookup"><span data-stu-id="6f29d-145">Try or buy Talent apps</span></span>](https://dynamics.microsoft.com/talent/overview/)
- [<span data-ttu-id="6f29d-146">Nouveautés ou modifications dans Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="6f29d-146">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="6f29d-147">Programmes de lancement</span><span class="sxs-lookup"><span data-stu-id="6f29d-147">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="6f29d-148">Obtenir de l'aide sur Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="6f29d-148">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
