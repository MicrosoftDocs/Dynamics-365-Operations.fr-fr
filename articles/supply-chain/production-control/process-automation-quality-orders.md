---
title: Invoquer les flux d’automatisation de processus pour créer des ordres de qualité
description: Cette rubrique fournit des ressources pour utiliser Power Automate pour automatiser les processus métier, en utilisant l’exemple des ordres de qualité.
author: cabeln
ms.date: 05/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f35adab3075ba810964a41899ba95ae40c115e83
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115183"
---
# <a name="invoke-process-automation-flows-to-create-quality-orders"></a><span data-ttu-id="9b45b-103">Invoquer les flux d’automatisation de processus pour créer des ordres de qualité</span><span class="sxs-lookup"><span data-stu-id="9b45b-103">Invoke process automation flows to create quality orders</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="9b45b-104">Les organisations ont une demande croissante pour automatiser les processus métier standard, fournir des interactions plus pratiques avec le personnel et utiliser divers signaux et systèmes de données pour gérer automatiquement les processus métier.</span><span class="sxs-lookup"><span data-stu-id="9b45b-104">Organizations have an increasing demand to automate standard business processes, provide more convenient interactions to the staff, and utilize various data signals and systems to drive business processes automatically.</span></span> <span data-ttu-id="9b45b-105">Avec l’automatisation robotisée des processus (RPA) et Microsoft Power Automate, les entreprises peuvent utiliser une expérience sans code pour automatiser les processus répétitifs et gagner ainsi en efficacité et en précision.</span><span class="sxs-lookup"><span data-stu-id="9b45b-105">With robotic process automation (RPA) and Microsoft Power Automate, businesses can use a no-code experience to automate repetitive processes, thus gaining efficiency and accuracy.</span></span>

<span data-ttu-id="9b45b-106">Le modèle de solution d’automatisation téléchargeable pour Supply Chain Management montre comment Power Automate peut être utilisé pour automatiser les processus métier en utilisant les ordres de qualité comme exemple.</span><span class="sxs-lookup"><span data-stu-id="9b45b-106">The downloadable automation solution template for Supply Chain Management showcases how Power Automate can be used to automate business processes using quality orders as an example.</span></span>

<span data-ttu-id="9b45b-107">Vous pouvez télécharger le modèle de solution d’automatisation [ici](https://aka.ms/D365SCMQualityOrderRPASolution).</span><span class="sxs-lookup"><span data-stu-id="9b45b-107">You can download the automation solution template [here](https://aka.ms/D365SCMQualityOrderRPASolution).</span></span>

<span data-ttu-id="9b45b-108">Pour obtenir une vue d’ensemble de cette fonctionnalité et de ses capacités, regardez la vidéo suivante : [Utiliser RPA pour créer des ordres de qualité dans Dynamics 365 Supply Chain Management](https://www.youtube.com/watch?v=LFbzJ6-H89w)</span><span class="sxs-lookup"><span data-stu-id="9b45b-108">For an overview of this feature and its capabilities, see the following video: [Utilize RPA to create quality orders in Dynamics 365 Supply Chain Management](https://www.youtube.com/watch?v=LFbzJ6-H89w)</span></span>

<span data-ttu-id="9b45b-109">![Options d’automatisation avec RPA](media/rpa-automation-options.png "Options d’automatisation avec RPA")</span><span class="sxs-lookup"><span data-stu-id="9b45b-109">![Automation options with RPA](media/rpa-automation-options.png "Automation options with RPA")</span></span>

<span data-ttu-id="9b45b-110">Le modèle de solution Power Automate comprend un flux d’automatisation cloud et un flux d’automatisation de bureau qui automatisent la création d’ordres de qualité dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9b45b-110">The Power Automate solution template includes a cloud automation flow and a desktop automation flow that automate the creation of quality orders in Supply Chain Management.</span></span>

<span data-ttu-id="9b45b-111">L’automatisation peut être lancée en réponse à de nombreux événements et signaux, notamment l’entrée de l’utilisateur ou les signaux de la machine (notamment l’Internet des objets (IoT)).</span><span class="sxs-lookup"><span data-stu-id="9b45b-111">The automation can be started in response to many events and signals, including user input or machine signals (including the Internet of Things (IoT)).</span></span> <span data-ttu-id="9b45b-112">L’exemple *Q-Order* de Power Application est inclus dans le modèle de solution.</span><span class="sxs-lookup"><span data-stu-id="9b45b-112">The *Q-Order* Power Application example is included in the solution template.</span></span> <span data-ttu-id="9b45b-113">Il permet à l’utilisateur de scanner le code QR d’un article, d’entrer la quantité et de joindre des images à l’aide d’un appareil photo.</span><span class="sxs-lookup"><span data-stu-id="9b45b-113">It allows the user to scan an item QR code, enter quantity, and attach pictures using a camera.</span></span>

<span data-ttu-id="9b45b-114">Les paramètres de la solution sont inclus pour configurer l’automatisation pour un scénario d’utilisation spécifique dans une installation de production.</span><span class="sxs-lookup"><span data-stu-id="9b45b-114">Solution parameters are included to configure the automation for a specific use case in a production facility.</span></span>

<span data-ttu-id="9b45b-115">![Créer un ordre de qualité](media/rpa-create-quality-roder.png "Créer un ordre de qualité")</span><span class="sxs-lookup"><span data-stu-id="9b45b-115">![Create quality order](media/rpa-create-quality-roder.png "Create quality order")</span></span>

<span data-ttu-id="9b45b-116">Pour obtenir un guide étape par étape complet sur la façon de télécharger, d’installer et d’utiliser l’exemple de solution pour automatiser la création d’ordres de qualité, consultez [Automatiser la création d’ordres de qualité dans Dynamics 365 Supply Chain Management avec l’automatisation robotisée des processus en utilisant Power Automate Desktop](/power-automate/desktop-flows/dynamics365-scm-rpa).</span><span class="sxs-lookup"><span data-stu-id="9b45b-116">For a complete step-by-step guide about how to download, install, and use the sample solution for automating quality order creation, see [Automate quality order creation on Dynamics 365 Supply Chain Management with Robotic Process Automation using Power Automate Desktop](/power-automate/desktop-flows/dynamics365-scm-rpa).</span></span>

