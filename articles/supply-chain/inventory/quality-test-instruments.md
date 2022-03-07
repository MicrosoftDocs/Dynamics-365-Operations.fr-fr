---
title: Instruments de test de gestion de la qualité
description: Cette rubrique décrit comment créer des instruments de test, afin que plusieurs tests puissent être utilisés avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: dc09021f89a9064a3140a726fca74e3eceab13da
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956655"
---
# <a name="quality-management-test-instruments"></a>Instruments de test de gestion de la qualité

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer des instruments de test, afin que plusieurs tests puissent être utilisés avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.

La page **Instruments de test** permet de définir et d'afficher les détails sur les appareils utilisés pour effectuer des tests sur les ordres de qualité. Les instruments de test sont facultatifs. Cependant, ils peuvent aider les responsables qualité à savoir quel appareil ou outil ils doivent utiliser pour effectuer un test spécifique.

## <a name="test-instrument-example"></a>Exemple d'instrument de test

Vous effectuez divers tests sur des composants électriques. Certains tests concernent la tension de sortie des composants, un test concerne leur température et un test leur poids. Différents outils, dispositifs ou équipements sont utilisés pour effectuer chaque test. Par exemple, un voltmètre est utilisé pour mesurer la tension, un thermomètre est utilisé pour mesurer la température et une balance est utilisée pour mesurer le poids. Vous pouvez configurer chacun de ces appareils en tant qu'instrument de test et indiquer l'unité de mesure dans laquelle les résultats du test doivent être enregistrés. Par exemple, les résultats du voltmètre sont enregistrés en volts, les résultats du thermomètre sont enregistrés en degrés Fahrenheit ou Celsius et les résultats de l'échelle sont enregistrés en livres ou en kilogrammes.

## <a name="create-a-test-instrument"></a>Créer un instrument de test

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \>Instruments de test**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Instrument de test** - Saisissez un identifiant ou un nom unique pour l'instrument de test.
    - **Description** - Entrez une description détaillée de l'instrument de test.
    - **Unité** - Sélectionnez l'unité dans laquelle l'instrument mesure les résultats. Le champ **Précision** est automatiquement défini en fonction de l'unité que vous sélectionnez.

1. Fermez la page.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Test de gestion de la qualité](quality-tests.md)
- [Groupes de tests de gestion de la qualité](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
