---
title: Activer Power BI pour la comptabilité globale des stocks
description: Cette rubrique décrit comment activer Microsoft Power BI pour la comptabilité globale des stocks.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d7979ed18b98ee6133774cd91bc866d6fca92d5f
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273155"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a><span data-ttu-id="1f4b2-103">Activer Power BI pour la comptabilité globale des stocks</span><span class="sxs-lookup"><span data-stu-id="1f4b2-103">Enable Power BI for Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="1f4b2-104">Vous pouvez épingler des vignettes, des tableaux de bord et des rapports provenant de votre compte [PowerBI.com](https://powerbi.com/) à votre espace de travail de l’application Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-104">You can pin tiles, dashboards, and reports from your [PowerBI.com](https://powerbi.com/) account to your Microsoft Dynamics 365 application workspace.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f4b2-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1f4b2-105">Prerequisites</span></span>

<span data-ttu-id="1f4b2-106">Les conditions préalables suivantes doivent être satisfaites avant de pouvoir activer la génération de rapports Power BI :</span><span class="sxs-lookup"><span data-stu-id="1f4b2-106">The following prerequisites must be in place before you can enable Power BI reporting:</span></span>

- <span data-ttu-id="1f4b2-107">Vous devez être un administrateur système dans l’application Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-107">You must be a system administrator in the Dynamics 365 application.</span></span>
- <span data-ttu-id="1f4b2-108">Vous devez avoir un compte [PowerBI.com](https://powerbi.com/).</span><span class="sxs-lookup"><span data-stu-id="1f4b2-108">You must have a [PowerBI.com](https://powerbi.com/) account.</span></span>
- <span data-ttu-id="1f4b2-109">Vous devez avoir au moins un tableau de bord et un rapport dans votre compte Power BI.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-109">You must have at least one dashboard and one report in your Power BI account.</span></span>
- <span data-ttu-id="1f4b2-110">Vous devez être administrateur de votre compte Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1f4b2-110">You must be an administrator for your Azure Active Directory (Azure AD) account.</span></span>
- <span data-ttu-id="1f4b2-111">Le domaine Azure AD doit être le même que celui que vous avez utilisé pour votre compte [PowerBI.com](https://powerbi.com/).</span><span class="sxs-lookup"><span data-stu-id="1f4b2-111">The Azure AD domain must be the same domain that you used for your [PowerBI.com](https://powerbi.com/) account.</span></span>

## <a name="setup"></a><span data-ttu-id="1f4b2-112">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="1f4b2-112">Setup</span></span>

<span data-ttu-id="1f4b2-113">Pour configurer l’intégration de Power BI, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-113">To set up the Power BI integration, follow these steps.</span></span>

1. <span data-ttu-id="1f4b2-114">Connectez-vous à [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="1f4b2-114">Sign in to [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="1f4b2-115">Accédez à **Bibliothèque d’actifs partagés**, sélectionnez **Modèle de rapport Power BI** comme type d’actif et téléchargez le package **Comptabilité globale des stocks**.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-115">Go to **Shared asset library**, select **Power BI report model** as the asset type, and download the **Global Inventory Accounting** package.</span></span> 
1. <span data-ttu-id="1f4b2-116">Connectez-vous à [PowerBI.com](https://app.powerbi.com/) et chargez le fichier de rapport Power BI **Comptabilité globale des stocks** en suivant ces étapes :</span><span class="sxs-lookup"><span data-stu-id="1f4b2-116">Sign in to [PowerBI.com](https://app.powerbi.com/), and upload the **Global Inventory Accounting** Power BI report file by following these steps:</span></span>

    1. <span data-ttu-id="1f4b2-117">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-117">Select **New**.</span></span>
    1. <span data-ttu-id="1f4b2-118">Sélectionnez **Charger un fichier**.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-118">Select **Upload a file**.</span></span>
    1. <span data-ttu-id="1f4b2-119">Sélectionnez le fichier de rapport Power BI **Comptabilité globale des stocks**.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-119">Select the **Global Inventory Accounting** Power BI report file.</span></span>

1. <span data-ttu-id="1f4b2-120">Configurez le rapport Power BI **Comptabilité globale des stocks** en suivant ces étapes :</span><span class="sxs-lookup"><span data-stu-id="1f4b2-120">Configure the **Global Inventory Accounting** Power BI report by following these steps:</span></span>

    1. <span data-ttu-id="1f4b2-121">Accédez à **Mon espace de travail**, recherchez le jeu de données pour la comptabilité globale des stocks puis, dans le menu **Options**, sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-121">Go to **My workspace**, find the dataset for Global Inventory Accounting, and then, on the **Options** menu, select **Settings**.</span></span>
    1. <span data-ttu-id="1f4b2-122">Dans **Paramètres de la comptabilité globale des stocks**, développez **Paramètres** et mettez à jour tous les paramètres si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-122">In **Settings for Global inventory accounting**, expand **Parameters**, and update all parameters as required.</span></span>

1. <span data-ttu-id="1f4b2-123">Enregistrez l’application comme décrit dans [Configurer l’intégration PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span><span class="sxs-lookup"><span data-stu-id="1f4b2-123">Register the application as described in [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span></span>
1. <span data-ttu-id="1f4b2-124">Intégrez le fichier de rapport Power BI **Comptabilité globale des stocks** dans Dynamics 365 Supply Chain Management en suivant les étapes ci-après :</span><span class="sxs-lookup"><span data-stu-id="1f4b2-124">Integrate the **Global Inventory Accounting** Power BI report file into Dynamics 365 Supply Chain Management by following these steps:</span></span>

    1. <span data-ttu-id="1f4b2-125">Accédez à **Administration système \> Paramétrage \> Configuration PowerBI.com**.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-125">Go to **System administration \> Setup \> PowerBI.com configuration**.</span></span>
    1. <span data-ttu-id="1f4b2-126">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-126">Select **Edit**.</span></span>
    1. <span data-ttu-id="1f4b2-127">Sélectionnez **Activer l’intégration PowerBI.Com**.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-127">Select **Enable PowerBI.Com integration**.</span></span>
    1. <span data-ttu-id="1f4b2-128">Dans le champ **ID application**, entrez l’ID d’application.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-128">In the **Application ID** field, enter the application ID.</span></span>
    1. <span data-ttu-id="1f4b2-129">Dans le champ **Clé d’application**, entrez la clé d’application.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-129">In the **Application key** field, enter the application key.</span></span>
    1. <span data-ttu-id="1f4b2-130">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-130">Select **Save**.</span></span>

1. <span data-ttu-id="1f4b2-131">Rafraîchissez la page pour que la boîte de dialogue de connexion Power BI s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-131">Refresh the page so that the Power BI sign-in dialog box appears.</span></span>
1. <span data-ttu-id="1f4b2-132">Sur l’onglet **Options**, sélectionnez **Ouvrir le catalogue de rapports**, puis sélectionnez le fichier de rapport Power BI **Comptabilité globale des stocks** que vous avez téléchargé précédemment.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-132">On the **Options** tab, select **Open report catalog**, and then select the **Global Inventory Accounting** Power BI report file that you uploaded earlier.</span></span>
1. <span data-ttu-id="1f4b2-133">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-133">Refresh the page.</span></span> <span data-ttu-id="1f4b2-134">Vous devriez voir que votre rapport a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-134">You should see that your report has been added.</span></span>
1. <span data-ttu-id="1f4b2-135">Sous **Rapports Power BI**, sélectionnez le lien **Comptabilité globale des stocks**.</span><span class="sxs-lookup"><span data-stu-id="1f4b2-135">Under **Power BI reports**, select the **Global Inventory Accounting** link.</span></span>

<span data-ttu-id="1f4b2-136">Pour plus d’informations, voir [Configuration de l’intégration PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span><span class="sxs-lookup"><span data-stu-id="1f4b2-136">For more information, see [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span></span>
