---
title: Éviter la troncation de texte de la hiérarchie des postes et exporter dans Visio
description: Cette rubrique explique comment résoudre un problème dans lequel les noms des personnes et les postes sont tronqués lorsque les clients affichent la hiérarchie des postes dans Dynamics 365 for Talent. La troncation de texte peut rendre difficile l'exécution d'une capture d'écran ou d'une impression de la hiérarchie.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b688a396e3b384aedb06c470b1634150ae7aa038
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304336"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="4fdad-104">Éviter la troncation de texte de la hiérarchie des postes et exporter dans Visio</span><span class="sxs-lookup"><span data-stu-id="4fdad-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4fdad-105">**Problème**</span><span class="sxs-lookup"><span data-stu-id="4fdad-105">**Issue**</span></span>

<span data-ttu-id="4fdad-106">Lorsqu'un client affiche la hiérarchie des postes dans Microsoft Dynamics 365 for Talent, les noms des personnes et les postes sont tronqués.</span><span class="sxs-lookup"><span data-stu-id="4fdad-106">When a customer views the position hierarchy in Microsoft Dynamics 365 for Talent, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="4fdad-107">Par conséquent, il peut être difficile d'effectuer une capture d'écran, ou d'imprimer et de distribuer la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="4fdad-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Hiérarchie des postes](media/position-h.png)

<span data-ttu-id="4fdad-109">**Cause**</span><span class="sxs-lookup"><span data-stu-id="4fdad-109">**Cause**</span></span>

<span data-ttu-id="4fdad-110">Ce comportement est fait exprès.</span><span class="sxs-lookup"><span data-stu-id="4fdad-110">This behavior is by design.</span></span>

<span data-ttu-id="4fdad-111">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="4fdad-111">**Resolution**</span></span>

<span data-ttu-id="4fdad-112">Malheureusement, les utilisateurs ne peuvent pas facilement modifier la taille du texte.</span><span class="sxs-lookup"><span data-stu-id="4fdad-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="4fdad-113">Toutefois, vous pouvez exporter la hiérarchie des postes de Talent puis les importer dans Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="4fdad-113">However, you can export the position hierarchy out of Talent and then import it into Microsoft Visio.</span></span> <span data-ttu-id="4fdad-114">Bien que l'article suivant a été rédigé pour Microsoft Dynamics AX 2012, le processus s'applique toujours à Talent : [Exporter une hiérarchie des postes vers Microsoft Visio](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="4fdad-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Talent: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="4fdad-115">Procédez comme suit pour exporter dans Visio.</span><span class="sxs-lookup"><span data-stu-id="4fdad-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="4fdad-116">Dans Talent, ouvrez la page de liste **Postes**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-116">In Talent, open the **Positions** list page.</span></span>

    <span data-ttu-id="4fdad-117">Pour inclure des informations supplémentaires dans le diagramme de structure de l'organisation, ajoutez des champs à la liste **Postes**, afin qu'ils soient disponibles lorsque vous utilisez l'Assistant ultérieurement dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="4fdad-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="4fdad-118">Dans le volet Actions, sélectionnez le bouton **Ouvrir dans Microsoft Office**, puis, sous **Exporter vers Excel**, sélectionnez **Postes**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="4fdad-119">Sinon, appuyez sur Ctrl+T.</span><span class="sxs-lookup"><span data-stu-id="4fdad-119">Alternatively, press Ctrl+T.</span></span>

    ![Exporter la page de la liste des postes vers Excel](media/org-admin.png)

3. <span data-ttu-id="4fdad-121">Enregistrez le fichier Excel exporté.</span><span class="sxs-lookup"><span data-stu-id="4fdad-121">Save the Excel file that is exported.</span></span>

    ![Boîte de dialogue Exporter vers Excel](media/export-excel.png)

4. <span data-ttu-id="4fdad-123">Dans Visio, sélectionnez **Visio - Créer**, puis sélectionnez la catégorie de modèle **Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Nouveau diagramme](media/new.png)

5. <span data-ttu-id="4fdad-125">Sélectionnez **Assistant de graphique d'organisation**, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Boîte de dialogue Assistant de graphique d'organisation](media/orgchart-wizard.png)

6. <span data-ttu-id="4fdad-127">Sélectionnez **Informations déjà stockées dans un fichier ou une base de données**, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Assistant Diagramme de l'organisation 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="4fdad-129">Choisissez **Un texte, Org Plus (\*.txt), ou fichier Excel**, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Assistant Diagramme de l'organisation 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="4fdad-131">Naviguez pour sélectionner le fichier Excel exporté contenant la hiérarchie des postes, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Assistant Diagramme de l'organisation 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="4fdad-133">Définissez le champ **Nom** sur **Poste**, définissez le champ **Référence** sur **Poste de référence**, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Assistant Diagramme de l'organisation 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="4fdad-135">Sélectionnez les champs qui doivent être affichés sur chaque nœud, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Assistant Diagramme de l'organisation 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="4fdad-137">Ajoutez la colonne **Poste** à la liste **Champs de données de forme**, puis la sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Assistant Diagramme de l'organisation 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="4fdad-139">Les images ne sont pas actuellement disponibles.</span><span class="sxs-lookup"><span data-stu-id="4fdad-139">Pictures aren't currently available.</span></span> <span data-ttu-id="4fdad-140">Par conséquent, sur la page suivante, sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="4fdad-141">Sélectionnez **Je souhaite que l'Assistant répartisse automatiquement mon graphique d'organisation entre les pages**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Assistant Diagramme de l'organisation 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="4fdad-143">Sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4fdad-143">Select **Finish**.</span></span>

    <span data-ttu-id="4fdad-144">Si des postes ne figurent pas dans la structure, vous êtes invité à les inclure dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="4fdad-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="4fdad-145">Le diagramme généré dans Visio affiche chaque responsable sur une feuille de calcul distincte.</span><span class="sxs-lookup"><span data-stu-id="4fdad-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="4fdad-146">Selon les champs sélectionnés à inclure dans le diagramme, chaque nœud affiche les informations appropriées lorsque le fichier Visio est généré.</span><span class="sxs-lookup"><span data-stu-id="4fdad-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Diagramme de la hiérarchie](media/hierarchy.png)

<span data-ttu-id="4fdad-148">**Option supplémentaire**</span><span class="sxs-lookup"><span data-stu-id="4fdad-148">**Additional option**</span></span>

<span data-ttu-id="4fdad-149">Dans Talent, vous pouvez également pouvoir utiliser l'espace de travail **Personnes** pour afficher des informations associées à la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="4fdad-149">In Talent, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>
