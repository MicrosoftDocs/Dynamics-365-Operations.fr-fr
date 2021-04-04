---
title: Éviter la troncation de texte de la hiérarchie des postes et exporter dans Visio
description: Cet article explique comment résoudre un problème dans lequel les noms des personnes et les postes sont tronqués lorsque les clients affichent la hiérarchie des postes dans Microsoft Dynamics 365 Human Resources. La troncation de texte peut rendre difficile l’exécution d’une capture d’écran ou d’une impression de la hiérarchie.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a745543f4d2a2e2a94a820f4ff5f35f8067a83d7
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466374"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="8305b-104">Éviter la troncation de texte de la hiérarchie des postes et exporter dans Visio</span><span class="sxs-lookup"><span data-stu-id="8305b-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8305b-105">**Problème**</span><span class="sxs-lookup"><span data-stu-id="8305b-105">**Issue**</span></span>

<span data-ttu-id="8305b-106">Lorsqu’un client affiche la hiérarchie des postes dans Microsoft Dynamics 365 Human Resources, les noms des personnes et les postes sont tronqués.</span><span class="sxs-lookup"><span data-stu-id="8305b-106">When a customer views the position hierarchy in Microsoft Dynamics 365 Human Resources, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="8305b-107">Par conséquent, il peut être difficile d’effectuer une capture d’écran, ou d’imprimer et de distribuer la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="8305b-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Hiérarchie des postes](media/position-h.png)

<span data-ttu-id="8305b-109">**Cause**</span><span class="sxs-lookup"><span data-stu-id="8305b-109">**Cause**</span></span>

<span data-ttu-id="8305b-110">Ce comportement est fait exprès.</span><span class="sxs-lookup"><span data-stu-id="8305b-110">This behavior is by design.</span></span>

<span data-ttu-id="8305b-111">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="8305b-111">**Resolution**</span></span>

<span data-ttu-id="8305b-112">Malheureusement, les utilisateurs ne peuvent pas facilement modifier la taille du texte.</span><span class="sxs-lookup"><span data-stu-id="8305b-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="8305b-113">Toutefois, vous pouvez exporter la hiérarchie des postes de Human Resources puis les importer dans Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="8305b-113">However, you can export the position hierarchy out of Human Resources and then import it into Microsoft Visio.</span></span> <span data-ttu-id="8305b-114">Bien que l’article suivant ait été rédigé pour Microsoft Dynamics AX 2012, le processus s’applique toujours à Human Resources : [Exporter une hiérarchie des postes vers Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="8305b-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Human Resources: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="8305b-115">Procédez comme suit pour exporter dans Visio.</span><span class="sxs-lookup"><span data-stu-id="8305b-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="8305b-116">Dans Human Resources, ouvrez la page de liste **Postes**.</span><span class="sxs-lookup"><span data-stu-id="8305b-116">In Human Resources, open the **Positions** list page.</span></span>

    <span data-ttu-id="8305b-117">Pour inclure des informations supplémentaires dans le diagramme de structure de l’organisation, ajoutez des champs à la liste **Postes**, afin qu’ils soient disponibles lorsque vous utilisez l’Assistant ultérieurement dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="8305b-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="8305b-118">Dans le volet Actions, sélectionnez le bouton **Ouvrir dans Microsoft Office**, puis, sous **Exporter vers Excel**, sélectionnez **Postes**.</span><span class="sxs-lookup"><span data-stu-id="8305b-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="8305b-119">Sinon, appuyez sur Ctrl+T.</span><span class="sxs-lookup"><span data-stu-id="8305b-119">Alternatively, press Ctrl+T.</span></span>

    ![Exporter la page de la liste des postes vers Excel](media/org-admin.png)

3. <span data-ttu-id="8305b-121">Enregistrez le fichier Excel exporté.</span><span class="sxs-lookup"><span data-stu-id="8305b-121">Save the Excel file that is exported.</span></span>

    ![Boîte de dialogue Exporter vers Excel](media/export-excel.png)

4. <span data-ttu-id="8305b-123">Dans Visio, sélectionnez **Visio - Créer**, puis sélectionnez la catégorie de modèle **Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="8305b-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Nouveau diagramme](media/new.png)

5. <span data-ttu-id="8305b-125">Sélectionnez **Assistant de graphique d’organisation**, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="8305b-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Boîte de dialogue Assistant de graphique d’organisation](media/orgchart-wizard.png)

6. <span data-ttu-id="8305b-127">Sélectionnez **Informations déjà stockées dans un fichier ou une base de données**, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8305b-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Assistant Diagramme de l’organisation 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="8305b-129">Choisissez **Un texte, Org Plus (\*.txt), ou fichier Excel**, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8305b-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Assistant Diagramme de l’organisation 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="8305b-131">Naviguez pour sélectionner le fichier Excel exporté contenant la hiérarchie des postes, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8305b-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Assistant Diagramme de l’organisation 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="8305b-133">Définissez le champ **Nom** sur **Poste**, définissez le champ **Référence** sur **Poste de référence**, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8305b-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Assistant Diagramme de l’organisation 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="8305b-135">Sélectionnez les champs qui doivent être affichés sur chaque nœud, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8305b-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Assistant Diagramme de l’organisation 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="8305b-137">Ajoutez la colonne **Poste** à la liste **Champs de données de forme**, puis la sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8305b-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Assistant Diagramme de l’organisation 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="8305b-139">Les images ne sont pas actuellement disponibles.</span><span class="sxs-lookup"><span data-stu-id="8305b-139">Pictures aren't currently available.</span></span> <span data-ttu-id="8305b-140">Par conséquent, sur la page suivante, sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8305b-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="8305b-141">Sélectionnez **Je souhaite que l’Assistant répartisse automatiquement mon graphique d’organisation entre les pages**.</span><span class="sxs-lookup"><span data-stu-id="8305b-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Assistant Diagramme de l’organisation 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="8305b-143">Sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="8305b-143">Select **Finish**.</span></span>

    <span data-ttu-id="8305b-144">Si des postes ne figurent pas dans la structure, vous êtes invité à les inclure dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="8305b-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="8305b-145">Le diagramme généré dans Visio affiche chaque responsable sur une feuille de calcul distincte.</span><span class="sxs-lookup"><span data-stu-id="8305b-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="8305b-146">Selon les champs sélectionnés à inclure dans le diagramme, chaque nœud affiche les informations appropriées lorsque le fichier Visio est généré.</span><span class="sxs-lookup"><span data-stu-id="8305b-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Diagramme de la hiérarchie](media/hierarchy.png)

<span data-ttu-id="8305b-148">**Option supplémentaire**</span><span class="sxs-lookup"><span data-stu-id="8305b-148">**Additional option**</span></span>

<span data-ttu-id="8305b-149">Dans Human Resources, vous pouvez également pouvoir utiliser l’espace de travail **Personnes** pour afficher des informations associées à la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="8305b-149">In Human Resources, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]