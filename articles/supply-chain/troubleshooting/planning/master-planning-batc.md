---
title: Impossible de filtrer les éléments de planification générale selon leurs valeurs de groupe de couverture associées
description: Impossible de filtrer les éléments de planification générale selon leurs valeurs de groupe de couverture associées.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049467"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a><span data-ttu-id="4d096-103">Impossible de filtrer les éléments de planification générale selon leurs valeurs de groupe de couverture associées</span><span class="sxs-lookup"><span data-stu-id="4d096-103">You can't filter master planning items by their related coverage group values</span></span>

<span data-ttu-id="4d096-104">Numéro de la base de connaissances : 4612572</span><span class="sxs-lookup"><span data-stu-id="4d096-104">KB number: 4612572</span></span>

## <a name="symptoms"></a><span data-ttu-id="4d096-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="4d096-105">Symptoms</span></span>

<span data-ttu-id="4d096-106">Vous souhaitez filtrer les articles qui seront inclus dans une tâche de traitement par lots de la planification générale, selon les valeurs des enregistrements associés dans la table de couverture des articles.</span><span class="sxs-lookup"><span data-stu-id="4d096-106">You want to filter the items that will be included in a master planning batch job, based on the values of related records from the item coverage table.</span></span> <span data-ttu-id="4d096-107">(Par exemple, vous souhaitez filtrer des articles selon leur valeur **Fournisseur** et/ou **Groupe de couverture**).</span><span class="sxs-lookup"><span data-stu-id="4d096-107">(For example, you want to filter items by their **Vendor** and/or **Coverage group** value).</span></span> <span data-ttu-id="4d096-108">La configuration du filtre pour la tâche de traitement par lots vous permet de créer une jointure entre la table **Articles** et la table **Couverture des articles**, puis de spécifier les valeurs de champ dans la table de couverture des articles de votre requête.</span><span class="sxs-lookup"><span data-stu-id="4d096-108">The filter setup for the batch job lets you create a join from the **Items** table to the **Item coverage** table, and then specify field values from the item coverage table in your query.</span></span> <span data-ttu-id="4d096-109">Cependant, une fois cette configuration terminée, le système crée toujours des ordres planifiés pour l’ensemble de la couverture des articles, et pas seulement pour les articles correspondant aux valeurs de champ spécifiées dans la table de couverture des articles.</span><span class="sxs-lookup"><span data-stu-id="4d096-109">However, after you complete this setup, the system still creates planned orders for the whole item coverage, not just for the items that match the specified field values from the item coverage table.</span></span>

## <a name="resolution"></a><span data-ttu-id="4d096-110">Résolution</span><span class="sxs-lookup"><span data-stu-id="4d096-110">Resolution</span></span>

<span data-ttu-id="4d096-111">Le filtre de la tâche de traitement par lots ne peut filtrer que les articles.</span><span class="sxs-lookup"><span data-stu-id="4d096-111">The batch job filter can filter only on items.</span></span> <span data-ttu-id="4d096-112">Bien que vous puissiez ajouter une jointure à la table **Couverture des articles**, les paramètres de filtre que vous définissez sur cette table n’affecteront pas la sortie de la requête.</span><span class="sxs-lookup"><span data-stu-id="4d096-112">Although you can add a join to the **Item coverage** table, filter settings that you make against that table won't affect the query output.</span></span> <span data-ttu-id="4d096-113">Au moment de l’exécution, le système exécute la planification pour tous les groupes de couverture et toutes les variantes des articles filtrés.</span><span class="sxs-lookup"><span data-stu-id="4d096-113">At runtime, the system runs planning for all the coverage groups and all the variations that the filtered items have.</span></span> <span data-ttu-id="4d096-114">Lorsqu’un article est déjà inclus dans l’exécution, les groupes de couverture inclus dans le filtre de l’article n’affecteront pas la sortie de la planification.</span><span class="sxs-lookup"><span data-stu-id="4d096-114">After an item is already included in the run, any coverage groups that are included in the item filter a won't affect the planning output.</span></span>
