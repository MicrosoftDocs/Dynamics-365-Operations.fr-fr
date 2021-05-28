---
title: Tests de gestion de la qualité
description: Cette rubrique décrit comment créer des tests pour les utiliser avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 95f759d051a520b577cb1cf3d595ce64e0dc4668
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021682"
---
# <a name="quality-management-tests"></a>Tests de gestion de la qualité

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer des tests pour les utiliser avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.

La page **Tests** permet de définir et d’afficher les tests individuels qui déterminent si vos produits correspondent aux spécifications de qualité. Vous pouvez affecter un ou plusieurs tests à un groupe de tests. Dans ce cas, vous pouvez également spécifier des informations spécifiques aux tests, telles que les valeurs de mesures acceptables. Des valeurs de mesure sont utilisées pour les tests quantitatifs. Pour les tests qualitatifs, des variables de test sont utilisées.

- Pour les tests quantitatifs, le champ **Type** est défini sur *Fraction* ou *Entier*. Une unité de mesure est également spécifiée. Les spécifications de qualité et les résultats des tests peuvent être exprimés sous forme de nombres.
- Pour les tests qualitatifs, le champ **Type** de la page Tests est défini sur *Option*. Les tests qualitatifs exigent des informations supplémentaires sur la variable de test mesurée et la liste de ses options. Les spécifications de qualité et les résultats des tests peuvent être exprimés sous forme de résultat.

Vous pouvez affecter un instrument de test à un test si vous le souhaitez. Cependant, les instruments de test ne sont pas nécessaires pour créer et utiliser des tests avec des ordres de qualité. Pour plus d'informations, consultez [Instruments de test de gestion de la qualité](quality-test-instruments.md).

Vous pouvez également spécifier une unité pour un test, pour indiquer l'unité de mesure dans laquelle les résultats du test sont enregistrés. Par exemple, un test de température peut inclure une unité de degrés Fahrenheit ou Celsius.

## <a name="example-of-a-test"></a>Exemple de test

Une société de fabrication réalise deux tests sur du matériel acheté : un test quantitatif concernant la qualité du matériel et un test qualitatif concernant la solidité de l’emballage. Elle spécifie des informations supplémentaires concernant le test qualitatif afin de définir la variable de test (par exemple, solidité de l’emballage) et ses résultats. Elle utilise la page **Groupes de test** pour affecter les deux tests à un groupe de test et spécifier les informations spécifiques aux tests. Le groupe de tests est affecté à un ordre de qualité, de sorte que la société puisse générer un état à partir des résultats des deux tests.

## <a name="create-a-test"></a>Créer un test

Pour créer un test, procédez comme suit :

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Tests**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Test** - Saisissez un identifiant ou un nom unique pour le test.
    - **Description** - Entrez une description détaillée du test.
    - **Type** - Sélectionnez le type de résultats produit par le test. Pour les tests quantitatifs, sélectionnez *Fraction* ou *Entier*. Pour les tests qualitatifs, sélectionnez *Option*.
    - **Instrument de test** – Sélectionnez un [instrument de test](quality-test-instruments.md) à utiliser pour le test.
    - **Unité** - Si vous avez sélectionné *Fraction* ou alors *Entier* dans le champ **Type** (c'est-à-dire, si le test est un test quantitatif), sélectionnez l'unité de mesure dans laquelle les résultats du test doivent être enregistrés.

1. Fermez la page.

> [!NOTE]
> Après avoir enregistré un test, vous ne pouvez plus modifier le champ **Type** dans la grille. Si vous devez changer le type de résultats de test qui seront enregistrés pour un test, sélectionnez **Modifier le type de test de qualité** dans le volet Actions. Dans la boîte de dialogue **Modifier le type de test de qualité**, définissez le champ **Nouveau type** du type souhaité, puis cliquez sur **OK** pour fermer la boîte de dialogue.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Instruments de test de gestion de la qualité](quality-test-instruments.md)
- [Groupes de tests de gestion de la qualité](quality-test-groups.md)
- [Variables de test de gestion de la qualité](quality-test-variables.md)
- [Associations de qualité](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
