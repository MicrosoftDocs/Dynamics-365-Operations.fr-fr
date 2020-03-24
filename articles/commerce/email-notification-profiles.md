---
title: Paramétrer un profil de notification par e-mail
description: Cette rubrique décrit comment créer un profil de notification par e-mail dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9e5d90eaf1815bbe54b0bea40d92a0a993a23b75
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113803"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="928aa-103">Paramétrer un profil de notification par e-mail</span><span class="sxs-lookup"><span data-stu-id="928aa-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="928aa-104">Cette rubrique décrit comment créer un profil de notification par e-mail dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="928aa-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="928aa-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="928aa-105">Overview</span></span>

<span data-ttu-id="928aa-106">Avant de créer des canaux, vous souhaiterez configurer un profil pour vous assurer que les notifications par e-mail peuvent être envoyées pour divers événements, tels que la création de commande, l'état d'expédition de la commande et l'échec du paiement.</span><span class="sxs-lookup"><span data-stu-id="928aa-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="928aa-107">Pour plus d'informations sur la configuration de l'e-mail, consultez la rubrique [Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="928aa-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="928aa-108">Créer un profil de notification par e-mail</span><span class="sxs-lookup"><span data-stu-id="928aa-108">Create an email notification profile</span></span>

<span data-ttu-id="928aa-109">Pour créer un profil de notification par e-mail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="928aa-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="928aa-110">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Profil de notification par e-mail de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="928aa-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="928aa-111">Dans le volet Actions, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="928aa-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="928aa-112">Dans le champ **Profil de notification par e-mail**, entrez un nom pour identifier le profil.</span><span class="sxs-lookup"><span data-stu-id="928aa-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="928aa-113">Entrez une description pertinente dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="928aa-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="928aa-114">Paramétrer le commutateur **Actif** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="928aa-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="928aa-115">Créer un modèle d'e-mail</span><span class="sxs-lookup"><span data-stu-id="928aa-115">Create an email template</span></span>

<span data-ttu-id="928aa-116">Avant de pouvoir créer une notification par e-mail, vous devez créer un modèle de courrier électronique pour l'organisation qui contient les informations d'e-mail de l'expéditeur et le modèle d'e-mail.</span><span class="sxs-lookup"><span data-stu-id="928aa-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="928aa-117">Pour créer un modèle d'e-mail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="928aa-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="928aa-118">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Paramètres \> Modèles d'e-mail pour l'organisation**.</span><span class="sxs-lookup"><span data-stu-id="928aa-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="928aa-119">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="928aa-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="928aa-120">Dans le champ **ID e-mail**, entrez un ID pour vous aider à identifier ce modèle.</span><span class="sxs-lookup"><span data-stu-id="928aa-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="928aa-121">Entrez le nom des expéditeurs dans le champ **Nom des expéditeurs**.</span><span class="sxs-lookup"><span data-stu-id="928aa-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="928aa-122">Entrez une description pertinente dans le champ **Description de l'e-mail**.</span><span class="sxs-lookup"><span data-stu-id="928aa-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="928aa-123">Dans le champ **E-mail de l'expéditeur**, entrez l'adresse e-mail des expéditeurs.</span><span class="sxs-lookup"><span data-stu-id="928aa-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="928aa-124">Dans la section **Général**, remplissez toutes les informations facultatives nécessaires (telles que la priorité des e-mails).</span><span class="sxs-lookup"><span data-stu-id="928aa-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="928aa-125">Élargissez la section **Contenu du message électronique** et sélectionnez **Nouveau** pour créer le contenu du modèle.</span><span class="sxs-lookup"><span data-stu-id="928aa-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="928aa-126">Pour chaque élément de contenu, sélectionnez la langue et indiquez la ligne d'objet de l'e-mail.</span><span class="sxs-lookup"><span data-stu-id="928aa-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="928aa-127">Si l'e-mail va avoir un corps, assurez-vous que la case **A un corps** est cochée.</span><span class="sxs-lookup"><span data-stu-id="928aa-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="928aa-128">Dans le volet Actions, sélectionnez **Message électronique** pour fournir un modèle de corps d'e-mail.</span><span class="sxs-lookup"><span data-stu-id="928aa-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="928aa-129">L'image suivante montre quelques exemples de paramètres de modèle d'e-mail.</span><span class="sxs-lookup"><span data-stu-id="928aa-129">The following image shows some example email template settings.</span></span>

![Paramètres du modèle d'e-mail](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="928aa-131">Créer un événement d'e-mail</span><span class="sxs-lookup"><span data-stu-id="928aa-131">Create an email event</span></span>

<span data-ttu-id="928aa-132">Pour créer un événement d'e-mail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="928aa-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="928aa-133">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Profil de notification par e-mail de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="928aa-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="928aa-134">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="928aa-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="928aa-135">Sélectionnez le modèle d'e-mail dans la liste déroulante **ID e-mail**.</span><span class="sxs-lookup"><span data-stu-id="928aa-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="928aa-136">Sélectionnez le bon **Type de notification par e-mail** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="928aa-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="928aa-137">Cochez la case **Actif**.</span><span class="sxs-lookup"><span data-stu-id="928aa-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="928aa-138">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="928aa-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="928aa-139">L'image suivante montre quelques exemples de notification d'événements.</span><span class="sxs-lookup"><span data-stu-id="928aa-139">The following image shows some example event notification settings.</span></span>

![Paramètres de notification d'événements](media/email-notification-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="928aa-141">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="928aa-141">Additional resources</span></span>

[<span data-ttu-id="928aa-142">Configurer et envoyer un e-mail</span><span class="sxs-lookup"><span data-stu-id="928aa-142">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="928aa-143">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="928aa-143">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="928aa-144">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="928aa-144">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="928aa-145">Vue d'ensemble des organisations et des hiérarchies d'organisation</span><span class="sxs-lookup"><span data-stu-id="928aa-145">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
