---
title: Groupes de créditer du client
description: Cette rubrique fournit des informations sur les groupes de crédits client.
author: mikefalkner
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3cdf4f7e72a55292c64b7a9191974242aab85a90
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835314"
---
# <a name="customer-credit-groups"></a><span data-ttu-id="435a1-103">Groupes de créditer du client</span><span class="sxs-lookup"><span data-stu-id="435a1-103">Customer credit groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="435a1-104">Vous pouvez définir des groupes de clients qui ont une limite de crédit partagée.</span><span class="sxs-lookup"><span data-stu-id="435a1-104">You can define groups of customers who have a shared credit limit.</span></span> <span data-ttu-id="435a1-105">La limite de crédit individuelle définie sur le compte de facture client est également prise en compte.</span><span class="sxs-lookup"><span data-stu-id="435a1-105">The individual credit limit that is defined on the customer invoice account is also considered.</span></span>

<span data-ttu-id="435a1-106">Les membres d’un groupe de crédits client peuvent être sélectionnés parmi différentes entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="435a1-106">Members of a customer credit group can be selected from different legal entities.</span></span> <span data-ttu-id="435a1-107">Lorsque vous ajoutez un client à la liste des clients du groupe de crédits client, la date d’expiration de la limite de crédit pour chaque client est remplacée par la date d’expiration affectée au groupe.</span><span class="sxs-lookup"><span data-stu-id="435a1-107">When you add a customer to the list of customers in the customer credit group, the expiration date of the credit limit for each customer is changed to the expiration date that is assigned to the group.</span></span>

<span data-ttu-id="435a1-108">Vous pouvez configurer des groupes de crédits client sur la page **Groupes de crédit client** (**Gestion de crédit \> Groupes de crédits client \> Groupes de crédits client**).</span><span class="sxs-lookup"><span data-stu-id="435a1-108">You can set up customer credit groups on the **Customer credit groups** page (**Credit management \> Customer credit groups \> Customer credit groups**).</span></span>

1. <span data-ttu-id="435a1-109">Dans les champs **Numéro du groupe** et **Description**, entrez un identificateur et une description pour le groupe.</span><span class="sxs-lookup"><span data-stu-id="435a1-109">In the **Group number** and **Description** fields, enter an identifier and description for the group.</span></span>
2. <span data-ttu-id="435a1-110">Dans les champs **Limite de crédit** et **Devise**, entrez la limite de crédit et la devise à utiliser lorsque le système vérifie la limite de crédit pour tout membre du groupe.</span><span class="sxs-lookup"><span data-stu-id="435a1-110">In the **Credit limit** and **Currency** fields, enter the credit limit and currency that should be used when the system checks the credit limit for any member of the group.</span></span>
3. <span data-ttu-id="435a1-111">Dans le champ **Limite de crédit à ce jour**, entrez la date d’expiration de la limite de crédit.</span><span class="sxs-lookup"><span data-stu-id="435a1-111">In the **Credit limit to date** field, enter the date when the credit limit expires.</span></span> <span data-ttu-id="435a1-112">Les groupes de crédit client doivent avoir une date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="435a1-112">Customer credit groups must have an expiration date.</span></span>

<span data-ttu-id="435a1-113">Une fois la configuration d’un groupe de crédits client terminée, vous pouvez y ajouter des clients en spécifiant leur entité juridique et leur ID de compte client.</span><span class="sxs-lookup"><span data-stu-id="435a1-113">After you've finished setting up a customer credit group, you can add customers to it by specifying their legal entity and customer account ID.</span></span> <span data-ttu-id="435a1-114">Lorsque vous ajoutez un nouveau client à un groupe de crédits client, le système recherche le même compte client dans toutes les entités juridiques et vous invite à l’ajouter au groupe de crédits client.</span><span class="sxs-lookup"><span data-stu-id="435a1-114">When you add a new customer to a customer credit group, the system searches for the same customer account across all legal entities and prompts you to add it to the customer credit group.</span></span>

<span data-ttu-id="435a1-115">Utilisez le menu **Soldes échus** pour afficher les détails de balance âgée pour tous les clients facturés dans un groupe de crédits client.</span><span class="sxs-lookup"><span data-stu-id="435a1-115">Use the **Aged balances** menu to view the details of the aging balance for all invoice customers in a customer credit group.</span></span> <span data-ttu-id="435a1-116">La page **Balance âgée** affiche un récapitulatif des soldes échus pour les comptes clients de facturation.</span><span class="sxs-lookup"><span data-stu-id="435a1-116">The **Aging balance** page shows a summary of the aged balances for the invoice customer accounts.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]