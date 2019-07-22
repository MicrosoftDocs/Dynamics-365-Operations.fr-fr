---
title: (Gestion des états électroniques) Importer les configurations depuis RCS
description: Cette rubrique fournit des informations sur la manière dont un utilisateur peut importer une nouvelle version d'une configuration ER à partir de RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c458cf815837fb7e4688c4c0443b7962cac403a5
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/04/2019
ms.locfileid: "1727004"
---
# <a name="er-import-configurations-from-rcs"></a><span data-ttu-id="e3b9b-103">(Gestion des états électroniques) Importer les configurations depuis RCS</span><span class="sxs-lookup"><span data-stu-id="e3b9b-103">(ER) Import configurations from RCS</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e3b9b-104">Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut importer une nouvelle version d'une configuration pour la génération d'états électroniques (ER) à partir de Microsoft Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="e3b9b-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Regulatory Configuration Services (RCS).</span></span> <span data-ttu-id="e3b9b-105">Dans cet exemple, vous sélectionnerez la version de la configuration ER qui a été configurée dans une instance RCS et l'importerez dans l'instance Finance and Operations actuelle pour la société fictive Litware, Inc. Ces étapes peuvent être réalisées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-105">In this example, you will select the version of the ER configuration that has been configured in an RCS instance and import it into the current Finance and Operations instance for sample company, Litware, Inc. These steps can be performed in any company because ER configurations are shared among companies.</span></span> <span data-ttu-id="e3b9b-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de cette rubrique, [Créer un fournisseur de configuration et le marquer comme actif](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e3b9b-106">To complete these steps, you must first complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="e3b9b-107">Pour effectuer ces étapes, vous devez également avoir accès à une instance RCS contenant au moins une configuration ER ayant le statut **Terminé** ou **Partagé**.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-107">To complete these steps, you must also have access to an RCS instance containing at least one ER configuration in either **Completed** or **Shared** status.</span></span>

1. <span data-ttu-id="e3b9b-108">Accédez à **Administration d'organisation** > **Espaces de travail** > **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-108">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="e3b9b-109">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-109">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="e3b9b-110">Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la rubrique [Créer un fournisseur de configuration et le marquer comme actif](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e3b9b-110">If you don’t see this configuration provider, complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3. <span data-ttu-id="e3b9b-111">Si vous n'avez pas d'environnement RCS configuré dans votre société, cliquez sur le lien externe **Regulatory services – Configuration** et suivez les instructions pour mettre en service un environnement RCS.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-111">If you have no RCS environment provisioned to your company, click **Regulatory services – Configuration** external link and follow the instructions to provision an RCS environment.</span></span> 
4. <span data-ttu-id="e3b9b-112">Cliquez sur **Paramètres de la gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-112">Click **Electronic reporting parameters**.</span></span> 
5. <span data-ttu-id="e3b9b-113">Cliquez sur l'onglet **RCS**.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-113">Click the **RCS** tab.</span></span> 
6. <span data-ttu-id="e3b9b-114">Si l'environnement de RCS a déjà été mis en service dans votre société, utilisez les URL affichées sur la page pour y accéder.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-114">If RCS environment has been already provisioned to your company, use presented on the page URLs to access it.</span></span> 
7. <span data-ttu-id="e3b9b-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-115">Close the page.</span></span> 

## <a name="register-a-new-er-repository"></a><span data-ttu-id="e3b9b-116">Enregistrez un nouveau référentiel ER.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-116">Register a new ER repository.</span></span> 
1. <span data-ttu-id="e3b9b-117">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-117">In the list, mark the selected row.</span></span> 
2. <span data-ttu-id="e3b9b-118">Sélectionnez le fournisseur Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-118">Select Litware, Inc. provider.</span></span> 
3. <span data-ttu-id="e3b9b-119">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-119">Click Repositories.</span></span> 
4. <span data-ttu-id="e3b9b-120">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-120">Click Add to open the drop dialog.</span></span> 
5. <span data-ttu-id="e3b9b-121">Dans le champ Type du référentiel de configuration, entrez « RCS ».</span><span class="sxs-lookup"><span data-stu-id="e3b9b-121">In the Configuration repository type field, enter 'RCS'.</span></span> 
6. <span data-ttu-id="e3b9b-122">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-122">Click Create repository.</span></span> 
7. <span data-ttu-id="e3b9b-123">Dans le champ Nom complet de l'environnement RCS, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-123">In the RCS environment display name field, enter or select a value.</span></span> 
8. <span data-ttu-id="e3b9b-124">Sélectionnez l'instance RCS souhaitée.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-124">Select the desired RCS instance.</span></span> <span data-ttu-id="e3b9b-125">Notez que vous pouvez en définir plusieurs.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-125">Note that you can have several of them.</span></span> 
9. <span data-ttu-id="e3b9b-126">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-126">Click OK.</span></span> 

## <a name="import-er-configurations-from-rcs-based-repository"></a><span data-ttu-id="e3b9b-127">Importer des configurations de gestion des états électroniques depuis un référentiel basé sur RCS</span><span class="sxs-lookup"><span data-stu-id="e3b9b-127">Import ER configurations from RCS based repository</span></span>
1. <span data-ttu-id="e3b9b-128">Cliquez sur **Afficher les filtres**.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-128">Click **Show filters**.</span></span> 
2. <span data-ttu-id="e3b9b-129">Entrez la valeur de filtre « RCS » dans le champ **Nom** à l'aide de l'opérateur de filtre **commence par**.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-129">Enter a filter value of "RCS" on the **Name** field using the **begins with** filter operator.</span></span> 
3. <span data-ttu-id="e3b9b-130">Lorsque vous ouvrez le référentiel sélectionné, dans la page **Connexion à Regulatory Configuration Services**, cliquez sur le lien **Cliquer ici pour se connecter à Regulatory Configuration Services**.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-130">When you open the selected repository, on the **Connect to Regulatory Configuration Services** page, click **Click here to connect to Regulatory Configuration Services** link.</span></span> 
4. <span data-ttu-id="e3b9b-131">Cliquez sur **Ouvrir.**</span><span class="sxs-lookup"><span data-stu-id="e3b9b-131">Click **Open**.</span></span> 
5. <span data-ttu-id="e3b9b-132">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-132">Click **Close**.</span></span> 
6. <span data-ttu-id="e3b9b-133">Sélectionnez la version souhaitée de la configuration ER et cliquez sur **Importer** pour l'importer dans l'instance Finance and Operations actuelle.</span><span class="sxs-lookup"><span data-stu-id="e3b9b-133">Select the desired version of ER configuration and click **Import** to bring it in the current Finance and Operations instance.</span></span>

