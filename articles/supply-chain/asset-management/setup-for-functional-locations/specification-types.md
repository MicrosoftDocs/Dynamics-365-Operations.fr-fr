---
title: Types d'attribut de maintenance
description: Cette rubrique explique comment créer des types d'attribut dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 469bcb16bb3099ffabdccfb026f0414de0213aaa
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428186"
---
# <a name="maintenance-attribute-types"></a>Types d'attribut de maintenance

[!include [banner](../../includes/banner.md)]

 

Cette rubrique explique comment créer des types d'attribut dans le module Gestion des actifs. Les attributs permettent de décrire les propriétés de différents éléments. Vous pouvez paramétrer des attributs sur les éléments suivants :

- [Types d'emplacement fonctionnels](../setup-for-functional-locations/functional-location-types.md)
- [Créer des emplacement fonctionnels](../functional-locations/create-functional-locations.md)
- [Types d'actif](../setup-for-objects/object-types.md)
- Actifs

Les attributs que vous pouvez paramétrer varient selon l'élément. Par exemple, pour un poste technique, vous pouvez paramétrer des attributs pour la configuration et la taille physique de l'emplacement. Pour un type d'actif ou un actif, vous pouvez paramétrer des attributs pour le volume du moteur, la consommation électrique et la capacité de charge maximale sous différentes conditions.

## <a name="create-attribute-types"></a>Création de types d'attributs

Vous pouvez créer vos propres types d'attribut. En outre, vous pouvez transférer des dimensions de produit vers la page **Types d'attributs**.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Types d'attributs**.
2. La première fois que vous paramétrez des types d'attribut, sélectionnez **Créer des dimensions de produit** pour transférer automatiquement des dimensions de produit standard.
3. Sélectionnez **Nouveau** pour créer un type d'attribut.
4. Dans le champ **Type d'attribut**, entrez un nom pour le type d'attribut.
5. Entrez une description dans le champ **Description**.
6. Dans le champ **Unité**, sélectionnez l'unité appropriée de l'attribut, au besoin.
7. Dans le champ **Type de données**, sélectionnez un type de données pour l'unité.
8. Si vous avez sélectionné **Chaîne** comme type de données, procédez comme suit pour créer des valeurs pour le type d'attribut :

    1. Sélectionnez le type d'attribut, puis sélectionnez **Valeurs**.
    2. Dans le champ **Valeurs d'attribut**, sélectionnez **Nouveau**.
    3. Dans le champ **Type d'attribut**, sélectionnez un type d'attribut (dimension).
    4. Dans le champ **Valeur**, entrez une valeur associée.
    5. Entrez une description dans le champ **Description**.
    6. Enregistrez l'enregistrement.
    7. Revenez à la page **Types d'attributs**.

9. Enregistrez l'enregistrement.

    Le champ **Types de poste technique** affiche le nombre de postes techniques qui utilisent le type d'attribut. Le champ **Types d'actif** affiche le nombre de types d'actif qui l'utilisent.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]