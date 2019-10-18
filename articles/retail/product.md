---
title: Recommandations produit sur le PDV
description: Cette rubrique décrit l'utilisation de recommandations de produit sur un appareil de PDV.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c78fc1f2f1bb08d01828a8b71ad5d3c16ad31b86
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278376"
---
# <a name="product-recommendations-on-pos"></a><span data-ttu-id="9f798-103">Recommandations produit sur le PDV</span><span class="sxs-lookup"><span data-stu-id="9f798-103">Product recommendations on POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9f798-104">Les recommandations de produit sont essentiellement une application métier transformative qui s'étend dans tous les espaces de la vente au détail pour créer des expériences de découverte de produit taillées sur mesure, stimulantes et riches.</span><span class="sxs-lookup"><span data-stu-id="9f798-104">At its core, product Recommendations are a transformative business application that span across all retail spaces to create rich, engaging, and tailored product discovery experiences.</span></span> <span data-ttu-id="9f798-105">Pour implémenter cette fonctionnalité au PDV, suivez les étapes [comment ajouter des recommandations à vos périphériques de PDV.](add-recommendations-control-pos-screen.md)</span><span class="sxs-lookup"><span data-stu-id="9f798-105">To implement this feature on POS, follow the steps on [how to add recommendations to your POS devices.](add-recommendations-control-pos-screen.md)</span></span> 

<span data-ttu-id="9f798-106">Pour en savoir plus sur les fonctionnalités de recommandations produit, consultez la [vue d'ensemble des recommandations produit.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="9f798-106">For more information about product recommendations features, read the [product recommendations overview.](../commerce/product-recommendations.md)</span></span> 

## <a name="scenarios"></a><span data-ttu-id="9f798-107">Scénarios</span><span class="sxs-lookup"><span data-stu-id="9f798-107">Scenarios</span></span>

<span data-ttu-id="9f798-108">Les recommandations de produit sont activées pour les scénarios de PDV suivants.</span><span class="sxs-lookup"><span data-stu-id="9f798-108">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="9f798-109">Elles sont disponibles dans le Cloud POS ou Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="9f798-109">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1. <span data-ttu-id="9f798-110">Sur la page **Détails de produit** :</span><span class="sxs-lookup"><span data-stu-id="9f798-110">On the **Product details** page:</span></span>

    - <span data-ttu-id="9f798-111">• Si un associé du magasin visite une page **Détails de produit** lorsque vous regardez des transactions antérieures sur différents canaux, le service de recommandation propose des éléments supplémentaires susceptibles d'être achetés ensemble.</span><span class="sxs-lookup"><span data-stu-id="9f798-111">• If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendations service suggests additional items that are likely to be purchased together.</span></span>

    <span data-ttu-id="9f798-112">[![Recommandations sur la page de Détails du produit](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="9f798-112">[![Recommendations on the Product details page](./media/proddetails.png)](./media/proddetails.png)</span></span>

2. <span data-ttu-id="9f798-113">Sur la page **Transaction** :</span><span class="sxs-lookup"><span data-stu-id="9f798-113">On the **Transaction** page:</span></span>

    - <span data-ttu-id="9f798-114">• Le moteur de recommandation suggère des articles selon la liste entière d'articles du panier qui sont fréquemment achetés ensemble.</span><span class="sxs-lookup"><span data-stu-id="9f798-114">• The recommendation engine suggests items based on the entire list of items in the basket that are frequently bought together.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9f798-115">Pour afficher les recommandations sur la page **Transaction**, le détaillant doit actualiser la mise en page de l'écran dans Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="9f798-115">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="9f798-116">Le contrôle **Recommandations** doit être déposé sur la page **Transaction**.</span><span class="sxs-lookup"><span data-stu-id="9f798-116">The **Recommendations** control must be dropped onto the **Transaction** page.</span></span>

    <span data-ttu-id="9f798-117">[![Recommandations sur la page Transaction](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="9f798-117">[![Recommendations on the Transaction page](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

## <a name="configure-dynamics-365-retail-to-enable-pos-recommendations"></a><span data-ttu-id="9f798-118">Configurer Dynamics 365 Retail pour activer les recommandations de PDV</span><span class="sxs-lookup"><span data-stu-id="9f798-118">Configure Dynamics 365 Retail to enable POS recommendations</span></span>

<span data-ttu-id="9f798-119">Pour paramétrer les recommandations de produit, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9f798-119">To set up product recommendations, follow these steps:</span></span>

1. <span data-ttu-id="9f798-120">Veillez à ce que votre service ait été mis à jour avec la **version 10.0.6.**</span><span class="sxs-lookup"><span data-stu-id="9f798-120">Ensure your service has been updated to the **10.0.6 build.**</span></span>
2. <span data-ttu-id="9f798-121">Suivez les instructions sur la procédure pour [activer les recommandations de produit](../commerce/enable-product-recommendations.md) pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="9f798-121">Follow the instructions on how to [enable product recommendations](../commerce/enable-product-recommendations.md) for your business.</span></span>
3. <span data-ttu-id="9f798-122">Facultatif : Pour afficher les recommandations dans l'écran de transaction, allez dans **Mise en page de l'écran**, choisissez une mise en page d'écran, lancez le **Concepteur de mise en page de l'écran**, puis faites glisser-déplacer le contrôle de **recommandations** à l'emplacement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9f798-122">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>
4. <span data-ttu-id="9f798-123">Accédez à **Paramètres des ventes au détail**, sélectionnez **Machine-learning**, sélectionnez **Oui** sous **Accepter des recommandations de PDV**.</span><span class="sxs-lookup"><span data-stu-id="9f798-123">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5. <span data-ttu-id="9f798-124">Pour afficher les recommandations sur le PDV, exécutez une tâche de configuration globale **1110**.</span><span class="sxs-lookup"><span data-stu-id="9f798-124">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="9f798-125">Pour refléter les modifications effectuées dans le concepteur de mise en page de l'écran du PDV, exécutez la tâche de configuration des canaux **1070**.</span><span class="sxs-lookup"><span data-stu-id="9f798-125">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>



## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="9f798-126">Résoudre les problèmes que vous rencontrez lorsque vous avez des recommandations produit déjà activées</span><span class="sxs-lookup"><span data-stu-id="9f798-126">Troubleshoot issues where you have Product recommendations already enabled</span></span>

- <span data-ttu-id="9f798-127">Accédez à **Paramètres Retail** \> **Listes de recommandation** \> **Désactiver les recommandations produit** et exécutez **Tâche de configuration globale \[9999\]**.</span><span class="sxs-lookup"><span data-stu-id="9f798-127">Navigate to **Retail Parameters** \> **Recommendation lists** \> **Disable product recommendations** and run **Global configuration job \[9999\]**.</span></span> 
- <span data-ttu-id="9f798-128">Si vous avez ajouté le **Contrôle de recommandations** à votre écran de transaction à l'aide du **Concepteur de mise en page de l'écran**, supprimez-le également.</span><span class="sxs-lookup"><span data-stu-id="9f798-128">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span>
- <span data-ttu-id="9f798-129">Si vous avez des questions supplémentaires, vérifiez [FAQ de recommandations](../commerce/faq-recommendations.md) pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="9f798-129">If you have additional questions, check out the [Recommendations FAQ](../commerce/faq-recommendations.md) for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f798-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9f798-130">Additional resources</span></span>

<span data-ttu-id="9f798-131">[Ajouter un contrôle de recommandations à la page de transaction sur un périphérique de PDV](add-recommendations-control-pos-screen.md)
[Vue d'ensemble des recommandations de produit](../commerce/product-recommendations.md)
[Activer les recommandations de produit](../commerce/enable-product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="9f798-131">[Add a recommendations control to the transaction page on a POS device](add-recommendations-control-pos-screen.md)
[Product recommendations overview](../commerce/product-recommendations.md)
[Enable product recommendations](../commerce/enable-product-recommendations.md)</span></span> 
