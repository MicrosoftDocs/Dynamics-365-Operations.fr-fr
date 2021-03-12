---
title: Réutiliser des configurations de produit
description: Vous pouvez spécifier que vous souhaitez réutiliser automatiquement une configuration existante pour un produit. Ensuite, lorsqu'un utilisateur a terminé une session de configuration, le système vérifie si une configuration qui correspond aux sélections effectuée par l'utilisateur existe déjà. Si une configuration correspondante est trouvée, l'ID configuration, la nomenclature correspondante et la gamme sont réutilisés.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be153fd6376d59bee93f432d26963a2937436666
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999754"
---
# <a name="reuse-product-configurations"></a><span data-ttu-id="8478e-105">Réutiliser des configurations de produit</span><span class="sxs-lookup"><span data-stu-id="8478e-105">Reuse product configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8478e-106">Vous pouvez spécifier que vous souhaitez réutiliser automatiquement une configuration existante pour un produit.</span><span class="sxs-lookup"><span data-stu-id="8478e-106">You can specify that you want to automatically reuse an existing configuration for a product.</span></span> <span data-ttu-id="8478e-107">Ensuite, lorsqu'un utilisateur a terminé une session de configuration, le système vérifie si une configuration qui correspond aux sélections effectuée par l'utilisateur existe déjà.</span><span class="sxs-lookup"><span data-stu-id="8478e-107">Then, when a user has completed a configuration session, the system verifies whether a configuration that matches the user’s selections already exists.</span></span> <span data-ttu-id="8478e-108">Si une configuration correspondante est trouvée, l'ID configuration, la nomenclature correspondante et la gamme sont réutilisés.</span><span class="sxs-lookup"><span data-stu-id="8478e-108">If a matching configuration is found, the configuration ID, corresponding bill of materials (BOM), and route are reused.</span></span>

<a name="requirements-for-reusing-configurations"></a><span data-ttu-id="8478e-109">Critères de réutilisation des configurations</span><span class="sxs-lookup"><span data-stu-id="8478e-109">Requirements for reusing configurations</span></span>
---------------------------------------

<span data-ttu-id="8478e-110">Pour activer les configurations à réutiliser, vous devez spécifier les informations suivantes pour les composants et les attributs sur la page **Détails de modélisation de configuration de produit** :</span><span class="sxs-lookup"><span data-stu-id="8478e-110">To enable configurations to be reused, you must specify the following information for the components and attributes on the **Product configuration model details** page:</span></span>

-   <span data-ttu-id="8478e-111">**Composants et sous-composants** – Dans l'organisateur **Général**, dans le champ **Réutiliser les configurations**, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8478e-111">**Components and subcomponents** – On the **General** FastTab, in the **Reuse configurations** field, select **Yes**.</span></span>
-   <span data-ttu-id="8478e-112">**Attributs** – Sous l'organisateur **Attributs**, sélectionnez l'option **Inclure dans la réutilisation**.</span><span class="sxs-lookup"><span data-stu-id="8478e-112">**Attributes** – On the **Attributes** FastTab, select the **Include in reuse** option.</span></span> <span data-ttu-id="8478e-113">L'option ne s'affiche que si la réutilisation du composant associé est activée.</span><span class="sxs-lookup"><span data-stu-id="8478e-113">This option appears only when the related component is enabled for reuse.</span></span> <span data-ttu-id="8478e-114">Si vous ne sélectionnez aucun attribut pour la réutilisation, la configuration est toujours réutilisée, quelles que soient les sélections effectuées par l'utilisateur au cours d'une session de configuration.</span><span class="sxs-lookup"><span data-stu-id="8478e-114">If you don't select any attributes for reuse, the configuration is always reused, regardless of the user’s selections during a configuration session.</span></span> <span data-ttu-id="8478e-115">Les valeurs d'attributs de la configuration existante doivent correspondre aux sélections effectuées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8478e-115">The attribute values in the existing configuration must match the user’s selections.</span></span> <span data-ttu-id="8478e-116">Par exemple, si l'utilisateur sélectionne la couleur **Bleu** comme couleur lors d'une session de configuration, le système vérifie si une configuration existante du composant a la couleur Bleu.</span><span class="sxs-lookup"><span data-stu-id="8478e-116">For example, if the user selects **Blue** as the color during a configuration session, the system verifies whether an existing configuration of the component has the color blue.</span></span>

## <a name="resetting-configuration-reuse"></a><span data-ttu-id="8478e-117">Réinitialisation de la réutilisation de configuration</span><span class="sxs-lookup"><span data-stu-id="8478e-117">Resetting configuration reuse</span></span>
<span data-ttu-id="8478e-118">Lorsque vous réinitialisez la réutilisation de configuration, les configurations précédemment créées ne sont plus prises en compte.</span><span class="sxs-lookup"><span data-stu-id="8478e-118">When you reset configuration reuse, previously created configurations are no longer considered.</span></span> <span data-ttu-id="8478e-119">Vous pouvez réinitialiser la réutilisation de configuration si la nomenclature ou la gamme a été modifiée, mais aucun attribut associé n'a été modifié.</span><span class="sxs-lookup"><span data-stu-id="8478e-119">You might want to reset configuration reuse if the BOM or route was changed, but no related attributes were changed.</span></span> <span data-ttu-id="8478e-120">Vous réinitialisez la réutilisation de configuration sur l'organisateur **Général** du composant.</span><span class="sxs-lookup"><span data-stu-id="8478e-120">You reset configuration reuse on the **General** FastTab for the component.</span></span>



