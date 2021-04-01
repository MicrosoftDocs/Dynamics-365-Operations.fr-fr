---
title: Configuration des demandes fournisseur
description: Cette rubrique décrit les champs qui doivent être renseignés dans une nouvelle demande fournisseur.
author: RichardLuan
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 61ef9ba4eb683fea030f06b3bacf687d7f146de4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246571"
---
# <a name="vendor-request-configurations"></a><span data-ttu-id="d043b-103">Configuration des demandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="d043b-103">Vendor request configurations</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="d043b-104">Pour effectuer une demande fournisseur, un contact fournisseur doit exécuter l’assistant d’enregistrement du fournisseur potentiel.</span><span class="sxs-lookup"><span data-stu-id="d043b-104">To complete a vendor request, a vendor contact person must complete the prospective vendor registration wizard.</span></span>

<span data-ttu-id="d043b-105">Dans l’écran **Configuration des demandes fournisseur**, vous pouvez créer des profils qui indiquent les champs obligatoires et les champs visibles dans l’assistant d’enregistrement du fournisseur potentiel.</span><span class="sxs-lookup"><span data-stu-id="d043b-105">In the **Vendor request configurations** form, you can create profiles that specify required fields and visible fields in the prospective vendor registration wizard.</span></span>

<span data-ttu-id="d043b-106">L’assistant d’enregistrement du fournisseur commence par demander à l’utilisateur fournisseur potentiel le pays ou la région où le fournisseur exerce des activités.</span><span class="sxs-lookup"><span data-stu-id="d043b-106">The vendor registration wizard will start out by asking the prospective vendor user which country/region the vendor is doing business in.</span></span> <span data-ttu-id="d043b-107">Ces informations déterminent la configuration applicable.</span><span class="sxs-lookup"><span data-stu-id="d043b-107">This information determines the applicable configuration.</span></span> <span data-ttu-id="d043b-108">Si aucune configuration spécifique n’est définie pour un pays ou une région, une configuration par défaut est utilisée.</span><span class="sxs-lookup"><span data-stu-id="d043b-108">If no specific configuration is defined for a country/region, a default configuration will be used.</span></span>

### <a name="set-up-a-vendor-request-configuration"></a><span data-ttu-id="d043b-109">Paramétrer une configuration de la demande fournisseur</span><span class="sxs-lookup"><span data-stu-id="d043b-109">Set up a vendor request configuration</span></span>

<span data-ttu-id="d043b-110">Par défaut, une configuration fournisseur est disponible dans l’écran Configuration des demandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d043b-110">By default, there is a vendor configuration available in the Vendor request configurations form.</span></span>

<span data-ttu-id="d043b-111">Il n’est pas possible de sélectionner un pays ou une région pour la configuration par défaut, la section **Pays/Régions** ne peut donc pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="d043b-111">It is not possible to select country/regions for the default configuration, so the **Countries/regions** section cannot be changed.</span></span>

1. <span data-ttu-id="d043b-112">Cliquez sur **Approvisionnements** > **Paramétrage** > **Fournisseurs**, puis cliquez sur **Configuration des demandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="d043b-112">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2. <span data-ttu-id="d043b-113">Cliquez sur l’onglet **Champs** pour définir le statut des champs répertoriés.</span><span class="sxs-lookup"><span data-stu-id="d043b-113">Click the **Fields** tab to set the status of the listed fields.</span></span>
3. <span data-ttu-id="d043b-114">Masqué (pas visible)</span><span class="sxs-lookup"><span data-stu-id="d043b-114">Hidden (Not visible)</span></span>
4. <span data-ttu-id="d043b-115">Affiché (visible mais pas obligatoire)</span><span class="sxs-lookup"><span data-stu-id="d043b-115">Displayed (Visible but not mandatory)</span></span>
5. <span data-ttu-id="d043b-116">Requis (visible et obligatoire)</span><span class="sxs-lookup"><span data-stu-id="d043b-116">Required (Visible and mandatory)</span></span>
6. <span data-ttu-id="d043b-117">Cliquez sur l’onglet **Contenu** pour indiquer si le texte doit être affiché dans l’assistant et si la confirmation de l’utilisateur fournisseur potentiel est requise avant de passer à l’étape suivante de l’assistant.</span><span class="sxs-lookup"><span data-stu-id="d043b-117">Click the **Content** tab to specify if text is going to be shown on the wizard and if there should be an acknowledgement that the prospective vendor user must accept this before moving to the next step in the wizard.</span></span> <span data-ttu-id="d043b-118">Une confirmation est demandée pour les conditions générales que l’utilisateur doit accepter pour continuer.</span><span class="sxs-lookup"><span data-stu-id="d043b-118">The acknowledgement will be requested for any terms and conditions that the user must accept to continue.</span></span>

<span data-ttu-id="d043b-119">Vous pouvez également entrer un message de confirmation qui s’affiche lorsque l’assistant est finalisé, et vous pouvez ajouter un ou plusieurs questionnaires.</span><span class="sxs-lookup"><span data-stu-id="d043b-119">You can also enter a confirmation message that will be displayed when the wizard is finalized, and you can add one or more questionnaires.</span></span>

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a><span data-ttu-id="d043b-120">Créer une configuration fournisseur pour un pays ou une région spécifique</span><span class="sxs-lookup"><span data-stu-id="d043b-120">Create a vendor configuration for a specific country/region</span></span>
1.  <span data-ttu-id="d043b-121">Cliquez sur **Approvisionnements** > **Paramétrage** > **Fournisseurs**, puis cliquez sur **Configuration des demandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="d043b-121">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="d043b-122">Cliquez sur **Nouveau** pour créer une configuration, puis entrez un nom pour la configuration.</span><span class="sxs-lookup"><span data-stu-id="d043b-122">Click **New** to create a new configuration, and provide a name for the configuration.</span></span>
3.  <span data-ttu-id="d043b-123">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d043b-123">Click **Save**.</span></span>
4.  <span data-ttu-id="d043b-124">Ouvrez l’onglet **Pays/région** pour sélectionner le pays ou la région pour lequel la configuration doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="d043b-124">Open the **Country/regions** tab to select the country/region that the configuration should be used for.</span></span>
5.  <span data-ttu-id="d043b-125">Exécutez la configuration en suivant les instructions pour la configuration par défaut.</span><span class="sxs-lookup"><span data-stu-id="d043b-125">Complete the configuration by following the guidelines for the default configuration.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]