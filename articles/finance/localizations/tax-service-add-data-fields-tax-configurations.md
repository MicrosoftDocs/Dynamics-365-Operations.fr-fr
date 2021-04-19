---
title: Ajouter des champs de données dans les configurations de taxe
description: Cette rubrique explique comment personnaliser les configurations de taxe en ajoutant des champs de données.
author: kailiang
ms.date: 03/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b9d9fce81151ad70d57c69e389e238a6f9137d56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819422"
---
# <a name="add-data-fields-in-tax-configurations"></a><span data-ttu-id="67630-103">Ajouter des champs de données dans les configurations de taxe</span><span class="sxs-lookup"><span data-stu-id="67630-103">Add data fields in tax configurations</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="67630-104">Cette rubrique explique comment personnaliser les configurations de taxe à l’aide de [champs de données ajoutés dans l’intégration fiscale](tax-service-add-data-fields-tax-integration-by-extension.md).</span><span class="sxs-lookup"><span data-stu-id="67630-104">This topic explains how to customize tax configurations by using [data fields that are added in the tax integration](tax-service-add-data-fields-tax-integration-by-extension.md).</span></span>

## <a name="customize-the-tax-data-model"></a><span data-ttu-id="67630-105">Personnaliser le modèle de données fiscales</span><span class="sxs-lookup"><span data-stu-id="67630-105">Customize the tax data model</span></span>

1. <span data-ttu-id="67630-106">Dans Microsoft Dynamics 365 Finance, accédez à **États électroniques** \> **Configurations de taxe**.</span><span class="sxs-lookup"><span data-stu-id="67630-106">In Microsoft Dynamics 365 Finance, go to **Electronic Reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="67630-107">Dans l’arborescence de configuration, sélectionnez **Modèle de données fiscales – Europe**.</span><span class="sxs-lookup"><span data-stu-id="67630-107">In the configuration tree, select **Tax Data Model - Europe**.</span></span> <span data-ttu-id="67630-108">Ensuite, dans le volet Actions, sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="67630-108">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="67630-109">Dans la boîte de dialogue déroulante, sélectionnez l’option **Modèle de document de taxe dérivé de Nom : Modèle de données fiscales – Europe, Microsoft**, entrez un nom pour le nouveau modèle de données fiscales, puis sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="67630-109">In the drop-down dialog box, select the **Taxable document model derived from Name: Tax Data Model -- Europe, Microsoft** option, enter a name for the new tax data model, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="67630-110">Sélectionnez le modèle de données fiscales que vous venez de créer, puis, dans le volet Actions, sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="67630-110">Select the tax data model that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="67630-111">Développez l’arborescence du modèle de données, sélectionnez **Lignes**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="67630-111">Expand the data model tree, select **Lines**, and then select **New**.</span></span>
6. <span data-ttu-id="67630-112">Dans la boîte de dialogue **Créer un nœud**, entrez un nom, spécifiez le type d’élément, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="67630-112">In the **Create node** dialog box, enter a name, specify the item type, and then select **Add**.</span></span>
7. <span data-ttu-id="67630-113">Ajoutez toutes les colonnes requises.</span><span class="sxs-lookup"><span data-stu-id="67630-113">Add any required columns.</span></span>
8. <span data-ttu-id="67630-114">Sur le volet Actions, sélectionnez **Enregistrer**, puis sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="67630-114">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="67630-115">Fermez la page et affichez la version achevée de votre modèle de données fiscales.</span><span class="sxs-lookup"><span data-stu-id="67630-115">Close the page, and view the completed version of your tax data model.</span></span>

## <a name="customize-the-tax-configuration"></a><span data-ttu-id="67630-116">Personnaliser la configuration de taxe</span><span class="sxs-lookup"><span data-stu-id="67630-116">Customize the tax configuration</span></span>

1. <span data-ttu-id="67630-117">Dans Finance, accédez à **États électroniques** \> **Configurations de taxe**.</span><span class="sxs-lookup"><span data-stu-id="67630-117">In Finance, go to **Electronic reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="67630-118">Dans l’arborescence de configuration, sélectionnez **Configuration de taxe – Europe**.</span><span class="sxs-lookup"><span data-stu-id="67630-118">In the configuration tree, select **Tax Configuration -- Europe**.</span></span> <span data-ttu-id="67630-119">Ensuite, dans le volet Actions, sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="67630-119">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="67630-120">Dans la boîte de dialogue déroulante, sélectionnez l’option **Configuration du service de taxe dérivé de Nom : Configuration de taxe – Europe, Microsoft**, entrez un nom pour la nouvelle configuration, puis sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="67630-120">In the drop-down dialog box, select the **Tax service configuration derived from Name: Tax Configuration -- Europe, Microsoft** option, enter a name for the new tax configuration, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="67630-121">Sélectionnez la configuration de taxe que vous venez de créer, puis, dans le volet Actions, sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="67630-121">Select the tax configuration that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="67630-122">Dans la section **Propriétés**, dans le champ **Modèle de données**, sélectionnez le modèle de données fiscales personnalisé que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="67630-122">In the **Properties** section, in the **Data model** field, select the customized tax data model that you created earlier.</span></span>
6. <span data-ttu-id="67630-123">Dans le champ **Version du modèle de données**, sélectionnez la version complète du modèle de données fiscales.</span><span class="sxs-lookup"><span data-stu-id="67630-123">In the **Data model version** field, select the completed version of the tax data model.</span></span>
7. <span data-ttu-id="67630-124">Sélectionnez **Ajouter** et ajoutez les mesures fiscales requises.</span><span class="sxs-lookup"><span data-stu-id="67630-124">Select **Add**, and add the required tax measures.</span></span>
8. <span data-ttu-id="67630-125">Sur le volet Actions, sélectionnez **Enregistrer**, puis sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="67630-125">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="67630-126">Fermez la page et affichez la version achevée de votre configuration de taxe.</span><span class="sxs-lookup"><span data-stu-id="67630-126">Close page, and view the completed version of your tax configuration.</span></span>

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a><span data-ttu-id="67630-127">Implémenter les fonctionnalités de taxe dans la configuration de taxe personnalisée</span><span class="sxs-lookup"><span data-stu-id="67630-127">Implement tax features in the customized tax configuration</span></span>

1. <span data-ttu-id="67630-128">Dans Regulatory Configuration Service (RCS), accédez à **Fonctionnalités de globalisation** \> **Taxes**.</span><span class="sxs-lookup"><span data-stu-id="67630-128">In Regulatory Configuration Service (RCS), go to **Globalization Features** \> **Tax**.</span></span>
2. <span data-ttu-id="67630-129">Sélectionnez **Ajouter**, entrez des informations sur la nouvelle fonctionnalité, puis sélectionnez **Créer une fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="67630-129">Select **Add**, enter information about the new feature, and then select **Create feature**.</span></span>
3. <span data-ttu-id="67630-130">Sur l’onglet **Versions**, sélectionnez la fonctionnalité, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="67630-130">On the **Versions** tab, select the feature, and then select **Edit**.</span></span>
4. <span data-ttu-id="67630-131">Sur l’onglet **Général**, dans le champ **Version de configuration**, sélectionnez la configuration de taxe et la version personnalisées.</span><span class="sxs-lookup"><span data-stu-id="67630-131">On the **General** tab, in the **Configuration version** field, select the customized tax configuration and version.</span></span>
5. <span data-ttu-id="67630-132">Dans la boîte de dialogue **Gérer les colonnes**, sélectionnez les colonnes d’en-tête et de ligne que vous souhaitez inclure dans votre mesure fiscale personnalisée, puis sélectionnez le bouton en forme de flèche vers la droite pour les ajouter à la liste **Colonnes sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="67630-132">In the **Manage columns** dialog box, select the header and line columns that you want to include in your customized tax measure, and then select the right arrow button to add them to the **Selected columns** list.</span></span>
