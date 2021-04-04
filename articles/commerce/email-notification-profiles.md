---
title: Paramétrer un profil de notification par e-mail
description: Cette rubrique décrit comment créer un profil de notification par e-mail dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d82a1abe68ff6e162acb75c6fdc1e207af11c279
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555305"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="7bc80-103">Configurer un profil de notification par e-mail</span><span class="sxs-lookup"><span data-stu-id="7bc80-103">Set up an email notification profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7bc80-104">Cette rubrique décrit comment créer un profil de notification par e-mail dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7bc80-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="7bc80-105">Lorsque vous créez des canaux, vous pouvez configurer un profil de notification par e-mail.</span><span class="sxs-lookup"><span data-stu-id="7bc80-105">When you create channels, you can set up an email notification profile.</span></span> <span data-ttu-id="7bc80-106">De cette manière, des e-mails peuvent être envoyés aux clients pour divers événements transactionnels, tels que la création d’une commande, le statut d’expédition d’une commande et l’échec de paiement.</span><span class="sxs-lookup"><span data-stu-id="7bc80-106">In that way, emails can be sent to customers for various transactional events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="7bc80-107">Pour plus d'informations sur la configuration de l'e-mail, consultez la rubrique [Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="7bc80-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="7bc80-108">Créer un profil de notification par e-mail</span><span class="sxs-lookup"><span data-stu-id="7bc80-108">Create an email notification profile</span></span>

<span data-ttu-id="7bc80-109">Pour créer un profil de notification par e-mail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7bc80-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="7bc80-110">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Profil de notification par e-mail de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="7bc80-111">Dans le volet Actions, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="7bc80-112">Dans le champ **Profil de notification par e-mail**, entrez un nom pour identifier le profil.</span><span class="sxs-lookup"><span data-stu-id="7bc80-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="7bc80-113">Entrez une description pertinente dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="7bc80-114">Paramétrer le commutateur **Actif** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="7bc80-115">Créer un modèle d'e-mail</span><span class="sxs-lookup"><span data-stu-id="7bc80-115">Create an email template</span></span>

<span data-ttu-id="7bc80-116">Avant qu’un type de notification par e-mail puisse être activé, vous devez créer un modèle d’e-mail d’organisation dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="7bc80-116">Before an email notification type can be enabled, you must create an organization email template in Commerce headquarters.</span></span> <span data-ttu-id="7bc80-117">Ce modèle définit l’objet de l’e-mail, l’expéditeur, la langue par défaut et le corps de l’e-mail pour chaque langue que vous souhaitez prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="7bc80-117">This template defines the email subject, sender, default language, and email body for each language that you want to support.</span></span>

<span data-ttu-id="7bc80-118">Pour créer un modèle d'e-mail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7bc80-118">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="7bc80-119">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Paramètres \> Modèles d'e-mail pour l'organisation**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-119">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="7bc80-120">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-120">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="7bc80-121">Dans le champ **ID e-mail**, entrez un ID pour vous aider à identifier ce modèle.</span><span class="sxs-lookup"><span data-stu-id="7bc80-121">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="7bc80-122">Entrez le nom des expéditeurs dans le champ **Nom des expéditeurs**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-122">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="7bc80-123">Entrez une description pertinente dans le champ **Description de l'e-mail**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-123">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="7bc80-124">Dans le champ **E-mail de l'expéditeur**, entrez l'adresse e-mail des expéditeurs.</span><span class="sxs-lookup"><span data-stu-id="7bc80-124">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="7bc80-125">Dans la section **Général**, sélectionnez une langue par défaut pour le modèle d’e-mail.</span><span class="sxs-lookup"><span data-stu-id="7bc80-125">In the **General** section, select a default language for the email template.</span></span> <span data-ttu-id="7bc80-126">La langue par défaut sera utilisée lorsqu’aucun modèle localisé n’existe pour la langue spécifiée.</span><span class="sxs-lookup"><span data-stu-id="7bc80-126">The default language will be used when no localized template exists for the specified language.</span></span>
1. <span data-ttu-id="7bc80-127">Élargissez la section **Contenu du message électronique** et sélectionnez **Nouveau** pour créer le contenu du modèle.</span><span class="sxs-lookup"><span data-stu-id="7bc80-127">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="7bc80-128">Pour chaque élément de contenu, sélectionnez la langue et indiquez la ligne d'objet de l'e-mail.</span><span class="sxs-lookup"><span data-stu-id="7bc80-128">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="7bc80-129">Si l'e-mail va avoir un corps, assurez-vous que la case **A un corps** est cochée.</span><span class="sxs-lookup"><span data-stu-id="7bc80-129">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="7bc80-130">Dans le volet Actions, sélectionnez **Message électronique** pour fournir un modèle de corps d'e-mail.</span><span class="sxs-lookup"><span data-stu-id="7bc80-130">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="7bc80-131">L'image suivante montre quelques exemples de paramètres de modèle d'e-mail.</span><span class="sxs-lookup"><span data-stu-id="7bc80-131">The following image shows some example email template settings.</span></span>

![Paramètres du modèle d'e-mail](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="7bc80-133">Créer un événement d'e-mail</span><span class="sxs-lookup"><span data-stu-id="7bc80-133">Create an email event</span></span>

<span data-ttu-id="7bc80-134">Pour créer un événement d'e-mail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7bc80-134">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="7bc80-135">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Profil de notification par e-mail de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-135">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="7bc80-136">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7bc80-136">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="7bc80-137">Sélectionnez le modèle d'e-mail dans la liste déroulante **ID e-mail**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-137">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="7bc80-138">Sélectionnez le bon **Type de notification par e-mail** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="7bc80-138">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="7bc80-139">Cochez la case **Actif**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-139">Select the **Active** check box.</span></span>
1. <span data-ttu-id="7bc80-140">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7bc80-140">On the action pane, select **Save**.</span></span>

<span data-ttu-id="7bc80-141">L'image suivante montre quelques exemples de notification d'événements.</span><span class="sxs-lookup"><span data-stu-id="7bc80-141">The following image shows some example event notification settings.</span></span>

![Paramètres de notification d'événements](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="7bc80-143">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="7bc80-143">Next steps</span></span>

<span data-ttu-id="7bc80-144">Avant de pouvoir envoyer des e-mails, vous devez configurer votre service de courrier sortant et configurer un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="7bc80-144">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="7bc80-145">Pour plus d'informations, voir [Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="7bc80-145">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="7bc80-146">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7bc80-146">Additional resources</span></span>

[<span data-ttu-id="7bc80-147">Configurer et envoyer un e-mail</span><span class="sxs-lookup"><span data-stu-id="7bc80-147">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="7bc80-148">Vue d'ensemble des canaux</span><span class="sxs-lookup"><span data-stu-id="7bc80-148">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="7bc80-149">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="7bc80-149">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="7bc80-150">Vue d'ensemble des organisations et des hiérarchies d'organisation</span><span class="sxs-lookup"><span data-stu-id="7bc80-150">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
