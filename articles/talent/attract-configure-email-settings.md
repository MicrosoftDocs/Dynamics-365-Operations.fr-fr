---
title: Configurer les paramètres d'e-mail dans Attract
description: Cette rubrique explique comment configurer les paramètres des e-mails envoyés par Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: e641e3f0d1873d91be1a1dc9bc22eb734a2b21d5
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124725"
---
# <a name="configure-email-settings-in-attract"></a><span data-ttu-id="a9d22-103">Configurer les paramètres d'e-mail dans Attract</span><span class="sxs-lookup"><span data-stu-id="a9d22-103">Configure email settings in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a9d22-104">Votre marque est un gage de confiance et vous aide à établir la relation avec les candidats avant même qu'ils ne postulent à vos offres d'emploi.</span><span class="sxs-lookup"><span data-stu-id="a9d22-104">Your brand establishes trust and helps you build a relationship with candidates before they even apply for your positions.</span></span> <span data-ttu-id="a9d22-105">Une perception de marque positive attire les meilleurs talents et augmente la fidélité des employés en place.</span><span class="sxs-lookup"><span data-stu-id="a9d22-105">Positive brand perception attracts top talent and increases the loyalty of existing employees.</span></span> <span data-ttu-id="a9d22-106">Microsoft Dynamics 365 Talent: Attract vous permet de configurer les e-mails pour qu'ils reflètent la marque de votre société.</span><span class="sxs-lookup"><span data-stu-id="a9d22-106">Microsoft Dynamics 365 Talent: Attract lets you configure emails so that they reflect your company's brand.</span></span> <span data-ttu-id="a9d22-107">Par conséquent, vous pouvez offrir une expérience cohérente aux candidats au fil de leur progression dans le processus de candidature.</span><span class="sxs-lookup"><span data-stu-id="a9d22-107">Therefore, you can provide a consistent experience to job candidates as they progress through the application process.</span></span>

<span data-ttu-id="a9d22-108">Attract vous permet d'exécuter les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a9d22-108">Attract lets you perform these actions:</span></span>

- <span data-ttu-id="a9d22-109">Configurer les paramètres d'e-mail afin d'utiliser le compte de service de messagerie Microsoft Exchange de votre société.</span><span class="sxs-lookup"><span data-stu-id="a9d22-109">Configure email settings so that your company's Microsoft Exchange email service account is used.</span></span> <span data-ttu-id="a9d22-110">Ainsi, les candidats savent que les e-mails proviennent de votre société.</span><span class="sxs-lookup"><span data-stu-id="a9d22-110">In this way, candidates know that the emails are coming from your company.</span></span> <span data-ttu-id="a9d22-111">Par exemple, vous pouvez configurer les paramètres afin que les candidats reçoivent des e-mails de `recruiting@contoso.com` au lieu de `contoso@microsoft.com`.</span><span class="sxs-lookup"><span data-stu-id="a9d22-111">For example, you can configure your settings so that candidates receive emails from `recruiting@contoso.com` instead of `contoso@microsoft.com`.</span></span>
- <span data-ttu-id="a9d22-112">Créer une personnalisation cohérente pour toutes les communications par e-mail, en définissant un en-tête et un pied de page globaux pour tous les modèles d'e-mails.</span><span class="sxs-lookup"><span data-stu-id="a9d22-112">Create consistent branding for all your email communications by setting a global header and footer for email templates.</span></span> 

> [!NOTE]
> <span data-ttu-id="a9d22-113">Pour configurer Attract afin qu'il utilise le compte de service de messagerie de votre société pour envoyer les e-mails, vous avez besoin du module complémentaire Recrutement complet.</span><span class="sxs-lookup"><span data-stu-id="a9d22-113">To configure Attract so that it uses your company's email service account to send email, you need the Comprehensive hiring add-on.</span></span>

## <a name="connect-an-email-service-account"></a><span data-ttu-id="a9d22-114">Connecter un compte de service de messagerie</span><span class="sxs-lookup"><span data-stu-id="a9d22-114">Connect an email service account</span></span>

<span data-ttu-id="a9d22-115">En connectant le compte de service de messagerie de votre société, vous pouvez créer une expérience de messagerie à l'image de votre marque pour les candidats à vos offres d'emploi.</span><span class="sxs-lookup"><span data-stu-id="a9d22-115">By connecting your company's email service account, you can create a branded email experience for your job candidates.</span></span> <span data-ttu-id="a9d22-116">Si vous ne connectez pas le compte de votre société, Attract utilise le compte de service de messagerie à l'image de marque de Microsoft par défaut.</span><span class="sxs-lookup"><span data-stu-id="a9d22-116">If you don't connect your company account, Attract uses the default Microsoft-branded email service account.</span></span>

1. <span data-ttu-id="a9d22-117">Sélectionnez **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit, puis sélectionnez **Centre d'administration**.</span><span class="sxs-lookup"><span data-stu-id="a9d22-117">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="a9d22-118">Dans l'onglet **Paramètres d'e-mail**, sous **Comptes de service de messagerie**, sélectionnez **Connecter un compte de société**.</span><span class="sxs-lookup"><span data-stu-id="a9d22-118">On the **Email settings** tab, under **Email service accounts**, select **Connect a company account**.</span></span>

    ![Connexion du compte du service de messagerie de votre société dans Attract](./media/attract-admin-email-service-accounts.png)

    <span data-ttu-id="a9d22-120">Pour plus d'informations sur la création d'un compte e-mail partagé, voir [Boîtes de réception partagées dans Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="a9d22-120">For more information about how to create a shared email account, see [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span></span>

3. <span data-ttu-id="a9d22-121">Dans la fenêtre de connexion Microsoft, connectez-vous à l'aide de vos informations d'identification d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="a9d22-121">In the Microsoft sign-in window, sign in by using your corporate credentials.</span></span>
4. <span data-ttu-id="a9d22-122">Si vous n'avez pas encore été paramétré de compte de service de messagerie, ou si vous souhaitez en ajouter un nouveau, sélectionnez **Ajouter un nouveau compte de service**, puis entrez vos informations de messagerie.</span><span class="sxs-lookup"><span data-stu-id="a9d22-122">If you haven't yet set up an email service account, or if you want to add a new one, select **Add new service account**, and then enter your email information.</span></span> <span data-ttu-id="a9d22-123">Si vous avez déjà configuré le compte de service de messagerie à utiliser, sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="a9d22-123">If you've already set up the email service account that you want to use, select it.</span></span>

<span data-ttu-id="a9d22-124">Lorsque votre compte de service de messagerie est correctement configuré, vous le voyez répertorié sous **Comptes de service de messagerie**.</span><span class="sxs-lookup"><span data-stu-id="a9d22-124">When your email service account is successfully configured, you will see it listed under **Email service accounts**.</span></span>

## <a name="disconnect-an-email-service-account"></a><span data-ttu-id="a9d22-125">Déconnecter un compte de service de messagerie</span><span class="sxs-lookup"><span data-stu-id="a9d22-125">Disconnect an email service account</span></span>

<span data-ttu-id="a9d22-126">Si vous souhaitez cesser d'utiliser le domaine de votre société dans vos communications par e-mail dans Attract, vous pouvez déconnecter un compte de service de messagerie.</span><span class="sxs-lookup"><span data-stu-id="a9d22-126">If you want to stop using your company's domain in email communications through Attract, you can disconnect an email service account.</span></span>

1. <span data-ttu-id="a9d22-127">Sélectionnez **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit, puis sélectionnez **Centre d'administration**.</span><span class="sxs-lookup"><span data-stu-id="a9d22-127">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="a9d22-128">Dans l'onglet **Paramètres d'e-mail**, sous **Comptes de service de messagerie**, sélectionnez le bouton **Plus** (trois points verticaux) en regard du compte de service de messagerie que vous souhaitez déconnecter.</span><span class="sxs-lookup"><span data-stu-id="a9d22-128">On the **Email settings** tab, under **Email service accounts**, select the **More** button (three vertical dots) next to the email service account that you want to disconnect.</span></span>
3. <span data-ttu-id="a9d22-129">Sélectionnez **Déconnecter le compte de messagerie**.</span><span class="sxs-lookup"><span data-stu-id="a9d22-129">Select **Disconnect email account**.</span></span>

    ![Déconnexion du compte du service de messagerie de votre société](./media/attract-admin-disconnect-email-account.png)

4. <span data-ttu-id="a9d22-131">Lorsque vous êtes invité à confirmer l'opération, sélectionnez **Déconnecter**.</span><span class="sxs-lookup"><span data-stu-id="a9d22-131">When you're prompted to confirm the operation, select **Disconnect**.</span></span>

    ![Conformation de la déconnexion du compte du service de messagerie de votre société](./media/attract-admin-email-confirm-disconnect.png)

<span data-ttu-id="a9d22-133">Si vous ne connectez pas d'autre compte de service de messagerie, les e-mails envoyés à partir d'Attract utiliseront compte de service de messagerie à l'image de marque de Microsoft par défaut.</span><span class="sxs-lookup"><span data-stu-id="a9d22-133">If you don't connect a different email service account, emails that are sent from Attract will use the default Microsoft-branded email service account.</span></span>

## <a name="configure-email-template-settings"></a><span data-ttu-id="a9d22-134">Configurer les paramètres de modèle d'e-mail</span><span class="sxs-lookup"><span data-stu-id="a9d22-134">Configure email template settings</span></span>

<span data-ttu-id="a9d22-135">Vous pouvez charger une image du logo de votre société et d'autres informations comme en-tête de marque pour vos e-mail.</span><span class="sxs-lookup"><span data-stu-id="a9d22-135">You can upload an image of your company's logo and other information as a branded header for your emails.</span></span> <span data-ttu-id="a9d22-136">Vous pouvez également fournir des liens vers votre politique de confidentialité et vos conditions d'utilisation dans les pieds de page d'e-mail.</span><span class="sxs-lookup"><span data-stu-id="a9d22-136">You can also provide links to your privacy policy and terms of use in email footers.</span></span>

> [!NOTE]
> <span data-ttu-id="a9d22-137">Vous devez respecter toutes les lois applicables de votre pays ou de votre région, ainsi que celles du pays ou de la région qui régissent le destinataire de l'e-mail.</span><span class="sxs-lookup"><span data-stu-id="a9d22-137">You must comply with all applicable laws of your country or region, and also the country or region that governs the email recipient.</span></span> <span data-ttu-id="a9d22-138">Ces lois comprennent les réglementations anti-courrier indésirable.</span><span class="sxs-lookup"><span data-stu-id="a9d22-138">These laws include anti-spam regulations.</span></span>

1. <span data-ttu-id="a9d22-139">Sélectionnez **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit, puis sélectionnez **Centre d'administration**.</span><span class="sxs-lookup"><span data-stu-id="a9d22-139">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="a9d22-140">Dans l'onglet **Paramètres d'e-mail**, sous **Paramètres du modèle d'e-mail**, faites glisser l'image que vous souhaitez utiliser comme en-tête d'e-mail dans la zone d'image, ou cliquez sur la zone d'image pour rechercher le fichier.</span><span class="sxs-lookup"><span data-stu-id="a9d22-140">On the **Email settings** tab, under **Email template settings**, drag the image that you want to use as your email header into the image box, or click in the image box to browse for the file.</span></span> <span data-ttu-id="a9d22-141">Pour remplacer une image existante, vous devez d'abord sélectionner **Supprimer** en regard de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="a9d22-141">To replace an existing image, you must first select **Remove** next to it.</span></span> <span data-ttu-id="a9d22-142">L'image doit être un fichier au format JPEG, JPG, PNG, ou SVG.</span><span class="sxs-lookup"><span data-stu-id="a9d22-142">The image must be a JPEG, JPG, PNG, or SVG file.</span></span> <span data-ttu-id="a9d22-143">La taille recommandée d'image est comprise entre 25 et 800 pixels de large, et entre 25 et 150 pixels de haut.</span><span class="sxs-lookup"><span data-stu-id="a9d22-143">The recommended size for images is between 25 and 800 pixels wide, and between 25 and 150 pixels high.</span></span> <span data-ttu-id="a9d22-144">La taille maximale de fichier pour l'en-tête est de 1 méga-octet (Mo).</span><span class="sxs-lookup"><span data-stu-id="a9d22-144">The maximum file size for the header is 1 megabyte (MB).</span></span>

    ![Ajouter une image à l'en-tête d'e-mail de votre société](./media/attract-admin-email-header.png)

3. <span data-ttu-id="a9d22-146">Sous **Votre politique de confidentialité pour les communications**, indiquez un lien vers la politique de confidentialité de votre société.</span><span class="sxs-lookup"><span data-stu-id="a9d22-146">Under **Your Privacy policy for communications**, provide a link to your company's privacy policy.</span></span> <span data-ttu-id="a9d22-147">Sous **Vos conditions générales pour les communications**, indiquez un lien vers les conditions d'utilisation de votre société.</span><span class="sxs-lookup"><span data-stu-id="a9d22-147">Under **Your Terms and conditions for communication**, provide a link to your company's terms of use.</span></span>

    ![Ajouter des liens vers la politique de confidentialité et les conditions d'utilisation de votre société dans le pied de page d'e-mail](./media/attract-admin-email-footer.png)

4. <span data-ttu-id="a9d22-149">Sélectionnez **Enregistrer** pour enregistrer vos paramètres de modèle d'e-mail.</span><span class="sxs-lookup"><span data-stu-id="a9d22-149">Select **Save** to save your email template settings.</span></span>
