---
title: Identifier une hypothèse et déterminer les métriques pour une expérience
description: Cette rubrique décrit comment identifier l'hypothèse et les métriques de réussite d'une expérience que vous exécuterez sur un site web d'e-commerce dans Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 91614cda804cae4574fce4c9cfb31c63d876f19b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238628"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a><span data-ttu-id="b9175-103">Identifier une hypothèse et déterminer les métriques de réussite pour une expérience</span><span class="sxs-lookup"><span data-stu-id="b9175-103">Identify a hypothesis and determine success metrics for an experiment</span></span>
<span data-ttu-id="b9175-104">La première phase du cycle de vie de l'expérimentation comprend l'identification de l'hypothèse de l'expérience et la détermination des métriques que vous suivrez pour évaluer la réussite.</span><span class="sxs-lookup"><span data-stu-id="b9175-104">The first phase in the experimentation lifecycle includes identifying the hypothesis for the experiment and determining the metrics you'll track to evaluate success.</span></span> <span data-ttu-id="b9175-105">Le diagramme suivant montre toutes les étapes impliquées dans [la configuration et l'exécution d'une expérience](experimentation-overview.md) sur un site web d'e-commerce dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b9175-105">The following diagram shows all of the steps involved in [setting up and running an experiment](experimentation-overview.md) on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="b9175-106">Les étapes supplémentaires sont traitées dans d'autres rubriques.</span><span class="sxs-lookup"><span data-stu-id="b9175-106">Additional steps are covered in separate topics.</span></span> 

<span data-ttu-id="b9175-107">[ ![Expérimentation parcours utilisateur - Identifier](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b9175-107">[ ![Experimentation user journey - Identify](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span></span>

<span data-ttu-id="b9175-108">Une hypothèse est une déclaration dans laquelle vous prédisez le résultat de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="b9175-108">A hypothesis is a statement where you predict the outcome of the experiment.</span></span> <span data-ttu-id="b9175-109">De nombreux facteurs entrent dans la définition d'une hypothèse, par exemple, la recherche sur le comportement des utilisateurs et les données de site web que vous avez collectées.</span><span class="sxs-lookup"><span data-stu-id="b9175-109">Many factors go into defining a hypothesis, for example, research about user behavior and website data you've collected.</span></span> <span data-ttu-id="b9175-110">Avec l'hypothèse, vous définirez l'hypothèse ou la théorie que vous souhaitez valider avec votre expérience.</span><span class="sxs-lookup"><span data-stu-id="b9175-110">With the hypothesis, you'll define the assumption or theory you want to validate with your experiment.</span></span> <span data-ttu-id="b9175-111">Un exemple d'hypothèse pour votre expérience peut être "*une photo d'un t-shirt blanc sur ma page d'accueil entraînera un taux de clics plus élevé que celle d'un pull bleu marine pendant les mois d'été, car les gens veulent porter quelque chose de léger et de couleur claire en été.*"</span><span class="sxs-lookup"><span data-stu-id="b9175-111">An example of a hypothesis for your experiment may be "*a picture of a white t-shirt on my home page will drive a higher clickthrough rate than a navy sweater during summer months because people want to wear something lightweight and light colored in the summer.*"</span></span> <span data-ttu-id="b9175-112">Dans ce cas, vous allez créer des variantes comprenant un t-shirt blanc et un pull bleu marine, et publier les deux en même temps.</span><span class="sxs-lookup"><span data-stu-id="b9175-112">In that case, you'll create variations that include a white t-shirt and a navy sweater, and publish both at the same time.</span></span>

<span data-ttu-id="b9175-113">Pour valider une hypothèse, la réussite ou l'échec d'une expérience doit être directement lié aux actions de l'utilisateur ; par exemple, si l'utilisateur du site web clique sur un lien ou un bouton.</span><span class="sxs-lookup"><span data-stu-id="b9175-113">To validate a hypothesis, the success or failure of an experiment should be directly tied to user actions; for example, if the website user clicks on a link or button.</span></span> <span data-ttu-id="b9175-114">Ces actions doivent correspondre aux événements qui seront signalés au service tiers qui effectue le suivi de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="b9175-114">These actions must correspond with events that will be reported to the third-party service tracking the experiment.</span></span> <span data-ttu-id="b9175-115">Au fil du temps, le pourcentage d'utilisateurs qui exécutent l'action sera comptabilisé comme une métrique que vous pouvez utiliser pour générer des rapports et effectuer des analyses.</span><span class="sxs-lookup"><span data-stu-id="b9175-115">Over time, the percentage of users that take the action will be tallied as a metric you can use to generate reports and conduct analyses.</span></span> <span data-ttu-id="b9175-116">Pour passer en revue tous les événements et attributs disponibles, voir [Événements des composants Commerce pour les diagnostics et le dépannage](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="b9175-116">To review all of the available events and attributes, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>

## <a name="previous-step"></a><span data-ttu-id="b9175-117">Étape précédente</span><span class="sxs-lookup"><span data-stu-id="b9175-117">Previous step</span></span>
[<span data-ttu-id="b9175-118">Expérimentation dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b9175-118">Experimentation in Dynamics 365 Commerce</span></span>](experimentation-overview.md)


## <a name="next-step"></a><span data-ttu-id="b9175-119">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="b9175-119">Next step</span></span>
[<span data-ttu-id="b9175-120">Paramétrer une expérience</span><span class="sxs-lookup"><span data-stu-id="b9175-120">Set up an experiment</span></span>](experimentation-setup.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]