---
title: Intégration d’une note
description: Cette rubrique décrit l’intégration des données d’une note en double écriture.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: beab7f2fc4fd96ce7a28734d2449445b3b5d4451
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750834"
---
# <a name="note-integration"></a><span data-ttu-id="bcaf3-103">Intégration d’une note</span><span class="sxs-lookup"><span data-stu-id="bcaf3-103">Note integration</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="bcaf3-104">Au cours des processus métier, les utilisateurs de Microsoft Dynamics 365 recueillent souvent des informations sur leurs clients.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-104">During business processes, Microsoft Dynamics 365 users often gather information about their customers.</span></span> <span data-ttu-id="bcaf3-105">Ces informations sont enregistrées sous forme d’activités et de notes.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-105">This information is recorded as activities and notes.</span></span> <span data-ttu-id="bcaf3-106">Cette rubrique décrit l’intégration des données d’une note en double écriture.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-106">This topic describes the integration of note data in dual-write.</span></span>

<span data-ttu-id="bcaf3-107">Les informations client peuvent être classées des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="bcaf3-107">Customer information can be classified in the following ways:</span></span>

+ <span data-ttu-id="bcaf3-108">**Informations exploitables qu’un utilisateur Dynamics 365 gère au nom d’un client** – Par exemple, Contoso (un utilisateur de Dynamics 365) réalise un jeu télévisé.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-108">**Actionable information that a Dynamics 365 user handles on behalf of a customer** – For example, Contoso (a Dynamics 365 user) is conducting a game show.</span></span> <span data-ttu-id="bcaf3-109">L’un des clients de Contoso (un client) souhaite assister au jeu télévisé.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-109">One of Contoso's customers (a customer) wants to attend the game show.</span></span> <span data-ttu-id="bcaf3-110">Le client demande à un employé de Contoso de lui réserver une place dans le jeu télévisé.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-110">The customer asks a Contoso employee to book a slot in the game show for them.</span></span> <span data-ttu-id="bcaf3-111">La réservation a lieu dans le calendrier du participant à l’événement de Contoso.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-111">The booking occurs in Contoso's event attendee's calendar.</span></span>
+ <span data-ttu-id="bcaf3-112">**Informations exploitables pour un utilisateur Dynamics 365** – Par exemple, un client qui achète une unité Surface entre des instructions spéciales indiquant que l’appareil doit être mis dans un emballage cadeau avant la livraison.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-112">**Actionable information for a Dynamics 365 user** – For example, a customer who is purchasing a Surface unit enters special instructions that indicate that the device should be gift wrapped before delivery.</span></span> <span data-ttu-id="bcaf3-113">Ces instructions constituent des informations exploitables qui doivent être gérées par l’employé de Contoso responsable de l’emballage.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-113">These instructions are actionable information that should be handled by the Contoso employee who is responsible for packaging.</span></span>
+ <span data-ttu-id="bcaf3-114">**Informations non exploitables** – Par exemple, un client visite le magasin Contoso et, au cours de sa conversation avec un collaborateur du magasin, exprime son intérêt pour les jeux et accessoires de jeux *Halo*.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-114">**Non-actionable information** – For example, a customer visits the Contoso store and, during their conversation with a store associate, expresses interest in *Halo* games and gaming accessories.</span></span> <span data-ttu-id="bcaf3-115">Le collaborateur du magasin prend note de ces informations.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-115">The store associate makes a note of this information.</span></span> <span data-ttu-id="bcaf3-116">Le moteur de recommandations de produits l’utilise ensuite pour faire des recommandations au client.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-116">The product recommendations engine then uses it to make recommendations to the customer.</span></span>

<span data-ttu-id="bcaf3-117">En général, les informations exploitables sont capturées en tant qu’*activités* dans les applications Finance and Operations et les applications Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-117">In general, actionable information is captured as *activities* in Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="bcaf3-118">En général, les informations non exploitables sont capturées en tant que *notes* dans les applications Finance and Operations et en tant qu’*annotations* dans les applications Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-118">Non-actionable information is captured as *notes* in Finance and Operations apps, and as *annotations* in customer engagement apps.</span></span>

> [!TIP]
> <span data-ttu-id="bcaf3-119">Bien que les notes soient destinées à des informations non exploitables, les applications ne vous empêcheront pas de les utiliser pour stocker et gérer des informations exploitables si vous souhaitez les utiliser de cette manière.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-119">Although notes are intended for non-actionable information, the apps won't prevent you from using them to store and handle actionable information if you want to use them in that way.</span></span>

<span data-ttu-id="bcaf3-120">Microsoft publie actuellement des fonctionnalités pour l’intégration des notes.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-120">Microsoft is currently releasing functionality for note integration.</span></span> <span data-ttu-id="bcaf3-121">(La fonctionnalité d’intégration des activités sera publiée ultérieurement.) L’intégration des notes est disponible pour les clients, les fournisseurs, les commandes client et les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-121">(Functionality for activity integration will be released later.) Note integration is available for customers, vendors, sales orders, and purchase orders.</span></span>

## <a name="create-a-note-in-a-customer-engagement-app"></a><span data-ttu-id="bcaf3-122">Créer une note dans une application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="bcaf3-122">Create a note in a customer engagement app</span></span>

<span data-ttu-id="bcaf3-123">Pour créer une note dans une application Customer Engagement, puis la synchroniser avec une application Finance and Operations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-123">To create a note in a customer engagement app and then sync it to a Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="bcaf3-124">Dans l’application Customer Engagement, ouvrez l’enregistrement de compte d’un client.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-124">In the customer engagement app, open the account record for a customer.</span></span>
2. <span data-ttu-id="bcaf3-125">Dans le volet **Chronologie**, sélectionnez le signe plus (**+**), puis sélectionnez **Note** pour créer une note.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-125">In the **Timeline** pane, select the plus sign (**+**), and then select **Note** to create a note.</span></span>

    ![Création d’une note dans l’application Customer Engagement](media/notes-ce-1.png)

3. <span data-ttu-id="bcaf3-127">Entrez un nom et une description, puis sélectionnez **Ajouter une note**.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-127">Enter a title and description, and then select **Add note**.</span></span>

    ![Saisie d’un titre et d’une description](media/notes-ce-2.png)

    <span data-ttu-id="bcaf3-129">La nouvelle note est ajoutée à la chronologie du client.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-129">The new note is added to the customer timeline.</span></span>

    ![Nouvelle note sur la chronologie du client](media/notes-ce-3.png)

4. <span data-ttu-id="bcaf3-131">Connectez-vous à l’application Finance and Operations et ouvrez le même enregistrement client.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-131">Sign in to the Finance and Operations app, and open the same customer record.</span></span> <span data-ttu-id="bcaf3-132">Notez que le bouton **Pièces jointes** (symbole de trombone) dans le coin supérieur droit indique que l’enregistrement a une pièce jointe.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-132">Notice that the **Attachments** button (paperclip symbol) in the upper-right corner indicates that the record has an attachment.</span></span>

    ![Notification concernant une pièce jointe](media/notes-ce-4.png)

5. <span data-ttu-id="bcaf3-134">Sélectionnez le bouton **Pièces jointes** pour ouvrir la page **Pièces jointes**.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-134">Select the **Attachments** button to open the **Attachments** page.</span></span> <span data-ttu-id="bcaf3-135">Vous devriez trouver la note que vous avez créée dans l’application Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-135">You should find the note that you created in the customer engagement app.</span></span>

    ![Note de l’application Customer Engagement](media/notes-ce-5.png)

<span data-ttu-id="bcaf3-137">Toutes les mises à jour de la note sont synchronisées entre l’application Finance and Operations et l’application Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-137">Any updates to the note are synced back and forth between the Finance and Operations app and the customer engagement app.</span></span>

## <a name="create-a-note-in-a-finance-and-operations-app"></a><span data-ttu-id="bcaf3-138">Créer une note dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bcaf3-138">Create a note in a Finance and Operations app</span></span>

<span data-ttu-id="bcaf3-139">Vous pouvez également créer une note dans une application Finance and Operations, puis la synchroniser avec une application Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-139">You can also create a note in a Finance and Operations app, and it will be synced to a customer engagement app.</span></span>

<span data-ttu-id="bcaf3-140">Pour créer une note dans une application Finance and Operations, puis la synchroniser avec une application Customer Engagement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-140">To create a note in a Finance and Operations app and then sync it to a customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="bcaf3-141">Dans l’application Finance and Operations, sur la page **Pièces jointes**, sélectionnez **Nouveau** \> **Note**.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-141">In the Finance and Operations app, on the **Attachments** page, select **New** \> **Note**.</span></span>

    ![Création d’une note dans l’application Finance and Operations](media/notes-fo-1.png)

2. <span data-ttu-id="bcaf3-143">Entrez un titre et des instructions brèves, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-143">Enter a title and a brief set of instructions, and then select **Save**.</span></span>

    ![Saisie d’un titre et d’instructions](media/notes-fo-2.png)

3. <span data-ttu-id="bcaf3-145">Dans l’application Customer Engagement, mettez à jour l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-145">In the customer engagement app, update the record.</span></span> <span data-ttu-id="bcaf3-146">La nouvelle note doit figurer sur la chronologie.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-146">You should find the new note on the timeline.</span></span>

    ![Nouvelle note sur la chronologie dans l’application Customer Engagement](media/notes-fo-3.png)

<span data-ttu-id="bcaf3-148">Vous pouvez classer une note comme interne ou externe.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-148">You can classify a note as either internal or external.</span></span>

- <span data-ttu-id="bcaf3-149">Dans l’application Finance and Operations, sur la page **Pièces jointes**, ouvrez la note, puis, dans le champ **Restriction**, sélectionnez **Interne** ou **Externe**.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-149">In the Finance and Operations app, on the **Attachments** page, open the note, and then, in the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Champ de restriction](media/notes-fo-4.png)

<span data-ttu-id="bcaf3-151">Vous pouvez également créer une URL.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-151">You can also create a URL.</span></span>

1. <span data-ttu-id="bcaf3-152">Dans l’application Finance and Operations, sur la page **Pièces jointes**, sélectionnez **Nouveau** \> **URL**.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-152">In the Finance and Operations app, on the **Attachments** page, select **New** \> **URL**.</span></span>
2. <span data-ttu-id="bcaf3-153">Entrez un titre et l’URL.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-153">Enter a title and the URL.</span></span>
3. <span data-ttu-id="bcaf3-154">Dans le champ **Restriction**, sélectionnez **Interne** ou **Externe**.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-154">In the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Création d’une URL dans l’application Finance and Operations](media/notes-fo-5.png)

4. <span data-ttu-id="bcaf3-156">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-156">Select **Save**.</span></span>

    <span data-ttu-id="bcaf3-157">Étant donné que les applications Customer Engagement n’ont pas de type d’URL, l’URL est intégrée à la double écriture en tant que note.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-157">Because customer engagement apps don't have a URL type, the URL is integrated with dual-write as a note.</span></span>

    ![URL apparaissant en tant que note dans l’application Customer Engagement](media/notes-ce-6.png)

> [!NOTE]
> <span data-ttu-id="bcaf3-159">Les pièces jointes ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-159">File attachments aren't supported.</span></span>

## <a name="templates"></a><span data-ttu-id="bcaf3-160">Modèles</span><span class="sxs-lookup"><span data-stu-id="bcaf3-160">Templates</span></span>

<span data-ttu-id="bcaf3-161">L’intégration de notes comprend un ensemble de mappages de tables qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-161">Note integration includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="bcaf3-162">Application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bcaf3-162">Finance and Operations app</span></span> | <span data-ttu-id="bcaf3-163">Application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="bcaf3-163">Customer engagement app</span></span> | <span data-ttu-id="bcaf3-164">Description</span><span class="sxs-lookup"><span data-stu-id="bcaf3-164">Description</span></span> |
|----------------------------|-------------------------|-------------|
| [<span data-ttu-id="bcaf3-165">Pièces jointes clients</span><span class="sxs-lookup"><span data-stu-id="bcaf3-165">Customer Attachments</span></span>](mapping-reference.md#230) | <span data-ttu-id="bcaf3-166">Annotations</span><span class="sxs-lookup"><span data-stu-id="bcaf3-166">Annotations</span></span> | <span data-ttu-id="bcaf3-167">Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux clients (pour les organisations et les personnes).</span><span class="sxs-lookup"><span data-stu-id="bcaf3-167">Businesses that use plain text and URLs to capture customer-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="bcaf3-168">Pièces jointes de document fournisseur</span><span class="sxs-lookup"><span data-stu-id="bcaf3-168">Vendor document attachments</span></span>](mapping-reference.md#231) | <span data-ttu-id="bcaf3-169">Annotations</span><span class="sxs-lookup"><span data-stu-id="bcaf3-169">Annotations</span></span> | <span data-ttu-id="bcaf3-170">Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux fournisseurs (pour les organisations et les personnes).</span><span class="sxs-lookup"><span data-stu-id="bcaf3-170">Businesses that use plain text and URLs to capture vendor-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="bcaf3-171">Pièces jointes des documents d’en-tête de commande client</span><span class="sxs-lookup"><span data-stu-id="bcaf3-171">Sales order header document attachments</span></span>](mapping-reference.md#229) | <span data-ttu-id="bcaf3-172">Annotations</span><span class="sxs-lookup"><span data-stu-id="bcaf3-172">Annotations</span></span> | <span data-ttu-id="bcaf3-173">Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux commandes client.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-173">Businesses that use plain text and URLs to capture sales order–specific information.</span></span> |
| [<span data-ttu-id="bcaf3-174">Pièces jointes des documents d’en-tête de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="bcaf3-174">Purchase order header document attachments</span></span>](mapping-reference.md#232) | <span data-ttu-id="bcaf3-175">Annotations</span><span class="sxs-lookup"><span data-stu-id="bcaf3-175">Annotations</span></span> | <span data-ttu-id="bcaf3-176">Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="bcaf3-176">Businesses that use plain text and URLs to capture purchase order–specific information.</span></span> |

<span data-ttu-id="bcaf3-177">Pour plus d’informations, voir [Référence de mappage en double écriture](mapping-reference.md).</span><span class="sxs-lookup"><span data-stu-id="bcaf3-177">For more information, see [Dual-write mapping reference](mapping-reference.md).</span></span>
