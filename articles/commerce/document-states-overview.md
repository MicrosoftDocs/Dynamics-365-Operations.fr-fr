---
title: États et cycle de vie des documents
description: Cette rubrique décrit les différents états de document des éléments de page dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7c30932800beda13ac8fe6b0386fe29efe93f79c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982614"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="27d20-103">États et cycle de vie des documents</span><span class="sxs-lookup"><span data-stu-id="27d20-103">Document states and lifecycle</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="27d20-104">Cette rubrique décrit les différents états de document des éléments de page dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="27d20-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="27d20-105">Description de l'état d'un document</span><span class="sxs-lookup"><span data-stu-id="27d20-105">Document state descriptions</span></span>

<span data-ttu-id="27d20-106">La rubrique [Éléments de page](page-elements-overview.md) répertorie les différents types de système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="27d20-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="27d20-107">Ces types de documents peuvent avoir plusieurs états dans l'outil de création.</span><span class="sxs-lookup"><span data-stu-id="27d20-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="27d20-108">Les états de document permettent d'éviter des conflits de données et d'appliquer le contrôle des versions.</span><span class="sxs-lookup"><span data-stu-id="27d20-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="27d20-109">Ils déterminent qui peut modifier les documents, quand les documents peuvent être modifiés, et quand des modifications peuvent être affichées par d'autres personnes.</span><span class="sxs-lookup"><span data-stu-id="27d20-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="27d20-110">Le tableau suivant indique les états de document possibles des éléments de page dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="27d20-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="27d20-111">État de document</span><span class="sxs-lookup"><span data-stu-id="27d20-111">Document state</span></span>      | <span data-ttu-id="27d20-112">Action du générateur de site</span><span class="sxs-lookup"><span data-stu-id="27d20-112">Site builder action</span></span>        | <span data-ttu-id="27d20-113">Description</span><span class="sxs-lookup"><span data-stu-id="27d20-113">Description</span></span>                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="27d20-114">Extrait</span><span class="sxs-lookup"><span data-stu-id="27d20-114">Checked out</span></span>         | <span data-ttu-id="27d20-115">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="27d20-115">Select **Edit**.</span></span>           | <span data-ttu-id="27d20-116">Le document applicable est extrait pour vous.</span><span class="sxs-lookup"><span data-stu-id="27d20-116">The applicable document is checked out to you.</span></span> <span data-ttu-id="27d20-117">Lorsqu'un document est défini à cet état, il ne peut pas être modifié par d'autres utilisateurs système authentifiés, et toute modification apportée au document est visible uniquement de vous.</span><span class="sxs-lookup"><span data-stu-id="27d20-117">While a document is in this state, it can't be changed by other authenticated system users, and any changes that you make to the document are visible only to you.</span></span> |
| <span data-ttu-id="27d20-118">Enregistré</span><span class="sxs-lookup"><span data-stu-id="27d20-118">Saved</span></span>               | <span data-ttu-id="27d20-119">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="27d20-119">Select **Save**.</span></span>           | <span data-ttu-id="27d20-120">Les modifications qui ont été effectuées vers un document extrait sont enregistrées vers la base de données, mais le document n'est pas encore vérifié ou publié.</span><span class="sxs-lookup"><span data-stu-id="27d20-120">Changes that have been made to a checked-out document are saved to the database, but the document isn't yet checked in or published.</span></span> <span data-ttu-id="27d20-121">Les modifications enregistrées ne sont pas visibles aux autres utilisateurs système authentifiés jusqu'à ce que l'auteur sélectionne **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="27d20-121">The saved changes aren't visible to other authenticated system users until the author selects **Finish editing**.</span></span> <span data-ttu-id="27d20-122">Elles restent invisibles des utilisateurs externes jusqu'à ce que l'article soit publié.</span><span class="sxs-lookup"><span data-stu-id="27d20-122">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="27d20-123">Extraction ignorée</span><span class="sxs-lookup"><span data-stu-id="27d20-123">Discarded check out</span></span> | <span data-ttu-id="27d20-124">Sélectionnez **Ignorer les modifications**.</span><span class="sxs-lookup"><span data-stu-id="27d20-124">Select **Discard edits**.</span></span>  | <span data-ttu-id="27d20-125">Toutes les modifications apportées au document extrait sont ignorées et l'article revient à la dernière version archivée.</span><span class="sxs-lookup"><span data-stu-id="27d20-125">All changes to the checked-out document are discarded, and the item reverts to the last version that was checked in.</span></span> |
| <span data-ttu-id="27d20-126">Enregistré</span><span class="sxs-lookup"><span data-stu-id="27d20-126">Checked in</span></span>          | <span data-ttu-id="27d20-127">Sélectionnez **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="27d20-127">Select **Finish editing**.</span></span> | <span data-ttu-id="27d20-128">Le document modifié est archivé.</span><span class="sxs-lookup"><span data-stu-id="27d20-128">The edited document is checked in.</span></span> <span data-ttu-id="27d20-129">Toutes les modifications sont visibles pour les autres utilisateurs système authentifiés, et ces utilisateurs peuvent ensuite modifier le document.</span><span class="sxs-lookup"><span data-stu-id="27d20-129">All changes are visible to other authenticated system users, and those users can then edit the document.</span></span> <span data-ttu-id="27d20-130">Chaque archivage crée un enregistrement de version du document dans l'historique de l'article.</span><span class="sxs-lookup"><span data-stu-id="27d20-130">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="27d20-131">Publiées</span><span class="sxs-lookup"><span data-stu-id="27d20-131">Published</span></span>           | <span data-ttu-id="27d20-132">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="27d20-132">Select **Publish**.</span></span>        | <span data-ttu-id="27d20-133">Le document est publié et les modifications sont transmises à votre site en direct et deviennent détectables par des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="27d20-133">The document is published, and the changes are pushed to your live site and become discoverable by external users.</span></span> <span data-ttu-id="27d20-134">Les éléments ne peuvent être publiés que s'ils ont été archivés tout d'abord en sélectionnant **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="27d20-134">Items can be published only if they have first been checked in by selecting **Finish editing**.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="27d20-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="27d20-135">Additional resources</span></span>

[<span data-ttu-id="27d20-136">Manières d’ajouter du contenu</span><span class="sxs-lookup"><span data-stu-id="27d20-136">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="27d20-137">Glossaire sur le modèle de page</span><span class="sxs-lookup"><span data-stu-id="27d20-137">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="27d20-138">Utilisation de groupes de publication</span><span class="sxs-lookup"><span data-stu-id="27d20-138">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="27d20-139">Activer et utiliser le partage intercanal</span><span class="sxs-lookup"><span data-stu-id="27d20-139">Enable and use cross-channel sharing</span></span>](cross-channel-sharing.md)

[<span data-ttu-id="27d20-140">Utiliser des modules</span><span class="sxs-lookup"><span data-stu-id="27d20-140">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="27d20-141">Utiliser des fragments</span><span class="sxs-lookup"><span data-stu-id="27d20-141">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="27d20-142">Vue d’ensemble des modèles et dispositions</span><span class="sxs-lookup"><span data-stu-id="27d20-142">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="27d20-143">Personnaliser la navigation dans le site</span><span class="sxs-lookup"><span data-stu-id="27d20-143">Customize site navigation</span></span>](customize-site-navigation.md)
