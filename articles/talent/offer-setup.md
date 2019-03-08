---
title: Paramétrer la gestion des offres
description: Cette rubrique décrit comment paramétrer les offres dans Talent.
author: josaw
manager: AnnBe
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa6c8c80870dd7bd06498c7571ba8a110be85c86
ms.sourcegitcommit: 3b12ff5ca81650ae666ff443b0bc998182f3931e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "376505"
---
# <a name="set-up-offer-management"></a><span data-ttu-id="e51d7-103">Paramétrer la gestion des offres</span><span class="sxs-lookup"><span data-stu-id="e51d7-103">Set up offer management</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="e51d7-104">Lorsqu'un candidat est déplacé vers le stade de l'offre dans Dynamics 365 for Talent : Attract, vous devez vous assurer que les offres peuvent être rapidement créées pour le candidat, approuvées au besoin, et soumises au candidat.</span><span class="sxs-lookup"><span data-stu-id="e51d7-104">When a candidate is moved to the offer stage in Dynamics 365 for Talent: Attract, you need to ensure that the offers can be quickly created for the candidate, approved as necessary, and sent out to the candidate.</span></span> <span data-ttu-id="e51d7-105">Comme la plupart des offres sont standard, elles peuvent être créées à partir de modèles réutilisables.</span><span class="sxs-lookup"><span data-stu-id="e51d7-105">Because most offers are standard, they can be created from reusable templates.</span></span> <span data-ttu-id="e51d7-106">Dans Attract, toutes les offres sont regroupées dans un package d'offre, qui est un ensemble d'un ou plusieurs documents d'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-106">In Attract, all offers are rolled into an offer package, which is a collection of one or more offer documents.</span></span> 

<span data-ttu-id="e51d7-107">Cette rubrique répertorie toutes les étapes qu'un administrateur Attract doit suivre pour paramétrer différents modèles de package d'offre dans le cadre de la fonctionnalité de gestion des offres d'Attract.</span><span class="sxs-lookup"><span data-stu-id="e51d7-107">This topic lists all the steps that an Attract administrator would follow to set up different offer package templates as part of the offer management capability in Attract.</span></span> <span data-ttu-id="e51d7-108">Les utilisateurs avec des rôles non-administrateurs n'ont pas accès à ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="e51d7-108">Users with non-administrator roles will not have access to these capabilities.</span></span>

>[!NOTE]
> <span data-ttu-id="e51d7-109">Les fonctionnalités de gestion des offres sont disponibles dans le cadre du composant additionnel de recrutement complet.</span><span class="sxs-lookup"><span data-stu-id="e51d7-109">Offer management capabilities are available as part of the Comprehensive Hiring Add-On.</span></span>

## <a name="offer-data"></a><span data-ttu-id="e51d7-110">Données de l'offre</span><span class="sxs-lookup"><span data-stu-id="e51d7-110">Offer data</span></span> 

<span data-ttu-id="e51d7-111">Les données de l'offre constituent la plus petite unité à l'intérieur du modèle de package d'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-111">Offer data is the smallest unit inside the offer package template.</span></span> <span data-ttu-id="e51d7-112">Une offre classique consiste en un texte standard et un ensemble de valeurs.</span><span class="sxs-lookup"><span data-stu-id="e51d7-112">A typical offer consists of standard text and a set of values.</span></span> <span data-ttu-id="e51d7-113">Les ensembles de valeurs sont les seuls éléments qui peuvent changer entre les offres.</span><span class="sxs-lookup"><span data-stu-id="e51d7-113">The sets of values are the only pieces that could change between offers.</span></span> <span data-ttu-id="e51d7-114">Lors de la création de l'offre, l'aspect le plus important que le créateur de l'offre doit prendre en compte est la liste des espaces réservés des données de l'offre présents dans un modèle de package d'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-114">During the offer creation, the most important aspect that the offer creator can focus on is the list of offer data placeholders present in an offer package template.</span></span> <span data-ttu-id="e51d7-115">Pour paramétrer les données de l'offre, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e51d7-115">To set up offer data, do the following.</span></span>

1.  <span data-ttu-id="e51d7-116">Accédez à **Gestion des offres**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-116">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="e51d7-117">Développez la section **Bibliothèque** dans le volet de navigation gauche, puis accédez à **Données de l'offre**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-117">Expand the **Library** section in the left navigation pane, then go to **Offer data**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="e51d7-118">Dans la page **Données de l'offre** se trouvent les sections **Détails du candidat** et **Détails de la mission**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-118">On the **Offer data** page are the **Candidate details** and **Job details** sections.</span></span> <span data-ttu-id="e51d7-119">Attract fournit quelques espaces réservés de données prêts à l'emploi.</span><span class="sxs-lookup"><span data-stu-id="e51d7-119">Attract provides a few offer data placeholders out-of-the-box.</span></span>
    
    > <span data-ttu-id="e51d7-120">Il existe des sections dans la page permettant d'organiser les différents espaces réservés de données de l'offre en groupes logiques.</span><span class="sxs-lookup"><span data-stu-id="e51d7-120">There are sections on the page to organize different offer data placeholders together in logical groups.</span></span> <span data-ttu-id="e51d7-121">Ces sections peuvent vous aider dans la mise à jour des données de l'offre et le renseignement des données lors du processus de création de l'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-121">These sections can help with maintenance of offer data and population of data during the offer creation process.</span></span>

1.  <span data-ttu-id="e51d7-122">Pour créer une section de données de l'offre, cliquez sur **Ajouter une section** et entrez un nom unique pour la section.</span><span class="sxs-lookup"><span data-stu-id="e51d7-122">To create a new offer data section, click **Add a section** and enter a unique name for the section.</span></span>

1.  <span data-ttu-id="e51d7-123">Pour ajouter des espaces réservés de données de l'offre dans une section, cliquez sur **Ajouter des données de l'offre** et entrez un nom unique pour l'espace réservé.</span><span class="sxs-lookup"><span data-stu-id="e51d7-123">To add offer data placeholders to any section, click **Add offer data** and enter a unique name for the placeholder.</span></span>

1.  <span data-ttu-id="e51d7-124">Pour modifier le nom d'une section, placez votre pointeur sur le nom de la section et mettez-le à jour.</span><span class="sxs-lookup"><span data-stu-id="e51d7-124">To edit the name of any section, hover over the section name and update the name.</span></span>

1.  <span data-ttu-id="e51d7-125">Pour modifier le nom d'un espace réservé de données de l'offre existant, assurez-vous d'abord que l'espace réservé ne fait pas déjà partie d'un modèle.</span><span class="sxs-lookup"><span data-stu-id="e51d7-125">To edit the name of any existing offer data placeholder, first make sure that the placeholder is not already part of any template.</span></span> <span data-ttu-id="e51d7-126">Ensuite, placez votre pointeur sur le nom de l'espace réservé de données de l'offre et mettez à jour le nom selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="e51d7-126">Then, hover over the name of the offer data placeholder and update the name as needed.</span></span>

1. <span data-ttu-id="e51d7-127">Pour supprimer un espace réservé de données de l'offre existant, assurez-vous d'abord que l'espace réservé ne fait pas partie d'un autre modèle.</span><span class="sxs-lookup"><span data-stu-id="e51d7-127">To delete an existing offer data placeholder, first make sure that the placeholder is not part of any other template.</span></span> <span data-ttu-id="e51d7-128">Ensuite, placez votre pointeur sur l'espace réservé et lorsque l'icône de la poubelle s'affiche, cliquez dessus pour supprimer l'espace réservé de données de l'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-128">Then, hover over the placeholder and when the trash can icon appears, click the trash can to delete the offer data placeholder.</span></span>
    >[!NOTE]
    > <span data-ttu-id="e51d7-129">Vous pouvez voir le nombre de modèles dont fait partie un espace réservé de données de l'offre grâce à l'indicateur de chiffre en regard de chaque donnée de l'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-129">You can see how many templates an offer data placeholder is part of by the number indicator next to each offer data.</span></span> 

1. <span data-ttu-id="e51d7-130">Pour supprimer une section, placez votre pointeur sur le nom.</span><span class="sxs-lookup"><span data-stu-id="e51d7-130">To delete any section, hover over the name.</span></span> <span data-ttu-id="e51d7-131">Si aucun des espaces réservés de données de l'offre dans la section n'apparaît dans aucun modèle, vous pouvez cliquer sur l'icône de la poubelle pour la supprimer.</span><span class="sxs-lookup"><span data-stu-id="e51d7-131">If none of the offer data placeholders inside the section appear in any template, you can click the trash can icon to delete it.</span></span> 
    >[!NOTE]
    > <span data-ttu-id="e51d7-132">La suppression de la section supprimera également tous les espaces réservés de données de l'offre qu'elle contient.</span><span class="sxs-lookup"><span data-stu-id="e51d7-132">Deleting the section will also delete all the offer data placeholders inside that section.</span></span>

<span data-ttu-id="e51d7-133">Une fois les espaces réservés des données de l'offre définis, vous pouvez les utiliser dans n'importe quel modèle de document.</span><span class="sxs-lookup"><span data-stu-id="e51d7-133">After the offer data placeholders have been set up, you can use them across any document template.</span></span> <span data-ttu-id="e51d7-134">Les espaces réservés de données de l'offre ne sont pas limités à un modèle spécifique : le même ensemble peut être utilisé dans tous les modèles.</span><span class="sxs-lookup"><span data-stu-id="e51d7-134">Offer data placeholders are not restricted to a specific template -- the same set can be used across all templates.</span></span>

## <a name="offer-data-rules"></a><span data-ttu-id="e51d7-135">Règles de données de l'offre</span><span class="sxs-lookup"><span data-stu-id="e51d7-135">Offer data rules</span></span>

<span data-ttu-id="e51d7-136">La plupart d'organisation disposent de règles relatives à la création des offres.</span><span class="sxs-lookup"><span data-stu-id="e51d7-136">Most organization have rules for how offers must be created.</span></span> <span data-ttu-id="e51d7-137">Par exemple, une organisation peut souhaiter exiger que les offres de salaire annuel maximales pour une combinaison de lieu et de niveau d'ancienneté spécifiques soient situées dans une certaine plage, ou que seules quelques valeurs spécifiques soient possibles au niveau de l'offre pour la nouvelle recrue.</span><span class="sxs-lookup"><span data-stu-id="e51d7-137">For example, an organization may want to require that the maximum annual salary offer for a specific location and seniority level combination has to be within a certain range, or that there are only a few specific values possible for the offer level for the new hire.</span></span> <span data-ttu-id="e51d7-138">Attract prend actuellement en charge toutes ces règles de données à l'aide d'un fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="e51d7-138">Attract currently supports all such data rules using a CSV file.</span></span>

<span data-ttu-id="e51d7-139">Pour préparer le fichier CSV de règles de données, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e51d7-139">To prepare the data rules CSV file, do the following.</span></span>

1.  <span data-ttu-id="e51d7-140">Déterminez l'espace réservé de données de l'offre pour l'ensemble de règles.</span><span class="sxs-lookup"><span data-stu-id="e51d7-140">Determine the offer data placeholder for the rule set.</span></span> <span data-ttu-id="e51d7-141">Par exemple, **Salaire annuel**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-141">For example, **Annual Salary**.</span></span>

1.  <span data-ttu-id="e51d7-142">Identifiez les valeurs de l'espace réservé de données de l'offre dépendantes.</span><span class="sxs-lookup"><span data-stu-id="e51d7-142">Identify the dependent offer data placeholder values.</span></span> <span data-ttu-id="e51d7-143">Par exemple, **Emplacement de la mission** et **Niveau**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-143">For example, **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="e51d7-144">Spécifiez les colonnes 1 et 2 en **Emplacement de la mission** et **Niveau**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-144">Specify columns 1 and 2 as **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="e51d7-145">Pour charger une valeur de plage, faites des colonnes 3 et 4 **Salaire annuel**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-145">To upload a range value, make columns 3 and 4 **Annual Salary**.</span></span> <span data-ttu-id="e51d7-146">Pour charger une valeur spécifique au lieu d'une plage, faites de la colonne 3 **Salaire annuel**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-146">To upload a specific value instead of a range, only make column 3 **Annual Salary**.</span></span>

1.  <span data-ttu-id="e51d7-147">Renseignez le fichier Microsoft Excel selon vos rôles obligatoires.</span><span class="sxs-lookup"><span data-stu-id="e51d7-147">Populate the Microsoft Excel file based on your required roles.</span></span>

1.  <span data-ttu-id="e51d7-148">Assurez-vous que chaque ligne soit une combinaison unique des valeurs regroupées.</span><span class="sxs-lookup"><span data-stu-id="e51d7-148">Ensure that each row is a unique combination of all the values put together.</span></span>

1.  <span data-ttu-id="e51d7-149">Enregistrez le fichier au format CSV.</span><span class="sxs-lookup"><span data-stu-id="e51d7-149">Save the file as a CSV format.</span></span>

<span data-ttu-id="e51d7-150">Pour charge le fichier de règles de données de l'offre, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e51d7-150">To upload the offer data rules file, do the following.</span></span>

1.  <span data-ttu-id="e51d7-151">Accédez à **Gestion des offres**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-151">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="e51d7-152">Développez la section **Bibliothèque** dans le volet de navigation gauche, puis accédez à **Règles de données de l'offre**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-152">Expand the **Library** section in the left navigation panel, then go to **Offer data rules**.</span></span>

1.  <span data-ttu-id="e51d7-153">Cliquez sur **Nouvel ensemble de données** pour afficher la boîte de dialogue **Charger**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-153">Click **New data set** to display the **Upload** dialog box.</span></span>

1.  <span data-ttu-id="e51d7-154">Spécifiez un nom unique pour l'ensemble de règles puis chargez le fichier CSV enregistré.</span><span class="sxs-lookup"><span data-stu-id="e51d7-154">Specify a unique name for the rule set and then upload the saved CSV file.</span></span>

1.  <span data-ttu-id="e51d7-155">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-155">Click **Add**.</span></span>
    <span data-ttu-id="e51d7-156">L'ensemble de règles sera traité en arrière-plan et vous sera notifié dans l'application avertie et par courrier électronique lorsque le traitement sera terminé.</span><span class="sxs-lookup"><span data-stu-id="e51d7-156">The rule set will be processed in the background and you will be notified in-app and via email once it completes.</span></span>

    <span data-ttu-id="e51d7-157">Vous serez averti si des erreurs surviennent lors du traitement du chargement.</span><span class="sxs-lookup"><span data-stu-id="e51d7-157">You will be notified if there are errors while processing the upload.</span></span> <span data-ttu-id="e51d7-158">Vous pouvez ensuite télécharger le journal des erreurs, corriger le fichier, et le charger de nouveau.</span><span class="sxs-lookup"><span data-stu-id="e51d7-158">You can then download the error log, fix the file, and upload it again.</span></span>

1.  <span data-ttu-id="e51d7-159">L'option du bouton (**...**) si vous souhaitez télécharger l'ensemble de règles et mettre à jour l'ensemble de valeurs.</span><span class="sxs-lookup"><span data-stu-id="e51d7-159">Use the ellipses button (**…**) option if you want to download the rule set and update the set of values.</span></span> <span data-ttu-id="e51d7-160">Après la mise à jour, vous pouvez charger le fichier de nouveau.</span><span class="sxs-lookup"><span data-stu-id="e51d7-160">After updating, you can upload the file again.</span></span>

1.  <span data-ttu-id="e51d7-161">Vous pouvez supprimer un chargement de l'ensemble de règles existant si l'espace réservé est défini comme inutilisé dans un autre modèle de document.</span><span class="sxs-lookup"><span data-stu-id="e51d7-161">You can delete an existing rule set upload if the placeholder being defined is not being used in another document template.</span></span>

>[!NOTE]
> - <span data-ttu-id="e51d7-162">Chaque espace réservé ne peut disposer que d'un seul ensemble de colonnes dont il dépend.</span><span class="sxs-lookup"><span data-stu-id="e51d7-162">Each placeholder can only have one unique set of columns that it is dependent on.</span></span> <span data-ttu-id="e51d7-163">Par exemple, si **Salaire annuel** dépend d'**Emplacement de la mission** et de **Niveau**, vous ne pouvez pas charger un autre ensemble de règles où **Salaire annuel** dépend d'un ensemble de colonnes différent.</span><span class="sxs-lookup"><span data-stu-id="e51d7-163">For example, if **Annual Salary** is dependent on **Job Location** and **Level**, you can't upload another rule set where **Annual Salary** is dependent on a different set of columns.</span></span>

> - <span data-ttu-id="e51d7-164">Vous pouvez télécharger des exemples d'ensembles de règles de données de l'offre dans l'onglet **Exemples** de la page **Règles de données de l'offre**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-164">You can download sample offer data rule sets on the **Samples** tab on the **Offer data rules** page.</span></span>

> - <span data-ttu-id="e51d7-165">Lorsqu'un créateur d'offre remplace les valeurs recommandées par les règles de données de l'offre, l'offre est marquée comme non standard et le workflow d'approbation de l'offre est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="e51d7-165">When an offer creator overrides the values that are recommended by the offer data rules, the offer is flagged as non-standard and offer approval workflow will be mandated.</span></span>

## <a name="document-templates"></a><span data-ttu-id="e51d7-166">Modèles de document</span><span class="sxs-lookup"><span data-stu-id="e51d7-166">Document templates</span></span>

<span data-ttu-id="e51d7-167">Un modèle de document d'offre peut aider les administrateurs à créer des lettres d'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-167">An offer document template can help administrators create offer letters.</span></span> <span data-ttu-id="e51d7-168">Le modèle de document d'offre est une combinaison du texte faisant partie de l'offre et des espaces réservés de données de l'offre définis.</span><span class="sxs-lookup"><span data-stu-id="e51d7-168">The offer document template is a combination of the text that will be part of the offer as well as the defined offer data placeholders.</span></span> 

<span data-ttu-id="e51d7-169">Pour créer un modèle de document d'offre, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e51d7-169">To create an offer document template, do the following.</span></span>

1.  <span data-ttu-id="e51d7-170">Accédez à **Gestion des offres**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-170">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="e51d7-171">Développez la section **Bibliothèque** dans le volet de navigation gauche et accédez à **Modèles**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-171">Expand the **Library** section in the left navigation pane and go to **Templates**.</span></span>

    <span data-ttu-id="e51d7-172">La page **Modèles** affiche une liste des modèles de documents déjà définis.</span><span class="sxs-lookup"><span data-stu-id="e51d7-172">The **Templates** page will display a list of document templates that have already been defined.</span></span>

1.  <span data-ttu-id="e51d7-173">Pour créer un modèle de document, cliquez sur **Nouveau modèle**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-173">To create a new document template, click **New Template**.</span></span>

1.  <span data-ttu-id="e51d7-174">Entrez un nom unique pour le modèle, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-174">Enter a unique name for the template and click **Create**.</span></span>

1.  <span data-ttu-id="e51d7-175">L'éditeur de texte enrichi vous permet d'insérer ou de modifier le contenu du document d'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-175">Use the rich text editor to insert or edit the offer document content.</span></span> <span data-ttu-id="e51d7-176">Vous pouvez insérer des tableaux, des images et des liens hypertexte à l'aide des options disponibles en haut de l'éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="e51d7-176">You can insert tables, images, and hyperlinks using the options available at the top of the text editor.</span></span>

1.  <span data-ttu-id="e51d7-177">Vous pouvez insérer des espaces réservés de données de l'offre dans le modèle de document d'offre en :</span><span class="sxs-lookup"><span data-stu-id="e51d7-177">You can insert offer data placeholders in the offer template document by:</span></span>

    - <span data-ttu-id="e51d7-178">Les faisant glisser et déplacer depuis le volet droit.</span><span class="sxs-lookup"><span data-stu-id="e51d7-178">Dragging and dropping from the right pane.</span></span>

    - <span data-ttu-id="e51d7-179">Ajoutant une balise de hachage directement à l'emplacement de l'espace réservé de données de l'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-179">Hashtag the offer data placeholder directly into position.</span></span> <span data-ttu-id="e51d7-180">Entrez **\#** puis commencez à saisir le nom de l'espace réservé de données de l'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-180">Type **\#** and then start typing the name of the offer data placeholder.</span></span> <span data-ttu-id="e51d7-181">Des options s'afficheront dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="e51d7-181">Options will appear in the drop-down list.</span></span> <span data-ttu-id="e51d7-182">Cliquez ou appuyez sur **Entrée** pour insérer l'espace réservé de données de l'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-182">Click or press **Enter** to insert the offer data placeholder.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="e51d7-183">Pour associer un espace réservé au modèle de document d'offre sans exposer sa valeur au candidat, placez votre pointeur sur l'espace réservé de données de l'offre et cliquez sur l'icône **Épingler**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-183">To associate a placeholder to the offer document template without exposing its value to the candidate, hover over the offer data placeholder and click the **Pin** icon.</span></span> <span data-ttu-id="e51d7-184">Cela placera l'espace réservé dans la section **Données de l'offre épinglées** du modèle de document de l'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-184">This will push the placeholder to the **Pinned offer data** section of the offer document template.</span></span> <span data-ttu-id="e51d7-185">Pour annuler l'épinglage, suivez les mêmes étapes mais cliquez sur **Annuler l'épinglage** dans la liste des espaces réservés de données de l'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-185">To unpin, follow the same steps but click **Unpin** in the list of offer data placeholders.</span></span>

    > - <span data-ttu-id="e51d7-186">Pour afficher la liste des espaces réservés de données de l'offre actifs, basculez vers l'onglet **Actif** dans le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="e51d7-186">To view the list of active offer data placeholders, switch to the **Active** tab in the right pane.</span></span>

    > - <span data-ttu-id="e51d7-187">Si vous insérez un espace réservé basé sur un ensemble de règles de données de l'offre, la dépendance de cet espace réservé de données de l'offre s'affiche sur d'autres valeurs.</span><span class="sxs-lookup"><span data-stu-id="e51d7-187">If you insert a placeholder that is driven by an offer data rule set, you can see the dependency of that offer data placeholder on other values.</span></span>

    > - <span data-ttu-id="e51d7-188">Sinon, vous pouvez **Importer** le contenu d'un fichier .docx sur votre ordinateur local et le modifier au besoin.</span><span class="sxs-lookup"><span data-stu-id="e51d7-188">Alternatively, you can **Import** the content from a .docx file on your local machine and edit as required.</span></span> <span data-ttu-id="e51d7-189">Ainsi, vous n'avez pas besoin d'entrer tout le contenu dans l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="e51d7-189">That way, you don’t have to type in all the content in the editor.</span></span>

1. <span data-ttu-id="e51d7-190">Pour afficher un aperçu du document d'offre, utilisez l'option **Aperçu** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="e51d7-190">To preview the offer document, use the **Preview** option at the top of the page.</span></span>

1. <span data-ttu-id="e51d7-191">Pour contrôler si un créateur d'offre peut modifier le contenu du document d'offre, utilisez l'option **Gérer les autorisations** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="e51d7-191">To control whether an offer creator can edit the offer document content, use the **Manage permission** option at the top of the page.</span></span> <span data-ttu-id="e51d7-192">Si vous souhaitez que le créateur de l'offre insère uniquement les valeurs de l'espace réservé sans modifier le texte, définissez la valeur d'autorisation sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-192">If you want the offer creator to only insert placeholder values and not edit text, set the permission value to **No**.</span></span>

1. <span data-ttu-id="e51d7-193">Cliquez sur **Enregistrer** pour enregistrer votre progression.</span><span class="sxs-lookup"><span data-stu-id="e51d7-193">Click **Save** to save your progress.</span></span> <span data-ttu-id="e51d7-194">Le modèle sera enregistré dans un état de brouillon.</span><span class="sxs-lookup"><span data-stu-id="e51d7-194">The template will be saved in a draft state.</span></span>

1. <span data-ttu-id="e51d7-195">Pour terminer et marquer le document comme publié, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-195">To finalize and mark the document as published, click **Finish**.</span></span>

1. <span data-ttu-id="e51d7-196">Vous pouvez afficher les modèles de document actuellement actifs, en mode de brouillon et archivés qui ne sont plus en cours d'utilisation sur l'expérience de page de destination de la bibliothèque de modèles de documents.</span><span class="sxs-lookup"><span data-stu-id="e51d7-196">You can see which document templates are currently active, in draft mode, and have been archived and are no longer in use on the document templates library landing experience.</span></span>

>[!NOTE]
> <span data-ttu-id="e51d7-197">Vous pouvez supprimer un modèle de document d'offre qui ne fait pas partie d'un modèle de package d'offre existant.</span><span class="sxs-lookup"><span data-stu-id="e51d7-197">You can delete any offer document template that is not part of an existing offer package template.</span></span>


## <a name="offer-package-templates"></a><span data-ttu-id="e51d7-198">Modèles de packages d'offre</span><span class="sxs-lookup"><span data-stu-id="e51d7-198">Offer package templates</span></span>

<span data-ttu-id="e51d7-199">Les packages d'offre sont les artefacts d'offre qui sont partagés avec le candidat et se composent d'une combinaison d'un ou de plusieurs modèles de document d'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-199">Offer packages are the offer artifacts that are shared with the candidate and consist of a combination of one or more offer document templates.</span></span> <span data-ttu-id="e51d7-200">Pour créer un package d'offre, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e51d7-200">To create an offer package, do the following.</span></span>

1.  <span data-ttu-id="e51d7-201">Accédez à **Gestion des offres**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-201">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="e51d7-202">Accédez à **Packages** dans volet de navigation de gauche.</span><span class="sxs-lookup"><span data-stu-id="e51d7-202">Go to **Packages** from the left navigation pane.</span></span>

    <span data-ttu-id="e51d7-203">Une liste des modèles de packages d'offre actifs disponibles pour les créateurs d'offres s'affiche.</span><span class="sxs-lookup"><span data-stu-id="e51d7-203">A list of active package templates that are available for offer creators to use is displayed.</span></span>

1.  <span data-ttu-id="e51d7-204">Pour créer un package d'offre, cliquez sur **Nouveau package**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-204">To create a new offer package, click **New Package**.</span></span>

1.  <span data-ttu-id="e51d7-205">Entrez un nom unique et cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-205">Enter a unique name and click **Create**.</span></span>

1.  <span data-ttu-id="e51d7-206">Cliquez sur **Ajouter un modèle**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-206">Click **Add template**.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="e51d7-207">Vous pouvez choisir de créer un modèle ou d'utiliser un modèle existant.</span><span class="sxs-lookup"><span data-stu-id="e51d7-207">You can choose to create a new template or choose from an existing one.</span></span>

    > - <span data-ttu-id="e51d7-208">Si vous choisissez d'ajouter un modèle existant, vous devez vous assurer que le modèle de document d'offre a été enregistré, terminé et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="e51d7-208">If you choose to add an existing template, you need to make sure that the   offer document template was saved, finalized, and marked as   active.</span></span>
    
    > - <span data-ttu-id="e51d7-209">Vous pouvez choisir autant de modèles de documents que vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="e51d7-209">You can choose as many document templates as you want.</span></span> 
    
1.  <span data-ttu-id="e51d7-210">Cliquez sur **Terminé** pour revenir à **Gestion du package**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-210">Click **Done** to return to **Package management**.</span></span>

    <span data-ttu-id="e51d7-211">Vous pouvez configurer la séquence des documents et également marquer si le document d'offre spécifique est obligatoire lors de la création d'une offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-211">You can configure the sequence of the documents and also mark whether the specific offer document is required during offer creation.</span></span> <span data-ttu-id="e51d7-212">Le créateur d'offre disposera d'une option pour supprimer les documents marqués comme **Non obligatoire**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-212">The offer creator will have an option to delete the documents marked as **Not required**.</span></span>

1. <span data-ttu-id="e51d7-213">Pour enregistrer le modèle de package d'offre afin qu'il soit utilisable par tous les créateurs d'offres, cliquez sur **Enregistrer et publier**.</span><span class="sxs-lookup"><span data-stu-id="e51d7-213">To save the offer package template so that it's usable by all offer creators, click **Save and publish**.</span></span>

   <span data-ttu-id="e51d7-214">Pour afficher les brouillons de modèles de packages d'offre, accédez à l'onglet **Brouillons**. Si une modification est apportée au modèle de package d'offre, celui-ci doit être enregistré et republié.</span><span class="sxs-lookup"><span data-stu-id="e51d7-214">To view draft offer package templates, go to the **Drafts** tab. If a change is made to the offer package template, it must be  saved and republished.</span></span>

## <a name="configure-an-offer-process"></a><span data-ttu-id="e51d7-215">Configurer un processus d'offre</span><span class="sxs-lookup"><span data-stu-id="e51d7-215">Configure an offer process</span></span>

<span data-ttu-id="e51d7-216">Il existe plusieurs parties du processus de création d'offre qui peuvent être configurées par un administrateur Attract.</span><span class="sxs-lookup"><span data-stu-id="e51d7-216">There are several parts of the offer creation process that can be configured by an Attract administrator.</span></span>

- <span data-ttu-id="e51d7-217">**Approbations de l'offre** : Choisissez si des approbations de l'offre sont requises avant que l'offre puisse être envoyée au candidat.</span><span class="sxs-lookup"><span data-stu-id="e51d7-217">**Offer approvals** - Choose whether offer approvals are required before the offer can be sent to the candidate.</span></span> <span data-ttu-id="e51d7-218">En tant qu'administrateur, vous pouvez également décider si toutes les approbations de l'offre se produiront de manière séquentielle ou via un workflow d'approbation parallèle.</span><span class="sxs-lookup"><span data-stu-id="e51d7-218">As an administrator, you can also decide whether all offer approvals will happen in a sequential manner or parallel approval workflow.</span></span> <span data-ttu-id="e51d7-219">Vous pouvez également décider si les approbateurs de l'offre doivent ajouter obligatoirement un commentaire à leur approbation d'offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-219">You can also mandate whether offer approvers must add a comment along with their offer approval.</span></span> <span data-ttu-id="e51d7-220">Les approbations d'offre sont obligatoires pour toutes les offres non standard.</span><span class="sxs-lookup"><span data-stu-id="e51d7-220">Offer approvals are mandatory for all non-standard offers.</span></span>

- <span data-ttu-id="e51d7-221">**Expérience d'offre du candidat** : En tant qu'administrateur, vous pouvez choisir de définir si toutes les offres ont une date d'expiration et, le cas échéant, quelle doit être la contrepartie par défaut pour la date d'expiration.</span><span class="sxs-lookup"><span data-stu-id="e51d7-221">**Candidate’s offer experience** - As administrator, you can choose to set whether all offers have an expiration date, and if so, what the default offset for the expiration date should be.</span></span> <span data-ttu-id="e51d7-222">Vous pouvez également configurer si les candidats peuvent refuser une offre.</span><span class="sxs-lookup"><span data-stu-id="e51d7-222">You can also configure whether candidates can decline an offer.</span></span>

- <span data-ttu-id="e51d7-223">**Signatures électroniques** - Tant donc qu'administrateur, vous pouvez également sélectionner la méthode que les candidats peuvent utiliser pour signer des offres.</span><span class="sxs-lookup"><span data-stu-id="e51d7-223">**e-Signatures** - As an administrator, you can also choose the method that candidates can use to sign offers.</span></span>
    - <span data-ttu-id="e51d7-224">Adobe Sign - Tous les packages d'offre sont envoyés et signés via Adobe Sign.</span><span class="sxs-lookup"><span data-stu-id="e51d7-224">Adobe Sign - All offer packages will be sent and signed via Adobe Sign.</span></span> <span data-ttu-id="e51d7-225">Chaque créateur d'offre publiant l'offre doit avoir sa licence Adobe Sign connectée Attract.</span><span class="sxs-lookup"><span data-stu-id="e51d7-225">Each offer creator publishing the offer needs to have their Adobe Sign license connected to Attract.</span></span> 

    - <span data-ttu-id="e51d7-226">ESign - Il s'agit de l'option par défaut, prédéfinie, permettant à l'utilisateur de signer une offre en entrant son nom et ses initiales.</span><span class="sxs-lookup"><span data-stu-id="e51d7-226">ESign - This is the default option, provided out of the box, where the user can sign an offer by typing their name and initials.</span></span>

>[!NOTE]
> <span data-ttu-id="e51d7-227">Pour les licences Adobe Sign et une version d'évaluation, consultez ce [lien](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).</span><span class="sxs-lookup"><span data-stu-id="e51d7-227">For Adobe Sign licenses and a free Trial, please visit this [link](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).</span></span>

<span data-ttu-id="e51d7-228">Pour en savoir plus sur le processus de création d'offre, voir [Création, approbation et signature des offres](./creating-offers.md).</span><span class="sxs-lookup"><span data-stu-id="e51d7-228">To learn more about the offer creation process, see [Creating, approving, and signing offers](./creating-offers.md).</span></span>
