---
title: Approbations de factures par téléphone portable
description: Cette rubrique est destinée à fournir une approche pratique pour concevoir des scénarios mobiles en prenant les approbations de facture de fournisseur pour mobile en tant que cas d'utilisation.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 956c866a6b39e2a81f085910e00d2bfe8683829c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177796"
---
# <a name="mobile-invoice-approvals"></a><span data-ttu-id="0c50b-103">Approbations de factures par téléphone portable</span><span class="sxs-lookup"><span data-stu-id="0c50b-103">Mobile invoice approvals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0c50b-104">Les fonctionnalités mobiles permettent aux entreprises de créer des expériences mobiles.</span><span class="sxs-lookup"><span data-stu-id="0c50b-104">Mobile capabilities let a business user design mobile experiences.</span></span> <span data-ttu-id="0c50b-105">Pour les scénarios avancés, la plateforme permet également aux développeurs d'étendre les capacités comme ils le désirent.</span><span class="sxs-lookup"><span data-stu-id="0c50b-105">For advanced scenarios, the platform also lets developers extend the capabilities as they desire.</span></span> <span data-ttu-id="0c50b-106">Le moyen le plus efficace d'apprendre quelques-uns des nouveaux concepts sur la fonction mobile est de passer en revue le processus de conception de quelques scénarios.</span><span class="sxs-lookup"><span data-stu-id="0c50b-106">The most effective way to learn some of the new concepts on mobile is to go through the process of designing a few scenarios.</span></span> <span data-ttu-id="0c50b-107">Cette rubrique est destinée à fournir une approche pratique pour concevoir des scénarios mobiles en prenant les approbations de facture de fournisseur pour mobile en tant que cas d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="0c50b-107">This topic is intended to provide a practical approach to designing mobile scenarios by taking vendor invoice approvals for mobile as a use case.</span></span> <span data-ttu-id="0c50b-108">Cette rubrique doit vous aider à créer d'autres variations de scénarios et peut également être appliquée à d'autres scénarios non liés aux factures fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0c50b-108">This topic should help you design other variations of the scenarios and can also be applied to other scenarios that aren’t related to vendor invoices.</span></span>

<a name="prerequisites"></a><span data-ttu-id="0c50b-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="0c50b-109">Prerequisites</span></span>
-------------

| <span data-ttu-id="0c50b-110">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="0c50b-110">Prerequisite</span></span>                                                                                            | <span data-ttu-id="0c50b-111">Description</span><span class="sxs-lookup"><span data-stu-id="0c50b-111">Description</span></span>                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0c50b-112">Pré-lecture manuel mobile</span><span class="sxs-lookup"><span data-stu-id="0c50b-112">Mobile handbook pre-read</span></span>                                                                                |[<span data-ttu-id="0c50b-113">Plateforme mobile</span><span class="sxs-lookup"><span data-stu-id="0c50b-113">Mobile platform</span></span>](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| <span data-ttu-id="0c50b-114">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="0c50b-114">Dynamics 365 Finance</span></span>                                                                              | <span data-ttu-id="0c50b-115">Un environnement avec version 1611 et Platform update 3 (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="0c50b-115">An environment that has version 1611 and Platform update 3 (November 2016)</span></span>                   |
| <span data-ttu-id="0c50b-116">Installez le correctif KB 3204341.</span><span class="sxs-lookup"><span data-stu-id="0c50b-116">Install hotfix KB 3204341.</span></span>                                                                              | <span data-ttu-id="0c50b-117">L'enregistreur de tâches peut enregistrer de manière erronée deux commandes Fermer pour les boîtes de dialogue déroulantes, incluses dans Platform Update 3 (mise à jour novembre 2016).</span><span class="sxs-lookup"><span data-stu-id="0c50b-117">Task recorder can erroneously record two Close commands for dropdown dialogs; this is included in Platform update 3 (November 2016 update).</span></span> |
| <span data-ttu-id="0c50b-118">Installez le correctif KB 3207800.</span><span class="sxs-lookup"><span data-stu-id="0c50b-118">Install hotfix KB 3207800.</span></span>                                                                              | <span data-ttu-id="0c50b-119">Ce correctif permet d'afficher les pièces jointes sur le client mobile, ce qui est inclus dans Platform Update 3 (mise à jour de novembre 2016).</span><span class="sxs-lookup"><span data-stu-id="0c50b-119">This hotfix enables attachments to be viewed on the mobile client; this is included in Platform update 3 (November 2016 update).</span></span>           |
| <span data-ttu-id="0c50b-120">Installez le correctif KB 3208224.</span><span class="sxs-lookup"><span data-stu-id="0c50b-120">Install hotfix KB 3208224.</span></span>                                                                              | <span data-ttu-id="0c50b-121">Le code d'application pour la demande d'approbation de facture fournisseur mobile est inclus dans la version 7.0.1 (mai 2016).</span><span class="sxs-lookup"><span data-stu-id="0c50b-121">Application code for the mobile vendor invoice approval application; this is included in version 7.0.1 (May 2016).</span></span>                          |
| <span data-ttu-id="0c50b-122">Périphérique Android ou iOS ou Windows doté de l'application mobile installée.</span><span class="sxs-lookup"><span data-stu-id="0c50b-122">An Android or iOS or a Windows device that has the mobile app installed.</span></span> | <span data-ttu-id="0c50b-123">Recherche de l'application dans le magasin d'application adéquat.</span><span class="sxs-lookup"><span data-stu-id="0c50b-123">Search for the app in the appropriate app store.</span></span>                                                                                                                     |

## <a name="introduction"></a><span data-ttu-id="0c50b-124">Introduction</span><span class="sxs-lookup"><span data-stu-id="0c50b-124">Introduction</span></span>
<span data-ttu-id="0c50b-125">Les approbations mobiles pour les factures fournisseur requièrent les trois correctifs mentionnés dans la section « Conditions préalables ».</span><span class="sxs-lookup"><span data-stu-id="0c50b-125">Mobile approvals for vendor invoices require the three hotfixes that are mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="0c50b-126">Ces correctifs ne présentent pas un espace de travail pour les approbations des factures.</span><span class="sxs-lookup"><span data-stu-id="0c50b-126">These hotfixes don’t provide a workspace for the invoice approvals.</span></span> <span data-ttu-id="0c50b-127">Pour savoir ce qu'est un espace de travail dans le contexte mobile, lisez le manuel mobile qui est mentionné dans la section « Conditions préalables ».</span><span class="sxs-lookup"><span data-stu-id="0c50b-127">To learn what a workspace is in the context of mobile, read the mobile handbook that is mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="0c50b-128">L'espace de travail des approbations de facture doit être conçu.</span><span class="sxs-lookup"><span data-stu-id="0c50b-128">The invoice approvals workspace must be designed.</span></span> 

<span data-ttu-id="0c50b-129">Chaque organisation orchestre et définit son processus métier pour les factures fournisseur différemment.</span><span class="sxs-lookup"><span data-stu-id="0c50b-129">Every organization orchestrates and defines its business process for vendor invoices differently.</span></span> <span data-ttu-id="0c50b-130">Avant de concevoir une expérience mobile pour les approbations de facture fournisseur, vous devriez considérer les aspects suivants du processus métier.</span><span class="sxs-lookup"><span data-stu-id="0c50b-130">Before you design a mobile experience for vendor invoice approvals, you should consider the following aspects of the business process.</span></span> <span data-ttu-id="0c50b-131">L'idée est d'utiliser ces points de données autant que possible pour optimiser l'expérience utilisateur sur le périphérique.</span><span class="sxs-lookup"><span data-stu-id="0c50b-131">The idea is to use these data points as much as possible to optimize the user experience on the device.</span></span>

-   <span data-ttu-id="0c50b-132">Quels champs de l'en-tête de la facture l'utilisateur souhaitera voir dans l'expérience mobile et dans quel ordre ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-132">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="0c50b-133">Quels champs des lignes de la facture l'utilisateur souhaitera voir dans l'expérience mobile et dans quel ordre ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-133">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="0c50b-134">Combien de lignes de facture y-a-t-il dans une facture ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-134">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="0c50b-135">Appliquez la règle 80-20 ici et effectuez une optimisation pour les 80 %.</span><span class="sxs-lookup"><span data-stu-id="0c50b-135">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span>
-   <span data-ttu-id="0c50b-136">Les utilisateurs souhaiteront-ils voir les répartitions comptables (codage de facture) sur l'appareil mobile pendant les révisions ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-136">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span> <span data-ttu-id="0c50b-137">Si la réponse à la question est Oui, tenez compte des questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c50b-137">If the answer to this question is yes, consider the following questions:</span></span>
    -   <span data-ttu-id="0c50b-138">Combien de répartitions comptables (prix global, taxes, frais, fractionnements, etc.) y-a-t-il pour une ligne de facture ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-138">How many accounting distributions (extended price, sales tax, charges, splits, and so on) are there for an invoice line?</span></span> <span data-ttu-id="0c50b-139">Là aussi, appliquez la règle 80-20.</span><span class="sxs-lookup"><span data-stu-id="0c50b-139">Again, apply the 80-20 rule.</span></span>
    -   <span data-ttu-id="0c50b-140">Les factures ont-elles également les répartitions comptables dans l'en-tête de facture ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-140">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="0c50b-141">Dans ce cas, ces répartitions comptables doivent-elles être disponibles dans le périphérique ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-141">If so, should these accounting distributions be available on the device?</span></span>

> [!NOTE]
> <span data-ttu-id="0c50b-142">Cette rubrique n'explique pas comment modifier les répartitions comptables, car cette fonctionnalité n'est actuellement pas prise en charge pour les scénarios mobiles.</span><span class="sxs-lookup"><span data-stu-id="0c50b-142">This topic doesn’t explain how to edit accounting distributions, because this functionality isn’t currently supported for mobile scenarios.</span></span>

-   <span data-ttu-id="0c50b-143">Les utilisateurs souhaiteront-ils afficher les pièces jointes pour la facture sur le périphérique ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-143">Will users want to see attachments for the invoice on the device?</span></span>

<span data-ttu-id="0c50b-144">La conception de l'expérience mobile pour les approbations des factures peut varier, selon les réponses à ces questions.</span><span class="sxs-lookup"><span data-stu-id="0c50b-144">The design of the mobile experience for invoice approvals will differ, depending on the answers to these questions.</span></span> <span data-ttu-id="0c50b-145">Le but est d'optimiser l'expérience utilisateur pour le processus métier sur la fonction mobile dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="0c50b-145">The objective is to optimize the user experience for the business process on mobile in an organization.</span></span> <span data-ttu-id="0c50b-146">Dans le reste de cette rubrique, nous regarderons deux variations de scénario basées sur les réponses aux questions précédentes.</span><span class="sxs-lookup"><span data-stu-id="0c50b-146">In the rest of this topic, we will look at two scenario variations that are based on different answers to the preceding questions.</span></span> 

<span data-ttu-id="0c50b-147">En général, lorsque vous travaillez avec le Concepteur mobile, veillez à « publier » les modifications pour empêcher la perte des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="0c50b-147">As a general guidance, when working with the mobile designer, make sure to 'publish' the changes to prevent losing the updates.</span></span>

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a><span data-ttu-id="0c50b-148">Conception d'un scénario simple d'approbation des factures pour Contoso</span><span class="sxs-lookup"><span data-stu-id="0c50b-148">Designing a simple invoice approval scenario for Contoso</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c50b-149">Attribut du scénario</span><span class="sxs-lookup"><span data-stu-id="0c50b-149">Scenario attribute</span></span></th>
<th><span data-ttu-id="0c50b-150">Répondre</span><span class="sxs-lookup"><span data-stu-id="0c50b-150">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0c50b-151">Quels champs de l'en-tête de la facture l'utilisateur souhaitera voir dans l'expérience mobile et dans quel ordre ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-151">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="0c50b-152">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="0c50b-152">Vendor name</span></span></li>
<li><span data-ttu-id="0c50b-153">Total de la facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-153">Invoice total</span></span></li>
<li><span data-ttu-id="0c50b-154">Compte de facturation</span><span class="sxs-lookup"><span data-stu-id="0c50b-154">Invoice account</span></span></li>
<li><span data-ttu-id="0c50b-155">Numéro de facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-155">Invoice number</span></span></li>
<li><span data-ttu-id="0c50b-156">Date de facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-156">Invoice date</span></span></li>
<li><span data-ttu-id="0c50b-157">Description de la facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-157">Invoice description</span></span></li>
<li><span data-ttu-id="0c50b-158">Date d'échéance</span><span class="sxs-lookup"><span data-stu-id="0c50b-158">Due date</span></span></li>
<li><span data-ttu-id="0c50b-159">Devise de facturation</span><span class="sxs-lookup"><span data-stu-id="0c50b-159">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0c50b-160">Quels champs des lignes de la facture l'utilisateur souhaitera voir dans l'expérience mobile et dans quel ordre ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-160">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="0c50b-161">Catégorie d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="0c50b-161">Procurement category</span></span></li>
<li><span data-ttu-id="0c50b-162">Quantité</span><span class="sxs-lookup"><span data-stu-id="0c50b-162">Quantity</span></span></li>
<li><span data-ttu-id="0c50b-163">Prix unitaire</span><span class="sxs-lookup"><span data-stu-id="0c50b-163">Unit price</span></span></li>
<li><span data-ttu-id="0c50b-164">Montant net de ligne</span><span class="sxs-lookup"><span data-stu-id="0c50b-164">Line net amount</span></span></li>
<li><span data-ttu-id="0c50b-165">Montant des honoraires</span><span class="sxs-lookup"><span data-stu-id="0c50b-165">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0c50b-166">Combien de lignes de facture y-a-t-il dans une facture ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-166">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="0c50b-167">Appliquez la règle 80-20 ici et effectuez une optimisation pour les 80 %.</span><span class="sxs-lookup"><span data-stu-id="0c50b-167">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="0c50b-168">1</span><span class="sxs-lookup"><span data-stu-id="0c50b-168">1</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0c50b-169">Les utilisateurs souhaiteront-ils voir les répartitions comptables (codage de facture) sur l'appareil mobile pendant les révisions ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-169">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="0c50b-170">Oui</span><span class="sxs-lookup"><span data-stu-id="0c50b-170">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0c50b-171">Combien de répartitions comptables (prix global, taxes, frais, etc.) y-a-t-il pour une ligne de facture ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-171">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="0c50b-172">Là aussi, appliquez la règle 80-20.</span><span class="sxs-lookup"><span data-stu-id="0c50b-172">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="0c50b-173">Prix global : 2 Taxe : 0 Frais : 0</span><span class="sxs-lookup"><span data-stu-id="0c50b-173">Extended price: 2 Sales tax: 0 Charges: 0</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0c50b-174">Les factures ont-elles également les répartitions comptables dans l'en-tête de facture ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-174">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="0c50b-175">Dans ce cas, ces répartitions comptables doivent-elles être disponibles dans le périphérique ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-175">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="0c50b-176">Non utilisé</span><span class="sxs-lookup"><span data-stu-id="0c50b-176">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0c50b-177">Les utilisateurs souhaiteront-ils afficher les pièces jointes pour la facture sur le périphérique ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-177">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="0c50b-178">Oui</span><span class="sxs-lookup"><span data-stu-id="0c50b-178">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a><span data-ttu-id="0c50b-179">Créer l'espace de travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-179">Create the workspace</span></span>

1.  <span data-ttu-id="0c50b-180">Dans un navigateur, connectez-vous à l'application.</span><span class="sxs-lookup"><span data-stu-id="0c50b-180">In a browser, and sign in to the application.</span></span>
2.  <span data-ttu-id="0c50b-181">Après vous être connecté, ajoutez **&mode=mobile** à l'URL comme indiqué dans l'exemple suivant, puis rafraîchissez la page : https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span><span class="sxs-lookup"><span data-stu-id="0c50b-181">After you’ve signed in, append **&mode=mobile** to the URL as shown in the following example, and refresh the page: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span></span>
3.  <span data-ttu-id="0c50b-182">Cliquez sur le bouton **Paramètres** (engrenage) dans la partie supérieure droite de la page, puis cliquez sur **Application mobile**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-182">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**.</span></span> <span data-ttu-id="0c50b-183">Le Concepteur d'application mobile doit s'afficher, ainsi que l'Enregistreur de tâches.</span><span class="sxs-lookup"><span data-stu-id="0c50b-183">The mobile app designer must show up just as Task recorder shows up.</span></span>
4.  <span data-ttu-id="0c50b-184">Cliquez sur **Ajouter** pour créer un espce de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-184">Click **Add** to create a new workspace.</span></span> <span data-ttu-id="0c50b-185">Pour cet exemple, nommez l'espace de travail **Mes approbations**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-185">For this example, name the workspace **My approvals**.</span></span>
5.  <span data-ttu-id="0c50b-186">Entrez une description.</span><span class="sxs-lookup"><span data-stu-id="0c50b-186">Enter a description.</span></span>
6.  <span data-ttu-id="0c50b-187">Sélectionnez une couleur d'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-187">Select a workspace color.</span></span> <span data-ttu-id="0c50b-188">La couleur de l'espace de travail est utilisée pour le style général des expériences mobiles de cet espace de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-188">The workspace color will be used for the overall style of the mobile experience for this workspace.</span></span>
7.  <span data-ttu-id="0c50b-189">Sélectionnez une icône pour l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-189">Select an icon for the workspace.</span></span>
8.  <span data-ttu-id="0c50b-190">Cliquez sur **Terminé**</span><span class="sxs-lookup"><span data-stu-id="0c50b-190">Click **Done**</span></span>
9.  <span data-ttu-id="0c50b-191">Cliquez sur **Publier l'espace de travail** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="0c50b-191">Click **Publish workspace** to save the changes</span></span>

### <a name="vendor-invoices-assigned-to-me"></a><span data-ttu-id="0c50b-192">Factures fournisseur qui me sont affectées</span><span class="sxs-lookup"><span data-stu-id="0c50b-192">Vendor invoices assigned to me</span></span>

<span data-ttu-id="0c50b-193">La première page mobile que vous devez configurer est la liste des factures affectées à l'utilisateur pour révision.</span><span class="sxs-lookup"><span data-stu-id="0c50b-193">The first mobile page that you should design is the list of invoices that are assigned to the user for review.</span></span> <span data-ttu-id="0c50b-194">Pour concevoir cette page mobile, utilisez la page **VendMobileInvoiceAssignedToMeListPage**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-194">To design this mobile page, use the **VendMobileInvoiceAssignedToMeListPage** page.</span></span> <span data-ttu-id="0c50b-195">Avant de pouvoir exécuter cette procédure, assurez-vous qu'au moins une facture fournisseur vous est affectée à la révision, et que la ligne de facture a les deux répartitions.</span><span class="sxs-lookup"><span data-stu-id="0c50b-195">Before you complete this procedure, make sure that at least one vendor invoice is assigned to you for review, and that the invoice line has two distributions.</span></span> <span data-ttu-id="0c50b-196">Ce paramétrage correspond aux exigences pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="0c50b-196">This setup meets the requirements for this scenario.</span></span>

1.  <span data-ttu-id="0c50b-197">Dans l'URL, remplacez le nom de l'option de menu par **VendMobileInvoiceAssignedToMeListPage** pour ouvrir la version mobile de la page de liste **Factures fournisseur en attente qui me sont affectées** dans le module **Comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-197">In the URL, replace the name of the menu item with **VendMobileInvoiceAssignedToMeListPage** to open the mobile version of the **Pending vendor invoices assigned to me** list page in the **Accounts payable** module.</span></span> <span data-ttu-id="0c50b-198">Selon le nombre de factures que vous avez dans votre système qui vous est affecté, cette page affiche les factures.</span><span class="sxs-lookup"><span data-stu-id="0c50b-198">Depending on the number of invoices that you have in your system assigned to you, this page will show those invoices.</span></span> <span data-ttu-id="0c50b-199">Pour trouver une facture spécifique, vous pouvez utiliser le filtre à gauche.</span><span class="sxs-lookup"><span data-stu-id="0c50b-199">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="0c50b-200">Toutefois, nous n'avons pas besoin d'une facture spécifique pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="0c50b-200">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="0c50b-201">Nous demandons simplement une facture qui vous est attribuée, ce qui vous permettra de concevoir la page mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-201">We just require some invoice assigned to you which is going to allow you to design the mobile page.</span></span> <span data-ttu-id="0c50b-202">Les nouvelles pages disponibles doivent être désignées spécifiquement pour développer les scénarios mobiles pour la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0c50b-202">The new pages that are available have been designed specifically for developing mobile scenarios for vendor invoice.</span></span> <span data-ttu-id="0c50b-203">Par conséquent, vous devez utiliser ces pages.</span><span class="sxs-lookup"><span data-stu-id="0c50b-203">Therefore, you must use these pages.</span></span> <span data-ttu-id="0c50b-204">L'URL doit ressembler à l'adresse suivante, et une fois que vous l'avez entrée, la page affichée dans l'illustration doit apparaître : https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Page de liste des factures fournisseur en attente qui me sont affectées](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span><span class="sxs-lookup"><span data-stu-id="0c50b-204">The URL should resemble the following URL, and after you enter it, the page that is shown in the illustration must appear: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span></span>
2.  <span data-ttu-id="0c50b-205">Cliquez sur le bouton **Paramètres** (engrenage) dans la partie supérieure droite de la page, puis cliquez sur **Application mobile**</span><span class="sxs-lookup"><span data-stu-id="0c50b-205">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
3.  <span data-ttu-id="0c50b-206">Sélectionnez l'espace de travail et cliquez sur **Modifier**</span><span class="sxs-lookup"><span data-stu-id="0c50b-206">Select your workspace and click **Edit**</span></span>
4.  <span data-ttu-id="0c50b-207">Cliquez sur **Ajouter une page** pour créer la première page mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-207">Click **Add page** to create the first mobile page.</span></span>
5.  <span data-ttu-id="0c50b-208">Entrez un nom, par exemple **Mes factures fournisseur**, et une description, par exemple **Factures fournisseur qui me sont affectées pour révision**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-208">Enter a name, such as **My vendor invoices**, and a description, such as **Vendor invoices assigned to me for review**.</span></span>
6.  <span data-ttu-id="0c50b-209">Cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-209">Click **Done**.</span></span>
7.  <span data-ttu-id="0c50b-210">Dans le Concepteur mobile, sous l'onglet **Champs**, cliquez sur **Sélectionner des champs**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-210">In the mobile designer, on the **Fields** tab, click **Select fields**.</span></span> <span data-ttu-id="0c50b-211">Les colonnes de la page de liste doivent ressembler à l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="0c50b-211">The columns on the list page must resemble the following illustration.</span></span> <span data-ttu-id="0c50b-212">[![Colonnes figurant dans les factures fournisseur en attente qui me sont affectées](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span><span class="sxs-lookup"><span data-stu-id="0c50b-212">[![Columns on the Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span></span>
8.  <span data-ttu-id="0c50b-213">Ajoutez les colonnes voulues de la page de liste à afficher aux utilisateurs de la page mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-213">Add the required columns from the list page that must be shown to the users in the mobile page.</span></span> <span data-ttu-id="0c50b-214">L'ordre dans lequel vous ajoutez est l'ordre dans lequel les champs seront affichés à l'utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="0c50b-214">The order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="0c50b-215">La seule façon de modifier l'ordre des champs consiste à sélectionner tous les champs.</span><span class="sxs-lookup"><span data-stu-id="0c50b-215">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> <span data-ttu-id="0c50b-216">Selon la configuration requise pour ce scénario, les huit champs suivants sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="0c50b-216">Based on the requirements for this scenario, the following eight fields are required.</span></span> <span data-ttu-id="0c50b-217">Cependant, certains utilisateurs pourraient considérer que huit champs constituent trop d'informations sur un périphérique mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-217">However, some users might consider eight fields too much information to have on a mobile device.</span></span> <span data-ttu-id="0c50b-218">Par conséquent, nous afficherons uniquement les champs principaux dans la vue de liste mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-218">Therefore, we will show only the most important fields in the mobile list view.</span></span> <span data-ttu-id="0c50b-219">Les champs restants apparaîtront dans l'affichage détaillé que nous concevrons ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="0c50b-219">The remaining fields will appear in the details view that we will design later.</span></span> <span data-ttu-id="0c50b-220">Dans l'immédiat, nous ajouterons les champs suivants.</span><span class="sxs-lookup"><span data-stu-id="0c50b-220">For now, we will add the following fields.</span></span> <span data-ttu-id="0c50b-221">Cliquez sur le signe plus (**+**) dans les colonnes à ajouter à la page mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-221">Click the plus sign (**+**) in these columns to add to the mobile page.</span></span>
    - <span data-ttu-id="0c50b-222">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="0c50b-222">Vendor name</span></span>
    - <span data-ttu-id="0c50b-223">Total de la facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-223">Invoice total</span></span>
    - <span data-ttu-id="0c50b-224">Compte de facturation</span><span class="sxs-lookup"><span data-stu-id="0c50b-224">Invoice account</span></span>
    - <span data-ttu-id="0c50b-225">Numéro de facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-225">Invoice number</span></span>
    - <span data-ttu-id="0c50b-226">Date de facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-226">Invoice date</span></span>

    <span data-ttu-id="0c50b-227">Une fois que les champs sont ajoutés, la page mobile doit ressembler à l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="0c50b-227">After the fields are added, the mobile page must resemble the following illustration.</span></span> 
    <span data-ttu-id="0c50b-228">[![Page après l'ajout des champs](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span><span class="sxs-lookup"><span data-stu-id="0c50b-228">[![Page after fields are added](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span></span>
9.  <span data-ttu-id="0c50b-229">Vous devez également ajouter les colonnes suivantes maintenant, de manière à ce que nous puissions activer les actions de workflow ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="0c50b-229">You must also add the following columns now, so that we can enable workflow actions later.</span></span>
    - <span data-ttu-id="0c50b-230">Afficher la tâche de fin</span><span class="sxs-lookup"><span data-stu-id="0c50b-230">Show complete task</span></span>
    - <span data-ttu-id="0c50b-231">Afficher la tâche de délégation</span><span class="sxs-lookup"><span data-stu-id="0c50b-231">Show delegate task</span></span>
    - <span data-ttu-id="0c50b-232">Afficher la tâche de rappel</span><span class="sxs-lookup"><span data-stu-id="0c50b-232">Show recall task</span></span>
    - <span data-ttu-id="0c50b-233">Afficher la tâche de rejet</span><span class="sxs-lookup"><span data-stu-id="0c50b-233">Show reject task</span></span>
    - <span data-ttu-id="0c50b-234">Afficher la tâche d'exécution de la demande</span><span class="sxs-lookup"><span data-stu-id="0c50b-234">Show request completion task</span></span>
    - <span data-ttu-id="0c50b-235">Afficher la tâche de resoumission</span><span class="sxs-lookup"><span data-stu-id="0c50b-235">Show resubmit task</span></span>

10. <span data-ttu-id="0c50b-236">Cliquez sur **Terminé** pour quitter le mode d'édition.</span><span class="sxs-lookup"><span data-stu-id="0c50b-236">Click **Done** to exit edit mode.</span></span>
11. <span data-ttu-id="0c50b-237">Cliquez sur **Précédent**, puis **Terminé** pour quitter l'espace de travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-237">Click **Back** and then **Done** to exit the workspace</span></span>
12. <span data-ttu-id="0c50b-238">Cliquez sur **Publier l'espace de travail** pour enregistrer votre travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-238">Click **Publish workspace** to save your work.</span></span>
13. <span data-ttu-id="0c50b-239">Activez **Afficher le nombre total de factures sur la liste des factures fournisseur en attente** dans l'écran Paramètres Comptabilité fournisseur sous **Facture**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-239">Enable **Display invoice total on pending vendor invoices list** in accounts payable parameters form under **Invoice**.</span></span> <span data-ttu-id="0c50b-240">Notez que, uniquement en activant ce paramètre, les totaux de la facture sont calculés pour être affichés dans la page de liste des factures fournisseur en attente.</span><span class="sxs-lookup"><span data-stu-id="0c50b-240">Note that, only by enabling this parameter, invoice totals will be calculated to be displayed on the pending vendor invoices list page.</span></span> <span data-ttu-id="0c50b-241">Il s'agit d'une nouvelle fonctionnalité dans le cadre du correctif logiciel 3208224 de condition préalable.</span><span class="sxs-lookup"><span data-stu-id="0c50b-241">This is a new capability as part of the pre-requisite hot fix 3208224.</span></span>

### <a name="vendor-invoice-details"></a><span data-ttu-id="0c50b-242">Détails de la facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="0c50b-242">Vendor invoice details</span></span>

<span data-ttu-id="0c50b-243">Pour déterminer la page Détails de facture pour la fonction mobile, utilisez la page **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-243">To design the invoice details page for mobile, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="0c50b-244">Notez qu'en fonction du nombre de factures que vous avez dans votre système, cette page affiche l'ancienne facture (la facture qui a été créée préalablement).</span><span class="sxs-lookup"><span data-stu-id="0c50b-244">Note that, depending on the number of invoices that you have in your system, this page shows the oldest invoice (the invoice that was created first).</span></span> <span data-ttu-id="0c50b-245">Pour trouver une facture spécifique, vous pouvez utiliser le filtre à gauche.</span><span class="sxs-lookup"><span data-stu-id="0c50b-245">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="0c50b-246">Toutefois, nous n'avons pas besoin d'une facture spécifique pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="0c50b-246">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="0c50b-247">Nous avons juste besoin de certaines données de factures afin que nous puissions concevoir la page mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-247">We just require some invoice data so that we can design the mobile page.</span></span> <span data-ttu-id="0c50b-248">[![Page Workflow](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span><span class="sxs-lookup"><span data-stu-id="0c50b-248">[![Workflow page](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span></span>

1. <span data-ttu-id="0c50b-249">Dans l'URL, remplacez le nom de l'option de menu par **VendMobileInvoiceHeaderDetails** pour ouvrir l'écran</span><span class="sxs-lookup"><span data-stu-id="0c50b-249">In the URL, replace the name of the menu item with **VendMobileInvoiceHeaderDetails** to open the form</span></span>
2. <span data-ttu-id="0c50b-250">Ouvrez le Concepteur mobile à partir du bouton **Paramètres** (engrenage)</span><span class="sxs-lookup"><span data-stu-id="0c50b-250">Open the mobile designer from the **Settings** (gear) button.</span></span>
3. <span data-ttu-id="0c50b-251">Cliquez sur le bouton **Modifier** pour passer en mode d'édition dans l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-251">Click the **Edit** button to start edit mode in the workspace.</span></span>
4. <span data-ttu-id="0c50b-252">Sélectionnez la page **Mes factures fournisseur** créée précédemment, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-252">Select the **My vendor invoices** page that you created earlier, and then click **Edit**.</span></span>
5. <span data-ttu-id="0c50b-253">Sous l'onglet **Champs**, cliquez sur l'en-tête de colonne **Grille**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-253">On the **Fields** tab, click the **Grid** column heading.</span></span>
6. <span data-ttu-id="0c50b-254">Cliquez sur **Propriétés &gt; Ajouter une page**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-254">Click **Properties &gt; Add page**.</span></span> <span data-ttu-id="0c50b-255">**Remarque :** lorsque vous cliquez sur l'en-tête **Grille** et que vous ajoutez une page, la relation avec la page de détails est établie automatiquement.</span><span class="sxs-lookup"><span data-stu-id="0c50b-255">**Note:** When you click the **Grid** heading and add a page, the relationship with the details page is established automatically.</span></span>
7. <span data-ttu-id="0c50b-256">Entrez un titre de page, tel que **Détails de la facture**, et une description, par exemple **Afficher les détails de l'en-tête et de la ligne**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-256">Enter a page title, such as **Invoice details**, and a description, such as **View invoice header and line details**.</span></span>
8. <span data-ttu-id="0c50b-257">Cliquez sur **Sélectionner des champs**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-257">Click **Select fields**.</span></span> <span data-ttu-id="0c50b-258">Notez que l'ordre dans lequel vous ajoutez est l'ordre dans lequel les champs seront affichés à l'utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="0c50b-258">Note that, the order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="0c50b-259">La seule façon de modifier l'ordre des champs consiste à sélectionner tous les champs.</span><span class="sxs-lookup"><span data-stu-id="0c50b-259">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> 
9. <span data-ttu-id="0c50b-260">Ajoutez les champs suivants à partir de l'en-tête selon la configuration requise pour ce scénario :</span><span class="sxs-lookup"><span data-stu-id="0c50b-260">Add the following fields from the header, based on the requirements for this scenario:</span></span>
   - <span data-ttu-id="0c50b-261">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="0c50b-261">Vendor name</span></span>
   - <span data-ttu-id="0c50b-262">Total de la facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-262">Invoice total</span></span>
   - <span data-ttu-id="0c50b-263">Compte de facturation</span><span class="sxs-lookup"><span data-stu-id="0c50b-263">Invoice account</span></span>
   - <span data-ttu-id="0c50b-264">Numéro de facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-264">Invoice number</span></span>
   - <span data-ttu-id="0c50b-265">Date de facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-265">Invoice date</span></span>
   - <span data-ttu-id="0c50b-266">Description de la facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-266">Invoice description</span></span>
   - <span data-ttu-id="0c50b-267">Date d'échéance</span><span class="sxs-lookup"><span data-stu-id="0c50b-267">Due date</span></span>
   - <span data-ttu-id="0c50b-268">Devise de facturation</span><span class="sxs-lookup"><span data-stu-id="0c50b-268">Invoice currency</span></span>

10. <span data-ttu-id="0c50b-269">Ajoutez les champs suivants à partir de la grille de lignes dans la page :</span><span class="sxs-lookup"><span data-stu-id="0c50b-269">Add the following fields from the lines grid on the page:</span></span>
    - <span data-ttu-id="0c50b-270">Catégorie d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="0c50b-270">Procurement category</span></span>
    - <span data-ttu-id="0c50b-271">Quantité</span><span class="sxs-lookup"><span data-stu-id="0c50b-271">Quantity</span></span>
    - <span data-ttu-id="0c50b-272">Prix unitaire</span><span class="sxs-lookup"><span data-stu-id="0c50b-272">Unit price</span></span>
    - <span data-ttu-id="0c50b-273">Montant net de ligne</span><span class="sxs-lookup"><span data-stu-id="0c50b-273">Line net amount</span></span>
    - <span data-ttu-id="0c50b-274">Montant des honoraires</span><span class="sxs-lookup"><span data-stu-id="0c50b-274">1099 amount</span></span>

11. <span data-ttu-id="0c50b-275">Une fois que l'ensemble des champs des deux étapes précédentes ont été ajoutés, cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-275">After all the fields from the previous two steps have been added, click **Done**.</span></span> <span data-ttu-id="0c50b-276">La page doit ressembler à l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="0c50b-276">The page must resemble the following illustration.</span></span>
    <span data-ttu-id="0c50b-277">[![Page après l'ajout des champs](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span><span class="sxs-lookup"><span data-stu-id="0c50b-277">[![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span></span>
12. <span data-ttu-id="0c50b-278">Cliquez sur **Terminé** pour quitter le mode d'édition.</span><span class="sxs-lookup"><span data-stu-id="0c50b-278">Click **Done** to exit edit mode.</span></span>
13. <span data-ttu-id="0c50b-279">Cliquez sur **Précédent**, puis **Terminé** pour quitter l'espace de travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-279">Click **Back** and then **Done** to exit the workspace</span></span>
14. <span data-ttu-id="0c50b-280">Cliquez sur **Publier l'espace de travail** pour enregistrer votre travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-280">Click **Publish workspace** to save your work</span></span>

### <a name="workflow-actions"></a><span data-ttu-id="0c50b-281">Actions de workflow</span><span class="sxs-lookup"><span data-stu-id="0c50b-281">Workflow actions</span></span>

<span data-ttu-id="0c50b-282">Pour ajouter des actions de workflow, utilisez la page **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-282">To add workflow actions, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="0c50b-283">Pour ouvrir cette page, remplacez le nom de l'option de menu dans l'URL, comme effectué précédemment.</span><span class="sxs-lookup"><span data-stu-id="0c50b-283">To open this page, replace the name of the menu item in the URL, as you did earlier.</span></span> <span data-ttu-id="0c50b-284">Ensuite, ouvrez le Concepteur mobile à partir du bouton **Paramètres** (engrenage).</span><span class="sxs-lookup"><span data-stu-id="0c50b-284">Then open the mobile designer from the **Settings** (gear) button.</span></span> <span data-ttu-id="0c50b-285">Procédez comme suit pour ajouter des actions de workflow dans la page de détails.</span><span class="sxs-lookup"><span data-stu-id="0c50b-285">Follow these steps to add workflow actions on the details page.</span></span> <span data-ttu-id="0c50b-286">Vous devez avoir des factures qui vous sont affectées dans l'état approprié pour vous permettre d'effectuer des actions de workflow en vue de les concevoir.</span><span class="sxs-lookup"><span data-stu-id="0c50b-286">You must have invoices assigned to you that are in the appropriate state to make the workflow actions available to you that you are going to design for.</span></span>

#### <a name="record-workflow-actions"></a><span data-ttu-id="0c50b-287">Enregistrer les actions de workflow</span><span class="sxs-lookup"><span data-stu-id="0c50b-287">Record workflow actions</span></span>
1.  <span data-ttu-id="0c50b-288">Cliquez sur le bouton **Modifier** pour passer en mode d'édition dans l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-288">Click the **Edit** button to start edit mode in the workspace.</span></span>
2.  <span data-ttu-id="0c50b-289">Sélectionnez la page **Détails de la facture** créée précédemment, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-289">Select the **Invoice details** page that you created earlier, and then click **Edit**.</span></span>
3.  <span data-ttu-id="0c50b-290">Dans l'onglet **Actions**, cliquez sur **Ajouter une action**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-290">On the **Actions** tab, click **Add action**.</span></span>
4.  <span data-ttu-id="0c50b-291">Entrez un titre d'action, par exemple **Approuver**, et une description, par exemple **Approuver la facture**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-291">Enter an action title, such as **Approve**, and a description, such as **Approve invoice**.</span></span> <span data-ttu-id="0c50b-292">Notez que le titre d'action que vous entrez ici devient le nom de l'action affiché pour l'utilisateur de l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-292">Note that the action title that you enter here becomes the name of the action that is shown to the user in the mobile app.</span></span>
5.  <span data-ttu-id="0c50b-293">Cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-293">Click **Done**.</span></span>
6.  <span data-ttu-id="0c50b-294">Cliquez sur **Sélectionner des champs**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-294">Click **Select fields**.</span></span>
7.  <span data-ttu-id="0c50b-295">Passez via le processus de workflow sur la page **VendMobileInvoiceHeaderDetails**, puis complétez l'action que vous avez souhaité enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0c50b-295">Go through the workflow process on the **VendMobileInvoiceHeaderDetails** page, and complete the action that you wanted to record.</span></span> <span data-ttu-id="0c50b-296">Assurez-vous que vous entrez des commentaires de workflow lors de ce processus, afin qu'un champ de commentaires soit également inclus à l'expérience mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-296">Make sure that you enter workflow comments during this process, so that a comments field is also included in the mobile experience.</span></span>
8.  <span data-ttu-id="0c50b-297">Une fois l'action de workflow exécutée, cliquez sur **Terminé** pour exécuter la tâche Sélectionner le champ.</span><span class="sxs-lookup"><span data-stu-id="0c50b-297">After the workflow action is run, click **Done** to complete the Select fields task.</span></span>
9.  <span data-ttu-id="0c50b-298">Cliquez sur **Terminé** pour quitter le mode d'édition.</span><span class="sxs-lookup"><span data-stu-id="0c50b-298">Click **Done** to exit edit mode.</span></span>
10. <span data-ttu-id="0c50b-299">Cliquez sur **Précédent**, puis **Terminé** pour quitter l'espace de travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-299">Click **Back** and then **Done** to exit the workspace</span></span>
11. <span data-ttu-id="0c50b-300">Cliquez sur **Publier l'espace de travail** pour enregistrer votre travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-300">Click **Publish workspace** to save your work</span></span>
12. <span data-ttu-id="0c50b-301">Répétez les étapes précédentes pour enregistrer toutes les actions de workflow voulues.</span><span class="sxs-lookup"><span data-stu-id="0c50b-301">Repeat the previous steps to record all the required workflow actions.</span></span> 

#### <a name="create-a-js-file"></a><span data-ttu-id="0c50b-302">Créez un fichier .js.</span><span class="sxs-lookup"><span data-stu-id="0c50b-302">Create a .js file</span></span>
1. <span data-ttu-id="0c50b-303">Ouvrez le Bloc-notes ou Microsoft Visual Studio, et collez le code suivant.</span><span class="sxs-lookup"><span data-stu-id="0c50b-303">Open Notepad or Microsoft Visual Studio, and paste the following code.</span></span> <span data-ttu-id="0c50b-304">Enregistrer le fichier au format .js.</span><span class="sxs-lookup"><span data-stu-id="0c50b-304">Save the file as a .js file.</span></span> <span data-ttu-id="0c50b-305">Ce code exécute ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0c50b-305">This code does the following:</span></span>
    - <span data-ttu-id="0c50b-306">Il masque les colonnes de workflow supplémentaires liées que nous avons ajoutées plus haut dans la page de liste mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-306">It hides the extra workflow-related columns that we added earlier on the mobile list page.</span></span> <span data-ttu-id="0c50b-307">Nous avons ajouté ces colonnes afin que l'application dispose de ces informations en contexte et puisse effectuer l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="0c50b-307">We added these columns so that the app has that information in context and can do the next step.</span></span>
    - <span data-ttu-id="0c50b-308">Selon l'étape de workflow active, une logique permet d'afficher uniquement les actions.</span><span class="sxs-lookup"><span data-stu-id="0c50b-308">Based on the workflow step that is active, it applies logic to show only those actions.</span></span>

> [!NOTE]
> <span data-ttu-id="0c50b-309">Le nom des pages et d'autres contrôles dans le code doivent être identiques aux noms dans l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-309">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  <span data-ttu-id="0c50b-310">Téléchargez le fichier de code vers l'espace de travail en sélectionnant l'onglet **Logique**</span><span class="sxs-lookup"><span data-stu-id="0c50b-310">Upload the code file to the workspace by selecting the **Logic** tab</span></span>
3.  <span data-ttu-id="0c50b-311">Cliquez sur **Terminé** pour quitter le mode d'édition.</span><span class="sxs-lookup"><span data-stu-id="0c50b-311">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="0c50b-312">Cliquez sur **Précédent**, puis **Terminé** pour quitter l'espace de travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-312">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="0c50b-313">Cliquez sur **Publier l'espace de travail** pour enregistrer votre travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-313">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-attachments"></a><span data-ttu-id="0c50b-314">Pièces jointes facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="0c50b-314">Vendor invoice attachments</span></span>

1. <span data-ttu-id="0c50b-315">Cliquez sur le bouton **Paramètres** (engrenage) dans la partie supérieure droite de la page, puis cliquez sur **Application mobile**</span><span class="sxs-lookup"><span data-stu-id="0c50b-315">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
2. <span data-ttu-id="0c50b-316">Cliquez sur le bouton **Modifier** pour passer en mode d'édition dans l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-316">Click the **Edit** button to start edit mode in the workspace.</span></span>
3. <span data-ttu-id="0c50b-317">Sélectionnez la page <strong>Détails de la facture **créée précédemment, puis cliquez sur** Modifier</strong>.</span><span class="sxs-lookup"><span data-stu-id="0c50b-317">Select the <strong>Invoice details \*\*page that you created earlier, and then click \*\*Edit</strong>.</span></span>
4. <span data-ttu-id="0c50b-318">Définissez l'option **Gestion des documents** sur **Oui** comme suit.</span><span class="sxs-lookup"><span data-stu-id="0c50b-318">Set the **Document management** option to **Yes** as shown below.</span></span> <span data-ttu-id="0c50b-319">**Remarque :** s'il n'existe aucune exigence d'afficher les pièces jointes sur le périphérique mobile, vous pouvez laisser cette option définie sur **Non**, qui est le paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="0c50b-319">**Note:** If there are no requirements to show attachments on the mobile device, you can leave this option set to **No**, which is the default setting.</span></span>
   <span data-ttu-id="0c50b-320">![Gestion des documents](./media/docmanagement-216x300.png)</span><span class="sxs-lookup"><span data-stu-id="0c50b-320">![Document management](./media/docmanagement-216x300.png)</span></span>
5. <span data-ttu-id="0c50b-321">Cliquez sur **Terminé** pour quitter le mode d'édition.</span><span class="sxs-lookup"><span data-stu-id="0c50b-321">Click **Done** to exit edit mode.</span></span>
6. <span data-ttu-id="0c50b-322">Cliquez sur **Précédent**, puis **Terminé** pour quitter l'espace de travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-322">Click **Back** and then **Done** to exit the workspace</span></span>
7. <span data-ttu-id="0c50b-323">Cliquez sur **Publier l'espace de travail** pour enregistrer votre travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-323">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-line-distributions"></a><span data-ttu-id="0c50b-324">Répartitions des lignes de factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="0c50b-324">Vendor invoice line distributions</span></span>

<span data-ttu-id="0c50b-325">Les exigences pour ce scénario confirment qu'il n'y aura que des distributions au niveau ligne, et qu'une facture n'aura qu'une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="0c50b-325">The requirements for this scenario confirm that there will be only line-level distributions, and that an invoice will always have only one line.</span></span> <span data-ttu-id="0c50b-326">Comme ce scénario est unique, l'expérience utilisateur sur le périphérique mobile doit également être suffisamment simple pour que l'utilisateur ne descende pas de plusieurs niveaux pour afficher les répartitions.</span><span class="sxs-lookup"><span data-stu-id="0c50b-326">Because this scenario is simple, the user experience on the mobile device must also be simple enough that the user doesn’t have to drill down several levels to view the distributions.</span></span> <span data-ttu-id="0c50b-327">Les factures fournisseur incluent l'option pour afficher toutes les répartitions de l'en-tête de facture.</span><span class="sxs-lookup"><span data-stu-id="0c50b-327">Vendor invoices include the option of showing all distributions from the invoice header.</span></span> <span data-ttu-id="0c50b-328">Cette expérience est utile pour le scénario mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-328">This experience is what we need for the mobile scenario.</span></span> <span data-ttu-id="0c50b-329">Par conséquent, nous emploierons la page **VendMobileInvoiceAllDistributionTree** pour concevoir cette partie du scénario mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-329">Therefore, we will use the **VendMobileInvoiceAllDistributionTree** page to design this part of the mobile scenario.</span></span> 

> [!NOTE] 
> <span data-ttu-id="0c50b-330">Connaître les besoins nous aide à définir les pages spécifiques à utiliser et comment optimiser exactement l'expérience de la mobilité pour l'utilisateur lorsque nous concevons le scénario.</span><span class="sxs-lookup"><span data-stu-id="0c50b-330">Knowing the requirements helps us decide which specific page to use and how exactly to optimize the mobile experience for the user when we design the scenario.</span></span> <span data-ttu-id="0c50b-331">Dans le deuxième cas, nous utiliserons une page différente pour afficher les répartitions, car les exigences pour ce scénario diffèrent.</span><span class="sxs-lookup"><span data-stu-id="0c50b-331">In the second scenario, we will use a different page to show the distributions, because the requirements for that scenario differ.</span></span>

1.  <span data-ttu-id="0c50b-332">Dans l'URL, remplacez le nom de l'option de menu, comme effectué précédemment.</span><span class="sxs-lookup"><span data-stu-id="0c50b-332">In the URL, replace the name of the menu item, as you did before.</span></span> <span data-ttu-id="0c50b-333">La page qui apparaît doit ressembler à l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="0c50b-333">The page that appears should resemble the following illustration.</span></span>
<span data-ttu-id="0c50b-334">[![Page Toutes les répartitions](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span><span class="sxs-lookup"><span data-stu-id="0c50b-334">[![All distributions page](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span></span>
2.  <span data-ttu-id="0c50b-335">Ouvrez le Concepteur mobile à partir du bouton **Paramètres** (engrenage)</span><span class="sxs-lookup"><span data-stu-id="0c50b-335">Open the mobile designer from the **Settings** (gear) button.</span></span>
3.  <span data-ttu-id="0c50b-336">Cliquez sur le bouton **Modifier** pour passer en mode d'édition dans l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-336">Click the **Edit** button to start edit mode in the workspace.</span></span> <span data-ttu-id="0c50b-337">**Remarque :** deux nouvelles pages ont été créées automatiquement et s'affichent.</span><span class="sxs-lookup"><span data-stu-id="0c50b-337">**Note:** You will see that two new pages were created automatically.</span></span> <span data-ttu-id="0c50b-338">Le système crée ces pages, si vous avez activé la gestion des documents dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="0c50b-338">The system creates these pages, because you turned on document management in the previous section.</span></span> <span data-ttu-id="0c50b-339">Vous pouvez ignorer ces nouvelles pages.</span><span class="sxs-lookup"><span data-stu-id="0c50b-339">You can ignore these new pages.</span></span>
4.  <span data-ttu-id="0c50b-340">Cliquez sur **Ajouter une page**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-340">Click **Add page**.</span></span>
5.  <span data-ttu-id="0c50b-341">Entrez un titre de page, tel que **Afficher la comptabilité** et une description, par exemple **Afficher la comptabilité pour la facture**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-341">Enter a page title, such as **View accounting**, and a description, such as **View accounting for the invoice**.</span></span>
6.  <span data-ttu-id="0c50b-342">Cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-342">Click **Done**.</span></span>
7.  <span data-ttu-id="0c50b-343">Sous l'onblet **Champs**, cliquez sur **Sélectionner des champs**, sélectionnez les champs suivants dans la page des répartitions, puis cliquez sur **Terminé** :</span><span class="sxs-lookup"><span data-stu-id="0c50b-343">On the **Fields** tab, click **Select fields**, select the following fields from the distributions page, and then click **Done**:</span></span>
    1.  <span data-ttu-id="0c50b-344">Montant</span><span class="sxs-lookup"><span data-stu-id="0c50b-344">Amount</span></span>
    2.  <span data-ttu-id="0c50b-345">Devise</span><span class="sxs-lookup"><span data-stu-id="0c50b-345">Currency</span></span>
    3.  <span data-ttu-id="0c50b-346">Compte général</span><span class="sxs-lookup"><span data-stu-id="0c50b-346">Ledger account</span></span>

    > [!NOTE] 
    > <span data-ttu-id="0c50b-347">Nous n'avons pas sélectionné la colonne **Description** dans la grille des répartitions, car les conditions requises pour ce scénario ont confirmé que le prix global est le seul montant pour lequel il y aura des répartitions.</span><span class="sxs-lookup"><span data-stu-id="0c50b-347">We didn’t select the **Description** column from the distributions grid, because the requirements for this scenario confirmed that the extended price is the only amount that there will be distributions for.</span></span> <span data-ttu-id="0c50b-348">Par conséquent, l'utilisateur ne demandera pas un autre champ pour déterminer le type de montant auquel la répartition est destinée.</span><span class="sxs-lookup"><span data-stu-id="0c50b-348">Therefore, the user won’t require another field to determine the amount type that the distribution is for.</span></span> <span data-ttu-id="0c50b-349">Toutefois, au prochain scénario, nous **utiliserons** ces informations, car les exigences pour ce scénario spécifient que d'autres types de montants disposent de répartitions (par exemple, taxe).</span><span class="sxs-lookup"><span data-stu-id="0c50b-349">However, in the next scenario, we **will** use this information, because the requirements for that scenario specify that other amount types have distributions (for example, sales tax).</span></span>
8.  <span data-ttu-id="0c50b-350">Cliquez sur **Terminé** pour quitter le mode d'édition.</span><span class="sxs-lookup"><span data-stu-id="0c50b-350">Click **Done** to exit edit mode.</span></span>
9.  <span data-ttu-id="0c50b-351">Cliquez sur **Précédent**, puis **Terminé** pour quitter l'espace de travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-351">Click **Back** and then **Done** to exit the workspace</span></span>
10. <span data-ttu-id="0c50b-352">Cliquez sur **Publier l'espace de travail** pour enregistrer votre travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-352">Click **Publish workspace** to save your work</span></span>

> [!NOTE] 
> <span data-ttu-id="0c50b-353">La page **Afficher la comptabilité** n'est actuellement pas liée aux pages mobiles que nous avons conçues jusqu'à présent.</span><span class="sxs-lookup"><span data-stu-id="0c50b-353">The **View accounting** mobile page isn’t currently linked to any of the mobile pages that we have designed so far.</span></span> <span data-ttu-id="0c50b-354">Étant donné que l'utilisateur doit pouvoir naviguer vers la page **Afficher la comptabilité** à partir de la page **Détails de la facture** sur l'appareil mobile, nous devons fournir la navigation à partir de la page **Détails de la facture** vers la page **Afficher la comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-354">Because the user should be able to navigate to the **View accounting** page from the **Invoice details** page on the mobile device, we must provide navigation from the **Invoice details** page to the **View accounting** page.</span></span> <span data-ttu-id="0c50b-355">Nous établissons cette navigation à l'aide de la logique supplémentaire via Javascript.</span><span class="sxs-lookup"><span data-stu-id="0c50b-355">We establish this navigation by using additional logic via JavaScript.</span></span>

1.  <span data-ttu-id="0c50b-356">Ouvrez le fichier .js créé précédemment, et ajoutez les lignes qui sont en surbrillance dans le code suivant.</span><span class="sxs-lookup"><span data-stu-id="0c50b-356">Open the .js file that you created earlier, and add the lines that are highlighted in the following code.</span></span> <span data-ttu-id="0c50b-357">Ce code permet d'effectuer deux choses :</span><span class="sxs-lookup"><span data-stu-id="0c50b-357">This code does two things:</span></span>
    1.  <span data-ttu-id="0c50b-358">Il permet de garantir que les utilisateurs ne peuvent pas accéder directement à la page **Afficher la comptabilité** à partir de l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-358">It helps guarantee that users can’t navigate directly from the workspace to the **View accounting** page.</span></span>
    2.  <span data-ttu-id="0c50b-359">Il établit un contrôle de navigation à partir de la page **Détails de la facture** à la page **Afficher la comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-359">It establishes a navigation control from the **Invoice details** page to the **View accounting** page.</span></span>

> [!NOTE] 
> <span data-ttu-id="0c50b-360">Le nom des pages et d'autres contrôles dans le code doivent être identiques aux noms dans l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="0c50b-360">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  <span data-ttu-id="0c50b-361">Téléchargez le fichier de code vers l'espace de travail en sélectionnant l'onglet **Logique** pour remplacer le code précédent</span><span class="sxs-lookup"><span data-stu-id="0c50b-361">Upload the code file to the workspace by selecting the **Logic** tab to overwrite the previous code</span></span>
3.  <span data-ttu-id="0c50b-362">Cliquez sur **Terminé** pour quitter le mode d'édition.</span><span class="sxs-lookup"><span data-stu-id="0c50b-362">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="0c50b-363">Cliquez sur **Précédent**, puis **Terminé** pour quitter l'espace de travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-363">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="0c50b-364">Cliquez sur **Publier l'espace de travail** pour enregistrer votre travail</span><span class="sxs-lookup"><span data-stu-id="0c50b-364">Click **Publish workspace** to save your work</span></span>

### <a name="validation"></a><span data-ttu-id="0c50b-365">Validation</span><span class="sxs-lookup"><span data-stu-id="0c50b-365">Validation</span></span>

<span data-ttu-id="0c50b-366">Dans votre périphérique mobile, ouvrez l'application, puis connectez-vous à votre instance.</span><span class="sxs-lookup"><span data-stu-id="0c50b-366">From your mobile device, open the app, and connect to your instance.</span></span> <span data-ttu-id="0c50b-367">Vérifiez que vous vous connectez à la société par rapport à laquelle les factures fournisseur vous sont affectées pour la révision.</span><span class="sxs-lookup"><span data-stu-id="0c50b-367">Make sure that you sign in to the company where vendor invoices are assigned to you for review.</span></span> <span data-ttu-id="0c50b-368">Vous devriez pouvoir effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c50b-368">You should be able to perform the following actions:</span></span>

-   <span data-ttu-id="0c50b-369">Voir l'espace de travail **Mes approbations**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-369">See the **My approvals** workspace.</span></span>
-   <span data-ttu-id="0c50b-370">Explorez l'espace de travail **Mes approbations** et consultez la page **Mes factures fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="0c50b-370">Drill into the **My approvals** workspace and see the **My vendor invoices** page.</span></span>
-   <span data-ttu-id="0c50b-371">Explorez la page **Mes factures fournisseur** et consultez la liste des factures qui vous sont affectées.</span><span class="sxs-lookup"><span data-stu-id="0c50b-371">Drill into the **My vendor invoices** page and see the list of invoices that are assigned to you.</span></span>
-   <span data-ttu-id="0c50b-372">Explorez l'une des factures, puis consultez les détails de la ligne d'en-tête et les détails de la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="0c50b-372">Drill into one of the invoices, and see the invoice header details and line details.</span></span>
-   <span data-ttu-id="0c50b-373">Dans la page des détails, consultez le lien vers les pièces jointes, puis utilisez ce lien pour accéder à la liste des pièces jointes et afficher les pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="0c50b-373">On the details page, see a link to attachments, and use this link to navigate to the attachments list and view the attachments.</span></span>
-   <span data-ttu-id="0c50b-374">Dans la page des détails, consultez le lien vers la page **Afficher la comptabilité**, puis utilisez ce lien pour accéder à la page des répartitions et afficher ces dernières.</span><span class="sxs-lookup"><span data-stu-id="0c50b-374">On the details page, see a link to the **View accounting** page, and use this link to navigate to the distributions page and view the distributions.</span></span>
-   <span data-ttu-id="0c50b-375">Dans la page des détails, cliquez sur le menu **Actions** situé en bas de l'écran, et effectuez des actions de workflow qui s'appliquent à l'étape de workflow.</span><span class="sxs-lookup"><span data-stu-id="0c50b-375">On the details page, click the **Actions** menu at the bottom, and perform workflow actions that are applicable to the workflow step.</span></span>

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a><span data-ttu-id="0c50b-376">Conception d'un scénario complexe d'approbation des factures pour Fabrikam</span><span class="sxs-lookup"><span data-stu-id="0c50b-376">Designing a complex invoice approval scenario for Fabrikam</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c50b-377">Attribut du scénario</span><span class="sxs-lookup"><span data-stu-id="0c50b-377">Scenario attribute</span></span></th>
<th><span data-ttu-id="0c50b-378">Répondre</span><span class="sxs-lookup"><span data-stu-id="0c50b-378">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0c50b-379">Quels champs de l'en-tête de la facture l'utilisateur souhaitera voir dans l'expérience mobile et dans quel ordre ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-379">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="0c50b-380">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="0c50b-380">Vendor name</span></span></li>
<li><span data-ttu-id="0c50b-381">Montant de la facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-381">Invoice amount</span></span></li>
<li><span data-ttu-id="0c50b-382">Compte de facturation</span><span class="sxs-lookup"><span data-stu-id="0c50b-382">Invoice account</span></span></li>
<li><span data-ttu-id="0c50b-383">Numéro de facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-383">Invoice number</span></span></li>
<li><span data-ttu-id="0c50b-384">Date de facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-384">Invoice date</span></span></li>
<li><span data-ttu-id="0c50b-385">Description de la facture</span><span class="sxs-lookup"><span data-stu-id="0c50b-385">Invoice description</span></span></li>
<li><span data-ttu-id="0c50b-386">Date d'échéance</span><span class="sxs-lookup"><span data-stu-id="0c50b-386">Due date</span></span></li>
<li><span data-ttu-id="0c50b-387">Devise de facturation</span><span class="sxs-lookup"><span data-stu-id="0c50b-387">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0c50b-388">Quels champs des lignes de la facture l'utilisateur souhaitera voir dans l'expérience mobile et dans quel ordre ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-388">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="0c50b-389">Catégorie d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="0c50b-389">Procurement category</span></span></li>
<li><span data-ttu-id="0c50b-390">Quantité</span><span class="sxs-lookup"><span data-stu-id="0c50b-390">Quantity</span></span></li>
<li><span data-ttu-id="0c50b-391">Prix unitaire</span><span class="sxs-lookup"><span data-stu-id="0c50b-391">Unit price</span></span></li>
<li><span data-ttu-id="0c50b-392">Montant net de ligne</span><span class="sxs-lookup"><span data-stu-id="0c50b-392">Line net amount</span></span></li>
<li><span data-ttu-id="0c50b-393">Montant des honoraires</span><span class="sxs-lookup"><span data-stu-id="0c50b-393">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0c50b-394">Combien de lignes de facture y-a-t-il dans une facture ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-394">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="0c50b-395">Appliquez la règle 80-20 ici et effectuez une optimisation pour les 80 %.</span><span class="sxs-lookup"><span data-stu-id="0c50b-395">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="0c50b-396">5</span><span class="sxs-lookup"><span data-stu-id="0c50b-396">5</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0c50b-397">Les utilisateurs souhaiteront-ils voir les répartitions comptables (codage de facture) sur l'appareil mobile pendant les révisions ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-397">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="0c50b-398">Oui</span><span class="sxs-lookup"><span data-stu-id="0c50b-398">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0c50b-399">Combien de répartitions comptables (prix global, taxes, frais, etc.) y-a-t-il pour une ligne de facture ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-399">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="0c50b-400">Là aussi, appliquez la règle 80-20.</span><span class="sxs-lookup"><span data-stu-id="0c50b-400">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="0c50b-401">Prix global : 2 Taxe : 2 Frais : 2</span><span class="sxs-lookup"><span data-stu-id="0c50b-401">Extended price: 2 Sales tax: 2 Charges: 2</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0c50b-402">Les factures ont-elles également les répartitions comptables dans l'en-tête de facture ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-402">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="0c50b-403">Dans ce cas, ces répartitions comptables doivent-elles être disponibles dans le périphérique ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-403">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="0c50b-404">Non utilisé</span><span class="sxs-lookup"><span data-stu-id="0c50b-404">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0c50b-405">Les utilisateurs souhaiteront-ils afficher les pièces jointes pour la facture sur le périphérique ?</span><span class="sxs-lookup"><span data-stu-id="0c50b-405">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="0c50b-406">Oui</span><span class="sxs-lookup"><span data-stu-id="0c50b-406">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a><span data-ttu-id="0c50b-407">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="0c50b-407">Next steps</span></span>

<span data-ttu-id="0c50b-408">Les modifications suivantes peuvent être effectuées pour le scénario 1, selon les exigences du scénario 2.</span><span class="sxs-lookup"><span data-stu-id="0c50b-408">The following variations can be done for scenario 1, based on the requirements for scenario 2.</span></span> <span data-ttu-id="0c50b-409">Vous pouvez utiliser cette section pour améliorer votre expérience d'application mobile.</span><span class="sxs-lookup"><span data-stu-id="0c50b-409">You can use this section to improve your mobile app experience.</span></span>

1.  <span data-ttu-id="0c50b-410">Étant donné que plus de lignes de facturation sont attendues dans le scénario 2, les modifications suivantes à la conception aideront à optimiser l'expérience utilisateur sur l'appareil mobile :</span><span class="sxs-lookup"><span data-stu-id="0c50b-410">Because more invoice lines are expected in scenario 2, the following changes to the design will help optimize the user experience on the mobile device:</span></span>
    1.  <span data-ttu-id="0c50b-411">Au lieu des lignes de facture affichées dans la page de détails (comme dans le scénario 1), les utilisateurs peuvent choisir d'afficher des lignes sur une page mobile distincte.</span><span class="sxs-lookup"><span data-stu-id="0c50b-411">Instead of viewing invoice lines on the details page (as in scenario 1), users can choose to view lines on a separate mobile page.</span></span>
    2.  <span data-ttu-id="0c50b-412">Comme plusieurs lignes de facture sont prévues dans ce scénario, si la page **VendMobileInvoiceAllDistributionTree** est utilisée pour concevoir la page des répartitions pour la fonction mobile (comme dans le scénario 1), il peut être perturbant pour l'utilisateur de corréler des lignes aux répartitions.</span><span class="sxs-lookup"><span data-stu-id="0c50b-412">Because more than one invoice line is expected in this scenario, if the **VendMobileInvoiceAllDistributionTree** page is used to design the distributions page for mobile (as in scenario 1), it might be confusing for the user to correlate lines to distributions.</span></span> <span data-ttu-id="0c50b-413">Utilisez par conséquent la page **VendMobileInvoiceLineDistributionTree** pour concevoir la page des répartitions.</span><span class="sxs-lookup"><span data-stu-id="0c50b-413">Therefore, use the **VendMobileInvoiceLineDistributionTree** page to design the distributions page.</span></span>
    3.  <span data-ttu-id="0c50b-414">Idéalement, les répartitions doivent être affichées dans le contexte d'une ligne de facture dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="0c50b-414">Ideally, the distributions should be shown in the context of an invoice line in this scenario.</span></span> <span data-ttu-id="0c50b-415">Par conséquent, veillez à ce que l'utilisateur puisse explorer une ligne pour afficher la page des répartitions.</span><span class="sxs-lookup"><span data-stu-id="0c50b-415">Therefore, make sure that the user can drill into a line to see the distributions page.</span></span> <span data-ttu-id="0c50b-416">Utilisez la fonctionnalité de lien de page pour établir le suivi, tout comme vous l'avez fait pour les pages d'en-tête et de détails dans le scénario 1.</span><span class="sxs-lookup"><span data-stu-id="0c50b-416">Use the page link capability to establish the drill-through, just as you did for the header and details pages in scenario 1.</span></span>

2.  <span data-ttu-id="0c50b-417">Comme plusieurs types de montant sont prévus sur les répartitions dans le scénario 2 (taxes, frais, etc.), il est utile d'afficher la description du type de montant.</span><span class="sxs-lookup"><span data-stu-id="0c50b-417">Because more than one amount type is expected on the distributions in scenario 2 (sales tax, charges, and so on), it will be useful to show the description of the amount type.</span></span> <span data-ttu-id="0c50b-418">(Nous avons omis ces informations dans le scénario 1).</span><span class="sxs-lookup"><span data-stu-id="0c50b-418">(We omitted this information in scenario 1.)</span></span>




