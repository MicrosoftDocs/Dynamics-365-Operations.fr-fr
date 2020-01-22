---
title: Planifier le carnet d'adresses global et d'autres carnets d'adresses
description: Cette rubrique décrit les considérations et les décisions que vous devez prendre au cours du processus de planification avant de paramétrer et configurer le carnet d'adresses global et des carnets d'adresses supplémentaires.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 89c6e71e5f537f0f9309eca1025c8e74cdce6716
ms.sourcegitcommit: 75bbcff474cfb8d2f282be2b9d2d7984d1505fa3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2019
ms.locfileid: "2883409"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a><span data-ttu-id="7f08d-103">Planifier le carnet d'adresses global et d'autres carnets d'adresses</span><span class="sxs-lookup"><span data-stu-id="7f08d-103">Plan for the global address book and other address books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7f08d-104">Cette rubrique décrit les considérations et les décisions que vous devez prendre au cours du processus de planification avant de paramétrer et configurer le carnet d'adresses global et des carnets d'adresses supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="7f08d-104">This topic describes the considerations and decisions that you must make during the planning process, before you set up and configure the global address book and any additional address books.</span></span> <span data-ttu-id="7f08d-105">Certaines de ces décisions nécessitent que vous confirmiez les décisions qui ont été prises pour d'autres zones du produit, telles que la hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="7f08d-105">Some of the decisions will require that you confirm the decisions that have been made for other areas of the product, such as the organization hierarchy.</span></span>

## <a name="global-address-book"></a><span data-ttu-id="7f08d-106">Carnet d'adresses global</span><span class="sxs-lookup"><span data-stu-id="7f08d-106">Global address book</span></span>

<span data-ttu-id="7f08d-107">Avant de commencer à travailler avec le carnet d'adresses global, vous devez déterminer les valeurs par défaut pour celui-ci.</span><span class="sxs-lookup"><span data-stu-id="7f08d-107">Before you begin to work with the global address book, you must determine the default values for it.</span></span> <span data-ttu-id="7f08d-108">Ces valeurs par défaut sont ensuite utilisées pour tous les carnets d'adresses supplémentaires que vous créez.</span><span class="sxs-lookup"><span data-stu-id="7f08d-108">These default values are then used for any additional address books that you create.</span></span>

<span data-ttu-id="7f08d-109">**Décisions**</span><span class="sxs-lookup"><span data-stu-id="7f08d-109">**Decisions**</span></span>

- <span data-ttu-id="7f08d-110">Dans quel ordre les noms doivent-ils s'afficher pour les enregistrements de parties de type **Personne** ?</span><span class="sxs-lookup"><span data-stu-id="7f08d-110">What sequence should names be displayed in for party records of the **Person** type?</span></span> <span data-ttu-id="7f08d-111">Par exemple, nom, deuxième prénom, prénom.</span><span class="sxs-lookup"><span data-stu-id="7f08d-111">For example, one sequence is last name, middle name, first name.</span></span>
- <span data-ttu-id="7f08d-112">Les enregistrements de parties doivent-ils être supprimés du carnet d'adresses lorsque l'enregistrement de rôle est supprimé ?</span><span class="sxs-lookup"><span data-stu-id="7f08d-112">Should party records be deleted from the address book when the role record is deleted?</span></span> <span data-ttu-id="7f08d-113">Par exemple, si un enregistrement client est supprimé, l'enregistrement de partie doit-il également être supprimé ?</span><span class="sxs-lookup"><span data-stu-id="7f08d-113">For example, if a customer record is deleted, should the party record also be deleted?</span></span>
- <span data-ttu-id="7f08d-114">Lorsqu'un enregistrement est créé, les utilisateurs doivent-ils être avertis si un enregistrement en double est trouvé dans le carnet d'adresses global ?</span><span class="sxs-lookup"><span data-stu-id="7f08d-114">When a new record is created, should users be notified if a duplicate record is found in the global address book?</span></span>
- <span data-ttu-id="7f08d-115">Le numéro DUNS (Data Universal Numbering System) doit-il être inclus dans les informations d'un enregistrement de partie ?</span><span class="sxs-lookup"><span data-stu-id="7f08d-115">Should the Data Universal Numbering System (DUNS) number be included in a party record's information?</span></span>
- <span data-ttu-id="7f08d-116">Si le numéro DUNS est inclus dans un enregistrement de partie, le caractère unique du nombre doit-il être vérifié ?</span><span class="sxs-lookup"><span data-stu-id="7f08d-116">If the DUNS number is included in a party record, should the uniqueness of the number be checked?</span></span>
- <span data-ttu-id="7f08d-117">Lorsqu'un enregistrement de partie est créé dans le carnet d'adresses global, souhaitez-vous définir comme type de partie par défaut une personne ou une organisation ?</span><span class="sxs-lookup"><span data-stu-id="7f08d-117">When a party record is created in the global address book, do you want a default party type, person, or organization?</span></span>
- <span data-ttu-id="7f08d-118">Quels rôles utilisateur doivent avoir accès aux adresses privées et aux informations de contact des enregistrements de parties ?</span><span class="sxs-lookup"><span data-stu-id="7f08d-118">Which user roles should have access to the private addresses and contact information of party records?</span></span>

## <a name="additional-address-books"></a><span data-ttu-id="7f08d-119">Carnets d'adresses supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7f08d-119">Additional address books</span></span>

<span data-ttu-id="7f08d-120">Une fois que vous avez créé le carnet d'adresses global, vous pouvez créer des carnets d'adresses supplémentaires selon vos besoins, par exemple un carnet d'adresses distinct pour chaque société de votre organisation ou pour chaque activité.</span><span class="sxs-lookup"><span data-stu-id="7f08d-120">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span> <span data-ttu-id="7f08d-121">Par exemple, Fabrikam est une organisation internationale qui comporte plusieurs sociétés et plusieurs activités.</span><span class="sxs-lookup"><span data-stu-id="7f08d-121">For example, Fabrikam is an international organization that has multiple companies and multiple lines of business.</span></span> <span data-ttu-id="7f08d-122">Fabrikam prévoit de créer un carnet d'adresses pour chaque activité.</span><span class="sxs-lookup"><span data-stu-id="7f08d-122">Fabrikam plans to create an address book for each line of business.</span></span> <span data-ttu-id="7f08d-123">Pour les activités qui concernent plusieurs emplacements, par exemple l'activité d'outils pneumatiques, Fabrikam prévoit de créer un carnet d'adresses par emplacement.</span><span class="sxs-lookup"><span data-stu-id="7f08d-123">For lines of business that occur in more than one location, such as the pneumatic tools business, Fabrikam plans to create an address book for each location.</span></span> <span data-ttu-id="7f08d-124">Chris, le responsable informatique de Fabrikam, a créé la liste suivante des carnets d'adresses nécessaires.</span><span class="sxs-lookup"><span data-stu-id="7f08d-124">Chris, the IT manager at Fabrikam, has created the following list of address books that are required.</span></span> <span data-ttu-id="7f08d-125">Cette liste décrit également les enregistrements de parties que chaque carnet d'adresses doit inclure.</span><span class="sxs-lookup"><span data-stu-id="7f08d-125">This list also describes the party records that each address book must include.</span></span>

- <span data-ttu-id="7f08d-126">**Public Sector Contracts (PubSC)** – Enregistrements de parties pour toutes les parties impliquées dans les contrats du secteur public détenus par Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="7f08d-126">**Public Sector Contracts (PubSC)** – Party records for all parties that are involved in the public sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="7f08d-127">**Private Sector Contracts (PriSC)** – Enregistrements de parties pour toutes les parties impliquées dans les contrats du secteur privé détenus par Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="7f08d-127">**Private Sector Contracts (PriSC)** – Party records for all parties that are involved in the private sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="7f08d-128">**Electronic Tools (ET)** – Enregistrements de parties pour toutes les parties impliquées dans l'achat ou la vente d'outils électroniques ou qui interagissent d'une façon ou d'une autre avec les outils électroniques fournis par ou achetés pour Fabrikam dans la société Fabrikam-Japan.</span><span class="sxs-lookup"><span data-stu-id="7f08d-128">**Electronic Tools (ET)** – Party records for all parties that are involved in the purchase or sale of electronic tools, or that otherwise interact with the electronic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="7f08d-129">**Pneumatic Tools (PTJPN)** – Enregistrements de parties pour toutes les parties impliquées dans l'achat ou la vente d'outils pneumatiques ou qui interagissent d'une façon ou d'une autre avec les outils pneumatiques fournis par ou achetés pour Fabrikam dans la société Fabrikam-Japan.</span><span class="sxs-lookup"><span data-stu-id="7f08d-129">**Pneumatic Tools (PTJPN)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="7f08d-130">**Pneumatic Tools (PTUSA)** – Enregistrements de parties pour toutes les parties impliquées dans l'achat ou la vente d'outils pneumatiques ou qui interagissent d'une façon ou d'une autre avec les outils pneumatiques fournis par ou achetés pour Fabrikam dans la société Fabrikam-US.</span><span class="sxs-lookup"><span data-stu-id="7f08d-130">**Pneumatic Tools (PTUSA)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-US company.</span></span>

<span data-ttu-id="7f08d-131">**Décision :**</span><span class="sxs-lookup"><span data-stu-id="7f08d-131">**Decision:**</span></span>

- <span data-ttu-id="7f08d-132">Combien de carnets d'adresses supplémentaires allez-vous créer ?</span><span class="sxs-lookup"><span data-stu-id="7f08d-132">How many additional address books will you create?</span></span>
