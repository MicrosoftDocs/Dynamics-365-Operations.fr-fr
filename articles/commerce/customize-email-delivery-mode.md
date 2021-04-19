---
title: Personnalisez les e-mails transactionnels par mode de livraison
description: Cette rubrique décrit comment configurer des modèles d’e-mail personnalisés pour des types de notification et des modes de livraison spécifiques dans Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 411e694b33e0443a336f6a8cdad78714630e4bf3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799371"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a><span data-ttu-id="c0895-103">Personnaliser les e-mails transactionnels par mode de livraison</span><span class="sxs-lookup"><span data-stu-id="c0895-103">Customize transactional emails by mode of delivery</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c0895-104">Cette rubrique décrit comment configurer des modèles d’e-mail personnalisés pour des types de notification et des modes de livraison spécifiques dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0895-104">This topic describes how to set up custom email templates for specific notification types and modes of delivery in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c0895-105">Les e-mails transactionnels peuvent désormais être personnalisés pour une combinaison d’un type de notification (par exemple, **Commande créée**, **Commande conditionnée**, ou **Commande facturée**) et un mode de livraison (par exemple, la nuit, le retrait en magasin ou le retrait à un point-relais).</span><span class="sxs-lookup"><span data-stu-id="c0895-105">Transactional emails can now be customized for a combination of a notification type (for example, **Order created**, **Order packed**, or **Order invoiced**) and a mode of delivery (for example, overnight, in-store pickup, or curbside pickup).</span></span> <span data-ttu-id="c0895-106">Les e-mails transactionnels personnalisés permettent aux détaillants de proposer à leurs clients des expériences de traitement adaptées au mode de livraison de la commande.</span><span class="sxs-lookup"><span data-stu-id="c0895-106">Custom transactional emails let retailers provide their customers order with fulfillment experiences that are tailored to the order's mode of delivery.</span></span> <span data-ttu-id="c0895-107">Par exemple, l’événement "commande conditionnée" peut être personnalisé de manière à fournir des instructions de retrait en point-relais pour les clients qui choisissent ce mode de retrait.</span><span class="sxs-lookup"><span data-stu-id="c0895-107">For example, the "order packed" event can be customized so that it provides curbside pickup instructions for customers who choose curbside pickup.</span></span> <span data-ttu-id="c0895-108">Il peut également fournir des informations sur le transporteur et la livraison aux clients qui choisissent de faire expédier leur commande.</span><span class="sxs-lookup"><span data-stu-id="c0895-108">Alternatively, it can provide shipping carrier and delivery information for customers who choose to have their order shipped.</span></span>

> [!NOTE]
> <span data-ttu-id="c0895-109">Pour utiliser la fonctionnalité des e-mails transactionnels personnalisés, vous devez d’abord activer la fonctionnalité **Personnaliser les modèles d’e-mails transactionnels par mode de livraison** en allant à **Espaces de travail \> Gestion des fonctionnalités** au siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0895-109">To use the functionality for customized transactional emails, you first must turn on the **Customize transactional email templates by mode of delivery** feature by going to **Workspaces \> Feature management** in Commerce headquarters.</span></span>

<span data-ttu-id="c0895-110">Les e-mails peuvent être personnalisés par mode de livraison pour les types de notification suivants :</span><span class="sxs-lookup"><span data-stu-id="c0895-110">Emails can be customized by mode of delivery for the following notification types:</span></span>

- <span data-ttu-id="c0895-111">**Annulation de la commande** – Ce type de notification par e-mail est nouveau.</span><span class="sxs-lookup"><span data-stu-id="c0895-111">**Order cancellation** – This email notification type is new.</span></span>
- <span data-ttu-id="c0895-112">**Commande créée**</span><span class="sxs-lookup"><span data-stu-id="c0895-112">**Order created**</span></span>
- <span data-ttu-id="c0895-113">**Commande confirmée**</span><span class="sxs-lookup"><span data-stu-id="c0895-113">**Order confirmed**</span></span>
- <span data-ttu-id="c0895-114">**Commande facturée** – Ce type de notification par e-mail est nouveau.</span><span class="sxs-lookup"><span data-stu-id="c0895-114">**Order invoiced** – This email notification type is new.</span></span> <span data-ttu-id="c0895-115">Il peut être utilisé à la place du type de notification **Commande expédiée** qui enverra une notification pour tout événement de facturation qui a un mode de livraison expédié (pas un retrait, à emporter ou un mode de livraison électronique).</span><span class="sxs-lookup"><span data-stu-id="c0895-115">It can be used instead of the **Order shipped** notification type that will send a notification for any invoice event that has a shipped mode of delivery (not a pickup, carry out, or electronic mode of delivery).</span></span>
- <span data-ttu-id="c0895-116">**Commande retirée**</span><span class="sxs-lookup"><span data-stu-id="c0895-116">**Order picked**</span></span>
- <span data-ttu-id="c0895-117">**Commande conditionnée**</span><span class="sxs-lookup"><span data-stu-id="c0895-117">**Order packed**</span></span>
- <span data-ttu-id="c0895-118">**Commande prête pour le retrait** – Ce type de notification ne peut être personnalisé par mode de livraison que si la fonctionnalité **Prise en charge de plusieurs modes de livraison par retrait** est activée.</span><span class="sxs-lookup"><span data-stu-id="c0895-118">**Order ready for pickup** – This notification type can be customized by mode of delivery only if the **Support for multiple pickup delivery modes** feature is turned on.</span></span> <span data-ttu-id="c0895-119">Dans ce cas, ce type de notification est fonctionnellement équivalent au type de notification **Commande conditionnée**.</span><span class="sxs-lookup"><span data-stu-id="c0895-119">In that case, this notification type is functionally equivalent to the **Order packed** notification type.</span></span>
- <span data-ttu-id="c0895-120">**Échec du paiement**</span><span class="sxs-lookup"><span data-stu-id="c0895-120">**Payment failed**</span></span>
- <span data-ttu-id="c0895-121">**Ordre de remplacement créé**</span><span class="sxs-lookup"><span data-stu-id="c0895-121">**Replacement order created**</span></span>

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a><span data-ttu-id="c0895-122">Configurer des modèles d’e-mails pour des modes de livraison spécifiques</span><span class="sxs-lookup"><span data-stu-id="c0895-122">Configure email templates for specific modes of delivery</span></span>

<span data-ttu-id="c0895-123">Pour cette procédure, on suppose que vous avez déjà créé vos modèles d’e-mails personnalisés et les avez ajoutés à la page **Modèles d’e-mail d’organisation**.</span><span class="sxs-lookup"><span data-stu-id="c0895-123">For this procedure, the assumption is that you've already created your new, custom email templates and added them to the **Organization email templates** page.</span></span> <span data-ttu-id="c0895-124">Pour plus d’informations sur la création et le chargement de modèles d’e-mail, voir [Créer des modèles d’e-mail pour les événements transactionnels](email-templates-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="c0895-124">For information about how to create and upload email templates, see [Create email templates for transactional events](email-templates-transactions.md).</span></span>

<span data-ttu-id="c0895-125">Pour configurer des modèles d’e-mail pour des modes de livraison spécifiques au siège de Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c0895-125">To configure email templates for specific modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c0895-126">Aller à **Profil de notification par e-mail Commerce**.</span><span class="sxs-lookup"><span data-stu-id="c0895-126">Go to **Commerce email notification profile**.</span></span>
1. <span data-ttu-id="c0895-127">Sous **Paramètres de notification des événements de vente au détail**, sélectionnez un type de notification existant.</span><span class="sxs-lookup"><span data-stu-id="c0895-127">Under **Retail event notification settings**, select an existing notification type.</span></span>
1. <span data-ttu-id="c0895-128">Pendant que le type de notification est toujours sélectionné, sélectionnez **Configurer les modes de livraison**.</span><span class="sxs-lookup"><span data-stu-id="c0895-128">While the notification type is still selected, select **Configure modes of delivery**.</span></span>
1. <span data-ttu-id="c0895-129">Dans la boîte de dialogue **Modes de livraison**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c0895-129">In the **Modes of delivery** dialog box, select **New**.</span></span>
1. <span data-ttu-id="c0895-130">Dans la nouvelle ligne du champ **Mode de livraison**, sélectionnez un mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="c0895-130">In the new row, in the **Mode of delivery** field, select a mode of delivery.</span></span>
1. <span data-ttu-id="c0895-131">Dans le champ **ID e-mail**, sélectionnez le modèle d’e-mail à mapper au mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="c0895-131">In the **Email ID** field, select the email template to map to the mode of delivery.</span></span>
1. <span data-ttu-id="c0895-132">Cochez la case **Actif**.</span><span class="sxs-lookup"><span data-stu-id="c0895-132">Select the **Active** check box.</span></span>
1. <span data-ttu-id="c0895-133">Répétez les étapes 4 à 7 pour ajouter d’autres modes de livraison.</span><span class="sxs-lookup"><span data-stu-id="c0895-133">Repeat steps 4 through 7 to add more modes of delivery.</span></span>
1. <span data-ttu-id="c0895-134">Lorsque vous avez terminé, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0895-134">When you've finished, select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="c0895-135">Lorsque plusieurs modes de livraison sont présents sur les lignes d’une commande client, le modèle par défaut est utilisé.</span><span class="sxs-lookup"><span data-stu-id="c0895-135">When more than one mode of delivery is present across lines in a sales order, the default template will be used.</span></span> <span data-ttu-id="c0895-136">Le modèle par défaut est le modèle qui est mappé au type de notification sur la page **Profil de notification par e-mail Commerce**.</span><span class="sxs-lookup"><span data-stu-id="c0895-136">The default template is the template that is mapped to the notification type on the **Commerce email notification profile** page.</span></span>
> - <span data-ttu-id="c0895-137">Si une commande client a un mode de livraison qui n’a pas été configuré pour un modèle d’e-mail personnalisé, le modèle d’e-mail par défaut sera utilisé.</span><span class="sxs-lookup"><span data-stu-id="c0895-137">If a sales order has a mode of delivery that hasn't been configured for a custom email template, the default email template will be used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c0895-138">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c0895-138">Additional resources</span></span>

[<span data-ttu-id="c0895-139">Créer des commandes de centre d’appels</span><span class="sxs-lookup"><span data-stu-id="c0895-139">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="c0895-140">Modifier le mode de livraison dans le PDV</span><span class="sxs-lookup"><span data-stu-id="c0895-140">Change mode of delivery in POS</span></span>](pos-change-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]