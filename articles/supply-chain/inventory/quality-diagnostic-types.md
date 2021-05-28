---
title: Types de diagnostic pour les non-conformités
description: Cette rubrique décrit comment utiliser et créer des types de diagnostic pouvant être utilisés avec des non-conformités.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7a5c593f1d9e8f7a77f693f6e652e9355a985fb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022274"
---
# <a name="diagnostic-types-for-nonconformances"></a>Types de diagnostic pour les non-conformités

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment utiliser et créer des types de diagnostic pouvant être utilisés avec des non-conformités.

La page **Types de diagnostic** permet de définir une classification des actions de diagnostic. Ensuite, lorsque vous créez une correction pour une non-conformité, vous devez sélectionner un diagnostic. Une correction spécifie le type d’action de diagnostic à prendre pour une non-conformité approuvée, ainsi que la personne qui doit exécuter cette action. Elle spécifie également la date de fin demandée et la date de fin prévue.

## <a name="examples-of-diagnostic-types"></a>Exemples de types de diagnostic

Vous travaillez pour une entreprise de fabrication et plusieurs articles ont échoué aux tests de qualité. Ces articles sont placés dans une zone de quarantaine et marqués comme produits non conformes. Un enregistrement de non-conformité est créé dans Microsoft Dynamics 365 Supply Chain Management pour suivre les détails grâce à la résolution des problèmes.

Dans ce cas, les problèmes de qualité se produisent parce que les roulements de la machine qui emballe les articles se sont détériorés et surchauffent. Pour résoudre ce problème il faut remplacer les pièces de la machine.

Lorsque vous configurez les types de diagnostic, vous pouvez créer plusieurs enregistrements, chacun représentant un type de problème différent que la machine peut rencontrer. Vous pouvez également créer un type de diagnostic générique qui représente la réparation de la machine.

## <a name="create-a-diagnostic-type"></a>Créer un type de diagnostic

1. Accédez à **Gestion des stocks \> Paramétrage \> Gestion de la qualité \> Types de diagnostics**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Diagnostic** – Entrez un identificateur ou un nom unique pour le type de diagnostic.
    - **Description** - Entrez une description détaillée du type de diagnostic.

1. Fermez la page.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la gestion de la qualité](quality-management-processes.md)
- [Activer la gestion de la qualité et de la non-conformité](enable-quality-management.md)
- [Collaborateurs chargés d'approuver les non-conformités](quality-responsible-workers.md)
- [Zones de contrôle pour les non-conformités](quality-quarantine-zones.md)
- [Types de problème pour les non-conformités](quality-problem-types.md)
- [Frais de qualité pour les non-conformités](quality-charges.md)
- [Opérations pour les non-conformités](quality-operations.md)
- [Gestion de la qualité pour les processus d'entrepôt](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
