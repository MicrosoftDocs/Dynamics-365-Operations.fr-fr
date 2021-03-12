---
title: Nouveautés ou modifications apportées à la version 7.0.1 de l’application Dynamics AX (mai 2016)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version 7.0.1 de l’application Microsoft Dynamics AX. Cette version a été publiée en mai 2016 et a pour numéro de version 7.0.1265.23014.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 17067ff534e0e3f4636d7a307563128db55cf2ba
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797162"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a><span data-ttu-id="76b7e-104">Nouveautés ou modifications apportées à la version 7.0.1 de l’application Dynamics AX (mai 2016)</span><span class="sxs-lookup"><span data-stu-id="76b7e-104">What's new or changed in Dynamics AX application version 7.0.1 (May 2016)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76b7e-105">Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version 7.0.1 de l’application Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="76b7e-105">This article describes features that are either new or changed in Microsoft Dynamics AX application version 7.0.1.</span></span> <span data-ttu-id="76b7e-106">Cette version a été publiée en mai 2016 et a pour numéro de version 7.0.1265.23014.</span><span class="sxs-lookup"><span data-stu-id="76b7e-106">This version was released in May 2016 and has a build number of 7.0.1265.23014.</span></span>

## <a name="electronic-reporting-er"></a><span data-ttu-id="76b7e-107">Gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="76b7e-107">Electronic reporting (ER)</span></span>

| <span data-ttu-id="76b7e-108">Que pouvez-vous faire ?</span><span class="sxs-lookup"><span data-stu-id="76b7e-108">What can you do?</span></span> | <span data-ttu-id="76b7e-109">Pourquoi est-ce important ?</span><span class="sxs-lookup"><span data-stu-id="76b7e-109">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="76b7e-110">Configurez une boîte de dialogue d’exécution pour les états électroniques afin que les utilisateurs puissent sélectionner les dimensions financières de leur choix.</span><span class="sxs-lookup"><span data-stu-id="76b7e-110">Configure a run-time dialog box for designing Electronic reporting (ER) reports, so that users can select the financial dimensions that they want.</span></span> | <span data-ttu-id="76b7e-111">Au moment de l’exécution, dans la boîte de dialogue d’exécution d’un état électronique, les utilisateurs peuvent sélectionner plusieurs dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="76b7e-111">At run time, in the dialog box for running an ER report, users can select multiple financial dimensions.</span></span> <span data-ttu-id="76b7e-112">Les détails des dimensions financières sélectionnées seront affichées dans le document électronique qui est généré.</span><span class="sxs-lookup"><span data-stu-id="76b7e-112">The details of the selected financial dimensions will be displayed in the electronic document that is generated.</span></span> |
| <span data-ttu-id="76b7e-113">Configurez l’accès à plusieurs dimensions financières lors de la conception d’un état électronique, via un seul mappage à la source de données souhaitée.</span><span class="sxs-lookup"><span data-stu-id="76b7e-113">Configure access to multiple financial dimensions during the design of an ER report, via a single mapping to the desired data source.</span></span> | <span data-ttu-id="76b7e-114">La même configuration d’états électroniques peut servir à générer des documents électroniques qui présentent les données transactionnelles ainsi que des détails des dimensions financières, quel que soit le nombre de dimensions financières qui sont sélectionnées par l’utilisateur ou configurées pour l’entité juridique ou l’instance actuelle.</span><span class="sxs-lookup"><span data-stu-id="76b7e-114">The same ER report configuration can be used to generate electronic documents that present transactional data together with details of financial dimensions, regardless of the number of financial dimensions that are either selected by the user or configured for the current legal entity or instance.</span></span> |
| <span data-ttu-id="76b7e-115">Configurez un état électronique pour entrer des données dans les colonnes générées de manière dynamique d’un document électronique qui est créé au format de feuille de calcul OPENXML.</span><span class="sxs-lookup"><span data-stu-id="76b7e-115">Configure an ER report to enter data in dynamically generated columns of an electronic document that is created in OPENXML worksheet format.</span></span> | <span data-ttu-id="76b7e-116">Un état électronique peut entrer des données dans une feuille de calcul OPENXML qui est générée, par la réplication des colonnes horizontalement.</span><span class="sxs-lookup"><span data-stu-id="76b7e-116">An ER report can enter data in an OPENXML worksheet that is generated, via horizontally replicating columns.</span></span> <span data-ttu-id="76b7e-117">Par conséquent, la même configuration d’états électroniques peut être réutilisée pour générer des documents électroniques ayant un nombre différent de colonnes générées de façon dynamique.</span><span class="sxs-lookup"><span data-stu-id="76b7e-117">Therefore, the same ER report configuration can be reused to generate electronic documents that have a different number of dynamically generated columns.</span></span> |
| <span data-ttu-id="76b7e-118">Configurez les destinations d’états électroniques afin que le résultat d’un format de sortie soit dirigé vers une destination spécifique : fichier, courrier électronique ou archive (dossier Microsoft SharePoint ou stockage Microsoft Azure).</span><span class="sxs-lookup"><span data-stu-id="76b7e-118">Configure ER destinations so that the output result of a format is directed to specific destination: file, email, or archive (Microsoft SharePoint folder or Microsoft Azure Storage).</span></span> | <span data-ttu-id="76b7e-119">Auparavant, lorsque vous exécutiez une configuration d’état électronique, une zone de message apparaissait nécessitant une de l’utilisateur pour enregistrer ou ouvrir un fichier.</span><span class="sxs-lookup"><span data-stu-id="76b7e-119">Previously, when you ran an ER configuration, a message box appeared that required user action to save or open a file.</span></span> <span data-ttu-id="76b7e-120">Vous pouvez maintenant configurer une destination pour chaque configuration de format et pour chaque composant de sortie (un dossier ou un fichier) séparément.</span><span class="sxs-lookup"><span data-stu-id="76b7e-120">You can now pre-configure a destination for each format configuration and for each output component (a folder or a file) separately.</span></span> <span data-ttu-id="76b7e-121">Les utilisateurs qui disposent des droits d’accès appropriés peuvent également modifier les paramètres de destination au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="76b7e-121">Users who have appropriate access rights can also modify destination settings at run time.</span></span> |

## <a name="pos--microsoft-dynamics-ax-retail"></a><span data-ttu-id="76b7e-122">PDV - Microsoft Dynamics AX Retail</span><span class="sxs-lookup"><span data-stu-id="76b7e-122">POS – Microsoft Dynamics AX Retail</span></span>

| <span data-ttu-id="76b7e-123">Que pouvez-vous faire ?</span><span class="sxs-lookup"><span data-stu-id="76b7e-123">What can you do?</span></span> | <span data-ttu-id="76b7e-124">Pourquoi est-ce important ?</span><span class="sxs-lookup"><span data-stu-id="76b7e-124">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="76b7e-125">Utilisez le navigateur Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="76b7e-125">Use the Google Chrome browser.</span></span> | <span data-ttu-id="76b7e-126">Les détaillants peuvent maintenant démarrer Cloud POS depuis le navigateur Chrome et peuvent bénéficier de toutes les fonctionnalités qui sont disponible dans la version de Cloud POS sur Microsoft Edge et Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="76b7e-126">Retailers can now start Cloud POS from the Chrome browser, and can experience all the functionality that is available in the Microsoft Edge and Internet Explorer version of Cloud POS.</span></span> |

## <a name="financial-reporting"></a><span data-ttu-id="76b7e-127">États financiers</span><span class="sxs-lookup"><span data-stu-id="76b7e-127">Financial reporting</span></span>

| <span data-ttu-id="76b7e-128">Que pouvez-vous faire ?</span><span class="sxs-lookup"><span data-stu-id="76b7e-128">What can you do?</span></span> | <span data-ttu-id="76b7e-129">Pourquoi est-ce important ?</span><span class="sxs-lookup"><span data-stu-id="76b7e-129">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="76b7e-130">Recréez le magasin de données d’états financiers.</span><span class="sxs-lookup"><span data-stu-id="76b7e-130">Rebuild the Financial reporting data mart.</span></span> | <span data-ttu-id="76b7e-131">Lorsque vous déplacez des bases de données Dynamics AX entre différents environnements ou que vous apportez d’autres modifications invasives à l’environnement, la base de données de génération d’états financiers peut devoir être recréée.</span><span class="sxs-lookup"><span data-stu-id="76b7e-131">When you move Dynamics AX databases between environments or make other invasive changes to the environment, the Financial reporting database might have to be rebuilt.</span></span> <span data-ttu-id="76b7e-132">Un script Windows PowerShell est désormais fourni pour recréer la base de données pour vous.</span><span class="sxs-lookup"><span data-stu-id="76b7e-132">A Windows PowerShell script is now provided to rebuild the database for you.</span></span> |
| <span data-ttu-id="76b7e-133">Vous ne pouvez plus sélectionner les options du générateur d’états qui ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="76b7e-133">You can no longer select report designer options that aren't valid.</span></span> | <span data-ttu-id="76b7e-134">Plusieurs options du générateur d’états qui étaient utilisées dans les versions de mise sur le marché de Management reporter ne s’appliquent pas à cette version de Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="76b7e-134">Several report designer options that were used in the in-market versions of Management reporter don't apply to this version of Dynamics AX.</span></span> <span data-ttu-id="76b7e-135">Ces options étaient liées à la génération, la sortie et la liaison d’états financiers.</span><span class="sxs-lookup"><span data-stu-id="76b7e-135">These options were related to financial report design, output, and linking.</span></span> <span data-ttu-id="76b7e-136">Ces options ont été supprimées du générateur d’états financiers pour empêcher les erreurs de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="76b7e-136">These options have been removed from the financial report designer to prevent user errors.</span></span> |

## <a name="financial-management"></a><span data-ttu-id="76b7e-137">Gestion financière</span><span class="sxs-lookup"><span data-stu-id="76b7e-137">Financial management</span></span>

| <span data-ttu-id="76b7e-138">Que pouvez-vous faire ?</span><span class="sxs-lookup"><span data-stu-id="76b7e-138">What can you do?</span></span> | <span data-ttu-id="76b7e-139">Pourquoi est-ce important ?</span><span class="sxs-lookup"><span data-stu-id="76b7e-139">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="76b7e-140">Générez des fichiers de paiement positif pour les paiemets de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="76b7e-140">Generate positive pay files for accounts payable payments.</span></span> | <span data-ttu-id="76b7e-141">Les fichiers de paiement positifs peuvent être générés pour aider les banques à empêcher les fraudes par chèque.</span><span class="sxs-lookup"><span data-stu-id="76b7e-141">Positive pay files can be generated to help prevent check fraud.</span></span> |

## <a name="warehouse-and-production"></a><span data-ttu-id="76b7e-142">Entrepôt et production</span><span class="sxs-lookup"><span data-stu-id="76b7e-142">Warehouse and production</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="76b7e-143">Que pouvez-vous faire ?</span><span class="sxs-lookup"><span data-stu-id="76b7e-143">What can you do?</span></span></th>
<th><span data-ttu-id="76b7e-144">Pourquoi est-ce important ?</span><span class="sxs-lookup"><span data-stu-id="76b7e-144">Why is this important?</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="76b7e-145">Définissez une stratégie de travail d’entrepôt qui contrôle la création du travail pour un ensemble de produits à des emplacements spécifiques.</span><span class="sxs-lookup"><span data-stu-id="76b7e-145">Define a warehouse work policy that controls the creation of work for a set of products at specific locations.</span></span></td>
<td><span data-ttu-id="76b7e-146">Les processus d’entrepôt n’incluent pas systématiquement les tâches.</span><span class="sxs-lookup"><span data-stu-id="76b7e-146">Warehouse processes don't always include work.</span></span> <span data-ttu-id="76b7e-147">À l’aide de la nouvelle stratégie de travail d’entrepôt, vous pouvez empêcher la création de tâche pour le prélèvement de matières premières et le rangement de produits finis pour un ensemble de produits à des emplacements spécifiques.</span><span class="sxs-lookup"><span data-stu-id="76b7e-147">By using the new warehouse work policy, you can prevent work from being created for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="76b7e-148">Spécifiez que les plaques d’immatriculation d’un emplacement de sortie de production ne font pas l’objet d’un contrôle.</span><span class="sxs-lookup"><span data-stu-id="76b7e-148">Specify that a production output location isn't license plate–controlled.</span></span></td>
<td><span data-ttu-id="76b7e-149">Vous pouvez maintenant spécifier que les plaques d’immatriculation d’un emplacement de sortie de production ne font pas l’objet d’un contrôle.</span><span class="sxs-lookup"><span data-stu-id="76b7e-149">You can now specify that a product output location isn't license plate–controlled.</span></span> <span data-ttu-id="76b7e-150">Par exemple, cette fonctionnalité est utile lorsqu’un ordre de fabrication en amont signale les éléments terminés directement à un emplacement qui sert d’emplacement d’entrée en production pour un ordre de fabrication en aval.</span><span class="sxs-lookup"><span data-stu-id="76b7e-150">For example, this feature is useful when an upstream production order reports items as finished directly to a location that acts as production input location for a downstream production order.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="76b7e-151">Prenez en charge les nomenclatures qui incluent des articles dotés de dimensions de produit différentes d’un même article.</span><span class="sxs-lookup"><span data-stu-id="76b7e-151">Support BOMs that include items with different product dimensions of the same item.</span></span></td>
<td><span data-ttu-id="76b7e-152">Lorsque vous utilisez une ou plusieurs des dimensions de produit dans la production, vous pouvez avoir des situations où vous souhaitez produire un article, basé sur une autre variante du même article.</span><span class="sxs-lookup"><span data-stu-id="76b7e-152">When using one or multiple of the product dimensions in production, you can have situations where you would like to produce an item, based on a different variant of the same item.</span></span> <span data-ttu-id="76b7e-153">Pour plus d’informations, voir <a href="https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/">ce blog</a>.</span><span class="sxs-lookup"><span data-stu-id="76b7e-153">For more information, see <a href="https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/">this blog</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="76b7e-154">Les ordres de fabrication avec des structures circulaires au premier niveau de leurs nomenclatures sont exclus du calcul de nomenclature pour la planification de la ressource matérielle.</span><span class="sxs-lookup"><span data-stu-id="76b7e-154">Production orders with circular structures at the first level of their BOMs are excluded from BOM level calculation for material resource planning.</span></span></td>
<td><span data-ttu-id="76b7e-155">Il n’est pas possible d’affecter des niveaux de nomenclature corrects aux variantes de produit pour les ordres de fabrication entraînant une circularité dans la hiérarchie de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="76b7e-155">It is not possible to assign correct BOM levels to product variants for production orders that cause circularity in the BOM hierarchy.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="76b7e-156">Calculez les différents niveaux de nomenclature pour la planification des ressources matérielles et le calcul de coût :</span><span class="sxs-lookup"><span data-stu-id="76b7e-156">Calculate separate BOM levels for material resource planning and cost calculation:</span></span>
<ul>
<li><span data-ttu-id="76b7e-157">Pour la planification de ressource matérielle, les niveaux de nomenclature sont calculés dans la nouvelle table <strong>ReqItemLevel</strong>.</span><span class="sxs-lookup"><span data-stu-id="76b7e-157">For material resource planning, BOM levels are calculated in the new <strong>ReqItemLevel</strong> table.</span></span> <span data-ttu-id="76b7e-158">Les ordres de fabrication terminés sont ignorés dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="76b7e-158">Ended production orders are ignored in the calculation.</span></span></li>
<li><span data-ttu-id="76b7e-159">Pour le calcul des coûts de production, les niveaux de nomenclature sont calculés dans la table <strong>InventTable</strong>.</span><span class="sxs-lookup"><span data-stu-id="76b7e-159">For production cost calculation, BOM levels are calculated in the <strong>InventTable</strong>.</span></span> <span data-ttu-id="76b7e-160">Les ordres de fabrication terminés sont inclus dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="76b7e-160">Ended production orders are included in the calculation.</span></span></li>
</ul>
</td>
<td>
<ul>
<li><span data-ttu-id="76b7e-161">Lors de l’exécution de planification des ressources matérielles, par exemple, la planification planifie le plan et les explosions, seuls les niveaux de nomenclature utilisés pour la planification de ressource matérielle doivent être recalculés.</span><span class="sxs-lookup"><span data-stu-id="76b7e-161">When running material resource planning, for example, master planning plan scheduling and explosion, only BOM levels used for material resource planning need to be recalculated.</span></span> <span data-ttu-id="76b7e-162">Autrement dit, il n’est pas nécessaire de calculer les niveaux de la nomenclature utilisés pour le calcul de la production.</span><span class="sxs-lookup"><span data-stu-id="76b7e-162">In other words, there is no need to calculate BOM levels used for production costing calculation.</span></span></li>
<li><span data-ttu-id="76b7e-163">Lors de l’exécution des opérations d’évaluation des coûts, par exemple, les stocks de clôture, seuls les niveaux de nomenclature utilisés pour le calcul de coût de la production doivent être recalculés.</span><span class="sxs-lookup"><span data-stu-id="76b7e-163">When running costing operations, for example, inventory closing, only BOM levels used for production costing calculation need to be recalculated.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="76b7e-164">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="76b7e-164">Additional resources</span></span>

[<span data-ttu-id="76b7e-165">Page d’accueil Nouveautés ou modifications dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="76b7e-165">What's new or changed in Finance and Operations home page</span></span>](whats-new-changed.md)

[<span data-ttu-id="76b7e-166">Guides de tâches nouveaux ou mis à jour (mai 2016)</span><span class="sxs-lookup"><span data-stu-id="76b7e-166">New or updated task guides (May 2016)</span></span>](new-updated-task-guides-available-may-2016.md)
