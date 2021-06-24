---
title: Retour de produits contrôlés par numéro de série dans le PDV
description: Cette rubrique décrit les fonctionnalités de validation des articles à numéro de série dans le cadre du processus de retour dans l’application de point de vente (PDV) de Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7a067994828f3df577c0dc4146d26ac81990d4ac
ms.sourcegitcommit: 927574c77f4883d906e5c7bddf0af9b717e492bf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129807"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a><span data-ttu-id="5c914-103">Retour de produits contrôlés par numéro de série dans le PDV</span><span class="sxs-lookup"><span data-stu-id="5c914-103">Return serial number–controlled products in POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="5c914-104">Cette rubrique décrit les fonctionnalités de validation des articles à numéro de série dans le cadre du processus de retour dans l’application de point de vente (PDV) de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5c914-104">This topic describes the capabilities for validating serialized items as part of the return process in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

> [!NOTE]
> <span data-ttu-id="5c914-105">Dans les versions 10.0.20 et ultérieures de Commerce, une nouvelle fonctionnalité nommée **Expérience unifiée du traitement des retours dans la PDV** est disponible.</span><span class="sxs-lookup"><span data-stu-id="5c914-105">In the Commerce version 10.0.20 release and later, a new feature that is named **Unified return processing experience in POS** is available.</span></span> <span data-ttu-id="5c914-106">Pour utiliser la validation du numéro de série lors du traitement des retours dans le PDV, vous devez activer cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="5c914-106">To use serial number validation during return order processing in POS, you must turn on this feature.</span></span> <span data-ttu-id="5c914-107">Pour plus d’informations sur les autres possibilités de cette fonctionnalité lorsqu’elle est activée, voir [Créer des retours dans le PDV](POS-returns.md).</span><span class="sxs-lookup"><span data-stu-id="5c914-107">For information about others capabilities that this feature provides when it's turned on, see [Create returns in POS)](POS-returns.md).</span></span>
>
> <span data-ttu-id="5c914-108">Une fois la fonctionnalité activée, elle ne peut pas être désactivée.</span><span class="sxs-lookup"><span data-stu-id="5c914-108">After the feature is turned on, it can't be turned off.</span></span>

## <a name="options-for-validating-serialized-returns"></a><span data-ttu-id="5c914-109">Options de validation des retours à numéro de série</span><span class="sxs-lookup"><span data-stu-id="5c914-109">Options for validating serialized returns</span></span>

<span data-ttu-id="5c914-110">Quand la fonctionnalité **Expérience unifiée du traitement des retours dans le PDV** est activée, les organisations peuvent réaliser la validation des retours d’articles contrôlés par numéro de série via le PDV.</span><span class="sxs-lookup"><span data-stu-id="5c914-110">When the **Unified return processing experience in POS** feature is turned on, organizations can perform a validation on returns of serial number–controlled items through POS.</span></span> <span data-ttu-id="5c914-111">Cette fonctionnalité peut avertir les utilisateurs si le numéro de série renvoyé diffère du numéro de série d’origine qui a été vendu.</span><span class="sxs-lookup"><span data-stu-id="5c914-111">This capability can warn users if the serial number that is being returned differs from the original serial number that was sold.</span></span> <span data-ttu-id="5c914-112">Dans la version 10.0.20 et les versions ultérieures de Commerce, le message que les utilisateurs reçoivent est uniquement un message d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="5c914-112">In the Commerce version 10.0.20 release and later, the message that users receive is only a warning message.</span></span> <span data-ttu-id="5c914-113">Les utilisateurs peuvent continuer à traiter un retour avec un numéro de série différent du numéro de série initialement vendu.</span><span class="sxs-lookup"><span data-stu-id="5c914-113">Users can continue to process a return against a serial number that differs from the serial number that was originally sold.</span></span>

<span data-ttu-id="5c914-114">Pour configurer la validation du numéro de série d’une organisation après avoir activé la fonctionnalité **Expérience unifiée du traitement des retours dans le PDV**, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres de Commerce** dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="5c914-114">To configure serial number validation for an organization after the **Unified return processing experience in POS** feature is turned on, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters** in Commerce headquarters.</span></span> <span data-ttu-id="5c914-115">Sur l’onglet **Stock**, dans le raccourci **Opérations de stock du magasin**, définissez l’option **Activer la validation des numéros de série sur les retours au PDV** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="5c914-115">On the **Inventory** tab, on the **Store inventory operations** FastTab, set the **Enable validation of serial numbers on POS returns** option to **Yes**.</span></span>

## <a name="process-returns-for-serialized-items-in-pos"></a><span data-ttu-id="5c914-116">Traiter les retours d’articles à numéro de série dans le PDV</span><span class="sxs-lookup"><span data-stu-id="5c914-116">Process returns for serialized items in POS</span></span>

<span data-ttu-id="5c914-117">Si l’option **Activer la validation des numéros de série sur les retours au PDV** a été définie sur **Oui**, lorsqu’un article contrôlé par numéro de série est retourné via le PDV, l’utilisateur peut saisir le numéro de série pour la ligne de retour dans le volet des détails de la page **Produits retournables**.</span><span class="sxs-lookup"><span data-stu-id="5c914-117">If the **Enable validation of serial numbers on POS returns** option has been set to **Yes**, when a serial number–controlled item is returned through POS, the user can enter the serial number for the return line in the details pane on the **Returnable products** page.</span></span> <span data-ttu-id="5c914-118">Si le numéro de série entré ne correspond pas au numéro de série d’origine qui a été vendu lors de la transaction de vente, l’utilisateur reçoit un message d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="5c914-118">If the serial number that is entered doesn't match the original serial number that was sold for the sales transaction, the user receives a warning message.</span></span> <span data-ttu-id="5c914-119">Cependant, l’application n’empêche pas l’utilisateur de continuer à valider le retour.</span><span class="sxs-lookup"><span data-stu-id="5c914-119">However, the application doesn't prevent the user from continuing to post the return.</span></span>

> [!NOTE]
> <span data-ttu-id="5c914-120">Actuellement, le PDV prend en charge la validation des numéros de série uniquement sur les lignes de retour où la quantité commandée d’origine n’est pas supérieure à un.</span><span class="sxs-lookup"><span data-stu-id="5c914-120">Currently, POS supports validation of serial numbers only on return lines where the original ordered quantity is no more than one.</span></span> <span data-ttu-id="5c914-121">Si la ligne de la commande client d’origine a été créée dans un canal autre que le PDV et si la quantité commandée pour l’article à numéro de série sur une ligne de vente donnée est supérieure à un, l’article ne peut pas être correctement retourné via le PDV.</span><span class="sxs-lookup"><span data-stu-id="5c914-121">If the original sales order line was created in a non-POS channel, and if the quantity that was ordered for the serialized item on a given sales line is more than one, the item can't be correctly returned through POS.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5c914-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5c914-122">Additional resources</span></span>

[<span data-ttu-id="5c914-123">Créer des retours dans le PDV</span><span class="sxs-lookup"><span data-stu-id="5c914-123">Create returns in POS</span></span>](POS-returns.md)
