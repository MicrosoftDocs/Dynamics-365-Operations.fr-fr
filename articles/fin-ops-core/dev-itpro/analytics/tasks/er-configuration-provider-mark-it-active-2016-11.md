---
title: Créer des fournisseurs de configuration et les marquer comme actif
description: Cette rubrique explique comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut créer un fournisseur de configuration.
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 835e35ef233ba5734e5a4d47f624629e95ae5b89
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092058"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="a10a4-103">Créer des fournisseurs de configuration et les marquer comme actif</span><span class="sxs-lookup"><span data-stu-id="a10a4-103">Create configuration providers and mark them as active</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a10a4-104">Cette rubrique explique comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut créer un fournisseur de configuration pour la génération d’états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="a10a4-104">This topic explains how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="a10a4-105">Chaque configuration ER fait référence au fournisseur en tant que l’auteur de la configuration.</span><span class="sxs-lookup"><span data-stu-id="a10a4-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="a10a4-106">Dans cet exemple, vous allez créer un fournisseur de configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n’importe quelle société car les fournisseurs de configurations ER sont partagés entre toutes les sociétés.</span><span class="sxs-lookup"><span data-stu-id="a10a4-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>

## <a name="create-a-provider"></a><span data-ttu-id="a10a4-107">Créer un fournisseur</span><span class="sxs-lookup"><span data-stu-id="a10a4-107">Create a provider</span></span>
1. <span data-ttu-id="a10a4-108">Accédez au **volet de navigation** dans le coin supérieur gauche et sélectionnez **Administration d’organisation**.</span><span class="sxs-lookup"><span data-stu-id="a10a4-108">Go to the **navigation pane** in the upper left corner and select **Organization administration**.</span></span>
2. <span data-ttu-id="a10a4-109">Accédez à **Espaces de travail > États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="a10a4-109">Go to **Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="a10a4-110">Accédez à **Liens connexes > Fournisseurs de configuration**.</span><span class="sxs-lookup"><span data-stu-id="a10a4-110">Go to **Related links > Configuration providers**.</span></span>
4. <span data-ttu-id="a10a4-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a10a4-111">Select **New**.</span></span>
    - <span data-ttu-id="a10a4-112">Un enregistrement fournisseur a un nom et une URL uniques.</span><span class="sxs-lookup"><span data-stu-id="a10a4-112">A provider record has a unique name and URL.</span></span> <span data-ttu-id="a10a4-113">Examinez le contenu de cette page et ignorez cette procédure si un enregistrement pour Litware, Inc. (https://www.litware.com) existe déjà.</span><span class="sxs-lookup"><span data-stu-id="a10a4-113">Review the content of this page and skip this procedure if a record for Litware, Inc. (https://www.litware.com) already exists.</span></span>  
5. <span data-ttu-id="a10a4-114">Dans le champ Nom, saisissez `Litware, Inc.`.</span><span class="sxs-lookup"><span data-stu-id="a10a4-114">In the Name field, type `Litware, Inc.`.</span></span>
6. <span data-ttu-id="a10a4-115">Dans le champ Adresse Internet, tapez « `https://www.litware.com` ».</span><span class="sxs-lookup"><span data-stu-id="a10a4-115">In the Internet address field, type `https://www.litware.com`.</span></span>
7. <span data-ttu-id="a10a4-116">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a10a4-116">Select **Save**.</span></span>
8. <span data-ttu-id="a10a4-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a10a4-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="a10a4-118">Sélectionner en tant que fournisseur actif</span><span class="sxs-lookup"><span data-stu-id="a10a4-118">Select as an active provider</span></span>
1. <span data-ttu-id="a10a4-119">Sélectionnez le fournisseur Litware, Inc. .</span><span class="sxs-lookup"><span data-stu-id="a10a4-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="a10a4-120">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="a10a4-120">Select **Set active**.</span></span>

![Page de l’espace de travail des états électroniques](../media/GER-Task-ActiveProvider-1.png)
