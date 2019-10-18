---
title: Prise en charge des appels paramétrés des sources de données de gestion des états électroniques (ER) de type Champ calculé
description: Cette rubrique offre des informations concernant l'utilisation du type Champ calculé pour les sources de données de gestion des états électroniques.
author: NickSelin
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86efa927fa97be0d54e965bf33b1a18519025c22
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248675"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a><span data-ttu-id="ab3af-103">Prise en charge des appels paramétrés des sources de données de gestion des états électroniques (ER) de type Champ calculé</span><span class="sxs-lookup"><span data-stu-id="ab3af-103">Support parameterized calls of ER data sources of the Calculated field type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab3af-104">Cette rubrique explique comment vous pouvez concevoir une source de données de gestion des états électroniques à l'aide du type **Champ Calculé**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-104">This topic explains how you can design an Electronic reporting (ER) data source by using the **Calculated field** type.</span></span> <span data-ttu-id="ab3af-105">Cette source de données peut contenir une expression de gestion des états électroniques qui, une fois exécutée, peut être contrôlée par les valeurs des arguments de paramètre qui sont configurés dans une liaison qui appelle cette source de données.</span><span class="sxs-lookup"><span data-stu-id="ab3af-105">This data source may contain an ER expression that, when executed, can be controlled by the values of the parameter arguments that are configured in a binding that calls this data source.</span></span> <span data-ttu-id="ab3af-106">En configurant les appels paramétrés d'une telle source de données, vous pouvez réutiliser une seule source de données dans de nombreuses liaisons, ce qui réduit le nombre total de sources de données qui doivent être configurées dans les mappages de modèle de gestion des états électroniques ou de formats de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="ab3af-106">By configuring parameterized calls of such a data source, you can reuse a single data source in many bindings, which reduces the total number of data sources that must be configured in ER model mappings or ER formats.</span></span> <span data-ttu-id="ab3af-107">Cela simplifie également le composant de gestion des états électroniques configuré, ce qui réduit les coûts de maintenance et le coût d'utilisation par d'autres consommateurs.</span><span class="sxs-lookup"><span data-stu-id="ab3af-107">It also simplifies the configured ER component, which reduces the maintenance costs and the cost of use by other consumers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ab3af-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="ab3af-108">Prerequisites</span></span>
<span data-ttu-id="ab3af-109">Pour exécuter les exemples décrits dans cette rubrique, vous devez disposer de l'accès suivant :</span><span class="sxs-lookup"><span data-stu-id="ab3af-109">To complete the examples in this topic, you must have the following access:</span></span>

- <span data-ttu-id="ab3af-110">Accès à l'un de ces rôles :</span><span class="sxs-lookup"><span data-stu-id="ab3af-110">Access to one of these roles:</span></span>

    - <span data-ttu-id="ab3af-111">Développeur d'états électroniques</span><span class="sxs-lookup"><span data-stu-id="ab3af-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="ab3af-112">Consultant fonctionnel des états électroniques</span><span class="sxs-lookup"><span data-stu-id="ab3af-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="ab3af-113">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="ab3af-113">System administrator</span></span>

- <span data-ttu-id="ab3af-114">Accès aux Regulatory Configuration Service (RCS) qui ont été mis en service pour le même locataire que Finance and Operations, pour un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="ab3af-114">Access to Regulatory Configuration Services (RCS) that have been provisioned for the same tenant as Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="ab3af-115">Développeur d'états électroniques</span><span class="sxs-lookup"><span data-stu-id="ab3af-115">Electronic reporting developer</span></span>
    - <span data-ttu-id="ab3af-116">Consultant fonctionnel des états électroniques</span><span class="sxs-lookup"><span data-stu-id="ab3af-116">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="ab3af-117">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="ab3af-117">System administrator</span></span>

<span data-ttu-id="ab3af-118">Dans le [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684), téléchargez le fichier archivé (compressé) **Prise en charge des appels paramétrés des sources de données de gestion des états électroniques (ER) de type Champ calculé**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-118">From the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684), download the zipped (compressed) file **Support parameterized calls of ER data sources of Calculated field type**.</span></span> <span data-ttu-id="ab3af-119">Il contient les configurations de gestion des états électroniques suivants qui doivent être extraites et stockées localement.</span><span class="sxs-lookup"><span data-stu-id="ab3af-119">It contains the following ER configurations that must be extracted and stored locally.</span></span>

| <span data-ttu-id="ab3af-120">**Contenu**</span><span class="sxs-lookup"><span data-stu-id="ab3af-120">**Content**</span></span>                           | <span data-ttu-id="ab3af-121">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="ab3af-121">**File name**</span></span>                                        |
|---------------------------------------|------------------------------------------------------|
| <span data-ttu-id="ab3af-122">Exemple de configuration de modèle de données ER</span><span class="sxs-lookup"><span data-stu-id="ab3af-122">Sample ER data model configuration</span></span>    | <span data-ttu-id="ab3af-123">Model to learn parameterized calls.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="ab3af-123">Model to learn parameterized calls.version.1.xml</span></span>     |
| <span data-ttu-id="ab3af-124">Exemple de configuration de métadonnées ER</span><span class="sxs-lookup"><span data-stu-id="ab3af-124">Sample ER metadata configuration</span></span>      | <span data-ttu-id="ab3af-125">Metadata to learn parameterized calls.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="ab3af-125">Metadata to learn parameterized calls.version.1.xml</span></span>  |
| <span data-ttu-id="ab3af-126">Exemple de configuration de mappage de modèles ER</span><span class="sxs-lookup"><span data-stu-id="ab3af-126">Sample ER model mapping configuration</span></span> | <span data-ttu-id="ab3af-127">Mapping to learn parameterized calls.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="ab3af-127">Mapping to learn parameterized calls.version.1.1.xml</span></span> |
| <span data-ttu-id="ab3af-128">Exemple de configuration de format ER</span><span class="sxs-lookup"><span data-stu-id="ab3af-128">Sample ER format configuration</span></span>        | <span data-ttu-id="ab3af-129">Format to learn parameterized calls.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="ab3af-129">Format to learn parameterized calls.version.1.1.xml</span></span>  |

## <a name="sign-in-to-your-rcs-instance"></a><span data-ttu-id="ab3af-130">Connexion à votre instance RCS</span><span class="sxs-lookup"><span data-stu-id="ab3af-130">Sign in to your RCS instance</span></span>
<span data-ttu-id="ab3af-131">Dans cet exemple, vous allez créer une configuration pour l'exemple de société, Litware, Inc. Tout d'abord, dans RCS, vous devez suivre les étapes de la procédure [ER Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md) :</span><span class="sxs-lookup"><span data-stu-id="ab3af-131">In this example, you will create a configuration for the sample company, Litware, Inc. First, in RCS, you must complete the steps in the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure:</span></span>

1. <span data-ttu-id="ab3af-132">Dans le tableau de bord par défaut, sélectionnez **Gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-132">On the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="ab3af-133">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-133">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="ab3af-134">Importez les configurations téléchargées vers RCS dans l'ordre suivant : modèle de données, métadonnées, mise en correspondance des modèles, format.</span><span class="sxs-lookup"><span data-stu-id="ab3af-134">Import the downloaded configurations to RCS in the following sequence: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="ab3af-135">Procédez comme suit pour chaque configuration de gestion des états électroniques :</span><span class="sxs-lookup"><span data-stu-id="ab3af-135">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="ab3af-136">Sélectionnez **Échanger**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-136">Select **Exchange.**</span></span>
    2. <span data-ttu-id="ab3af-137">Sélectionnez **Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-137">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="ab3af-138">Sélectionnez **Parcourir**, puis sélectionnez la configuration ER requise au format XML.</span><span class="sxs-lookup"><span data-stu-id="ab3af-138">Select **Browse**, and then select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="ab3af-139">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-139">Select **OK.**</span></span>

## <a name="review-the-provided-er-solution"></a><span data-ttu-id="ab3af-140">Examen de la solution ER fournie</span><span class="sxs-lookup"><span data-stu-id="ab3af-140">Review the provided ER solution</span></span>

### <a name="review-model-mapping"></a><span data-ttu-id="ab3af-141">Examen de la mise en correspondance des modèles</span><span class="sxs-lookup"><span data-stu-id="ab3af-141">Review model mapping</span></span>

1. <span data-ttu-id="ab3af-142">Dans l'arborescence de configuration, développez le contenu de l'élément **Modèle pour l'apprentissage des appels paramétrés**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-142">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="ab3af-143">Sélectionnez **Mise en correspondance pour l'apprentissage des appels paramétrés**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-143">Select **Mapping to learn parameterized calls**.</span></span>
3. <span data-ttu-id="ab3af-144">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-144">Select **Designer**.</span></span>
4. <span data-ttu-id="ab3af-145">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-145">Select **Designer**.</span></span>  
   
<span data-ttu-id="ab3af-146">Cette mise en correspondance des modèles de gestion des états électroniques est conçue pour faire ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ab3af-146">This ER model mapping is designed to do the following:</span></span>

- <span data-ttu-id="ab3af-147">Récupérez la liste des codes taxe (source de données **Taxe**) se trouvant dans la table **TaxTable**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-147">Fetch the list of tax codes (**Tax** data source) residing in the   **TaxTable** table.</span></span>
- <span data-ttu-id="ab3af-148">Récupérez la liste des transactions de taxe (source de données **Trans**) se trouvant dans la table **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-148">Fetch the list of tax transactions (**Trans** data source) residing in the   **TaxTrans** table:</span></span>
    
    - <span data-ttu-id="ab3af-149">Regroupez la liste des transactions extraites (source de données**Gr** ) par code taxe.</span><span class="sxs-lookup"><span data-stu-id="ab3af-149">Group the list of fetched transactions (**Gr** data source) by tax code.</span></span>
    - <span data-ttu-id="ab3af-150">Calculer les transactions regroupées selon les valeurs cumulées par code taxe :</span><span class="sxs-lookup"><span data-stu-id="ab3af-150">Calculate for grouped transactions following aggregated values per   tax code:</span></span>

        - <span data-ttu-id="ab3af-151">Somme des valeurs de base de taxe.</span><span class="sxs-lookup"><span data-stu-id="ab3af-151">Sum of tax base values.</span></span>
        - <span data-ttu-id="ab3af-152">Somme des valeurs de taxe.</span><span class="sxs-lookup"><span data-stu-id="ab3af-152">Sum of tax values.</span></span>
        - <span data-ttu-id="ab3af-153">Valeur minimale du taux de taxe appliqué.</span><span class="sxs-lookup"><span data-stu-id="ab3af-153">Minimum value of applied tax rate.</span></span>

<span data-ttu-id="ab3af-154">La mise en correspondance des modèles dans cette configuration met en œuvre le modèle des données de base pour tous les formats de gestion des états électroniques créés pour ce modèle et exécutés dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ab3af-154">The model mapping in this configuration implements the base data model for any of the ER formats created for this model and executed in Finance and Operations.</span></span> <span data-ttu-id="ab3af-155">Par conséquent, le contenu **Taxe** et source de données **Gr** est exposé pour les formats de gestion des états électroniques tels que des sources de données abstraites.</span><span class="sxs-lookup"><span data-stu-id="ab3af-155">As a result, the content of the **Tax** and **Gr** data sources is exposed for ER formats such as abstract data sources.</span></span>

  ![Page du concepteur de mise en correspondance des modèles affichant les sources des données Taxe et Gr](media/er-calculated-field-type-01.png)

5.  <span data-ttu-id="ab3af-157">Fermez la page **Concepteur de mise en correspondance des modèles**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-157">Close the **Model mapping designer** page.</span></span>
6.  <span data-ttu-id="ab3af-158">Fermez la page **Mise en correspondance des modèles**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-158">Close the **Model mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="ab3af-159">Examen du format</span><span class="sxs-lookup"><span data-stu-id="ab3af-159">Review format</span></span>

1. <span data-ttu-id="ab3af-160">Dans l'arborescence de configuration, développez le contenu de l'élément **Modèle pour l'apprentissage des appels paramétrés**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-160">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="ab3af-161">Sélectionnez **Format pour l'apprentissage des appels paramétrés**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-161">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="ab3af-162">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-162">Select **Designer**.</span></span> <span data-ttu-id="ab3af-163">Ce format de gestion des états électroniques est conçue pour faire ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ab3af-163">This ER format is designed to do the following:</span></span>

  - <span data-ttu-id="ab3af-164">Générez un relevé de taxe au format XML.</span><span class="sxs-lookup"><span data-stu-id="ab3af-164">Generate a tax statement in XML format.</span></span>
  - <span data-ttu-id="ab3af-165">Présentez les niveaux suivants de taxation dans le relevé de taxe : normal, réduit et aucun.</span><span class="sxs-lookup"><span data-stu-id="ab3af-165">Present the following levels of taxation in the tax statement: regular, reduced, and none.</span></span>
  - <span data-ttu-id="ab3af-166">Présentez plusieurs détails à chaque niveau de taxation, avec un nombre différents de détails à chaque niveau.</span><span class="sxs-lookup"><span data-stu-id="ab3af-166">Present multiple details at each taxation level, having a different number of details in each level.</span></span>

  ![Page Concepteur de formats](media/er-calculated-field-type-02.png)

4. <span data-ttu-id="ab3af-168">Sélectionnez **Mappage**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-168">Select **Mapping**.</span></span>
5. <span data-ttu-id="ab3af-169">Développez les articles **Modèle**, **Données** et **Synthèse**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-169">Expand the **Model**, **Data,** and **Summary** items.</span></span> 

   <span data-ttu-id="ab3af-170">Le champ calculé **Model.Data.Summary.Level** contient l'expression qui renvoie le code du niveau de taxation (**Normal**, **Réduit**, **Aucun,** ou **Autre**) comme valeur de texte pour un code taxe pouvant être récupéré de la source de données **Model.Data.Summary** au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="ab3af-170">The calculated field **Model.Data.Summary.Level** contains the expression that returns the code of the taxation level (**Regular**, **Reduced**, **None,** or **Other**) as a text value for any tax code that can be retrieved from the **Model.Data.Summary** data source at run time.</span></span>

  ![Page du concepteur de format affichant les détails du modèle Modèle de données pour l'apprentissage des appels paramétrés](media/er-calculated-field-type-03.png)

6. <span data-ttu-id="ab3af-172">Développez l'article **Modèle**. **Data2**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-172">Expand the **Model**.**Data2** item.</span></span>
7. <span data-ttu-id="ab3af-173">Développez l'article **Modèle**. **Data2.Summary2**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-173">Expand the **Model**.**Data2.Summary2** item.</span></span>
   
   <span data-ttu-id="ab3af-174">La source de données **Model**.**Data2.Summary2** est configurée pour regrouper les détails de transaction de la source de données **Model.Data.Summary** par niveau de taxation (renvoyé par le champ calculé **Model.Data.Summary.Level**) et calcul les agrégations.</span><span class="sxs-lookup"><span data-stu-id="ab3af-174">The **Model**.**Data2.Summary2** data source is configured to group the **Model.Data.Summary** data source transaction details by taxation level (returned by the **Model.Data.Summary.Level** calculated field) and compute the aggregations.</span></span>

  ![Page du concepteur de format présentant les détails de la source de données Model.Data2.Summary2](media/er-calculated-field-type-04.png)

8. <span data-ttu-id="ab3af-176">Examinez les champs calculés **Modèle**.**Data2.Level1**, **Modèle**.**Data2.Level2** et **Modèle**.**Data2.Level3.**</span><span class="sxs-lookup"><span data-stu-id="ab3af-176">Review the calculated fields **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span></span> <span data-ttu-id="ab3af-177">Ces champs calculés sont utilisés pour filtrer la liste des enregistrements **Modèle**.**Data2.Summary2** et renvoyer uniquement les enregistrements qui représentent un niveau de taxation spécifique.</span><span class="sxs-lookup"><span data-stu-id="ab3af-177">These calculated fields are used to filter the **Model**.**Data2.Summary2** records list and return only records that represent a particular taxation level.</span></span>
9. <span data-ttu-id="ab3af-178">Fermez la page **Concepteur de format**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-178">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="ab3af-179">Créer un format dérivé</span><span class="sxs-lookup"><span data-stu-id="ab3af-179">Create a derived format</span></span>
<span data-ttu-id="ab3af-180">Vous pouvez améliorer le format de livraison en ajoutant un champ calculé pour filtrer le niveau requis de taxation au lieu d'utiliser les trois champs existants : **Modèle**.**Data2.Level1**, **Modèle**.**Data2.Level2** et **Modèle**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-180">You can improve the provided format by adding one calculated field to filter the required taxation level instead of using the existing three fields: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** and **Model**.**Data2.Level3**.</span></span> <span data-ttu-id="ab3af-181">Le niveau de taxation requis peut être précisé à l'emplacement où ce nouveau champ calculé sera appelé.</span><span class="sxs-lookup"><span data-stu-id="ab3af-181">The required taxation level can be specified in the location where this new calculated field will be called.</span></span>

1. <span data-ttu-id="ab3af-182">Dans l'arborescence de configuration, développez le contenu de l'élément **Modèle pour l'apprentissage des appels paramétrés**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-182">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="ab3af-183">Sélectionnez **Format pour l'apprentissage des appels paramétrés**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-183">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="ab3af-184">Sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-184">Select **Create configuration**.</span></span>
4. <span data-ttu-id="ab3af-185">Sélectionnez **Provenant du nom : Format pour l'apprentissage des appels paramétrés, Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-185">Select **Derive from Name: Format to learn parameterized calls, Microsoft**.</span></span>
5. <span data-ttu-id="ab3af-186">Dans le champ **Nom**, entrez **Format pour l'apprentissage des appels paramétrés (personnalisés)**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-186">In the **Name** field, enter **Format to learn parameterized calls (custom)**.</span></span>
6. <span data-ttu-id="ab3af-187">Sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-187">Select **Create configuration.**</span></span>

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a><span data-ttu-id="ab3af-188">Configuration d'un champ calculé paramétré qui renvoie une liste des enregistrements</span><span class="sxs-lookup"><span data-stu-id="ab3af-188">Configure a parameterized calculated field that returns a list of records</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="ab3af-189">Commencer l'ajout d'un nouveau champ calculé</span><span class="sxs-lookup"><span data-stu-id="ab3af-189">Start adding a new calculated field</span></span>

1. <span data-ttu-id="ab3af-190">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-190">Select **Designer**.</span></span>
2. <span data-ttu-id="ab3af-191">Sélectionnez **Développer/Réduire** pour développer tous les articles de format.</span><span class="sxs-lookup"><span data-stu-id="ab3af-191">Select **Expand/collapse** to expand all format items.</span></span>
3. <span data-ttu-id="ab3af-192">Sélectionnez **Mappage**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-192">Select **Mapping**.</span></span>
4. <span data-ttu-id="ab3af-193">Développez l'article **Modèle**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-193">Expand the **Model** item.</span></span>
5. <span data-ttu-id="ab3af-194">Sélectionnez l'article **Modèle.Data2**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-194">Select the **Model.Data2** item.</span></span>
6. <span data-ttu-id="ab3af-195">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-195">Select **Add**.</span></span>
7. <span data-ttu-id="ab3af-196">Sélectionnez **Fonctions\\Champ calculé**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-196">Select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="ab3af-197">Dans le champ **Nom**, entrez **Niveaux**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-197">In the **Name** field, enter **Levels**.</span></span>
9. <span data-ttu-id="ab3af-198">Sélectionnez **Modifier la formule**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-198">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="ab3af-199">Définir un paramètre pour ajouter un champ calculé</span><span class="sxs-lookup"><span data-stu-id="ab3af-199">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="ab3af-200">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-200">Select **Parameters**.</span></span>
2. <span data-ttu-id="ab3af-201">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-201">Select **New**.</span></span>
3. <span data-ttu-id="ab3af-202">Dans le champ **Nom**, entrez **Niveau de taxation**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-202">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="ab3af-203">Dans le champ **Type**, sélectionnez **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-203">In the **Type** field, select **String**.</span></span>

    <span data-ttu-id="ab3af-204">Seuls les types de données principaux peuvent être utilisés pour préciser le type d'argument du paramètre.</span><span class="sxs-lookup"><span data-stu-id="ab3af-204">Only primitive data types can be used to specify the type of the parameter’s argument.</span></span> <span data-ttu-id="ab3af-205">Par conséquent, les types **Liste d'enregistrement**, **Enregistrement** et **Énumération** ne peuvent pas être utilisés à cet effet.</span><span class="sxs-lookup"><span data-stu-id="ab3af-205">Therefore, **Record list**, **Record**, and **Enum** types cannot be used for this purpose.</span></span>

    <span data-ttu-id="ab3af-206">Le nombre maximum de paramètres pouvant être spécifiés pour un unique champ calculé est 8.</span><span class="sxs-lookup"><span data-stu-id="ab3af-206">The maximum number of parameters that can be specified for a single calculated field is 8.</span></span>

    ![Liste de source de données des paramètres](media/er-calculated-field-type-05.png)

5. <span data-ttu-id="ab3af-208">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-208">Select **OK**.</span></span>

<span data-ttu-id="ab3af-209">En ajoutant ce paramètre, vous précisez la condition qui doit être en place pour appeler ce champ calculé.</span><span class="sxs-lookup"><span data-stu-id="ab3af-209">By adding this parameter, you specify the condition that must be in place to call this calculated field.</span></span> <span data-ttu-id="ab3af-210">Lorsque vous appelez ce champ calculé, vous devez spécifier l'argument du paramètre **Niveau de taxation** comme valeur avec le format **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-210">When you call this calculated field, you need to specify the argument of the **Taxation Level** parameter as a value with **String** format.</span></span>

   <span data-ttu-id="ab3af-211">Assurez-vous que vous définissez des paramètres uniquement pour ces champs calculés qui se trouvent dans un conteneur ( **Liste d'enregistrement**, **Enregistrement** ou **Conteneur**).</span><span class="sxs-lookup"><span data-stu-id="ab3af-211">Make sure that you define parameters only for those calculated fields that reside in a container (either **Record list**, **Record**, or **Container**).</span></span>

   <span data-ttu-id="ab3af-212">Le paramètre configuré est disponible dans la liste des sources de données de ce champ calculé.</span><span class="sxs-lookup"><span data-stu-id="ab3af-212">The configured parameter is available in the list of data sources for this calculated field.</span></span> <span data-ttu-id="ab3af-213">Vous pouvez ajouter le paramétrage à l'expression configurée en sélectionnant **Ajouter la source de données**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-213">You can add the parameter to the configured expression by selecting **Add data source**.</span></span>

   ![Champs de source de données](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="ab3af-215">Définir une expression pour ajouter un champ calculé</span><span class="sxs-lookup"><span data-stu-id="ab3af-215">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="ab3af-216">Dans le champ **Formule**, saisissez :</span><span class="sxs-lookup"><span data-stu-id="ab3af-216">In the **Formula** field, enter:</span></span> 

    <span data-ttu-id="ab3af-217">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span><span class="sxs-lookup"><span data-stu-id="ab3af-217">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span></span>
    
2. <span data-ttu-id="ab3af-218">Sélectionnez le paramètre **Niveau de taxation** dans la liste des sources de données.</span><span class="sxs-lookup"><span data-stu-id="ab3af-218">Select the **Taxation Level** parameter in the list of data sources.</span></span>
3. <span data-ttu-id="ab3af-219">Sélectionnez **Ajouter une source de données**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-219">Select **Add data source**.</span></span>
4. <span data-ttu-id="ab3af-220">Dans le champ **Formule**, finalisez l'expression comme suit :</span><span class="sxs-lookup"><span data-stu-id="ab3af-220">In the **Formula** field, finalize the expression as:</span></span>  

    <span data-ttu-id="ab3af-221">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span><span class="sxs-lookup"><span data-stu-id="ab3af-221">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span></span>

5. <span data-ttu-id="ab3af-222">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-222">Select **Save**.</span></span>

    ![Informations sur le champ de source de données](media/er-calculated-field-type-07.png)

6. <span data-ttu-id="ab3af-224">Fermez la page **Concepteur de formule**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-224">Close the **Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="ab3af-225">Terminer l'ajout d'un nouveau champ calculé</span><span class="sxs-lookup"><span data-stu-id="ab3af-225">Finish adding a new calculated field</span></span>

- <span data-ttu-id="ab3af-226">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-226">Select **OK**.</span></span>

<span data-ttu-id="ab3af-227">Sur la page **Concepteur de format**, le champ calculé paramétré configuré **Niveaux** exige un argument **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-227">On the **Format designer** page, the configured parameterized calculated field **Levels** requires a **String** argument.</span></span>

![Liste développée des niveaux de champ calculé](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a><span data-ttu-id="ab3af-229">Utiliser le champ calculé configuré pour lier les éléments de format</span><span class="sxs-lookup"><span data-stu-id="ab3af-229">Use the configured calculated field for binding format elements</span></span>

1. <span data-ttu-id="ab3af-230">Sélectionnez **Model.Data2.Levels** pour sélectionner le champ calculé configuré.</span><span class="sxs-lookup"><span data-stu-id="ab3af-230">Select **Model.Data2.Levels** to select the configured calculated field.</span></span>
2. <span data-ttu-id="ab3af-231">Sélectionnez l'élément de format **Statement.Taxation.Regular**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-231">Select the **Statement.Taxation.Regular** format element.</span></span>
3. <span data-ttu-id="ab3af-232">Sélectionnez **Lier**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-232">Select **Bind**.</span></span>
4. <span data-ttu-id="ab3af-233">Sélectionnez **Oui** pour confirmer le remplacement de la source de données utilisée actuellement, **Level1**, par la nouvelle source de données, **Niveaux**, dans tous les éléments de format imbriqués de l'élément de format sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ab3af-233">Select **Yes** to confirm the replacement of the currently used data source, **Level1**, by the new data source, **Levels**, in all nested format elements of the selected format element.</span></span>

    <span data-ttu-id="ab3af-234">La liaison appliquée a été créée comme appel du champ calculé paramétré.</span><span class="sxs-lookup"><span data-stu-id="ab3af-234">Applied binding has been built as a call of the parameterized calculated field.</span></span> <span data-ttu-id="ab3af-235">Par défaut, le nom de l'élément de format lié est utilisé comme argument pour le champ calculé paramétré sous les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ab3af-235">By default, the name of the bound format element is used as an argument for parameterized calculated field under the following conditions:</span></span>

      - <span data-ttu-id="ab3af-236">Le champ calculé est configuré pour utiliser un unique paramètre.</span><span class="sxs-lookup"><span data-stu-id="ab3af-236">The calculated field is configured to use a single parameter.</span></span>
      - <span data-ttu-id="ab3af-237">Le type de données de ce paramètre est défini sur **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-237">The data type of this parameter is defined as **String**.</span></span>

    <span data-ttu-id="ab3af-238">Lorsque le nom de l'élément de format lié est vide, le nom de source de données de cet élément est utilisé dans la liaison appliquée.</span><span class="sxs-lookup"><span data-stu-id="ab3af-238">When the name of the bound format element is blank, the data source name of this element is used in applied binding.</span></span>

5. <span data-ttu-id="ab3af-239">Sélectionnez l'élément de format **Statement.Taxation.Reduced**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-239">Select the **Statement.Taxation.Reduced** format element.</span></span>
6. <span data-ttu-id="ab3af-240">Sélectionnez **Lier**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-240">Select **Bind**.</span></span>
7. <span data-ttu-id="ab3af-241">Sélectionnez **Oui** pour confirmer le remplacement de la source de données utilisée actuellement, **Level2**, par la nouvelle source de données, **Niveaux**, dans tous les éléments de format imbriqués de l'élément de format sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ab3af-241">Select **Yes** to confirm the replacement of the currently used data source, **Level2**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>
8. <span data-ttu-id="ab3af-242">Sélectionnez l'élément de format **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-242">Select the **Statement.Taxation.None** format element.</span></span>
9. <span data-ttu-id="ab3af-243">Sélectionnez **Lier**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-243">Select **Bind**.</span></span>
10. <span data-ttu-id="ab3af-244">Sélectionnez **Oui** pour confirmer le remplacement de la source de données utilisée actuellement, **Level3**, par la nouvelle source de données, **Niveaux**, dans tous les éléments de format imbriqués de l'élément de format sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ab3af-244">Select **Yes** to confirm the replacement of the currently used data source, **Level3**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>

   <span data-ttu-id="ab3af-245">Lorsque vous spécifiez l'argument du champ calculé paramétré pour l'élément XML représentant le niveau de taxation (par exemple, la valeur **Model.Data2.Levels("Reduced")** comme valeur de texte), il est inutile de faire de même pour les attributs XML imbriqués. Leurs liaisons hériteront automatiquement de la valeur de l'argument définie sur le niveau parent (**Model.Data2.Levels.aggregated.Base**, **Model.Data2.Levels("Reduced").aggregated.Base**).</span><span class="sxs-lookup"><span data-stu-id="ab3af-245">When you specify the argument of the parameterized calculated field for the XML element representing taxation level (for example, **Model.Data2.Levels("Reduced")** as a text value), you don’t need to do the same for nested XML attributes—their bindings will automatically inherit the value of the argument defined on the parent level (**Model.Data2.Levels.aggregated.Base**, not **Model.Data2.Levels("Reduced").aggregated.Base**).</span></span>

<span data-ttu-id="ab3af-246">Les appels récurrents de tout champ calculé paramétré ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="ab3af-246">Recurrent calls of any parameterized calculated field are not supported.</span></span>

<span data-ttu-id="ab3af-247">Vous pouvez sélectionner **Modifier la formule**, et changer l'argument appliqué par défaut du champ calculé paramétré dans la liaison sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab3af-247">You can select **Edit formula**, and change the applied-by-default argument of the parameterized calculated field in the selected binding.</span></span> <span data-ttu-id="ab3af-248">Si cet argument manque, cela peut générer des erreurs à l'exécution. Les utilisateurs sont informés d'une telle situation lorsque le format actuel est validé.</span><span class="sxs-lookup"><span data-stu-id="ab3af-248">If this argument is missing, it can cause errors at run time — users are informed about such a situation when the current format is validated.</span></span>

![Notification d'avertissement de validation](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a><span data-ttu-id="ab3af-250">Configuration d'un champ calculé paramétré qui renvoie un enregistrement</span><span class="sxs-lookup"><span data-stu-id="ab3af-250">Configure a parameterized calculated field to return a record</span></span>
<span data-ttu-id="ab3af-251">Lorsqu'un champ calculé paramétré renvoie un enregistrement, vous devez prendre en charge la liaison des champs individuels de cet enregistrement avec les éléments de format.</span><span class="sxs-lookup"><span data-stu-id="ab3af-251">When a parameterized calculated field returns a record, you need to support binding of individual fields of this record to format elements.</span></span> <span data-ttu-id="ab3af-252">En pareille situation, il n'y aura pas de liaison parente qui contient la valeur d'un argument pour appeler un champ calculé paramétré. Cette valeur doit être définie dans la liaison d'un seul champ d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="ab3af-252">In such cases there will be no parent binding that contains the value of an argument to call a parameterized calculated field — this value must be defined in the binding of a single record’s field.</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="ab3af-253">Commencer l'ajout d'un nouveau champ calculé</span><span class="sxs-lookup"><span data-stu-id="ab3af-253">Start adding a new calculated field</span></span>

1. <span data-ttu-id="ab3af-254">Sélectionnez l'article **Modèle.Data2**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-254">Select the **Model.Data2** item.</span></span>
2. <span data-ttu-id="ab3af-255">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-255">Select **Add**.</span></span>
3. <span data-ttu-id="ab3af-256">Sélectionnez **Fonctions\\Champ calculé**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-256">Select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="ab3af-257">Dans le champ **Nom**, entrez **LevelRecord**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-257">In the **Name** field, enter **LevelRecord**.</span></span>
5. <span data-ttu-id="ab3af-258">Sélectionnez **Modifier la formule**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-258">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="ab3af-259">Définir un paramètre pour ajouter un champ calculé</span><span class="sxs-lookup"><span data-stu-id="ab3af-259">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="ab3af-260">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-260">Select **Parameters**.</span></span>
2. <span data-ttu-id="ab3af-261">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-261">Select **New**.</span></span>
3. <span data-ttu-id="ab3af-262">Dans le champ **Nom**, entrez **Niveau de taxation**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-262">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="ab3af-263">Dans le champ **Type**, sélectionnez **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-263">In the **Type** field, select **String**.</span></span>
5. <span data-ttu-id="ab3af-264">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-264">Select **OK**.</span></span>

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="ab3af-265">Définir une expression pour ajouter un champ calculé</span><span class="sxs-lookup"><span data-stu-id="ab3af-265">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="ab3af-266">Dans le champ **Formule**, entrez l'expression suivante :</span><span class="sxs-lookup"><span data-stu-id="ab3af-266">In the **Formula** field, enter the following:</span></span>  
    
    <span data-ttu-id="ab3af-267">**FIRSTORNULL(\@.Levels(**</span><span class="sxs-lookup"><span data-stu-id="ab3af-267">**FIRSTORNULL(\@.Levels(**</span></span>

2. <span data-ttu-id="ab3af-268">Sélectionnez le paramètre **Niveau de taxation**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-268">Select the **Taxation Level** parameter.</span></span>
3. <span data-ttu-id="ab3af-269">Sélectionnez **Ajouter une source de données**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-269">Select **Add data source**.</span></span>
4. <span data-ttu-id="ab3af-270">Dans le champ **Formule**, ajoutez **'Taxation Level'))** à ce que vous avez entré dans l'étape 1 pour finaliser l'expression :</span><span class="sxs-lookup"><span data-stu-id="ab3af-270">In the **Formula** field, append **'Taxation Level'))** to what you entered in Step 1 to finalize the expression to:</span></span>  
    
    <span data-ttu-id="ab3af-271">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span><span class="sxs-lookup"><span data-stu-id="ab3af-271">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span></span>

5. <span data-ttu-id="ab3af-272">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-272">Select **Save**.</span></span>
6. <span data-ttu-id="ab3af-273">Fermez la page **Concepteur de formule**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-273">Close **the Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="ab3af-274">Terminer l'ajout d'un nouveau champ calculé</span><span class="sxs-lookup"><span data-stu-id="ab3af-274">Finish adding a new calculated field</span></span>

-   <span data-ttu-id="ab3af-275">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-275">Select **OK**.</span></span>

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a><span data-ttu-id="ab3af-276">Utiliser le champ calculé configuré pour lier les éléments de format</span><span class="sxs-lookup"><span data-stu-id="ab3af-276">Use the configured calculated field to bind format elements</span></span>

1. <span data-ttu-id="ab3af-277">Développer **Model.Data2.LevelRecord** pour sélectionner le champ calculé configuré.</span><span class="sxs-lookup"><span data-stu-id="ab3af-277">Expand **Model.Data2.LevelRecord** to select the configured calculated field.</span></span>
2. <span data-ttu-id="ab3af-278">Développez le conteneur **Model.Data2.LevelRecord.aggregated** pour sélectionner le champ calculé configuré.</span><span class="sxs-lookup"><span data-stu-id="ab3af-278">Expand the **Model.Data2.LevelRecord.aggregated** container of the configured calculated field.</span></span>
3. <span data-ttu-id="ab3af-279">Sélectionnez le champ **Model.Data2.LevelRecord.aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-279">Select the **Model.Data2.LevelRecord.aggregated.Base** field.</span></span>
4. <span data-ttu-id="ab3af-280">Sélectionnez l'élément de format **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-280">Select the **Statement.Taxation.None** format element.</span></span>
5. <span data-ttu-id="ab3af-281">Sélectionnez **Annuler la liaison**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-281">Select **Unbind**.</span></span>
6. <span data-ttu-id="ab3af-282">Sélectionnez l'élément de format **Statement.Taxation.None.Base**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-282">Select the **Statement.Taxation.None.Base** format element.</span></span>
7. <span data-ttu-id="ab3af-283">Sélectionnez **Lier**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-283">Select **Bind**.</span></span>
8. <span data-ttu-id="ab3af-284">Sélectionnez **Modifier la formule**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-284">Select **Edit formula**.</span></span>
9. <span data-ttu-id="ab3af-285">Changez l'expression pour **Model.Data2.LevelRecord("None").aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-285">Change the expression to **Model.Data2.LevelRecord("None").aggregated.Base**.</span></span>

![Expression mise à jour](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a><span data-ttu-id="ab3af-287">Supprimer les champs calculés qui ne sont pas utilisés</span><span class="sxs-lookup"><span data-stu-id="ab3af-287">Remove calculated fields that are not used</span></span>

1. <span data-ttu-id="ab3af-288">Sélectionnez **Model.Data2.Level1**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-288">Select **Model.Data2.Level1**.</span></span>
2. <span data-ttu-id="ab3af-289">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-289">Select **Delete**.</span></span>
3. <span data-ttu-id="ab3af-290">Sélectionnez **Model.Data2.Level2**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-290">Select **Model.Data2.Level2**.</span></span>
4. <span data-ttu-id="ab3af-291">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-291">Select **Delete**.</span></span>
5. <span data-ttu-id="ab3af-292">Sélectionnez **Model.Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-292">Select **Model.Data2.Level3**.</span></span>
6. <span data-ttu-id="ab3af-293">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-293">Select **Delete**.</span></span>
7. <span data-ttu-id="ab3af-294">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-294">Select **Save**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ab3af-295">Vous avez réutilisé le même champ calculé **Model.Data2.Levels** plusieurs fois dans les liaisons de format.</span><span class="sxs-lookup"><span data-stu-id="ab3af-295">You reused the same calculated field **Model.Data2.Levels** several times in format bindings.</span></span> <span data-ttu-id="ab3af-296">Il est beaucoup plus facile d'utiliser et de tenir à jour seul un champ calculé au lieu de le faire pour plusieurs champs similaires.</span><span class="sxs-lookup"><span data-stu-id="ab3af-296">It is much easier to use and maintain a single calculated field instead of doing this for multiple similar fields.</span></span>

8. <span data-ttu-id="ab3af-297">Fermez la page **Concepteur de format**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-297">Close the **Format designer** page.</span></span>

## <a name="complete-adjusted-version-of-a-derived-format"></a><span data-ttu-id="ab3af-298">Terminer la version ajustée d'un format dérivé</span><span class="sxs-lookup"><span data-stu-id="ab3af-298">Complete adjusted version of a derived format</span></span>

1. <span data-ttu-id="ab3af-299">Dans l'organisateur **Versions**, sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-299">In the **Versions** FastTab, select **Change status**.</span></span>
2. <span data-ttu-id="ab3af-300">Sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-300">Select **Complete**.</span></span>

## <a name="export-completed-version-of-a-derived-format"></a><span data-ttu-id="ab3af-301">Exporter la version terminée d'un format dérivé</span><span class="sxs-lookup"><span data-stu-id="ab3af-301">Export completed version of a derived format</span></span>

1. <span data-ttu-id="ab3af-302">Sélectionnez le format **Format pour l'apprentissage des appels paramétrés (personnalisé)** dans l'arborescence de configurations.</span><span class="sxs-lookup"><span data-stu-id="ab3af-302">Select **Format to learn parameterized calls (custom)** format in the configurations tree.</span></span>
2. <span data-ttu-id="ab3af-303">Dans l'organisateur **Versions**, sélectionnez la version terminée 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="ab3af-303">In the **Versions** FastTab, select the completed version 1.1.1.</span></span>
3. <span data-ttu-id="ab3af-304">Sélectionnez **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-304">Select **Exchange**.</span></span>
4. <span data-ttu-id="ab3af-305">Sélectionnez **Exporter en tant que fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-305">Select **Export as XML file**.</span></span>
5. <span data-ttu-id="ab3af-306">Enregistrez la configuration téléchargée localement, au format XML.</span><span class="sxs-lookup"><span data-stu-id="ab3af-306">Store the downloaded configuration locally, in XML format.</span></span>

## <a name="test-er-formats"></a><span data-ttu-id="ab3af-307">Tester les formats de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="ab3af-307">Test ER formats</span></span> 
<span data-ttu-id="ab3af-308">Vous pouvez exécuter les formats de gestion des états électroniques d'origine et améliorés pour veiller à ce que les champs calculés paramétrés configurés fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="ab3af-308">You can run the initial and improved ER formats to make sure that configured parameterized calculated fields work properly.</span></span>

### <a name="import-er-configurations"></a><span data-ttu-id="ab3af-309">Importer les configurations ER</span><span class="sxs-lookup"><span data-stu-id="ab3af-309">Import ER configurations</span></span>
<span data-ttu-id="ab3af-310">Vous pouvez importer des configurations révisées depuis RCS à l'aide du référentiel de gestion des états électroniques de type **RCS**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-310">You can import reviewed configurations from RCS by using the ER repository of the **RCS** type.</span></span> <span data-ttu-id="ab3af-311">Si vous avez déjà effectué la procédure de la rubrique [Importer les configurations des états électroniques des services de configuration réglementaires](rcs-download-configurations.md), utilisez le référentiel de gestion des états électroniques configurés pour importer les configurations abordées précédemment dans cette rubrique dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="ab3af-311">If you already went through the steps in the topic, [Import Electronic reporting configurations from Regulatory Configuration Services](rcs-download-configurations.md), use the configured ER repository to import configurations discussed earlier in this topic to your environment.</span></span> <span data-ttu-id="ab3af-312">Sinon, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ab3af-312">Otherwise, follow these steps:</span></span>

1. <span data-ttu-id="ab3af-313">Sélectionnez la société **DEMF** et sur le tableau de bord par défaut, sélectionnez **Gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-313">Select the **DEMF** company and on the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="ab3af-314">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-314">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="ab3af-315">Importez les configurations provenant du centre de téléchargement Microsoft dans l'ordre suivant : modèle de données, métadonnées, mise en correspondance des modèles, format.</span><span class="sxs-lookup"><span data-stu-id="ab3af-315">Import the configurations from Microsoft Download Center in the following sequence: data model, model mapping, format.</span></span> <span data-ttu-id="ab3af-316">Procédez comme suit pour chaque configuration de gestion des états électroniques :</span><span class="sxs-lookup"><span data-stu-id="ab3af-316">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="ab3af-317">Sélectionnez **Échanger**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-317">Select **Exchange.**</span></span>
    2. <span data-ttu-id="ab3af-318">Sélectionnez **Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-318">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="ab3af-319">Sélectionnez **Parcourir** pour sélectionner la configuration ER requise au format XML.</span><span class="sxs-lookup"><span data-stu-id="ab3af-319">Select **Browse** to select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="ab3af-320">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-320">Select **OK**.</span></span>

4. <span data-ttu-id="ab3af-321">Importez la version finalisée 1.1.1 provenant de RCS du format **Format pour l'apprentissage des appels paramétrés (personnalisé)**  :</span><span class="sxs-lookup"><span data-stu-id="ab3af-321">Import the exported from RCS completed version 1.1.1 of the **Format to learn parameterized calls (custom)** format:</span></span>

    1. <span data-ttu-id="ab3af-322">Sélectionnez **Échanger**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-322">Select **Exchange.**</span></span>
    2. <span data-ttu-id="ab3af-323">Sélectionnez **Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-323">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="ab3af-324">Sélectionnez **Parcourir** pour sélectionner le fichier localement enregistré **Format pour l'apprentissage des appels paramétrés (personnalisé)** au format XML.</span><span class="sxs-lookup"><span data-stu-id="ab3af-324">Select **Browse** to select the locally stored **Format to learn parameterized calls (custom)** file in XML format.</span></span>
    4. <span data-ttu-id="ab3af-325">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-325">Select **OK**.</span></span>

### <a name="run-er-formats"></a><span data-ttu-id="ab3af-326">Exécuter les formats de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="ab3af-326">Run ER formats</span></span>

1. <span data-ttu-id="ab3af-327">Dans l'arborescence de configuration, développez le contenu de l'élément **Modèle pour l'apprentissage des appels paramétrés**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-327">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="ab3af-328">Sélectionnez **Format pour l'apprentissage des appels paramétrés**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-328">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="ab3af-329">Sélectionnez **Exécuter** dans le ruban le plus haut.</span><span class="sxs-lookup"><span data-stu-id="ab3af-329">Select **Run** on the top-most ribbon.</span></span>
4. <span data-ttu-id="ab3af-330">Enregistrez la sortie localement générée.</span><span class="sxs-lookup"><span data-stu-id="ab3af-330">Save the locally generated output.</span></span>
5. <span data-ttu-id="ab3af-331">Sélectionnez l'élément **Format pour l'apprentissage des appels paramétrés (personnalisé)**.</span><span class="sxs-lookup"><span data-stu-id="ab3af-331">Select the **Format to learn parameterized calls (custom)** item.</span></span>
6. <span data-ttu-id="ab3af-332">Sélectionnez **Exécuter** dans le ruban le plus haut.</span><span class="sxs-lookup"><span data-stu-id="ab3af-332">Select **Run** on the top-most ribbon.</span></span>
7. <span data-ttu-id="ab3af-333">Enregistrez la sortie localement générée.</span><span class="sxs-lookup"><span data-stu-id="ab3af-333">Save the generated output locally.</span></span> 
8. <span data-ttu-id="ab3af-334">Comparez le contenu des sorties générées.</span><span class="sxs-lookup"><span data-stu-id="ab3af-334">Compare the contents of the generated outputs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ab3af-335">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ab3af-335">Additional resources</span></span>
[<span data-ttu-id="ab3af-336">Concepteur de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="ab3af-336">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
