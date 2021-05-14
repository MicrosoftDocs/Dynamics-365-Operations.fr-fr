---
title: Zones de contrôle pour les non-conformités
description: Cette rubrique décrit comment créer et utiliser des zones de contrôle pour les non-conformités.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93ca74ec4586fffa3b9156aadab887629283b98a
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956658"
---
# <a name="quarantine-zones-for-nonconformances"></a>Zones de contrôle pour les non-conformités

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer et utiliser des zones de contrôle pour les non-conformités.

La page **Zones de contrôle** permet de définir les zones pouvant être affectées aux non-conformités. Lorsque vous créez une non-conformité, vous pouvez définir les champs **Zone de contrôle** et **Type de contrôle** sur l'onglet **Général** de la page **Non-conformités**. Le champ **Zone de contrôle** indique généralement la zone ou l'emplacement où se trouve l'élément. Le champ **Type de contrôle** définit l'élément comme *Utilisation limitée* ou *Inutilisable*.

Lorsque vous imprimez un rapport de non-conformité ou de corrections pour une non-conformité, vous pouvez afficher la zone de contrôle où se trouve l'élément.

Vous pouvez également imprimer une étiquette de non-conformité pour une non-conformité. Cet état indique la zone de quarantaine affectée et les informations relatives à l’utilisation, afin de fournir des instructions sur la gestion du matériel défectueux. Les zones de contrôle peuvent correspondre à des emplacements de stockage ou à des ressources opérationnelles.

## <a name="examples-of-quarantine-zones"></a>Exemples de zones de contrôle

### <a name="example-1"></a>Exemple 1

Vous travaillez dans une entreprise de fabrication de matériel électronique qui produit et distribue des téléviseurs, des haut-parleurs et des lecteurs multimédias. Dans ce cas, vous pouvez configurer une zone de contrôle pour représenter chaque type de produit.

### <a name="example-2"></a>Exemple 2

Trois bacs et deux racks sont utilisés pour stocker les articles non conformes. Dans ce cas, vous pouvez configurer cinq zones de contrôle, une pour chaque bac et chaque rack.

## <a name="create-a-quarantine-zone"></a>Créer une zone de contrôle

1. Accédez à **Gestion des stocks \> Paramétrage \> Gestion de la qualité \> Zones de contrôle**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Zone de contrôle** - Entrez un ID ou un nom unique pour la zone de contrôle.
    - **Description** - Entrez une description détaillée de la zone de contrôle.

1. Fermez la page.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la gestion de la qualité](quality-management-processes.md)
- [Activer la gestion de la qualité et de la non-conformité](enable-quality-management.md)
- [Collaborateurs chargés d'approuver les non-conformités](quality-responsible-workers.md)
- [Types de problème pour les non-conformités](quality-quarantine-zones.md)
- [Types de diagnostic pour les non-conformités](quality-diagnostic-types.md)
- [Frais de qualité pour les non-conformités](quality-charges.md)
- [Opérations pour les non-conformités](quality-operations.md)
- [Gestion de la qualité pour les processus d'entrepôt](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
