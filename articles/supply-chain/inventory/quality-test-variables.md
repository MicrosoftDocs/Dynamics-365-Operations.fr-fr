---
title: Variables de test de gestion de la qualité
description: Cette rubrique décrit comment créer des variables de test, afin que plusieurs tests qualitatifs puissent être utilisés avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
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
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4495c3d3f8df9f07ec079d8e497a17979abbe3ee
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575870"
---
# <a name="quality-management-test-variables"></a>Variables de test de gestion de la qualité

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer des variables de test, afin que plusieurs tests qualitatifs puissent être utilisés avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.

Vous devez définir une variable de test et ses résultats éventuels pour chaque test qualitatif défini sur la page **Tests**. (Pour les tests qualitatifs, le champ **Type** de la page **Tests** est défini sur *Option*.)

La page **Variables de test** permet de paramétrer, de modifier et d’afficher les résultats possibles pour une variable de test associée à un test qualitatif. Pour chaque résultat, vous devez attribuer un statut de *Réussite* ou d'*Échec* pour indiquer si le test a réussi ou échoué lorsque ce résultat est sélectionné comme résultat de test. La page **Groupes de tests** permet d'affecter une variable de test et un résultat par défaut à un test qualificatif spécifique.

Pour chaque variable de test, nous vous recommandons de définir au moins deux résultats : un dont le statut de résultat est *Réussite* et un qui a un statut de résultat *Échec*. Il n'y a pas de limite au nombre total de variables ou de résultats qui peuvent être définis. De plus, plusieurs tests peuvent utiliser les mêmes variables de test pour enregistrer les résultats.

## <a name="examples-of-test-variables"></a>Exemples de variables de test

### <a name="example-1"></a>Exemple 1

Une entreprise de fabrication effectue deux tests sur des produits manufacturés. Dans un test, le niveau de pH est associé à une bande de couleur. Les niveaux de pH acceptables sont dans des couleurs plus claires et les niveaux de pH inacceptables sont dans des couleurs plus foncées. Dans un autre test, plusieurs inspections visuelles sont effectuées et les responsables qualité utilisent leur jugement pour déterminer si l'article réussit ou échoue à l'inspection visuelle.

### <a name="example-2"></a>Exemple 2

Une société de fabrication de biscuits utilise un test d’inspection pour le produit fini. Ce test d’inspection comporte plusieurs variables. L’une des variables est le goût et les résultats possibles pour cette variable sont bon et mauvais. Une deuxième variable est la couleur et les résultats possibles sont trop foncé, trop clair et correct.

## <a name="create-a-test-variable"></a>Créer une variable de test

Pour créer une variable de test, procédez comme suit :

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Variables de test**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Variable** - Entrez un ID ou un nom unique pour la variable.
    - **Description** - Entrez une description détaillée de la variable.

1. Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez **Résultats** dans le volet Actions.
1. Sur la page **Résultats de la variable de test**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Résultat** - Entrez un ID ou un nom unique pour le résultat.
    - **Description** - Entrez une description détaillée du résultat.
    - **Statut du résultat** – Sélectionnez *Réussite* ou *Échec* pour indiquer si le test a réussi ou échoué lorsque ce résultat est sélectionné comme résultat de test.

1. Répétez l'étape précédente pour chaque résultat supplémentaire. Assurez-vous qu'au moins un résultat a un statut de résultat *Réussite* et au moins un a un statut de résultat *Échec*.
1. Fermez les pages.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Instruments de test de gestion de la qualité](quality-test-instruments.md)
- [Tests de gestion de la qualité](quality-tests.md)
- [Groupes de tests de gestion de la qualité](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
