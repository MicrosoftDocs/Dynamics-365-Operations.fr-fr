---
title: Ajouter un code QR ou un code barres dans les e-mails transactionnels et de ticket de caisse
description: Cette rubrique explique comment insérer des codes QR et des codes barres qui représentent les ID de commande dans les e-mails transactionnels et de ticket de caisse dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 791b244c867ea4263f08250abf220a1b75784cad
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907861"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a><span data-ttu-id="7c441-103">Ajouter un code QR ou un code barres dans les e-mails transactionnels et de ticket de caisse</span><span class="sxs-lookup"><span data-stu-id="7c441-103">Add a QR code or bar code to transactional and receipt emails</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7c441-104">Cette rubrique explique comment insérer des codes QR et des codes barres qui représentent les ID de commande dans les e-mails transactionnels et de ticket de caisse dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7c441-104">This topic explains how to insert QR codes and bar codes that represent order IDs into transactional and receipt emails in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="7c441-105">Vous pouvez facilement inclure des codes QR et des codes barres dans les e-mails transactionnels pour accélérer le processus de recherche de commande dans un environnement de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="7c441-105">You can easily include QR codes and bar codes in transactional emails to help speed up the order lookup process in a retail environment.</span></span> <span data-ttu-id="7c441-106">Pour insérer des codes QR et des codes barres dans des e-mails, vous utilisez une balise HTML **\<img\>** qui demande un code QR ou une image de code barres à un service de génération et d’affichage.</span><span class="sxs-lookup"><span data-stu-id="7c441-106">To insert QR codes and bar codes into emails, you use an HTML **\<img\>** tag that requests a QR code or bar code image from a generation and rendering service.</span></span> <span data-ttu-id="7c441-107">Microsoft ne fournit pas ce service.</span><span class="sxs-lookup"><span data-stu-id="7c441-107">Microsoft doesn't provide this service.</span></span> <span data-ttu-id="7c441-108">Cependant, il existe de nombreux services gratuits ou peu coûteux qui peuvent diffuser des codes QR ou des codes barres générés dynamiquement en fonction d’une valeur transmise dans une chaîne de requête.</span><span class="sxs-lookup"><span data-stu-id="7c441-108">However, there are many free or inexpensive services that can serve QR codes or bar codes that are dynamically generated based on a value that is passed in a query string.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a><span data-ttu-id="7c441-109">Ajouter un code QR ou un code barres dans un e-mail transactionnel</span><span class="sxs-lookup"><span data-stu-id="7c441-109">Add a QR code or bar code to a transactional email</span></span>

<span data-ttu-id="7c441-110">Pour insérer un code QR ou un code barres dans un e-mail transactionnel envoyé dans le cadre d’un achat en ligne, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7c441-110">To insert a QR code or bar code into a transactional email that is sent as part of an e-commerce purchase, follow these steps.</span></span>

1. <span data-ttu-id="7c441-111">Ouvrez le HTML source du modèle d’e-mail transactionnel et ajoutez une balise HTML **\<img\>** qui pointe vers votre code QR ou votre service de code barres.</span><span class="sxs-lookup"><span data-stu-id="7c441-111">Open the source HTML for the transactional email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="7c441-112">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="7c441-112">Here is an example.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    <span data-ttu-id="7c441-113">Voici une explication de l’exemple précédent :</span><span class="sxs-lookup"><span data-stu-id="7c441-113">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="7c441-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** représente le domaine de votre service de code QR ou de code barres.</span><span class="sxs-lookup"><span data-stu-id="7c441-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="7c441-115">**data** représente le paramètre que le service de code QR ou de code barres utilise pour recevoir le contenu qui doit être affiché sous forme de code QR ou de code barres.</span><span class="sxs-lookup"><span data-stu-id="7c441-115">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="7c441-116">La valeur **%salesid%** doit être affectée à ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="7c441-116">The value **%salesid%** must be assigned to this parameter.</span></span> <span data-ttu-id="7c441-117">Dans cet exemple, notez que la valeur est également utilisée comme texte de remplacement pour l’image.</span><span class="sxs-lookup"><span data-stu-id="7c441-117">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="7c441-118">**param1** et **param2** représentent des paramètres facultatifs supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="7c441-118">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="7c441-119">Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Modèles d’e-mail d’organisation** et téléchargez le code HTML mis à jour dans le modèle d’e-mail transactionnel approprié.</span><span class="sxs-lookup"><span data-stu-id="7c441-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the appropriate transactional email template.</span></span>

> [!NOTE]
> <span data-ttu-id="7c441-120">Les paramètres peuvent différer selon les fournisseurs de services de code QR et de code barres.</span><span class="sxs-lookup"><span data-stu-id="7c441-120">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="7c441-121">Par conséquent, assurez-vous de contacter votre fournisseur de services pour confirmer les paramètres auxquels vous devez attribuer des valeurs.</span><span class="sxs-lookup"><span data-stu-id="7c441-121">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a><span data-ttu-id="7c441-122">Ajouter un code QR ou un code barres dans un e-mail de ticket de caisse</span><span class="sxs-lookup"><span data-stu-id="7c441-122">Add a QR code or bar code to a receipt email</span></span> 

<span data-ttu-id="7c441-123">Pour insérer un code QR ou un code barres dans un e-mail de ticket de caisse qui peut être envoyé après un achat effectué au point de vente (PDV), procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7c441-123">To insert a QR code or bar code into a receipt email that can be sent after a purchase is made at the point of sale (POS), follow these steps.</span></span>

1. <span data-ttu-id="7c441-124">Ouvrez le HTML source du modèle d’e-mail de ticket de caisse et ajoutez une balise HTML **\<img\>** qui pointe vers votre code QR ou votre service de code barres.</span><span class="sxs-lookup"><span data-stu-id="7c441-124">Open the source HTML for the receipt email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="7c441-125">Voici un exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7c441-125">Here is an example below.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    <span data-ttu-id="7c441-126">Voici une explication de l’exemple précédent :</span><span class="sxs-lookup"><span data-stu-id="7c441-126">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="7c441-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** représente le domaine de votre service de code QR ou de code barres.</span><span class="sxs-lookup"><span data-stu-id="7c441-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="7c441-128">**data** représente le paramètre que le service de code QR ou de code barres utilise pour recevoir le contenu qui doit être affiché sous forme de code QR ou de code barres.</span><span class="sxs-lookup"><span data-stu-id="7c441-128">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="7c441-129">La valeur **%receiptid%** doit être affectée à ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="7c441-129">The value **%receiptid%** must be assigned to this parameter.</span></span> <span data-ttu-id="7c441-130">Dans cet exemple, notez que la valeur est également utilisée comme texte de remplacement pour l’image.</span><span class="sxs-lookup"><span data-stu-id="7c441-130">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="7c441-131">**param1** et **param2** représentent des paramètres facultatifs supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="7c441-131">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="7c441-132">Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Modèles d’e-mail d’organisation** et téléchargez le code HTML mis à jour dans le modèle d’e-mail dont l’ID est **emailrecpt**.</span><span class="sxs-lookup"><span data-stu-id="7c441-132">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the email template that has the email ID **emailrecpt**.</span></span>

> [!NOTE]
> <span data-ttu-id="7c441-133">Les paramètres peuvent différer selon les fournisseurs de services de code QR et de code barres.</span><span class="sxs-lookup"><span data-stu-id="7c441-133">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="7c441-134">Par conséquent, assurez-vous de contacter votre fournisseur de services pour confirmer les paramètres auxquels vous devez attribuer des valeurs.</span><span class="sxs-lookup"><span data-stu-id="7c441-134">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7c441-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7c441-135">Additional resources</span></span>

[<span data-ttu-id="7c441-136">Envoyer des accusés de réception par e-mail depuis MPOS</span><span class="sxs-lookup"><span data-stu-id="7c441-136">Send email receipts from Modern POS (MPOS)</span></span>](email-receipts.md)

[<span data-ttu-id="7c441-137">Créer des modèles de messages électroniques pour les événements transactionnels</span><span class="sxs-lookup"><span data-stu-id="7c441-137">Create email templates for transactional events</span></span>](email-templates-transactions.md)
