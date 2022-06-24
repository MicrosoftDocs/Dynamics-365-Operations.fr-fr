---
title: Types de problème pour les non-conformités
description: Cet article décrit comment créer et utiliser les types de problème pour les non-conformités.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a73e692257c2a27085d60e75e028445811ee778a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857748"
---
# <a name="problem-types-for-nonconformances"></a>Types de problème pour les non-conformités

[!include [banner](../includes/banner.md)]

Cet article décrit comment créer et utiliser les types de problème pour les non-conformités.

La page **Types de problème** permet de définir une classification des problèmes de qualité susceptibles de se produire pour les divers types de non-conformité. Pour chaque type de problème que vous créez, vous devez spécifier les types de non-conformité avec lesquels le type de problème peut être utilisé. Vous pouvez paramétrer les types de non-conformité suivants :

- **Interne** - Les non-conformités de ce type sont liées aux stocks disponibles (par exemple, les ordres de qualité ou les ordres de contrôle).
- **Client** - Les non-conformités de ce type sont liées aux commandes clients.
- **Fournisseur** - Les non-conformités de ce type sont liées aux commandes fournisseur.
- **Demande de service** - Les non-conformités de ce type sont liées aux commandes de service.
- **Production** – Les non-conformités de ce type sont liées aux lots de commande ou aux ordres de fabrication.
- **Production de coproduits** – Les non-conformités de ce type sont liées aux lots de commande pour des coproduits.

Lorsque vous créez un nouveau type de problème, sélectionnez **Types de non-conformité** dans le volet Actions pour créer une liste d'un ou plusieurs types de non-conformité autorisés pour le type de problème. Par exemple, un type de problème en lien avec un code défaut peut s'appliquer à tous les types de non-conformité. Cependant, un type de problème lié aux réclamations des clients peut s'appliquer uniquement aux types de non-conformité **Client** et **Demande de service**.

## <a name="examples-of-problem-types"></a>Exemples de types de problème

Voici quelques exemples de scénarios de types de problème pouvant être utilisés avec les différents types de non-conformité :

- **Client :** Un client a déposé une plainte, un client a effectué un retour ou des spécifications de qualité n'ont pas été respectées.
- **Fournisseur :** Le produit a été endommagé, les spécifications de qualité n'ont pas été respectées ou le mauvais produit a été reçu.
- **Demande de service :** Les spécifications de qualité n'ont pas été respectées, un client a déposé une plainte ou une maintenance de la machine est nécessaire.
- **Production :** Les spécifications de qualité n'ont pas été respectées, un entretien de la machine est nécessaire ou le produit a été endommagé.
- **Production de coproduits :** Les spécifications de qualité n'ont pas été respectées, un entretien de la machine est nécessaire ou le produit a été endommagé.

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a>Créer un type de problème et l'affecter à des types de non-conformité

1. Accédez à **Gestion des stocks \> Paramétrage \> Gestion de la qualité \> Types de problème**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Type de problème** – Entrez un identificateur ou un nom unique pour le type de problème.
    - **Description** - Entrez une description détaillée du type de problème.

1. Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez **Types de non-conformité** dans le volet Actions.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Ensuite, pour la nouvelle ligne, définissez le champ **Type de non-conformité** sur le type de non-conformité que vous souhaitez autoriser pour le type de problème.
1. Répétez l'étape précédente pour chaque type de non-conformité supplémentaire que vous souhaitez autoriser pour le type de problème.
1. Fermez les pages.

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
