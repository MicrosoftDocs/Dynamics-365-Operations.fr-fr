---
title: États et cycle de vie des documents
description: Cette rubrique décrit les différents états de document des éléments de page dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b4f1c462f734b2d58843308f0f877fe18a4d9af7
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002979"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="683f1-103">États et cycle de vie des documents</span><span class="sxs-lookup"><span data-stu-id="683f1-103">Document states and lifecycle</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="683f1-104">Cette rubrique décrit les différents états de document des éléments de page dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="683f1-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="683f1-105">Description de l'état d'un document</span><span class="sxs-lookup"><span data-stu-id="683f1-105">Document state descriptions</span></span>

<span data-ttu-id="683f1-106">La rubrique [Éléments de page](page-elements-overview.md) répertorie les différents types de système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="683f1-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="683f1-107">Ces types de documents peuvent avoir plusieurs états dans l'outil de création.</span><span class="sxs-lookup"><span data-stu-id="683f1-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="683f1-108">Les états de document permettent d'éviter des conflits de données et d'appliquer le contrôle des versions.</span><span class="sxs-lookup"><span data-stu-id="683f1-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="683f1-109">Ils déterminent qui peut modifier les documents, quand les documents peuvent être modifiés, et quand des modifications peuvent être affichées par d'autres personnes.</span><span class="sxs-lookup"><span data-stu-id="683f1-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="683f1-110">Le tableau suivant indique les états de document possibles des éléments de page dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="683f1-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="683f1-111">État de document</span><span class="sxs-lookup"><span data-stu-id="683f1-111">Document state</span></span> | <span data-ttu-id="683f1-112">Description</span><span class="sxs-lookup"><span data-stu-id="683f1-112">Description</span></span> |
|---|---|
| <span data-ttu-id="683f1-113">Extrait</span><span class="sxs-lookup"><span data-stu-id="683f1-113">Checked out</span></span> | <span data-ttu-id="683f1-114">Lorsqu'un article CMS est extrait vers vous, il ne peut pas être modifié par un autre utilisateur du système authentifié.</span><span class="sxs-lookup"><span data-stu-id="683f1-114">When a CMS item is checked out to you, it can't be edited by any other authenticated system users.</span></span> <span data-ttu-id="683f1-115">Vous êtes le seul utilisateur à pouvoir afficher les modifications apportées.</span><span class="sxs-lookup"><span data-stu-id="683f1-115">Any changes that you make to the item are visible only to you.</span></span> |
| <span data-ttu-id="683f1-116">Archivé</span><span class="sxs-lookup"><span data-stu-id="683f1-116">Checked in</span></span> | <span data-ttu-id="683f1-117">Lorsqu'un article CMS est archivé, toutes les modifications sont visibles pour d'autres utilisateurs du système authentifiés, et ils peuvent ensuite extraire l'article et le modifier.</span><span class="sxs-lookup"><span data-stu-id="683f1-117">When a CMS item is checked in, all changes are visible to other authenticated system users, and those users can then check out the item and edit it.</span></span> <span data-ttu-id="683f1-118">Chaque archivage crée un enregistrement de version du document dans l'historique de l'article.</span><span class="sxs-lookup"><span data-stu-id="683f1-118">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="683f1-119">Publiées</span><span class="sxs-lookup"><span data-stu-id="683f1-119">Published</span></span> | <span data-ttu-id="683f1-120">Lorsqu'un article CMS est publié, il est transmis à votre site en direct et devient découvrable sur Internet par les utilisateurs externes non authentifiés.</span><span class="sxs-lookup"><span data-stu-id="683f1-120">When a CMS item is published, it's pushed to your live site and becomes discoverable on the internet by non-authenticated external users.</span></span> <span data-ttu-id="683f1-121">Les articles peuvent être transmis uniquement s'ils ont été archivés.</span><span class="sxs-lookup"><span data-stu-id="683f1-121">Items can be published only if they have been checked in.</span></span> |
| <span data-ttu-id="683f1-122">Enregistré</span><span class="sxs-lookup"><span data-stu-id="683f1-122">Saved</span></span> | <span data-ttu-id="683f1-123">Les modifications apportées à un article extrait par CMS peut être enregistré dans CMS avant que l'article soit archivé ou publié.</span><span class="sxs-lookup"><span data-stu-id="683f1-123">Changes that have been made to a checked-out CMS item can be saved to the CMS before the item is checked in or published.</span></span> <span data-ttu-id="683f1-124">Ces modifications enregistrées ne sont pas visibles pour d'autres utilisateurs du système authentifiés tant que l'article n'est pas archivé.</span><span class="sxs-lookup"><span data-stu-id="683f1-124">These saved changes aren't visible to other authenticated system users until the item is checked in.</span></span> <span data-ttu-id="683f1-125">Elles restent invisibles des utilisateurs externes jusqu'à ce que l'article soit publié.</span><span class="sxs-lookup"><span data-stu-id="683f1-125">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="683f1-126">Extraction ignorée</span><span class="sxs-lookup"><span data-stu-id="683f1-126">Discarded check out</span></span> | <span data-ttu-id="683f1-127">Lorsqu'un article extrait par CMS est ignoré, toutes les modifications enregistrées sont supprimées, et l'article revient à la version qui a été récemment archivée.</span><span class="sxs-lookup"><span data-stu-id="683f1-127">When a checked-out CMS item is discarded, all saved changes are deleted, and the item reverts to the version that was most recently checked in.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="683f1-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="683f1-128">Additional resources</span></span>

[<span data-ttu-id="683f1-129">Manières d'ajouter du contenu</span><span class="sxs-lookup"><span data-stu-id="683f1-129">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="683f1-130">Glossaire sur le modèle de page</span><span class="sxs-lookup"><span data-stu-id="683f1-130">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="683f1-131">Utilisation de groupes de publication</span><span class="sxs-lookup"><span data-stu-id="683f1-131">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="683f1-132">Utiliser des modules</span><span class="sxs-lookup"><span data-stu-id="683f1-132">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="683f1-133">Utiliser des fragments</span><span class="sxs-lookup"><span data-stu-id="683f1-133">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="683f1-134">Vue d'ensemble des modèles et dispositions</span><span class="sxs-lookup"><span data-stu-id="683f1-134">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="683f1-135">Personnaliser la navigation dans le site</span><span class="sxs-lookup"><span data-stu-id="683f1-135">Customize site navigation</span></span>](customize-site-navigation.md)
