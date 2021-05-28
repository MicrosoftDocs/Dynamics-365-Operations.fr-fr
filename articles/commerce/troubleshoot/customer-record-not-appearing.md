---
title: Les enregistrements client ne s’affichent pas dans Commerce Headquarters
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque les enregistrements client ne s’affichent pas immédiatement dans Commerce Headquarters.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b8d065dd104df616ba8f10f7813e74c900fdcf77
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018480"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a><span data-ttu-id="c93a8-103">Les enregistrements client ne s’affichent pas dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="c93a8-103">Customer records don't appear in Commerce headquarters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c93a8-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque les enregistrements client ne s’affichent pas immédiatement dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="c93a8-104">This topic provides troubleshooting guidance that can help when customer records don't immediately appear in Commerce headquarters.</span></span>

## <a name="description"></a><span data-ttu-id="c93a8-105">Description</span><span class="sxs-lookup"><span data-stu-id="c93a8-105">Description</span></span>

<span data-ttu-id="c93a8-106">Lorsque vous créez un enregistrement client à l’aide du flux d’inscription dans la vitrine d’e-commerce, l’enregistrement client correspondant ne s’affiche pas immédiatement dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="c93a8-106">When you create a new customer record by using the sign-up flow in the e-commerce storefront, the corresponding customer record doesn't immediately appear in Commerce headquarters.</span></span>

## <a name="resolution"></a><span data-ttu-id="c93a8-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="c93a8-107">Resolution</span></span>

### <a name="disable-customer-creation-in-async-mode"></a><span data-ttu-id="c93a8-108">Désactiver la création de client en mode asynchrone</span><span class="sxs-lookup"><span data-stu-id="c93a8-108">Disable customer creation in async mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c93a8-109">Si vous désactivez la création de client asynchrone, les performances du système peuvent être affectées, car la création de chaque enregistrement produit une demande en temps réel à Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="c93a8-109">If you disable asynchronous customer creation, system performance could be affected, because creation of each record will produce a real-time request to Commerce headquarters.</span></span> <span data-ttu-id="c93a8-110">De plus, si Commerce Headquarters n’est pas opérationnel (par exemple, pendant les flux de maintenance), tout nouveau flux de création client produira des erreurs.</span><span class="sxs-lookup"><span data-stu-id="c93a8-110">In addition, if Commerce headquarters is down (for example, during servicing flows), any new customer creation flows will produce errors.</span></span>

<span data-ttu-id="c93a8-111">Pour désactiver la création de client en mode asynchrone dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c93a8-111">To disable customer creation in async mode in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c93a8-112">Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage du magasin en ligne \> Profils de fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="c93a8-112">Go to **Retail and Commerce \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="c93a8-113">Si vous n’utilisez pas encore de profil de fonctionnalité pour votre canal en ligne, créez-en un.</span><span class="sxs-lookup"><span data-stu-id="c93a8-113">If you aren't already using a functionality profile for your online channel, create one.</span></span>
1. <span data-ttu-id="c93a8-114">Assurez-vous que l’option **Créer un client en mode asynchrone** est définie sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="c93a8-114">Make sure that the **Create customer in async mode** option is set to **No**.</span></span>
1. <span data-ttu-id="c93a8-115">Accédez à **Commerce et vente au détail \> Canaux \> Magasins en ligne**.</span><span class="sxs-lookup"><span data-stu-id="c93a8-115">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="c93a8-116">Sélectionnez la boutique en ligne pour laquelle désactiver la création de clients asynchrones.</span><span class="sxs-lookup"><span data-stu-id="c93a8-116">Select the online store to disable asynchronous customer creation for.</span></span>
1. <span data-ttu-id="c93a8-117">Sur l’onglet **Général**, assurez-vous que le champ **Profil de fonctionnalité** est défini sur le profil de fonctionnalité que vous utilisez pour votre canal en ligne.</span><span class="sxs-lookup"><span data-stu-id="c93a8-117">On the **General** tab, make sure that the **Functionality profile** field is set to the functionality profile that you're using for your online channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c93a8-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c93a8-118">Additional resources</span></span>

[<span data-ttu-id="c93a8-119">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="c93a8-119">Setup a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
