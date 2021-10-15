---
title: Groupes de qualité d'article
description: Cette rubrique décrit comment utiliser et créer des groupes de qualité d'article pour regrouper logiquement des produits afin qu'ils puissent être affectés à des associations de qualité pour la génération automatique d'ordres de qualité.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f7a4932c561c052bec1eb0094a390e315b9b1bb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580910"
---
# <a name="item-quality-groups"></a>Groupes de qualité d'article

[!include [banner](../includes/banner.md)]

Un groupe de qualité représente des besoins de test communs pour les articles. Cette rubrique décrit comment utiliser et créer des groupes de qualité d'article pour regrouper logiquement des produits afin qu'ils puissent être affectés à des associations de qualité pour la génération automatique d'ordres de qualité.

Pour paramétrer, modifier et afficher les articles affectés à un groupe de qualité ou les groupes de qualité affectés à un article, accédez à **Gestion des stocks \> Paramétrage \> Groupes de qualité**. Une fois que vous avez défini les besoins de test sur la page **Groupes de test**, vous pouvez définir les règles de génération automatique des ordres de qualité. Pour simplifier le processus, vous ne devez pas définir de règles pour des articles individuels. Au lieu de cela, vous pouvez définir des règles pour un groupe de qualité sur la page **Associations de qualité**.

## <a name="example-of-an-item-quality-group"></a>Exemple de groupe de qualité d'article

Une société de fabrication achète diverses matières premières présentant les mêmes besoins de test pour l’inspection à venir. Par conséquent, la société définit un groupe de qualité, puis affecte les numéros d’articles associés aux matières premières à ce groupe. Ensuite, la société achète un nouveau type de matières premières ayant les mêmes besoins de test. Au lieu de paramétrer de nouveaux besoins de test pour les nouvelles matières, la société ajoute le numéro d’article pour la nouvelle matière au groupe de qualité existant.

La même société produit également des articles ayant les mêmes besoins de test de production et expédie les articles dotés des mêmes besoins en tests de pré-expédition. Par conséquent, la société définit deux groupes de qualité supplémentaires, puis affecte les numéros d’articles pertinents à chaque groupe.

## <a name="create-a-quality-group"></a>Créer un groupe de qualité

Pour créer un groupe de qualité, procédez comme suit :

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de qualité**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Groupe qualité** - Saisissez un identifiant ou un nom unique pour le groupe de qualité.
    - **Description** - Entrez une description détaillée du groupe de qualité.

1. Fermez la page.

## <a name="manually-add-items-to-a-quality-group"></a>Ajouter manuellement des articles à un groupe de qualité

Pour ajouter manuellement des éléments à un groupe de qualité, procédez comme suit :

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de qualité**.
1. Sélectionnez le groupe de qualité auquel vous souhaitez ajouter des éléments.
1. Dans le volet Actions, sélectionnez **Articles**.
1. Sur la page **Articles dans les groupes de qualité**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Ensuite, pour la nouvelle ligne, définissez le champ **Numéro d'article** du numéro d'article que vous souhaitez ajouter.
1. Répétez l'étape précédente pour chaque article supplémentaire à ajouter.
1. Fermez les pages.

## <a name="add-multiple-items-to-a-quality-group"></a>Ajouter plusieurs articles à un groupe de qualité

Pour ajouter plusieurs articles à un groupe de qualité, procédez comme suit :

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de qualité**.
1. Créez ou sélectionnez le groupe de qualité auquel vous souhaitez ajouter des éléments.
1. Dans le volet Actions, sélectionnez **Ajouter des articles**.
1. Dans la boîte de dialogue **Recherche**, entrez les critères de filtre pour les éléments que vous souhaitez ajouter. Par exemple, vous pouvez filtrer tous les éléments d'un groupe d'éléments spécifique.
1. Cliquez sur **OK**.
1. Dans la boîte de dialogue **Ajouter des articles**, une grille affiche tous les éléments qui correspondent à votre requête. Examinez les résultats.

    Si des modifications sont nécessaires, sélectionnez **Sélectionner** pour revenir dans la boîte de dialogue **Recherche** et modifiez votre requête.

1. Lorsque les résultats incluent tous les éléments que vous souhaitez ajouter, cliquez sur **OK**.
1. Fermez la page.

## <a name="manually-associate-an-item-with-a-quality-group"></a>Associer manuellement un article à un groupe de qualité

Pour associer manuellement un article à un groupe de qualité, procédez comme suit :

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Groupes de qualité d’article**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Numéro d'article** - Sélectionnez le numéro d'article à ajouter.
    - **Groupe de qualité** - Sélectionnez le groupe de qualité à attribuer à l'article.

1. Répétez l'étape précédente pour chaque combinaison supplémentaire d'un article et d'un groupe de qualité à ajouter.
1. Fermez les pages.

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a>Ajouter manuellement un groupe de qualité à partir de la page Produits lancés

Pour ajouter manuellement un groupe de qualité à partir de la page **Produits lancés**, procédez comme suit :

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez le produit auquel affecter un groupe de qualité.
1. Dans le volet Actions, sous l’onglet **Gérer le stock**, dans le groupe **Qualité**, sélectionnez **Groupes de qualité d’article**.
1. Sur la page **Articles dans les groupes de qualité**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Ensuite, pour la nouvelle ligne, définissez le champ **Groupe qualité** du groupe de qualité que vous souhaitez affecter au produit.
1. Répétez l'étape précédente pour chaque groupe de qualité supplémentaire que vous souhaitez attribuer au produit.
1. Fermez les pages.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Instruments de test de gestion de la qualité](quality-test-instruments.md)
- [Tests de gestion de la qualité](quality-tests.md)
- [Groupes de tests de gestion de la qualité](quality-test-groups.md)
- [Variables de test de gestion de la qualité](quality-test-variables.md)
- [Associations de qualité](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
