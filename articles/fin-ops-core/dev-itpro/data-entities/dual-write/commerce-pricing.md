---
title: Utilisez le moteur de tarification Dynamics 365 Commerce avec Dynamics 365 Sales
description: Cette rubrique décrit comment utiliser le moteur de tarification dans Microsoft Dynamics 365 Commerce pour créer des devis de vente dans Dynamics 365 Sales.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: fad5c21d75db62b85efe803f1667dd3f9164a5fc
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594916"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a><span data-ttu-id="0f551-103">Utilisez le moteur de tarification Dynamics 365 Commerce avec Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="0f551-103">Use the Dynamics 365 Commerce pricing engine with Dynamics 365 Sales</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0f551-104">Cette rubrique décrit comment utiliser le moteur de tarification dans Microsoft Dynamics 365 Commerce pour créer des devis de vente dans Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0f551-104">This topic describes how to use the Microsoft Dynamics 365 Commerce pricing engine to create sales quotations in Dynamics 365 Sales.</span></span>

<span data-ttu-id="0f551-105">Le moteur de tarification Dynamics 365 Commerce prend en charge la plupart des scénarios de tarification d’entreprise à consommateur (B2C), tels que la tarification au niveau du magasin, la tarification basée sur l’affiliation et la fidélité, les remises mix-and-match, les remises sur quantité et les remises sur seuil.</span><span class="sxs-lookup"><span data-stu-id="0f551-105">The Dynamics 365 Commerce pricing engine supports most business-to-consumer (B2C) pricing scenarios, such as store-level pricing, affiliation-based and loyalty-based pricing, mix-and-match discounts, quantity discounts, and threshold discounts.</span></span> <span data-ttu-id="0f551-106">Le moteur de tarification utilise des règles complexes pour déterminer le meilleur prix pour une offre ou une commande donnée.</span><span class="sxs-lookup"><span data-stu-id="0f551-106">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span>

<span data-ttu-id="0f551-107">Lorsque vous utilisez la [double écriture](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), vous avez trois options pour vos besoins de tarification.</span><span class="sxs-lookup"><span data-stu-id="0f551-107">When you use [dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), you have three options for your pricing needs.</span></span> <span data-ttu-id="0f551-108">Vous pouvez utiliser la tarification statique issue de la liste de prix dans Dynamics 365 Sales, le moteur de tarification dans Dynamics 365 Supply Chain Management, ou le moteur de tarification dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f551-108">You can use the static pricing that comes from the price list in Dynamics 365 Sales, the pricing engine in Dynamics 365 Supply Chain Management, or the pricing engine in Dynamics 365 Commerce.</span></span> <span data-ttu-id="0f551-109">Parmi ces options, le moteur de tarification Commerce est le mieux adapté aux scénarios B2C.</span><span class="sxs-lookup"><span data-stu-id="0f551-109">Among these options, the Commerce pricing engine is best suited to B2C scenarios.</span></span>

## <a name="use-the-commerce-pricing-engine-in-sales"></a><span data-ttu-id="0f551-110">Utiliser le moteur de tarification Commerce dans Sales</span><span class="sxs-lookup"><span data-stu-id="0f551-110">Use the Commerce pricing engine in Sales</span></span>

> [!NOTE]
> <span data-ttu-id="0f551-111">Actuellement, le moteur de tarification Commerce ne peut être utilisé que pour la création de devis dans Sales.</span><span class="sxs-lookup"><span data-stu-id="0f551-111">Currently, the Commerce pricing engine can be used only for quotation creation in the Sales.</span></span> <span data-ttu-id="0f551-112">L’intégration des commandes client avec le moteur de tarification Commerce n’est pas encore disponible.</span><span class="sxs-lookup"><span data-stu-id="0f551-112">Sales order integration with the Commerce pricing engine isn't yet available.</span></span>

<span data-ttu-id="0f551-113">Lorsque les utilisateurs lancent un devis dans Sales, la structure à double écriture copie les détails du devis dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f551-113">When users initiate a quotation in Sales, the dual-write framework copies the quotation details to Commerce.</span></span> <span data-ttu-id="0f551-114">Toutes les modifications apportées aux lignes de devis existantes ou aux lignes de devis nouvellement ajoutées dans Sales sont copiées dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f551-114">Any changes to existing quotation lines or any newly added quotation lines in Sales are copied to Commerce.</span></span> <span data-ttu-id="0f551-115">Lorsque les utilisateurs souhaitent utiliser le moteur de tarification Commerce pour fixer le prix du devis, ils peuvent sélectionner **Devis** pour mettre à jour les prix du devis, en fonction du moteur de tarification Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f551-115">When users want to use the Commerce pricing engine to price the quotation, they can select **Price quote** to update the prices of the quotation, based on the Commerce pricing engine.</span></span> <span data-ttu-id="0f551-116">Les prix sont ensuite automatiquement mis à jour dans Sales et Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f551-116">Prices are then automatically updated in both Sales and Commerce.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f551-117">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="0f551-117">Prerequisites</span></span>

- <span data-ttu-id="0f551-118">Avant de pouvoir utiliser le moteur de tarification Commerce dans Sales, vous devez suivre les étapes dans [Prospect en disponibilités en double écriture](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).</span><span class="sxs-lookup"><span data-stu-id="0f551-118">Before you can use the Commerce pricing engine in Sales, you must follow the steps in [Prospect-to-cash in dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).</span></span>
- <span data-ttu-id="0f551-119">Vous devez désactiver l’évaluation des accords commerciaux pour la saisie manuelle en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="0f551-119">You must turn off trade agreement evaluation for manual entry by following these steps:</span></span>

    1. <span data-ttu-id="0f551-120">Dans votre environnement Commerce, accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="0f551-120">In your Commerce environment, go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    1. <span data-ttu-id="0f551-121">Sur l’onglet **Prix**, sur le raccourci **Évaluation des accords commerciaux**, décochez la case **Saisie manuelle**.</span><span class="sxs-lookup"><span data-stu-id="0f551-121">On the **Prices** tab, on the **Trade agreement evaluation** FastTab, clear the **Manual entry** check box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f551-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0f551-122">Additional resources</span></span>

[<span data-ttu-id="0f551-123">Prospect en disponibilités en double écriture</span><span class="sxs-lookup"><span data-stu-id="0f551-123">Prospect-to-cash in dual-write</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/)
