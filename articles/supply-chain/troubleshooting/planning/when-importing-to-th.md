---
title: Vous êtes invité à enregistrer les paramètres de couverture des articles même si vous n’avez effectué aucune modification
description: Vous êtes invité à enregistrer les paramètres de couverture des articles même si vous n’avez effectué aucune modification.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049466"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a><span data-ttu-id="c3720-103">Vous êtes invité à enregistrer les paramètres de couverture des articles même si vous n’avez effectué aucune modification</span><span class="sxs-lookup"><span data-stu-id="c3720-103">You're prompted to save item coverage settings even though you made no changes</span></span>

<span data-ttu-id="c3720-104">Numéro de la base de connaissances : 4615588</span><span class="sxs-lookup"><span data-stu-id="c3720-104">KB number: 4615588</span></span>

## <a name="symptoms"></a><span data-ttu-id="c3720-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="c3720-105">Symptoms</span></span>

<span data-ttu-id="c3720-106">Dans certains scénarios, vous pouvez recevoir le message suivant lorsque vous ouvrez la page **Couverture d’article** après avoir importé des articles via l’entité *Couverture d’article V2* :</span><span class="sxs-lookup"><span data-stu-id="c3720-106">In some scenarios, you might receive the following message when you open the **Item coverage** page after you import items through the *Item coverage V2* entity:</span></span>

> <span data-ttu-id="c3720-107">Voulez-vous enregistrer les modifications avant de clôturer ?</span><span class="sxs-lookup"><span data-stu-id="c3720-107">Do you want to save your changes before closing?</span></span>

<span data-ttu-id="c3720-108">Vous recevez ce message même si vous n’avez effectué aucune modification.</span><span class="sxs-lookup"><span data-stu-id="c3720-108">You receive this message even though you haven't made any changes.</span></span>

## <a name="resolution"></a><span data-ttu-id="c3720-109">Résolution</span><span class="sxs-lookup"><span data-stu-id="c3720-109">Resolution</span></span>

<span data-ttu-id="c3720-110">La page **Couverture d’article** inclut une logique par défaut complexe qui peut entraîner l’affichage du message une fois que des changements directs ont été récemment effectués dans la base de données, par exemple via l’importation d’entités.</span><span class="sxs-lookup"><span data-stu-id="c3720-110">The **Item coverage** page includes complex defaulting logic that might cause the message to be shown after direct changes have recently been made in the database, such as through entity import.</span></span> <span data-ttu-id="c3720-111">Par exemple, le champ d’entité `AREGENERALSETTINGSOVERRIDDEN` est défini sur *Non*, mais vous importez un fichier qui fournit des valeurs nouvelles ou modifiées pour des champs tels que `PRODUCTCOVERAGEGROUPID` et/ou `VENDORACCOUNTNUMBER`.</span><span class="sxs-lookup"><span data-stu-id="c3720-111">For example, the `AREGENERALSETTINGSOVERRIDDEN` entity field is set to *No*, but you import a file that provides new or modified values for fields such as `PRODUCTCOVERAGEGROUPID` and/or `VENDORACCOUNTNUMBER`.</span></span> <span data-ttu-id="c3720-112">Dans ce cas, comme le champ `AREGENERALSETTINGSOVERRIDDEN` est défini sur *Non*, les valeurs sont automatiquement effacées des champs lorsque vous ouvrez la page **Couverture d’article** pour la première fois après l’importation.</span><span class="sxs-lookup"><span data-stu-id="c3720-112">In this case, because the `AREGENERALSETTINGSOVERRIDDEN` field is set to *No*, the values are automatically cleared from the fields when you open the **Item coverage** page for the first time after the import.</span></span> <span data-ttu-id="c3720-113">Si vous enregistrez les modifications à l’invite de la zone de message, elles sont stockées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c3720-113">If you save the changes as the message box prompts, they are stored in the database.</span></span> <span data-ttu-id="c3720-114">Sinon, vous recevrez le même message la prochaine fois que vous ouvrirez la page.</span><span class="sxs-lookup"><span data-stu-id="c3720-114">Otherwise, you will receive the same message the next time that you open the page.</span></span>

<span data-ttu-id="c3720-115">Pour éviter ce comportement mais aussi inclure des valeurs pour des champs tels que `PRODUCTCOVERAGEGROUPID` via l’importation d’entités, définissez `AREGENERALSETTINGSOVERRIDDEN` sur *Oui* lors de l’importation.</span><span class="sxs-lookup"><span data-stu-id="c3720-115">To prevent this behavior but also include values for fields such as `PRODUCTCOVERAGEGROUPID` through entity import, set `AREGENERALSETTINGSOVERRIDDEN` to *Yes* when you import.</span></span>
