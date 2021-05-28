---
title: Instruments de test de gestion de la qualité
description: Cette rubrique décrit comment créer des instruments de test, afin que plusieurs tests puissent être utilisés avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3806ca26b8909b03768dad54ddad0084e1cea4a6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021730"
---
# <a name="quality-management-test-instruments"></a><span data-ttu-id="33c54-103">Instruments de test de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="33c54-103">Quality management test instruments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33c54-104">Cette rubrique décrit comment créer des instruments de test, afin que plusieurs tests puissent être utilisés avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33c54-104">This topic describes how to create test instruments that can be used for tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="33c54-105">La page **Instruments de test** permet de définir et d'afficher les détails sur les appareils utilisés pour effectuer des tests sur les ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="33c54-105">You use the **Test instruments** page to define and view details about the devices that are used to perform tests on quality orders.</span></span> <span data-ttu-id="33c54-106">Les instruments de test sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="33c54-106">Test instruments are optional.</span></span> <span data-ttu-id="33c54-107">Cependant, ils peuvent aider les responsables qualité à savoir quel appareil ou outil ils doivent utiliser pour effectuer un test spécifique.</span><span class="sxs-lookup"><span data-stu-id="33c54-107">However, they can help quality workers know which device or tool they should use to perform a specific test.</span></span>

## <a name="test-instrument-example"></a><span data-ttu-id="33c54-108">Exemple d'instrument de test</span><span class="sxs-lookup"><span data-stu-id="33c54-108">Test instrument example</span></span>

<span data-ttu-id="33c54-109">Vous effectuez divers tests sur des composants électriques.</span><span class="sxs-lookup"><span data-stu-id="33c54-109">You're performing various tests on electrical components.</span></span> <span data-ttu-id="33c54-110">Certains tests concernent la tension de sortie des composants, un test concerne leur température et un test leur poids.</span><span class="sxs-lookup"><span data-stu-id="33c54-110">Some tests are for the voltage output of the components, one test is for their temperature, and one test is for their weight.</span></span> <span data-ttu-id="33c54-111">Différents outils, dispositifs ou équipements sont utilisés pour effectuer chaque test.</span><span class="sxs-lookup"><span data-stu-id="33c54-111">Different tools, devices, or equipment is used to perform each test.</span></span> <span data-ttu-id="33c54-112">Par exemple, un voltmètre est utilisé pour mesurer la tension, un thermomètre est utilisé pour mesurer la température et une balance est utilisée pour mesurer le poids.</span><span class="sxs-lookup"><span data-stu-id="33c54-112">For example, a voltage meter is used to measure voltage, a thermometer is used to measure temperature, and a scale is used to measure weight.</span></span> <span data-ttu-id="33c54-113">Vous pouvez configurer chacun de ces appareils en tant qu'instrument de test et indiquer l'unité de mesure dans laquelle les résultats du test doivent être enregistrés.</span><span class="sxs-lookup"><span data-stu-id="33c54-113">You can configure each of these devices as a test instrument and indicate the unit of measure that the test results should be recorded in.</span></span> <span data-ttu-id="33c54-114">Par exemple, les résultats du voltmètre sont enregistrés en volts, les résultats du thermomètre sont enregistrés en degrés Fahrenheit ou Celsius et les résultats de l'échelle sont enregistrés en livres ou en kilogrammes.</span><span class="sxs-lookup"><span data-stu-id="33c54-114">For example, results from the voltage meter are recorded in volts, results from the thermometer are recorded in degrees Fahrenheit or degrees Celsius, and results from the scale are recorded in pounds or kilograms.</span></span>

## <a name="create-a-test-instrument"></a><span data-ttu-id="33c54-115">Créer un instrument de test</span><span class="sxs-lookup"><span data-stu-id="33c54-115">Create a test instrument</span></span>

1. <span data-ttu-id="33c54-116">Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \>Instruments de test**.</span><span class="sxs-lookup"><span data-stu-id="33c54-116">Go to **Inventory management \> Setup \> Quality control \> Test instruments**.</span></span>
1. <span data-ttu-id="33c54-117">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="33c54-117">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="33c54-118">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="33c54-118">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="33c54-119">**Instrument de test** - Saisissez un identifiant ou un nom unique pour l'instrument de test.</span><span class="sxs-lookup"><span data-stu-id="33c54-119">**Test instrument** – Enter a unique ID or name for the test instrument.</span></span>
    - <span data-ttu-id="33c54-120">**Description** - Entrez une description détaillée de l'instrument de test.</span><span class="sxs-lookup"><span data-stu-id="33c54-120">**Description** – Enter a detailed description of the test instrument.</span></span>
    - <span data-ttu-id="33c54-121">**Unité** - Sélectionnez l'unité dans laquelle l'instrument mesure les résultats.</span><span class="sxs-lookup"><span data-stu-id="33c54-121">**Unit** – Select the unit that the instrument measures results in.</span></span> <span data-ttu-id="33c54-122">Le champ **Précision** est automatiquement défini en fonction de l'unité que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="33c54-122">The **Precision** field is automatically set, based on the unit that you select.</span></span>

1. <span data-ttu-id="33c54-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="33c54-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33c54-124">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="33c54-124">Additional resources</span></span>

- [<span data-ttu-id="33c54-125">Test de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="33c54-125">Quality management test</span></span>](quality-tests.md)
- [<span data-ttu-id="33c54-126">Groupes de tests de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="33c54-126">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
