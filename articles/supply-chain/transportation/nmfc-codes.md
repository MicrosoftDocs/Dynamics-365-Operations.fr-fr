---
title: Codes National Motor Freight Classification (NMFC)
description: Cette rubrique décrit comment utiliser les codes NMFC (National Motor Freight Classification) dans Microsoft Dynamics 365 Supply Chain Management
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 8e6aac6b3a8b730b6adc5c3d4410b98c3e8d5090eac866c337ed1d03409ba765
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731149"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a>Codes National Motor Freight Classification (NMFC)

[!include [banner](../includes/banner.md)]

Les codes NMFC (National Motor Freight Classification) vous aident à classer les articles qui peuvent être expédiés. Le code NMFC est une désignation utilisée pour regrouper les produits. Il permet aux entreprises de transport d'évaluer les marchandises à expédier en classant les articles en fonction de considérations telles que la capacité du camion, les problèmes de chargement, les problèmes de manutention et la périssabilité. Les produits sont regroupés dans l'une des 18 classes de fret en utilisant une plage de nombres de 50 à 500. La classe dans laquelle une marchandise est regroupée est basée sur une évaluation de quatre caractéristiques de transport : densité, capacité de rangement, manutention et responsabilité. Ces caractéristiques désignent ensemble la transportabilité de la marchandise.

Un code NMFC est associé à chaque article d'expédition à chargement partiel (LTL). Par exemple, un ordinateur portable peut se voir attribuer un NMFC classé à 2,5, tandis que des fils électriques peuvent se voir attribuer un NMFC classé à 65.

Cette fonctionnalité peut aider les collaborateurs à utiliser les codes NMFC pour classer les articles d'expédition LTL. Voici quelques exemples :

- Si votre entreprise inclut une description du fret sur la feuille de chargement (BOL), le transporteur aura une idée de sa composition. Le fret est une classification importante, car de nombreuses entreprises de transport fondent leur modèle commercial global sur les types de fret qu'elles expédient.
- Cette classification peut être essentielle pour votre entreprise car elle sert à déterminer le coût d'une charge donnée.
- Votre entreprise peut identifier la rentabilité d'une entreprise de logistique et de transport LTL.

Cette rubrique décrit comment utiliser des codes NMFC dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir créer des codes NMFC, vous devez configurer toutes les classes de fret LTL qui doivent y être mappées. Les classes de fret LTL représentent des catégories d'articles, tandis que les codes NMFC sont liés à des produits spécifiques dans chacune des 18 classes de fret. Pour plus d'informations sur l'utilisation des classes LTL, consultez [Classes de chargement partiel d'un camion (Less than truckload, LTL)](ltl-class.md).

## <a name="create-an-nmfc-code"></a>Créer un code NMFC

Pour créer un code NMFC, procédez comme suit :

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Codes NMFC**.
    - Accédez à **Gestion du transport \> Paramétrage \> Normes de transport \> Codes NMFC**.

1. Sélectionnez **Nouveau** pour créer un code NMFC. Définissez ensuite les champs suivants :

    - **Code NMFC** – Entrez le code NMFC du type de marchandise.
    - **Nom** – Entrez un nom pour le code NMFC.
    - **Classe LTL** - Sélectionnez la classe LTL associée au code NMFC.
    - **Unité de manutention BOL** - Définissez le type de manutention par défaut pour l'expédition.

## <a name="example-set-up-nmfc-codes"></a>Exemple : Paramétrer les codes NMFC

L'exemple suivant montre comment configurer deux codes NMFC différents que vous pouvez utiliser avec différents types de produits.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Codes NMFC**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Code NMFC :** *92,5*
    - **Nom :** *Ordinateurs*
    - **Classe LTL :** *92,5*
    - **Unité de manutention BOL :** *Unité*

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Code NMFC :** *125*
    - **Nom :** *Téléphones*
    - **Classe LTL :** *125*
    - **Unité de manutention BOL :** *Unité*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Classes de chargement partiel d'un camion (Less than truckload, LTL)](ltl-class.md)
- [Créer une feuille de chargement](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
