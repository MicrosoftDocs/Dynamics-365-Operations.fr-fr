---
title: Date de début pour le calcul de la fréquence de présélection
description: Cette rubrique décrit l’option Date de début pour le calcul de la fréquence de présélection définie pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae5ad3e556f40cedd385d8aadded9ef76447a98b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054090"
---
# <a name="screening-frequency-generate-from"></a><span data-ttu-id="35d37-103">Date de début pour le calcul de la fréquence de présélection</span><span class="sxs-lookup"><span data-stu-id="35d37-103">Screening frequency generate from</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="35d37-104">Cette rubrique décrit l’option Date de début pour le calcul de la fréquence de présélection définie pour Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="35d37-104">This topic describes the Screening frequency generate from option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="35d37-105">Nom physique : mshr_hcmfrequencygeneratefrom</span><span class="sxs-lookup"><span data-stu-id="35d37-105">Physical name: mshr_hcmfrequencygeneratefrom</span></span>

<span data-ttu-id="35d37-106">Cette énumération fournit le jeu d’options de valeurs pour déterminer la date de début du calcul pour la prochaine présélection obligatoire.</span><span class="sxs-lookup"><span data-stu-id="35d37-106">This enumeration provides the option set of values for determining the start date of the calculation for the next required screening.</span></span>

| <span data-ttu-id="35d37-107">Valeur</span><span class="sxs-lookup"><span data-stu-id="35d37-107">Value</span></span> | <span data-ttu-id="35d37-108">Étiquette</span><span class="sxs-lookup"><span data-stu-id="35d37-108">Label</span></span> | <span data-ttu-id="35d37-109">Description</span><span class="sxs-lookup"><span data-stu-id="35d37-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="35d37-110">200000000 Non sélectionné</span><span class="sxs-lookup"><span data-stu-id="35d37-110">200000000 Not selected</span></span> | <span data-ttu-id="35d37-111">Aucune valeur n’a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="35d37-111">No value has been selected.</span></span> |
| <span data-ttu-id="35d37-112">200000001 Date de fin</span><span class="sxs-lookup"><span data-stu-id="35d37-112">200000001 Date completed</span></span> | <span data-ttu-id="35d37-113">Le calcul est effectué à partir de la dernière date des tests.</span><span class="sxs-lookup"><span data-stu-id="35d37-113">Calculation is done from the last screening date completed.</span></span> |
| <span data-ttu-id="35d37-114">200000002 Date obligatoire</span><span class="sxs-lookup"><span data-stu-id="35d37-114">200000002 Date required</span></span> | <span data-ttu-id="35d37-115">Le calcul est effectué à partir de la dernière date des tests obligatoires.</span><span class="sxs-lookup"><span data-stu-id="35d37-115">Calculation is done from the last screening date required.</span></span> |

## <a name="see-also"></a><span data-ttu-id="35d37-116">Voir également :</span><span class="sxs-lookup"><span data-stu-id="35d37-116">See also</span></span>

[<span data-ttu-id="35d37-117">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="35d37-117">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="35d37-118">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="35d37-118">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]