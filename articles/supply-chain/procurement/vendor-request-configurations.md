---
title: Configuration des demandes fournisseur
description: "Cette rubrique décrit les champs qui doivent être renseignés dans une nouvelle demande fournisseur."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5610d1fc2adff0d04ea3931de4b1e23225e50ff0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="vendor-request-configurations"></a><span data-ttu-id="67ab3-103">Configuration des demandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="67ab3-103">Vendor request configurations</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="67ab3-104">Pour effectuer une demande fournisseur, un contact fournisseur doit exécuter l'assistant d'enregistrement du fournisseur potentiel.</span><span class="sxs-lookup"><span data-stu-id="67ab3-104">To complete a vendor request, a vendor contact person must complete the prospective vendor registration wizard.</span></span>

<span data-ttu-id="67ab3-105">Dans l'écran **Configuration des demandes fournisseur**, vous pouvez créer des profils qui indiquent les champs obligatoires et les champs visibles dans l'assistant d'enregistrement du fournisseur potentiel.</span><span class="sxs-lookup"><span data-stu-id="67ab3-105">In the **Vendor request configurations** form, you can create profiles that specify required fields and visible fields in the prospective vendor registration wizard.</span></span>

<span data-ttu-id="67ab3-106">L'assistant d'enregistrement du fournisseur commence par demander à l'utilisateur fournisseur potentiel le pays ou la région où le fournisseur exerce des activités.</span><span class="sxs-lookup"><span data-stu-id="67ab3-106">The vendor registration wizard will start out by asking the prospective vendor user which country/region the vendor is doing business in.</span></span> <span data-ttu-id="67ab3-107">Ces informations déterminent la configuration applicable.</span><span class="sxs-lookup"><span data-stu-id="67ab3-107">This information determines the applicable configuration.</span></span> <span data-ttu-id="67ab3-108">Si aucune configuration spécifique n'est définie pour un pays ou une région, une configuration par défaut est utilisée.</span><span class="sxs-lookup"><span data-stu-id="67ab3-108">If no specific configuration is defined for a country/region, a default configuration will be used.</span></span>

### <a name="set-up-a-vendor-request-configuration"></a><span data-ttu-id="67ab3-109">Paramétrer une configuration de la demande fournisseur</span><span class="sxs-lookup"><span data-stu-id="67ab3-109">Set up a vendor request configuration</span></span>

<span data-ttu-id="67ab3-110">Par défaut, une configuration fournisseur est disponible dans l'écran Configuration des demandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="67ab3-110">By default, there is a vendor configuration available in the Vendor request configurations form.</span></span>

<span data-ttu-id="67ab3-111">Il n'est pas possible de sélectionner un pays ou une région pour la configuration par défaut, la section **Pays/Régions** ne peut donc pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="67ab3-111">It is not possible to select country/regions for the default configuration, so the **Countries/regions** section cannot be changed.</span></span>

1. <span data-ttu-id="67ab3-112">Cliquez sur **Approvisionnements** > **Paramétrage** > **Fournisseurs**, puis cliquez sur **Configuration des demandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="67ab3-112">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2. <span data-ttu-id="67ab3-113">Cliquez sur l'onglet **Champs** pour définir le statut des champs répertoriés.</span><span class="sxs-lookup"><span data-stu-id="67ab3-113">Click the **Fields** tab to set the status of the listed fields.</span></span>
3. <span data-ttu-id="67ab3-114">Masqué (pas visible)</span><span class="sxs-lookup"><span data-stu-id="67ab3-114">Hidden (Not visible)</span></span>
4. <span data-ttu-id="67ab3-115">Affiché (visible mais pas obligatoire)</span><span class="sxs-lookup"><span data-stu-id="67ab3-115">Displayed (Visible but not mandatory)</span></span>
5. <span data-ttu-id="67ab3-116">Requis (visible et obligatoire)</span><span class="sxs-lookup"><span data-stu-id="67ab3-116">Required (Visible and mandatory)</span></span>
6. <span data-ttu-id="67ab3-117">Cliquez sur l'onglet **Contenu** pour indiquer si le texte doit être affiché dans l'assistant et si la confirmation de l'utilisateur fournisseur potentiel est requise avant de passer à l'étape suivante de l'assistant.</span><span class="sxs-lookup"><span data-stu-id="67ab3-117">Click the **Content** tab to specify if text is going to be shown on the wizard and if there should be an acknowledgement that the prospective vendor user must accept this before moving to the next step in the wizard.</span></span> <span data-ttu-id="67ab3-118">Une confirmation est demandée pour les conditions générales que l'utilisateur doit accepter pour continuer.</span><span class="sxs-lookup"><span data-stu-id="67ab3-118">The acknowledgement will be requested for any terms and conditions that the user must accept to continue.</span></span>

<span data-ttu-id="67ab3-119">Vous pouvez également entrer un message de confirmation qui s'affiche lorsque l'assistant est finalisé, et vous pouvez ajouter un ou plusieurs questionnaires.</span><span class="sxs-lookup"><span data-stu-id="67ab3-119">You can also enter a confirmation message that will be displayed when the wizard is finalized, and you can add one or more questionnaires.</span></span>

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a><span data-ttu-id="67ab3-120">Créer une configuration fournisseur pour un pays ou une région spécifique</span><span class="sxs-lookup"><span data-stu-id="67ab3-120">Create a vendor configuration for a specific country/region</span></span>
1.  <span data-ttu-id="67ab3-121">Cliquez sur **Approvisionnements** > **Paramétrage** > **Fournisseurs**, puis cliquez sur **Configuration des demandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="67ab3-121">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="67ab3-122">Cliquez sur **Nouveau** pour créer une configuration, puis entrez un nom pour la configuration.</span><span class="sxs-lookup"><span data-stu-id="67ab3-122">Click **New** to create a new configuration, and provide a name for the configuration.</span></span>
3.  <span data-ttu-id="67ab3-123">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="67ab3-123">Click **Save**.</span></span>
4.  <span data-ttu-id="67ab3-124">Ouvrez l'onglet **Pays/région** pour sélectionner le pays ou la région pour lequel la configuration doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="67ab3-124">Open the **Country/regions** tab to select the country/region that the configuration should be used for.</span></span>
5.  <span data-ttu-id="67ab3-125">Exécutez la configuration en suivant les instructions pour la configuration par défaut.</span><span class="sxs-lookup"><span data-stu-id="67ab3-125">Complete the configuration by following the guidelines for the default configuration.</span></span>


