---
title: Activer les notifications d'enregistrement des clients dans le point de vente (PDV)
description: Cette rubrique décrit comment activer les notifications d'enregistrement des clients dans le point de vente (PDV) Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e4defc15d9ef198a361934d51e31016747dbb5ab
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937582"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a><span data-ttu-id="21a1a-103">Activer les notifications d'enregistrement des clients dans le point de vente (PDV)</span><span class="sxs-lookup"><span data-stu-id="21a1a-103">Enable customer check-in notifications in point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="21a1a-104">Cette rubrique décrit comment activer les notifications d'enregistrement des clients dans le point de vente (PDV) Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="21a1a-104">This topic describes how to enable customer check-in notifications in Microsoft Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="21a1a-105">Dans leurs e-mails « commande prête à être ramassée », les organisations peuvent fournir un lien ou un bouton permettant aux clients d'informer le magasin qu'ils sont sur place et qu'ils attendent que leur colis leur soit apporté.</span><span class="sxs-lookup"><span data-stu-id="21a1a-105">In their "order ready for pickup" emails, organizations can provide a link or button that lets customers notify the store that they are on the premises and waiting for their package to be brought out to them.</span></span> <span data-ttu-id="21a1a-106">Les clients reçoivent ensuite une confirmation d'enregistrement et le magasin reçoit une notification en tant que tâche dans son application de point de vente.</span><span class="sxs-lookup"><span data-stu-id="21a1a-106">Customers then receive a check-in confirmation, and the store receives a notification as a task in its POS application.</span></span> <span data-ttu-id="21a1a-107">Cette tâche permet à un vendeur de livrer la commande au véhicule du client.</span><span class="sxs-lookup"><span data-stu-id="21a1a-107">This task serves as a prompt for a sales associate to deliver the order to the customer's vehicle.</span></span> <span data-ttu-id="21a1a-108">Par conséquent, le client n'a pas à entrer dans le magasin.</span><span class="sxs-lookup"><span data-stu-id="21a1a-108">Therefore, the customer doesn't have to enter the store.</span></span>

<span data-ttu-id="21a1a-109">Le workflow d'enregistrement des clients peut également être configuré pour collecter des informations supplémentaires, telles que le numéro de place de parking du client, la marque, le modèle et la couleur de son véhicule et les instructions de livraison.</span><span class="sxs-lookup"><span data-stu-id="21a1a-109">The customer check-in workflow can also be configured to collect additional information from customers, such as their parking spot number, the make, model, and color of their vehicle, and delivery instructions.</span></span> <span data-ttu-id="21a1a-110">Le préposé au magasin peut utiliser ces informations pour faciliter l'exécution des commandes.</span><span class="sxs-lookup"><span data-stu-id="21a1a-110">The retail store attendant can use this information to facilitate order fulfillment.</span></span>

## <a name="enable-customer-check-in"></a><span data-ttu-id="21a1a-111">Activer l'enregistrement client</span><span class="sxs-lookup"><span data-stu-id="21a1a-111">Enable customer check-in</span></span>

<span data-ttu-id="21a1a-112">Lorsque la fonction d'enregistrement client est activée, Commerce génère un ID de confirmation de commande (également appelé ID de référence de canal).</span><span class="sxs-lookup"><span data-stu-id="21a1a-112">When the customer check-in feature is turned on, Commerce generates an order confirmation ID (also known as the channel reference ID).</span></span> <span data-ttu-id="21a1a-113">Il génère également des ID de confirmation de commande pour les commandes créées via des points de vente (PDV) ou des canaux de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="21a1a-113">It also generates order confirmation IDs for orders that are created through point of sale (POS) or call center channels.</span></span> 

<span data-ttu-id="21a1a-114">Pour activer la fonctionnalité d'enregistrement des clients dans Commerce Headquarters, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="21a1a-114">To turn on the customer check-in feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="21a1a-115">Accédez à **Espaces de travail \> Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="21a1a-115">Go to **Workspaces \> Feature management**.</span></span>
2. <span data-ttu-id="21a1a-116">Recherchez la fonctionnalité **Générer un format d'identifiant de référence de canal cohérent sur tous les canaux**.</span><span class="sxs-lookup"><span data-stu-id="21a1a-116">Search for the **Generate a consistent channel reference ID format across channels** feature.</span></span> 
3. <span data-ttu-id="21a1a-117">Sélectionnez la fonctionnalité, puis, dans le volet des propriétés, sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="21a1a-117">Select the feature, and then select **Enable now** in the properties pane.</span></span> 

## <a name="create-a-check-in-confirmation-page"></a><span data-ttu-id="21a1a-118">Créer une page de confirmation d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="21a1a-118">Create a check-in confirmation page</span></span>

<span data-ttu-id="21a1a-119">Sur votre site de commerce électronique, vous devez créer une nouvelle page qui servira pour confirmer l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="21a1a-119">On your e-commerce site, you must create a new page that will serve as the check-in confirmation experience.</span></span> <span data-ttu-id="21a1a-120">Grâce à une configuration supplémentaire, la page peut également inclure un formulaire qui recueille d'autres informations auprès des clients pour faciliter l'exécution des commandes.</span><span class="sxs-lookup"><span data-stu-id="21a1a-120">Through additional configuration, the page can also include a form that collects additional information from customers to facilitate order fulfillment.</span></span> <span data-ttu-id="21a1a-121">Pour plus d'informations sur la configuration de la page et du module, voir [Module d'enregistrement client](check-in-pickup-module.md).</span><span class="sxs-lookup"><span data-stu-id="21a1a-121">For information about how to set up the page and module, see [Customer check-in module](check-in-pickup-module.md).</span></span>

## <a name="configure-the-transactional-email-template"></a><span data-ttu-id="21a1a-122">Configurer le modèle d'e-mail transactionnel</span><span class="sxs-lookup"><span data-stu-id="21a1a-122">Configure the transactional email template</span></span>

<span data-ttu-id="21a1a-123">Vous devez ajouter un lien ou bouton **Je suis là** vers le modèle pour l'e-mail transactionnel que les clients reçoivent lorsque leur commande est prête pour le retrait.</span><span class="sxs-lookup"><span data-stu-id="21a1a-123">You must add an **I am here** link or button to the template for the transactional email that customers receive when their order is ready for pickup.</span></span> <span data-ttu-id="21a1a-124">Les clients utiliseront ce lien ou bouton pour informer le magasin qu'ils sont là pour récupérer leur commande.</span><span class="sxs-lookup"><span data-stu-id="21a1a-124">Customers will use this link or button to notify the store that they have arrived to pick up their order.</span></span> 

<span data-ttu-id="21a1a-125">Ajoutez le lien ou le bouton au modèle mappé sur le type de notification **Emballage terminé** et le mode de livraison que vous utilisez pour l'exécution des commandes en retrait à un point-relais.</span><span class="sxs-lookup"><span data-stu-id="21a1a-125">Add the link or button to the template that is mapped to the **Packing completed** notification type and the mode of delivery that you're using for curbside order fulfillment.</span></span> <span data-ttu-id="21a1a-126">Dans le modèle, créez un lien ou un bouton HTML qui pointe vers l'URL de la page de confirmation d'enregistrement que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="21a1a-126">In the template, create an HTML link or button that points to the URL of the check-in confirmation page that you created.</span></span> <span data-ttu-id="21a1a-127">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="21a1a-127">Here is an example.</span></span>

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
<span data-ttu-id="21a1a-128">Pour plus d'informations sur la configuration des modèles d'e-mail, consultez [Personnaliser les e-mails transactionnels par mode de livraison](customize-email-delivery-mode.md).</span><span class="sxs-lookup"><span data-stu-id="21a1a-128">For more information about how to configure email templates, see [Customize transactional emails by mode of delivery](customize-email-delivery-mode.md).</span></span> 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a><span data-ttu-id="21a1a-129">Une tâche de confirmation d'enregistrement est créée dans le PDV</span><span class="sxs-lookup"><span data-stu-id="21a1a-129">A check-in confirmation task is created in POS</span></span>

<span data-ttu-id="21a1a-130">Une fois qu'un client a informé le magasin qu'il est présent pour le retrait, il reçoit une notification de confirmation d'enregistrement et une tâche est créée dans la liste des tâches dans le PDV du magasin où le client récupère la commande.</span><span class="sxs-lookup"><span data-stu-id="21a1a-130">After a customer notifies the store that they are present for pickup, they receive a check-in confirmation notification, and a task is created in the tasks list in POS for the store where the customer is picking up the order.</span></span> <span data-ttu-id="21a1a-131">La tâche contient toutes les informations sur le client et la commande nécessaires pour exécuter la commande.</span><span class="sxs-lookup"><span data-stu-id="21a1a-131">The task contains all the customer and order information that is required to fulfill the order.</span></span> <span data-ttu-id="21a1a-132">Dans la tâche, le champ d'instructions affiche toutes les informations collectées auprès du client via le formulaire d'informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="21a1a-132">In the task, the instructions field shows any information that was collected from the customer through the additional information form.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="21a1a-133">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="21a1a-133">Additional resources</span></span>

[<span data-ttu-id="21a1a-134">Module Enregistrement pour retrait</span><span class="sxs-lookup"><span data-stu-id="21a1a-134">Check-in for pickup module</span></span>](check-in-pickup-module.md)
