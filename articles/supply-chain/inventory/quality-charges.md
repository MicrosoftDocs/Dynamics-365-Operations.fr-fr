---
title: Frais pour les opérations de non-conformité
description: Cette rubrique décrit comment créer des frais de qualité pouvant être utilisés avec des opérations de non-conformité.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c062fecea23017e603c55d11de542942576dba74e0dda07452fd7a91109fe78
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771489"
---
# <a name="charges-for-nonconformance-operations"></a>Frais pour les opérations de non-conformité

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer des frais de qualité pouvant être utilisés avec des opérations de non-conformité.

La page **Frais de qualité** permet de définir les types de frais qui peuvent être ajoutés aux opérations de non-conformité. Les frais vous permettent de suivre les détails à propos des frais ou des charges que vous devez à un client pour des produits non conformes, ou qu'un fournisseur vous doit pour des produits non conformes que vous avez reçus. Vous pouvez également utiliser des frais pour suivre les coûts nécessaires pour les fournisseurs ou les services externes pour effectuer une opération.

## <a name="examples-of-quality-charges"></a>Exemples de frais de qualité

Vous travaillez pour une entreprise de fabrication. Votre entreprise a des contrats avec plusieurs fournisseurs. Ces contrats décrivent des normes pour l'expédition à temps, les dommages et la qualité des produits pour les articles. De même, plusieurs de vos clients ont des accords avec votre entreprise concernant les retours, les dommages et la qualité des produits.

Une grille tarifaire est définie pour chaque circonstance et spécifiée dans le contrat. Vous pouvez configurer des frais de qualité pour décrire les différents types de frais, tels que *Dommages*, *Retard de livraison* et *Qualité*. Ensuite, lorsque vous créez une non-conformité, vous devez ajouter une ou plusieurs opérations. Pour chaque opération, sélectionnez des **Frais** pour définir les détails.

## <a name="create-a-quality-charge"></a>Créer des frais de qualité

1. Accédez à **Gestion des stocks \> Paramétrage \> Gestion de la qualité \> Frais de qualité**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Code de frais** - Entrez un identifiant ou un nom unique pour les frais de qualité.
    - **Description** - Entrez une description détaillée des frais de qualité.

1. Fermez la page.

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a>Ajouter une charge de qualité à une opération suite à une non-conformité

Pour plus de détails sur la façon d'ajouter des opérations à une non-conformité et de leur appliquer des frais, voir [Opérations pour les non-conformités](quality-operations.md).

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la gestion de la qualité](quality-management-processes.md)
- [Activer la gestion de la qualité et de la non-conformité](enable-quality-management.md)
- [Collaborateurs chargés d'approuver les non-conformités](quality-responsible-workers.md)
- [Zones de contrôle pour les non-conformités](quality-quarantine-zones.md)
- [Types de diagnostic pour les non-conformités](quality-diagnostic-types.md)
- [Frais de qualité pour les non-conformités](quality-charges.md)
- [Opérations pour les non-conformités](quality-operations.md)
- [Gestion de la qualité pour les processus d'entrepôt](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
