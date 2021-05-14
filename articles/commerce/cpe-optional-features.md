---
title: Configurer des fonctionnalités facultatives pour un environnement d’évaluation Dynamics 365 Commerce
description: Cette rubrique explique comment configurer des fonctionnalités facultatives pour un environnement d’évaluation Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0a93429e836d818458f11f6f6821fda237edc291
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936978"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="e904d-103">Configurer des fonctionnalités facultatives pour un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e904d-103">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e904d-104">Cette rubrique explique comment configurer des fonctionnalités facultatives pour un environnement d’évaluation Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e904d-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e904d-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e904d-105">Prerequisites</span></span>

<span data-ttu-id="e904d-106">Si vous souhaitez évaluer les fonctionnalités d’e-mail transactionnelles, les conditions requises suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="e904d-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e904d-107">Un serveur de messagerie disponible (serveur \[SMTP\], Simple Mail Transfer Protocol) qui peut être utilisé par l’abonnement Microsoft Azure dans lequel vous avez mis en service l’environnement d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="e904d-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the evaluation environment.</span></span>
- <span data-ttu-id="e904d-108">Le nom de domaine complet (FQDN)/adresse IP, le numéro de port SMTP, et les détails d’authentification disponibles.</span><span class="sxs-lookup"><span data-stu-id="e904d-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="e904d-109">Configurer l’arrière-plan de l’image</span><span class="sxs-lookup"><span data-stu-id="e904d-109">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="e904d-110">Rechercher votre URL de base multimédia</span><span class="sxs-lookup"><span data-stu-id="e904d-110">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="e904d-111">Avant de pouvoir terminer cette procédure, vous devez suivre les étapes dans [Configurer votre site dans Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="e904d-111">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="e904d-112">Connectez-vous au générateur de site Commerce en utilisant l’URL que vous avez notée lorsque vous avez initialisé le commerce électronique lors de la mise en service (voir [Initialiser le commerce électronique](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="e904d-112">Sign in to the Commerce site builder by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="e904d-113">Ouvrez le site **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="e904d-113">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="e904d-114">Dans le menu à gauche, sélectionnez **Bibliothèque multimédia**.</span><span class="sxs-lookup"><span data-stu-id="e904d-114">On the menu on the left, select **Media Library**.</span></span>
1. <span data-ttu-id="e904d-115">Sélectionnez un actif d’image unique.</span><span class="sxs-lookup"><span data-stu-id="e904d-115">Select any single image asset.</span></span>
1. <span data-ttu-id="e904d-116">Dans l’inspecteur de propriété à droite, recherchez la propriété **URL publique**.</span><span class="sxs-lookup"><span data-stu-id="e904d-116">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="e904d-117">La valeur est une URL.</span><span class="sxs-lookup"><span data-stu-id="e904d-117">The value is a URL.</span></span> <span data-ttu-id="e904d-118">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="e904d-118">Here is an example:</span></span>

    <span data-ttu-id="e904d-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="e904d-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="e904d-120">Remplacez le dernier identificateur de l’URL (**MA1nQC** dans l’exemple précédent) par la chaîne **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="e904d-120">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="e904d-121">Voici à quoi ressemble l’exemple d’URL après cette modification :</span><span class="sxs-lookup"><span data-stu-id="e904d-121">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="e904d-122">Cette URL est l’URL de votre base multimédia.</span><span class="sxs-lookup"><span data-stu-id="e904d-122">This URL is your media base URL.</span></span> <span data-ttu-id="e904d-123">Prenez-en note.</span><span class="sxs-lookup"><span data-stu-id="e904d-123">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="e904d-124">Mise à jour de l’URL de base multimédia</span><span class="sxs-lookup"><span data-stu-id="e904d-124">Update the media base URL</span></span>

1. <span data-ttu-id="e904d-125">Connectez-vous au siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="e904d-125">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="e904d-126">Utilisez le menu à gauche pour accéder à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Profils du canal**.</span><span class="sxs-lookup"><span data-stu-id="e904d-126">Use the menu on the left to go to **Modules \> Retail and commerce \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="e904d-127">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e904d-127">Select **Edit**.</span></span>
1. <span data-ttu-id="e904d-128">Sous **Propriétés du profil**, remplacez la valeur de la propriété **URL de base du serveur multimédia** par l’URL de base multimédia créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="e904d-128">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="e904d-129">Sélectionnez le canal nommé **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="e904d-129">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="e904d-130">Sous **Propriétés du profil**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e904d-130">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="e904d-131">Pour la propriété qui a été ajoutée, sélectionnez **URL de base du serveur multimédia** comme clé de propriété.</span><span class="sxs-lookup"><span data-stu-id="e904d-131">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="e904d-132">En tant que valeur de propriété, entrez l’URL de la base multimédia que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="e904d-132">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="e904d-133">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e904d-133">Select **Save**.</span></span>

## <a name="configure-and-test-the-email-server"></a><span data-ttu-id="e904d-134">Configuration et test du serveur de messagerie</span><span class="sxs-lookup"><span data-stu-id="e904d-134">Configure and test the email server</span></span>

> [!NOTE]
> <span data-ttu-id="e904d-135">Le serveur SMTP ou le service de messagerie que vous entrez ici doivent être accessibles à partir de l’abonnement Azure que vous utilisez pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="e904d-135">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="e904d-136">Connectez-vous au siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="e904d-136">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="e904d-137">Utilisez le menu de gauche pour accéder à **Modules \> Retail et Commerce \> Paramétrage du Siège \> Paramètres \> Paramètres de la messagerie**.</span><span class="sxs-lookup"><span data-stu-id="e904d-137">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Email parameters**.</span></span>
1. <span data-ttu-id="e904d-138">Sur l’onglet **Paramètres SMTP** dans le champ **Serveur de courrier sortant**, saisissez le nom de domaine complet ou l’adresse IP de votre serveur SMTP ou service de messagerie.</span><span class="sxs-lookup"><span data-stu-id="e904d-138">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="e904d-139">Dans le champ **Numéro de port SMTP**, entrez le numéro du port à utiliser.</span><span class="sxs-lookup"><span data-stu-id="e904d-139">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="e904d-140">(Si vous n’utilisez pas Secure Sockets Layer \[SSL\], le numéro de port par défaut est **25**.)</span><span class="sxs-lookup"><span data-stu-id="e904d-140">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="e904d-141">Si l’authentification est requise, entrez des valeurs dans les champs **Nom d’utilisateur** et **Mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="e904d-141">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="e904d-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e904d-142">Select **Save**.</span></span>
1. <span data-ttu-id="e904d-143">Sélectionnez **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="e904d-143">Select **Refresh**.</span></span>
1. <span data-ttu-id="e904d-144">Sur l’onglet **Tester la messagerie** dans le champ **Fournisseur de messagerie**, sélectionnez **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="e904d-144">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="e904d-145">Dans le champ **Destinataire**, entrez l’adresse e-mail à laquelle l’e-mail de test soit remis.</span><span class="sxs-lookup"><span data-stu-id="e904d-145">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="e904d-146">Sélectionnez **Envoyer un e-mail de test**.</span><span class="sxs-lookup"><span data-stu-id="e904d-146">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="e904d-147">Configuration des modèles d’e-mails</span><span class="sxs-lookup"><span data-stu-id="e904d-147">Configure email templates</span></span>

<span data-ttu-id="e904d-148">Pour chaque événement transactionnel pour lequel envoyer des e-mails vous devez mettre à jour le modèle d’e-mail avec une adresse e-mail d’expéditeur valide.</span><span class="sxs-lookup"><span data-stu-id="e904d-148">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="e904d-149">Connectez-vous au siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="e904d-149">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="e904d-150">Utilisez le menu de gauche pour accéder à **Modules \> Retail et Commerce \> Paramétrage du Siège \> Paramètres \> Modèles d’e-mail d’organisation**.</span><span class="sxs-lookup"><span data-stu-id="e904d-150">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="e904d-151">Sélectionnez **Afficher la liste**.</span><span class="sxs-lookup"><span data-stu-id="e904d-151">Select **Show list**.</span></span>
1. <span data-ttu-id="e904d-152">Pour chaque modèle de la liste, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e904d-152">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="e904d-153">Ensuite, dans le champ **E-mail de l’expéditeur**, entrez l’adresse e-mail de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="e904d-153">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="e904d-154">Facultatif : Dans le champ **Nom de l’expéditeur**, entrez le nom qui doit être utilisé comme nom d’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="e904d-154">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="e904d-155">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e904d-155">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="e904d-156">Personnaliser des modèles d’e-mail</span><span class="sxs-lookup"><span data-stu-id="e904d-156">Customize email templates</span></span>

<span data-ttu-id="e904d-157">Vous souhaiterez peut-être personnaliser les modèles d’e-mails afin qu’ils utilisent des images différentes.</span><span class="sxs-lookup"><span data-stu-id="e904d-157">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="e904d-158">Ou vous souhaiterez peut-être mettre à jour les liens dans les modèles afin qu’ils accèdent à votre environnement d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="e904d-158">Or you might want to update the links in the templates so that they go to your evaluation environment.</span></span> <span data-ttu-id="e904d-159">Cette procédure explique le téléchargement des modèles par défaut, leur personnalisation et la mise à jour des modèles à jour dans le système.</span><span class="sxs-lookup"><span data-stu-id="e904d-159">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="e904d-160">Dans un navigateur web, téléchargez le [fichier .zip des modèles d’e-mails par défaut de l’environnement d’évaluation Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="e904d-160">In a web browser, download the [Microsoft Dynamics 365 Commerce Evaluation default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="e904d-161">Ce fichier contient les documents HTML suivants :</span><span class="sxs-lookup"><span data-stu-id="e904d-161">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="e904d-162">Modèle de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="e904d-162">Order confirmation template</span></span>
    - <span data-ttu-id="e904d-163">Émettre un modèle de carte cadeau</span><span class="sxs-lookup"><span data-stu-id="e904d-163">Issue gift card template</span></span>
    - <span data-ttu-id="e904d-164">Nouveau modèle de commande</span><span class="sxs-lookup"><span data-stu-id="e904d-164">New order template</span></span>
    - <span data-ttu-id="e904d-165">Modèle de commande emballée</span><span class="sxs-lookup"><span data-stu-id="e904d-165">Pack order template</span></span>
    - <span data-ttu-id="e904d-166">Modèle de commande à prélever</span><span class="sxs-lookup"><span data-stu-id="e904d-166">Pick order template</span></span>

1. <span data-ttu-id="e904d-167">Personnaliser les modèles à l’aide d’un texte ou un éditeur HTML.</span><span class="sxs-lookup"><span data-stu-id="e904d-167">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="e904d-168">Voir la liste des [jetons pris en charge](#supported-tokens-in-the-email-template) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="e904d-168">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="e904d-169">Connectez-vous à Commerce.</span><span class="sxs-lookup"><span data-stu-id="e904d-169">Sign in to Commerce.</span></span>
1. <span data-ttu-id="e904d-170">Utilisez le menu à gauche pour accéder à **Modules \> Administration de l’organisation \> Paramétrage \> Modèles d’e-mail de l’organisation**.</span><span class="sxs-lookup"><span data-stu-id="e904d-170">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="e904d-171">Développez la liste à gauche pour afficher tous les modèles.</span><span class="sxs-lookup"><span data-stu-id="e904d-171">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="e904d-172">Pour chaque modèle que vous souhaitez personnaliser, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e904d-172">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="e904d-173">Sélectionnez le modèle dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e904d-173">Select the template in the list.</span></span>
    1. <span data-ttu-id="e904d-174">Sous **Contenu de message électronique**, sélectionnez la version de langue appropriée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e904d-174">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="e904d-175">(La langue par défaut est **en-us**.)</span><span class="sxs-lookup"><span data-stu-id="e904d-175">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="e904d-176">En dessous de **Contenu du message électronique**, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e904d-176">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="e904d-177">Le volet **Télécharger un modèle d’e-mail** apparaît.</span><span class="sxs-lookup"><span data-stu-id="e904d-177">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="e904d-178">Sélectionnez **Parcourir** et recherchez le fichier HTML contenant le contenu personnalisé.</span><span class="sxs-lookup"><span data-stu-id="e904d-178">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="e904d-179">Sélectionnez **Charger**.</span><span class="sxs-lookup"><span data-stu-id="e904d-179">Select **Upload**.</span></span> <span data-ttu-id="e904d-180">Le modèle est chargé dans le système et un aperçu s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e904d-180">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="e904d-181">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e904d-181">Select **OK**.</span></span>
    1. <span data-ttu-id="e904d-182">Facultatif : Personnalisez la propriété **Objet** du modèle.</span><span class="sxs-lookup"><span data-stu-id="e904d-182">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="e904d-183">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e904d-183">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="e904d-184">Jetons pris en charge dans le modèle d’e-mail</span><span class="sxs-lookup"><span data-stu-id="e904d-184">Supported tokens in the email template</span></span>

<span data-ttu-id="e904d-185">Au moment de l’affichage de l’e-mail, ces jetons sont remplacés par les valeurs réelles s’appliquant au client et à sa commande.</span><span class="sxs-lookup"><span data-stu-id="e904d-185">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="e904d-186">Commande client</span><span class="sxs-lookup"><span data-stu-id="e904d-186">Sales order</span></span>

<span data-ttu-id="e904d-187">Les jetons suivants s’appliquent à la commande client globale.</span><span class="sxs-lookup"><span data-stu-id="e904d-187">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="e904d-188">Nom du jeton</span><span class="sxs-lookup"><span data-stu-id="e904d-188">Name of the token</span></span> | <span data-ttu-id="e904d-189">Jeton</span><span class="sxs-lookup"><span data-stu-id="e904d-189">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="e904d-190">Numéro d’ordre</span><span class="sxs-lookup"><span data-stu-id="e904d-190">Order number</span></span>      | <span data-ttu-id="e904d-191">%salesid%</span><span class="sxs-lookup"><span data-stu-id="e904d-191">%salesid%</span></span> |
| <span data-ttu-id="e904d-192">Nom du client</span><span class="sxs-lookup"><span data-stu-id="e904d-192">Customer's name</span></span>   | <span data-ttu-id="e904d-193">%customername%</span><span class="sxs-lookup"><span data-stu-id="e904d-193">%customername%</span></span> |
| <span data-ttu-id="e904d-194">Adresse de livraison</span><span class="sxs-lookup"><span data-stu-id="e904d-194">Delivery address</span></span>  | <span data-ttu-id="e904d-195">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="e904d-195">%deliveryaddress%</span></span> |
| <span data-ttu-id="e904d-196">Adresse de facturation</span><span class="sxs-lookup"><span data-stu-id="e904d-196">Billing address</span></span>   | <span data-ttu-id="e904d-197">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="e904d-197">%customeraddress%</span></span> |
| <span data-ttu-id="e904d-198">Date de commande</span><span class="sxs-lookup"><span data-stu-id="e904d-198">Order date</span></span>        | <span data-ttu-id="e904d-199">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="e904d-199">%shipdate%</span></span> |
| <span data-ttu-id="e904d-200">Mode de distribution</span><span class="sxs-lookup"><span data-stu-id="e904d-200">Delivery mode</span></span>     | <span data-ttu-id="e904d-201">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="e904d-201">%modeofdelivery%</span></span> |
| <span data-ttu-id="e904d-202">Remise</span><span class="sxs-lookup"><span data-stu-id="e904d-202">Discount</span></span>          | <span data-ttu-id="e904d-203">%discount%</span><span class="sxs-lookup"><span data-stu-id="e904d-203">%discount%</span></span> |
| <span data-ttu-id="e904d-204">Taxe de vente</span><span class="sxs-lookup"><span data-stu-id="e904d-204">Sales tax</span></span>         | <span data-ttu-id="e904d-205">%tax%</span><span class="sxs-lookup"><span data-stu-id="e904d-205">%tax%</span></span> |
| <span data-ttu-id="e904d-206">Total de la commande</span><span class="sxs-lookup"><span data-stu-id="e904d-206">Order total</span></span>       | <span data-ttu-id="e904d-207">%total%</span><span class="sxs-lookup"><span data-stu-id="e904d-207">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="e904d-208">Ligne de vente</span><span class="sxs-lookup"><span data-stu-id="e904d-208">Sales line</span></span>

<span data-ttu-id="e904d-209">Les jetons suivants sont remplacés par des valeurs pour chaque produit de la commande.</span><span class="sxs-lookup"><span data-stu-id="e904d-209">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="e904d-210">Mettez le jeton **Liste de produits - début** au début du bloc HTML répété pour chaque produit, et placez le jeton **Liste de produits - fin** à la fin du bloc.</span><span class="sxs-lookup"><span data-stu-id="e904d-210">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="e904d-211">Nom du jeton</span><span class="sxs-lookup"><span data-stu-id="e904d-211">Name of the token</span></span>      | <span data-ttu-id="e904d-212">Jeton</span><span class="sxs-lookup"><span data-stu-id="e904d-212">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="e904d-213">Liste de produits - début</span><span class="sxs-lookup"><span data-stu-id="e904d-213">Product list - start</span></span>   | \<!--%tablebegin.salesline% --\> |
| <span data-ttu-id="e904d-214">Liste de produits - fin</span><span class="sxs-lookup"><span data-stu-id="e904d-214">Product list - end</span></span>     | \<!--%tableend.salesline%--\> |
| <span data-ttu-id="e904d-215">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e904d-215">Product name</span></span>           | <span data-ttu-id="e904d-216">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="e904d-216">%lineproductname%</span></span> |
| <span data-ttu-id="e904d-217">Description</span><span class="sxs-lookup"><span data-stu-id="e904d-217">Description</span></span>            | <span data-ttu-id="e904d-218">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="e904d-218">%lineproductdescription%</span></span> |
| <span data-ttu-id="e904d-219">Quantité</span><span class="sxs-lookup"><span data-stu-id="e904d-219">Quantity</span></span>               | <span data-ttu-id="e904d-220">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="e904d-220">%linequantity%</span></span> |
| <span data-ttu-id="e904d-221">Prix unitaire de la ligne</span><span class="sxs-lookup"><span data-stu-id="e904d-221">Line unit price</span></span>        | <span data-ttu-id="e904d-222">%lineprice% (vérifier)</span><span class="sxs-lookup"><span data-stu-id="e904d-222">%lineprice% (verify)</span></span> |
| <span data-ttu-id="e904d-223">nombre total d’articles de ligne</span><span class="sxs-lookup"><span data-stu-id="e904d-223">line item total</span></span>        | <span data-ttu-id="e904d-224">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="e904d-224">%linenetamount%</span></span> |
| <span data-ttu-id="e904d-225">remise ligne</span><span class="sxs-lookup"><span data-stu-id="e904d-225">line discount</span></span>          | <span data-ttu-id="e904d-226">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="e904d-226">%linediscount%</span></span> |
| <span data-ttu-id="e904d-227">Date d’expédition</span><span class="sxs-lookup"><span data-stu-id="e904d-227">Ship date</span></span>              | <span data-ttu-id="e904d-228">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="e904d-228">%lineshipdate%</span></span> |
| <span data-ttu-id="e904d-229">Méthode d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="e904d-229">Procurement method</span></span>     | <span data-ttu-id="e904d-230">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="e904d-230">%linedeliverymode%</span></span> |
| <span data-ttu-id="e904d-231">adresse de livraison</span><span class="sxs-lookup"><span data-stu-id="e904d-231">delivery address</span></span>       | <span data-ttu-id="e904d-232">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="e904d-232">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="e904d-233">Unité de vente de la ligne</span><span class="sxs-lookup"><span data-stu-id="e904d-233">Sales unit of the line</span></span> | <span data-ttu-id="e904d-234">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="e904d-234">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="e904d-235">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e904d-235">Additional resources</span></span>

[<span data-ttu-id="e904d-236">Vue d’ensemble d’un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e904d-236">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="e904d-237">Mettre en service un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e904d-237">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="e904d-238">Configurer un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e904d-238">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="e904d-239">Configurer le BOPIS dans un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e904d-239">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="e904d-240">FAQ des environnements d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e904d-240">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="e904d-241">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="e904d-241">Microsoft Lifecycle Services (LCS)</span></span>](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="e904d-242">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="e904d-242">Retail Cloud Scale Unit (RCSU)</span></span>](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="e904d-243">Portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="e904d-243">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="e904d-244">Site web Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e904d-244">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]