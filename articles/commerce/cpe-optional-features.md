---
title: Configurer des fonctionnalités facultatives pour un environnement d'évaluation Commerce
description: Cette rubrique explique comment configurer des fonctionnalités facultatives pour un environnement d'aperçu Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2c4872cdebc414eaa865af025237bd9e1d14bfd2
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906114"
---
# <a name="configure-optional-features-for-a-commerce-preview-environment"></a><span data-ttu-id="99f09-103">Configurer des fonctionnalités facultatives pour un environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="99f09-103">Configure optional features for a Commerce preview environment</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="99f09-104">Cette rubrique explique comment configurer des fonctionnalités facultatives pour un environnement d'aperçu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="99f09-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="99f09-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="99f09-105">Prerequisites</span></span>

<span data-ttu-id="99f09-106">Si vous souhaitez évaluer les fonctionnalités d'e-mail transactionnelles, les conditions requises suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="99f09-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="99f09-107">Un serveur de messagerie disponible (serveur \[SMTP\], Simple Mail Transfer Protocol) qui peut être utilisé par l'abonnement Microsoft Azure dans lequel vous avez mis en service l'environnement d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="99f09-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the preview environment.</span></span>
- <span data-ttu-id="99f09-108">Le nom de domaine complet (FQDN)/adresse IP, le numéro de port SMTP, et les détails d'authentification disponibles.</span><span class="sxs-lookup"><span data-stu-id="99f09-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

<span data-ttu-id="99f09-109">Si vous souhaitez évaluer des fonctionnalités de gestion d'actifs numériques, notamment ingérer de nouvelles images omnicanales, vous devez disposer du nom de votre client du système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="99f09-109">If you want to evaluate Digital Asset Management features by ingesting new omni-channel images, you must have the name of your content management system (CMS) tenant available.</span></span> <span data-ttu-id="99f09-110">Les instructions pour rechercher ce nom sont fournies plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="99f09-110">Instructions for finding this name are provided later in this topic.</span></span> <span data-ttu-id="99f09-111">>>>(Q: where are the instructions?)</span><span class="sxs-lookup"><span data-stu-id="99f09-111">>>>(Q: where are the instructions?)</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="99f09-112">Configurer l'arrière-plan de l'image</span><span class="sxs-lookup"><span data-stu-id="99f09-112">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="99f09-113">Rechercher votre URL de base multimédia</span><span class="sxs-lookup"><span data-stu-id="99f09-113">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="99f09-114">Avant de pouvoir terminer cette procédure, vous devez suivre les étapes dans [Configurer votre site dans Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="99f09-114">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="99f09-115">Connectez-vous à l'outil de gestion de site Commerce en utilisant l'URL que vous avez notée lorsque vous avez initialisé le commerce électronique lors de la mise en service (voir [Initialiser le commerce électronique](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="99f09-115">Sign in to the Commerce site management tool by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="99f09-116">Ouvrez le site **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="99f09-116">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="99f09-117">Dans le menu à gauche, sélectionnez **Actifs**.</span><span class="sxs-lookup"><span data-stu-id="99f09-117">On the menu on the left, select **Assets**.</span></span>
1. <span data-ttu-id="99f09-118">Sélectionnez un actif d'image unique.</span><span class="sxs-lookup"><span data-stu-id="99f09-118">Select any single image asset.</span></span>
1. <span data-ttu-id="99f09-119">Dans l'inspecteur de propriété à droite, recherchez la propriété **URL publique**.</span><span class="sxs-lookup"><span data-stu-id="99f09-119">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="99f09-120">La valeur est une URL.</span><span class="sxs-lookup"><span data-stu-id="99f09-120">The value is a URL.</span></span> <span data-ttu-id="99f09-121">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="99f09-121">Here is an example:</span></span>

    <span data-ttu-id="99f09-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="99f09-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="99f09-123">Remplacez le dernier identificateur de l'URL (**MA1nQC** dans l'exemple précédent) par la chaîne **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="99f09-123">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="99f09-124">Voici à quoi ressemble l'exemple d'URL après cette modification :</span><span class="sxs-lookup"><span data-stu-id="99f09-124">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="99f09-125">Cette URL est l'URL de votre base multimédia.</span><span class="sxs-lookup"><span data-stu-id="99f09-125">This URL is your media base URL.</span></span> <span data-ttu-id="99f09-126">Prenez-en note.</span><span class="sxs-lookup"><span data-stu-id="99f09-126">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="99f09-127">Mise à jour de l'URL de base multimédia</span><span class="sxs-lookup"><span data-stu-id="99f09-127">Update the media base URL</span></span>

1. <span data-ttu-id="99f09-128">Connectez-vous à Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="99f09-128">Sign in to Dynamics 365 Retail.</span></span>
1. <span data-ttu-id="99f09-129">Utilisez le menu à gauche, accédez à **Modules \> Vente au détail \> Paramétrage du canal \> Profils du canal**.</span><span class="sxs-lookup"><span data-stu-id="99f09-129">Use the menu on the left to go to **Modules \> Retail \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="99f09-130">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="99f09-130">Select **Edit**.</span></span>
1. <span data-ttu-id="99f09-131">Sous **Propriétés du profil**, remplacez la valeur de la propriété **URL de base du serveur multimédia** par l'URL de base multimédia créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="99f09-131">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="99f09-132">Dans la liste à gauche, sous le canal **Par défaut**, sélectionnez l'autre canal.</span><span class="sxs-lookup"><span data-stu-id="99f09-132">In the list on the left, under the **Default** channel, select the other channel.</span></span>
1. <span data-ttu-id="99f09-133">Sous **Propriétés du profil**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="99f09-133">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="99f09-134">Pour la propriété qui a été ajoutée, sélectionnez **URL de base du serveur multimédia** comme clé de propriété.</span><span class="sxs-lookup"><span data-stu-id="99f09-134">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="99f09-135">En tant que valeur de propriété, entrez l'URL de la base multimédia que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="99f09-135">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="99f09-136">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="99f09-136">Select **Save**.</span></span>

## <a name="configure-the-email-server"></a><span data-ttu-id="99f09-137">Configuration du serveur de messagerie</span><span class="sxs-lookup"><span data-stu-id="99f09-137">Configure the email server</span></span>

> [!NOTE]
> <span data-ttu-id="99f09-138">Le serveur SMTP ou le service de messagerie que vous entrez ici doivent être accessibles à partir de l'abonnement Azure que vous utilisez pour l'environnement.</span><span class="sxs-lookup"><span data-stu-id="99f09-138">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="99f09-139">Connectez-vous à Retail.</span><span class="sxs-lookup"><span data-stu-id="99f09-139">Sign in to Retail.</span></span>
1. <span data-ttu-id="99f09-140">Utilisez le menu à gauche pour accéder à **Modules \> Administration de l'organisation \> Paramétrage \> E-mail \> Paramètres d'e-mail**.</span><span class="sxs-lookup"><span data-stu-id="99f09-140">Use the menu on the left to go to **Modules \> System administration \> Setup \> Email \> Email parameters**.</span></span>
1. <span data-ttu-id="99f09-141">Sur l'onglet **Paramètres SMTP** dans le champ **Serveur de courrier sortant**, saisissez le nom de domaine complet ou l'adresse IP de votre serveur SMTP ou service de messagerie.</span><span class="sxs-lookup"><span data-stu-id="99f09-141">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="99f09-142">Dans le champ **Numéro de port SMTP**, entrez le numéro du port à utiliser.</span><span class="sxs-lookup"><span data-stu-id="99f09-142">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="99f09-143">(Si vous n'utilisez pas Secure Sockets Layer \[SSL\], le numéro de port par défaut est **25**.)</span><span class="sxs-lookup"><span data-stu-id="99f09-143">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="99f09-144">Si l'authentification est requise, entrez des valeurs dans les champs **Nom d'utilisateur** et **Mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="99f09-144">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="99f09-145">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="99f09-145">Select **Save**.</span></span>
1. <span data-ttu-id="99f09-146">Sélectionnez **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="99f09-146">Select **Refresh**.</span></span>
1. <span data-ttu-id="99f09-147">Sur l'onglet **Tester la messagerie** dans le champ **Fournisseur de messagerie**, sélectionnez **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="99f09-147">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="99f09-148">Dans le champ **Destinataire**, entrez l'adresse e-mail à laquelle l'e-mail de test soit remis.</span><span class="sxs-lookup"><span data-stu-id="99f09-148">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="99f09-149">Sélectionnez **Envoyer un e-mail de test**.</span><span class="sxs-lookup"><span data-stu-id="99f09-149">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="99f09-150">Configuration des modèles d'e-mails</span><span class="sxs-lookup"><span data-stu-id="99f09-150">Configure email templates</span></span>

<span data-ttu-id="99f09-151">Pour chaque événement transactionnel pour lequel envoyer des e-mails vous devez mettre à jour le modèle d'e-mail avec une adresse e-mail d'expéditeur valide.</span><span class="sxs-lookup"><span data-stu-id="99f09-151">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="99f09-152">Connectez-vous à Retail.</span><span class="sxs-lookup"><span data-stu-id="99f09-152">Sign in to Retail.</span></span>
1. <span data-ttu-id="99f09-153">Utilisez le menu à gauche pour accéder à **Modules \> Administration de l'organisation \> Paramétrage \> Modèles d'e-mail de l'organisation**.</span><span class="sxs-lookup"><span data-stu-id="99f09-153">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="99f09-154">Sélectionnez **Afficher la liste**.</span><span class="sxs-lookup"><span data-stu-id="99f09-154">Select **Show list**.</span></span>
1. <span data-ttu-id="99f09-155">Pour chaque modèle de la liste, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="99f09-155">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="99f09-156">Ensuite, dans le champ **E-mail de l'expéditeur**, entrez l'adresse e-mail de l'expéditeur.</span><span class="sxs-lookup"><span data-stu-id="99f09-156">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="99f09-157">Facultatif : Dans le champ **Nom de l'expéditeur**, entrez le nom qui doit être utilisé comme nom d'expéditeur.</span><span class="sxs-lookup"><span data-stu-id="99f09-157">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="99f09-158">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="99f09-158">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="99f09-159">Personnaliser des modèles d'e-mail</span><span class="sxs-lookup"><span data-stu-id="99f09-159">Customize email templates</span></span>

<span data-ttu-id="99f09-160">Vous souhaiterez peut-être personnaliser les modèles d'e-mails afin qu'ils utilisent des images différentes.</span><span class="sxs-lookup"><span data-stu-id="99f09-160">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="99f09-161">Ou vous souhaiterez peut-être mettre à jour les liens dans les modèles afin qu'ils accèdent à votre environnement d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="99f09-161">Or you might want to update the links in the templates so that they go to your preview environment.</span></span> <span data-ttu-id="99f09-162">Cette procédure explique le téléchargement des modèles par défaut, leur personnalisation et la mise à jour des modèles à jour dans le système.</span><span class="sxs-lookup"><span data-stu-id="99f09-162">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="99f09-163">Dans un navigateur web, téléchargez le [fichier .zip des modèles d'e-mails par défaut de Microsoft Dynamics 365 Commerce Aperçu](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="99f09-163">In a web browser, download the [Microsoft Dynamics 365 Commerce Preview default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="99f09-164">Ce fichier contient les documents HTML suivants :</span><span class="sxs-lookup"><span data-stu-id="99f09-164">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="99f09-165">Modèle de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="99f09-165">Order confirmation template</span></span>
    - <span data-ttu-id="99f09-166">Émettre un modèle de carte cadeau</span><span class="sxs-lookup"><span data-stu-id="99f09-166">Issue gift card template</span></span>
    - <span data-ttu-id="99f09-167">Nouveau modèle de commande</span><span class="sxs-lookup"><span data-stu-id="99f09-167">New order template</span></span>
    - <span data-ttu-id="99f09-168">Modèle de commande emballée</span><span class="sxs-lookup"><span data-stu-id="99f09-168">Pack order template</span></span>
    - <span data-ttu-id="99f09-169">Modèle de commande à prélever</span><span class="sxs-lookup"><span data-stu-id="99f09-169">Pick order template</span></span>

1. <span data-ttu-id="99f09-170">Personnaliser les modèles à l'aide d'un texte ou un éditeur HTML.</span><span class="sxs-lookup"><span data-stu-id="99f09-170">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="99f09-171">Voir la liste des [jetons pris en charge](#supported-tokens-in-the-email-template) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="99f09-171">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="99f09-172">Connectez-vous à Retail.</span><span class="sxs-lookup"><span data-stu-id="99f09-172">Sign in to Retail.</span></span>
1. <span data-ttu-id="99f09-173">Utilisez le menu à gauche pour accéder à **Modules \> Administration de l'organisation \> Paramétrage \> Modèles d'e-mail de l'organisation**.</span><span class="sxs-lookup"><span data-stu-id="99f09-173">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="99f09-174">Développez la liste à gauche pour afficher tous les modèles.</span><span class="sxs-lookup"><span data-stu-id="99f09-174">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="99f09-175">Pour chaque modèle que vous souhaitez personnaliser, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="99f09-175">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="99f09-176">Sélectionnez le modèle dans la liste.</span><span class="sxs-lookup"><span data-stu-id="99f09-176">Select the template in the list.</span></span>
    1. <span data-ttu-id="99f09-177">Sous **Contenu de message électronique**, sélectionnez la version de langue appropriée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="99f09-177">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="99f09-178">(La langue par défaut est **en-us**.)</span><span class="sxs-lookup"><span data-stu-id="99f09-178">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="99f09-179">En dessous de **Contenu du message électronique**, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="99f09-179">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="99f09-180">Le volet **Télécharger un modèle d'e-mail** apparaît.</span><span class="sxs-lookup"><span data-stu-id="99f09-180">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="99f09-181">Sélectionnez **Parcourir**et recherchez le fichier HTML contenant le contenu personnalisé.</span><span class="sxs-lookup"><span data-stu-id="99f09-181">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="99f09-182">Sélectionnez **Charger**.</span><span class="sxs-lookup"><span data-stu-id="99f09-182">Select **Upload**.</span></span> <span data-ttu-id="99f09-183">Le modèle est chargé dans le système et un aperçu s'affiche.</span><span class="sxs-lookup"><span data-stu-id="99f09-183">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="99f09-184">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99f09-184">Select **OK**.</span></span>
    1. <span data-ttu-id="99f09-185">Facultatif : Personnalisez la propriété **Objet** du modèle.</span><span class="sxs-lookup"><span data-stu-id="99f09-185">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="99f09-186">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="99f09-186">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="99f09-187">Jetons pris en charge dans le modèle d'e-mail</span><span class="sxs-lookup"><span data-stu-id="99f09-187">Supported tokens in the email template</span></span>

<span data-ttu-id="99f09-188">Au moment de l'affichage de l'e-mail, ces jetons sont remplacés par les valeurs réelles s'appliquant au client et à sa commande.</span><span class="sxs-lookup"><span data-stu-id="99f09-188">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="99f09-189">Commande client</span><span class="sxs-lookup"><span data-stu-id="99f09-189">Sales order</span></span>

<span data-ttu-id="99f09-190">Les jetons suivants s'appliquent à la commande client globale.</span><span class="sxs-lookup"><span data-stu-id="99f09-190">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="99f09-191">Nom du jeton</span><span class="sxs-lookup"><span data-stu-id="99f09-191">Name of the token</span></span> | <span data-ttu-id="99f09-192">Jeton</span><span class="sxs-lookup"><span data-stu-id="99f09-192">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="99f09-193">Numéro de la commande</span><span class="sxs-lookup"><span data-stu-id="99f09-193">Order number</span></span>      | <span data-ttu-id="99f09-194">%salesid%</span><span class="sxs-lookup"><span data-stu-id="99f09-194">%salesid%</span></span> |
| <span data-ttu-id="99f09-195">Nom du client</span><span class="sxs-lookup"><span data-stu-id="99f09-195">Customer's name</span></span>   | <span data-ttu-id="99f09-196">%customername%</span><span class="sxs-lookup"><span data-stu-id="99f09-196">%customername%</span></span> |
| <span data-ttu-id="99f09-197">Adresse de livraison</span><span class="sxs-lookup"><span data-stu-id="99f09-197">Delivery address</span></span>  | <span data-ttu-id="99f09-198">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="99f09-198">%deliveryaddress%</span></span> |
| <span data-ttu-id="99f09-199">Adresse de facturation</span><span class="sxs-lookup"><span data-stu-id="99f09-199">Billing address</span></span>   | <span data-ttu-id="99f09-200">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="99f09-200">%customeraddress%</span></span> |
| <span data-ttu-id="99f09-201">Date de commande</span><span class="sxs-lookup"><span data-stu-id="99f09-201">Order date</span></span>        | <span data-ttu-id="99f09-202">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="99f09-202">%shipdate%</span></span> |
| <span data-ttu-id="99f09-203">Mode de distribution</span><span class="sxs-lookup"><span data-stu-id="99f09-203">Delivery mode</span></span>     | <span data-ttu-id="99f09-204">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="99f09-204">%modeofdelivery%</span></span> |
| <span data-ttu-id="99f09-205">Remise</span><span class="sxs-lookup"><span data-stu-id="99f09-205">Discount</span></span>          | <span data-ttu-id="99f09-206">%discount%</span><span class="sxs-lookup"><span data-stu-id="99f09-206">%discount%</span></span> |
| <span data-ttu-id="99f09-207">Taxe</span><span class="sxs-lookup"><span data-stu-id="99f09-207">Sales tax</span></span>         | <span data-ttu-id="99f09-208">%tax%</span><span class="sxs-lookup"><span data-stu-id="99f09-208">%tax%</span></span> |
| <span data-ttu-id="99f09-209">Total de la commande</span><span class="sxs-lookup"><span data-stu-id="99f09-209">Order total</span></span>       | <span data-ttu-id="99f09-210">%total%</span><span class="sxs-lookup"><span data-stu-id="99f09-210">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="99f09-211">Ligne de vente</span><span class="sxs-lookup"><span data-stu-id="99f09-211">Sales line</span></span>

<span data-ttu-id="99f09-212">Les jetons suivants sont remplacés par des valeurs pour chaque produit de la commande.</span><span class="sxs-lookup"><span data-stu-id="99f09-212">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="99f09-213">Mettez le jeton **Liste de produits - début** au début du bloc HTML répété pour chaque produit, et placez le jeton **Liste de produits - fin** à la fin du bloc.</span><span class="sxs-lookup"><span data-stu-id="99f09-213">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="99f09-214">Nom du jeton</span><span class="sxs-lookup"><span data-stu-id="99f09-214">Name of the token</span></span>      | <span data-ttu-id="99f09-215">Jeton</span><span class="sxs-lookup"><span data-stu-id="99f09-215">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="99f09-216">Liste de produits - début</span><span class="sxs-lookup"><span data-stu-id="99f09-216">Product list - start</span></span>   | <span data-ttu-id="99f09-217">\<!--%tablebegin.salesline% --\></span><span class="sxs-lookup"><span data-stu-id="99f09-217">\<!--%tablebegin.salesline% --\></span></span> |
| <span data-ttu-id="99f09-218">Liste de produits - fin</span><span class="sxs-lookup"><span data-stu-id="99f09-218">Product list - end</span></span>     | <span data-ttu-id="99f09-219">\<!--%tableend.salesline%--\></span><span class="sxs-lookup"><span data-stu-id="99f09-219">\<!--%tableend.salesline%--\></span></span> |
| <span data-ttu-id="99f09-220">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="99f09-220">Product name</span></span>           | <span data-ttu-id="99f09-221">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="99f09-221">%lineproductname%</span></span> |
| <span data-ttu-id="99f09-222">Description</span><span class="sxs-lookup"><span data-stu-id="99f09-222">Description</span></span>            | <span data-ttu-id="99f09-223">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="99f09-223">%lineproductdescription%</span></span> |
| <span data-ttu-id="99f09-224">Quantité</span><span class="sxs-lookup"><span data-stu-id="99f09-224">Quantity</span></span>               | <span data-ttu-id="99f09-225">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="99f09-225">%linequantity%</span></span> |
| <span data-ttu-id="99f09-226">Prix unitaire de la ligne</span><span class="sxs-lookup"><span data-stu-id="99f09-226">Line unit price</span></span>        | <span data-ttu-id="99f09-227">%lineprice% (vérifier)</span><span class="sxs-lookup"><span data-stu-id="99f09-227">%lineprice% (verify)</span></span> |
| <span data-ttu-id="99f09-228">nombre total d'articles de ligne</span><span class="sxs-lookup"><span data-stu-id="99f09-228">line item total</span></span>        | <span data-ttu-id="99f09-229">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="99f09-229">%linenetamount%</span></span> |
| <span data-ttu-id="99f09-230">remise ligne</span><span class="sxs-lookup"><span data-stu-id="99f09-230">line discount</span></span>          | <span data-ttu-id="99f09-231">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="99f09-231">%linediscount%</span></span> |
| <span data-ttu-id="99f09-232">Date d'expédition</span><span class="sxs-lookup"><span data-stu-id="99f09-232">Ship date</span></span>              | <span data-ttu-id="99f09-233">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="99f09-233">%lineshipdate%</span></span> |
| <span data-ttu-id="99f09-234">Méthode d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="99f09-234">Procurement method</span></span>     | <span data-ttu-id="99f09-235">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="99f09-235">%linedeliverymode%</span></span> |
| <span data-ttu-id="99f09-236">adresse de livraison</span><span class="sxs-lookup"><span data-stu-id="99f09-236">delivery address</span></span>       | <span data-ttu-id="99f09-237">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="99f09-237">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="99f09-238">Unité de vente de la ligne</span><span class="sxs-lookup"><span data-stu-id="99f09-238">Sales unit of the line</span></span> | <span data-ttu-id="99f09-239">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="99f09-239">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="99f09-240">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="99f09-240">Additional resources</span></span>

[<span data-ttu-id="99f09-241">Vue d'ensemble d'un environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="99f09-241">Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="99f09-242">Mettre en service un environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="99f09-242">Provision a Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="99f09-243">Configurer un environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="99f09-243">Configure a Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="99f09-244">FAQ relative à l'environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="99f09-244">Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="99f09-245">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="99f09-245">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="99f09-246">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="99f09-246">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="99f09-247">Portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="99f09-247">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="99f09-248">Site web Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="99f09-248">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="99f09-249">Ressources d'aide pour Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="99f09-249">Help resources for Dynamics 365 Retail</span></span>](../retail/index.md)
