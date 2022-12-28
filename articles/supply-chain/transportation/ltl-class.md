---
title: Classes de chargement partiel d’un camion (Less than truckload, LTL)
description: Cet article explique ce que sont les classes de chargement partiel d’un camion (Less than truckload, LTL) et explique comment les configurer dans Microsoft Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9c1c7233b637b84ec901d7f83ae00f8a04895edb
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838416"
---
# <a name="less-than-truckload-ltl-classes"></a>Classes de chargement partiel d’un camion (Less than truckload, LTL)

[!include [banner](../includes/banner.md)]

Une classe de chargement partiel d’un camion (Less than truckload, LTL) est une classe d’expédition de fret utilisée pour classer les articles pouvant être expédiés. En règle générale, chaque type de produit ou de marchandise a un code NMFC (National Motor Freight Classification) qui correspond à un numéro de classe de fret spécifique pour les envois LTL. Les classes de fret LTL représentent des catégories d’articles, tandis que les codes NMFC sont liés à des produits spécifiques dans chacune des 18 classes de fret.

Cette fonctionnalité vous permet d’utiliser votre système pour effectuer les tâches suivantes :

- Définir les classes de fret LTL utilisées dans votre entreprise.
- Attribuer chaque classe LTL à un code NMFC sur la page **Codes NMFC**. Pour plus d’informations, consultez les codes [National Motor Freight Classification (NMFC)](nmfc-codes.md).
- Attribuer un code NMFC (et donc son code LTL associé) à chaque produit sur la page **Produits**.
- Évaluer avec précision la classe LTL de chaque produit auquel un code NMFC est attribué.
- Déterminer les exigences d’emballage pour chaque classe LTL en vérifiant les normes internationales LTL. De cette façon, vous avez la certitude que vos produits seront bien protégés et expédiés en toute sécurité.
- Obtenir des estimations d’expédition précises, basées sur la classe de fret LTL pour chaque produit.

Cet article explique comment créer des classes LTL dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="create-an-ltl-class"></a>Créer une classe LTL

Pour créer une classe LTL, procédez comme suit :

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Classes LTL**.
    - Accédez à **Gestion du transport \> Paramétrage \> Normes de transport \> Classes LTL**.

2. Dans le volet Actions, sélectionnez **Nouveau** pour créer une classe LTL. Définissez ensuite les champs suivants :

    - **Classe LTL** - Entrez l’identifiant de classe LTL (ID) interne de votre entreprise pour le type de produit. La plupart des entreprises utilisent la norme internationale. Dans ce cas, la valeur de ce champ correspondra à la valeur du champ **Classe**. Cependant, si votre entreprise utilise sa propre norme, entrez un code conforme à cette norme.
    - **Nom** - Entrez un nom descriptif qui vous aidera, ainsi que les autres utilisateurs, à sélectionner la classe LTL correcte pour chaque code NMFC.
    - **Classer** - Entrez l’ID de classe LTL standard international pour le type de produit. Le code que vous entrez ici doit être conforme à la norme officielle.

## <a name="example-set-up-ltl-classes"></a>Exemple : Configurer des classes LTL

L’exemple suivant montre comment configurer deux classes LTL différentes que vous pouvez utiliser avec différents types de produits.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Classes LTL** ou **Gestion du transport \> Paramétrage \> Normes de transport \> Classes LTL**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Classe LTL :** *92,5*
    - **Nom :** *Ordinateurs, moniteurs, réfrigérateurs*
    - **Classe :** *92,5*

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Classe LTL :** *125*
    - **Nom :** *Petits appareils électroménagers*
    - **Classe :** *125*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Codes National Motor Freight Classification (NMFC)](nmfc-codes.md)
- [Créer une feuille de chargement](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
