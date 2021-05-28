---
title: Préparer votre environnement pour générer un FEC
description: Cette rubrique explique comment préparer votre environnement Microsoft Dynamics 365 Finance pour générer un fichier d'audit Fichier des écritures comptables (FEC).
author: liza-golub
ms.date: 05/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.author: elgolu
ms.reviewer: kfend
ms.search.region: France
ms.openlocfilehash: 33a90863b89b866f63d943a2083ec9a5a9b3d158
ms.sourcegitcommit: 51cad1ce3ed44ebf7eb9bdf553ee2df4c1f03135
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016198"
---
# <a name="prepare-your-environment-to-generate-an-fec"></a><span data-ttu-id="5eedc-103">Préparer votre environnement pour générer un FEC</span><span class="sxs-lookup"><span data-stu-id="5eedc-103">Prepare your environment to generate an FEC</span></span>

<span data-ttu-id="5eedc-104">Avant de pouvoir générer un fichier d'audit du Fichier des écritures comptables (FEC), vous devez importer les dernières versions des configurations de reporting électronique (ER) suivantes.</span><span class="sxs-lookup"><span data-stu-id="5eedc-104">Before you can generate a Fichier des écritures comptables (FEC) audit file, you must import the latest versions of the following Electronic reporting (ER) configurations.</span></span>

| <span data-ttu-id="5eedc-105">Configuration ER</span><span class="sxs-lookup"><span data-stu-id="5eedc-105">ER configuration</span></span>         | <span data-ttu-id="5eedc-106">Type</span><span class="sxs-lookup"><span data-stu-id="5eedc-106">Type</span></span>          | <span data-ttu-id="5eedc-107">Description </span><span class="sxs-lookup"><span data-stu-id="5eedc-107">Description</span></span> |
|--------------------------|---------------|-------------|
| <span data-ttu-id="5eedc-108">Modèle d'exportation des données</span><span class="sxs-lookup"><span data-stu-id="5eedc-108">Data export model</span></span>        | <span data-ttu-id="5eedc-109">Modèle</span><span class="sxs-lookup"><span data-stu-id="5eedc-109">Model</span></span>         | <span data-ttu-id="5eedc-110">Le modèle de données unifié pour l'exportation de données.</span><span class="sxs-lookup"><span data-stu-id="5eedc-110">The unified data model for data export.</span></span> |
| <span data-ttu-id="5eedc-111">Cartographie du modèle FEC français</span><span class="sxs-lookup"><span data-stu-id="5eedc-111">French FEC model mapping</span></span> | <span data-ttu-id="5eedc-112">Mappage de modèles</span><span class="sxs-lookup"><span data-stu-id="5eedc-112">Model mapping</span></span> | <span data-ttu-id="5eedc-113">La configuration qui collecte les données de différentes sources de données pour les préparer à la création de rapports FEC.</span><span class="sxs-lookup"><span data-stu-id="5eedc-113">The configuration that collects data from different data sources to prepare it for FEC reporting.</span></span> |
| <span data-ttu-id="5eedc-114">Fichier d’audit FEC (FR)</span><span class="sxs-lookup"><span data-stu-id="5eedc-114">FEC audit file (FR)</span></span>      | <span data-ttu-id="5eedc-115">Format</span><span class="sxs-lookup"><span data-stu-id="5eedc-115">Format</span></span>        | <span data-ttu-id="5eedc-116">Le format d'exportation dans la structure FEC.</span><span class="sxs-lookup"><span data-stu-id="5eedc-116">The exporting format in the FEC structure.</span></span> |

> [!NOTE]
> <span data-ttu-id="5eedc-117">Une fois que vous importez toutes les configurations ER du tableau précédent importées, sur la page **Configurations**, définissez l’option **Valeur par défaut pour le mappage de modèle** sur **Oui** pour la configuration **Cartographie du modèle FEC français**.</span><span class="sxs-lookup"><span data-stu-id="5eedc-117">After you import all the ER configurations in the previous table, on the **Configurations** page, set the **Default for model mapping** option to **Yes** for the **French FEC model mapping** configuration.</span></span>

<span data-ttu-id="5eedc-118">Pour plus d'informations sur le téléchargement des configurations ER à partir du référentiel global Microsoft, consultez [Télécharger les configurations ER à partir du référentiel global](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).</span><span class="sxs-lookup"><span data-stu-id="5eedc-118">For more information about how to download ER configurations from the Microsoft global repository, see [Download ER configurations from the Global repository](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).</span></span>

<span data-ttu-id="5eedc-119">À partir de la version 10.0.20, pour utiliser le format **Fichier d'audit FEC (FR)**, vous devez définir le nom de la configuration ER dans un nouveau paramètre de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="5eedc-119">Starting in version 10.0.20, to use the **FEC audit file (FR)** format, you must define the ER configuration name in a new General ledger parameter.</span></span> 

1. <span data-ttu-id="5eedc-120">Accédez à **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="5eedc-120">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="5eedc-121">Dans l'onglet **Registre**, dans le raccourci **Rapports électroniques**, dans la section **Exportation des écritures comptables**, dans le champ **Exportation des écritures comptables**, sélectionnez le format **Fichier d'audit FEC (FR)**.</span><span class="sxs-lookup"><span data-stu-id="5eedc-121">On the **Ledger** tab, on the **Electronic reporting** FastTab, in the **Ledger transactions export** section, in the **Ledger transactions export** field, select the **FEC audit file (FR)** format.</span></span>
3. <span data-ttu-id="5eedc-122">Enregistrez la nouvelle configuration.</span><span class="sxs-lookup"><span data-stu-id="5eedc-122">Save the new setting.</span></span>
