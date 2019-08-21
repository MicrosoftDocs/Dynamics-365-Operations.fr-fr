---
title: Documents d'actif
description: Cette rubrique explique les documents d'actif dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1c90788da7ad536fb9978db18160ccf6c158033
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783253"
---
# <a name="asset-documents"></a><span data-ttu-id="36888-103">Documents d'actif</span><span class="sxs-lookup"><span data-stu-id="36888-103">Asset documents</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="36888-104">Cette rubrique explique les documents d'actif dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="36888-104">This topic explains asset documents in Asset Management.</span></span>

<span data-ttu-id="36888-105">Dans le module Gestion des actifs, vous pouvez paramétrer des documents afin qu'ils soient automatiquement associés aux types de tâche, aux fabricants d'actif, aux types d'actif ou aux actifs, par exemple.</span><span class="sxs-lookup"><span data-stu-id="36888-105">In Asset Management, you can set up documents so that they are automatically related to job types, asset manufacturers, asset types, or assets, for example.</span></span> <span data-ttu-id="36888-106">Cette fonctionnalité est utile lorsque des versions de document mises à jour sont publiées.</span><span class="sxs-lookup"><span data-stu-id="36888-106">This functionality is useful when updated document versions are released.</span></span> <span data-ttu-id="36888-107">Dans ce cas, il vous suffit de placer le document mis à jour dans l'emplacement standard que vous utilisez pour vos documents Microsoft Dynamics 365 for Finance and Operations, et de joindre le document à l'enregistrement de document d'actif que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="36888-107">In that case, you just have to put the updated document in the standard location that you use for your Microsoft Dynamics 365 for Finance and Operations documents, and attach the document to the asset document record that you've created.</span></span> <span data-ttu-id="36888-108">Le document mis à jour est ensuite accessible à partir des éléments de menu **Tous les actifs**, **Actifs actifs**, **Mes actifs actifs**, **Tous les ordres de travail** et **Tâches de l'ordre de travail actif**.</span><span class="sxs-lookup"><span data-stu-id="36888-108">The updated document can then be accessed from the **All assets**, **Active assets**, **My active assets**, **All work orders**, and **Active work order jobs** menu items.</span></span> <span data-ttu-id="36888-109">Le processus pour joindre des documents à un enregistrement de document d'actif utilise le système de gestion des documents standard dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36888-109">The process for attaching documents to an asset document record uses the standard document handling system in Finance and Operations.</span></span>

<span data-ttu-id="36888-110">**Exemple 1 :** un document associé à un type de tâche peut décrire une procédure pour ce type de tâche.</span><span class="sxs-lookup"><span data-stu-id="36888-110">**Example 1:** A document that is related to a job type might describe a procedure for that job type.</span></span>

<span data-ttu-id="36888-111">**Exemple 2 :** un document associé à une combinaison d'un type d'actif, d'un fabricant et d'un modèle peut être le manuel standard pour le modèle de fabricant d'actif sélectionné.</span><span class="sxs-lookup"><span data-stu-id="36888-111">**Example 2:** A document that is related to a combination of an asset type, manufacturer, and model might be the standard manual for the selected asset manufacturer model.</span></span>

## <a name="create-asset-document-relation"></a><span data-ttu-id="36888-112">Créer une relation de document d'actif</span><span class="sxs-lookup"><span data-stu-id="36888-112">Create asset document relation</span></span>

1. <span data-ttu-id="36888-113">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Documents d'actif**.</span><span class="sxs-lookup"><span data-stu-id="36888-113">Select **Asset management** \> **Setup** \> **Asset documents**.</span></span>
2. <span data-ttu-id="36888-114">Sélectionnez **Nouveau** pour créer un enregistrement de document d'actif.</span><span class="sxs-lookup"><span data-stu-id="36888-114">Select **New** to create an asset document record.</span></span>
3. <span data-ttu-id="36888-115">Selon la spécificité de la relation de document, effectuez les sélections appropriées dans un ou plusieurs des champs suivants : **Type d'actif**, **Fabricant**, **Modèle**, **Actif**, **Catégorie de type de tâche**, **Type de tâche**, **Variante du type de tâche** et **Demande de tâche**.</span><span class="sxs-lookup"><span data-stu-id="36888-115">Depending on how specific you want the document relation to be, make relevant selections in one or more of the following fields: **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement**.</span></span> <span data-ttu-id="36888-116">Les options disponibles dans les champs **Variante du type de tâche** et **Demande de tâche** dépendent de votre sélection dans le champ **Type de tâche**.</span><span class="sxs-lookup"><span data-stu-id="36888-116">The options that are available in the **Job type variant** and **Job requirement** fields depend on your selection in the **Job type** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36888-117">Lorsque le système recherche des documents qui doivent être associés à un actif ou un ordre de travail, le module Gestion des actifs recherche une correspondance possible dans tous les enregistrements de document d'actif.</span><span class="sxs-lookup"><span data-stu-id="36888-117">When the system searches for documents that should be related to an asset or a work order, Asset Management goes through all asset document records to check for a possible match.</span></span> <span data-ttu-id="36888-118">Il vérifie toujours la combinaison la plus spécifique en premier.</span><span class="sxs-lookup"><span data-stu-id="36888-118">It always checks the most specific combination first.</span></span> <span data-ttu-id="36888-119">En d'autres termes, le module Gestion des actifs recherche d'abord une correspondance pour le champ **Demande de tâche**.</span><span class="sxs-lookup"><span data-stu-id="36888-119">In other words, Asset Management first checks for a match for the **Job requirement** field.</span></span> <span data-ttu-id="36888-120">Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Variante du type de tâche**.</span><span class="sxs-lookup"><span data-stu-id="36888-120">If no match is found, it checks for a match for the **Job type variant** field.</span></span> <span data-ttu-id="36888-121">Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Type de tâche**, etc.</span><span class="sxs-lookup"><span data-stu-id="36888-121">If no match is found, it checks for a match for the **Job type** field, and so on.</span></span> <span data-ttu-id="36888-122">Comme vous pouvez voir dans la disposition de la page **Documents d'actif**, ce comportement signifie que, pour trouver la combinaison la plus spécifique, le module Gestion des actifs recherche une correspondance dans chaque enregistrement en allant de la droite vers la gauche.</span><span class="sxs-lookup"><span data-stu-id="36888-122">As you can see in the layout of the **Asset documents** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="36888-123">Plusieurs documents peuvent être associés à un actif ou un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="36888-123">Several documents might be related to an asset or a work order.</span></span> <span data-ttu-id="36888-124">Vous pouvez modifier le niveau de service d'une demande de maintenance ou d'un ordre de travail si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="36888-124">You can edit the service level on a maintenance request or a work order as you require.</span></span>

4. <span data-ttu-id="36888-125">Sélectionnez **Pièces jointes**.</span><span class="sxs-lookup"><span data-stu-id="36888-125">Select **Attachments**.</span></span> <span data-ttu-id="36888-126">La page **Gestion des documents** standard dans Finance and Operations s'affiche.</span><span class="sxs-lookup"><span data-stu-id="36888-126">The standard **Document handling** page in Finance and Operations appears.</span></span>
5. <span data-ttu-id="36888-127">Paramétrez les documents ou les notes qui doivent être joints à l'enregistrement de document d'actif.</span><span class="sxs-lookup"><span data-stu-id="36888-127">Set up the documents or notes that should be attached to the asset document record.</span></span> <span data-ttu-id="36888-128">Après avoir joint des documents, le champ **Pièces jointes** affiche le nombre de documents associés à l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="36888-128">After you attach documents, the **Attachments** field shows the number of documents that are related to the record.</span></span>
