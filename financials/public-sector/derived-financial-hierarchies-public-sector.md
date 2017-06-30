---
title: "Hiérarchies financières dérivées dans le secteur public"
description: "Cet article décrit la fonctionnalité des hiérarchies financières dérivées disponible pour le secteur public."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResCategory, EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyRole, LedgerDerivedFinHierarchies, LedgerDerivedFinHierarchyFilterResults, LedgerDerivedFinHierarchyLegalEntities
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 20911
ms.assetid: a1b30d2a-a370-402a-b3bd-d562adca55f0
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 062e8225792dd789b73518cd222df4f499281ec1
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="derived-financial-hierarchies-in-the-public-sector"></a>Hiérarchies financières dérivées dans le secteur public

[!include[banner](../includes/banner.md)]


Cet article décrit la fonctionnalité des hiérarchies financières dérivées disponible pour le secteur public. 

Pour répondre aux exigences des principales classifications comptables applicables au niveau gouvernemental, les organisations du secteur public peuvent utiliser des hiérarchies financières dérivées afin de recueillir et d'analyser des données de transaction validées pour des numéros de compte principal, des numéros de compte complet et des valeurs de dimension financière spécifiques. 

En général, des hiérarchies de catégories sont définies dans le but de classer les transactions et de générer des états et analyses sur la base des dimensions financières de la structure de compte au moment de la validation. Toutefois, en utilisant des hiérarchies de catégories dotées du type Hiérarchie financière dérivée, vous pouvez créer des règles de filtre qui créent des catégories et valeurs de dimension financière qui n'appartiennent pas au numéro de compte. Les catégories et valeurs de dimension financière définies dans les règles de filtre sont dérivées des valeurs de la dimension de numéro de compte qui sont utilisées dans les transactions validées.

Les hiérarchies financières dérivées vous procurent une approche plus flexible du regroupement des transactions en vue d'analyses appropriées. Elles vous permettent de classer les transactions sans avoir à agrandir la structure de compte afin d'y inclure les catégories et dimensions supplémentaires dont vous souhaiter effectuer le suivi.

## <a name="example"></a>Exemple
Une organisation a un programme de bien-être des employés et un programme de formation des employés. Ces programmes ne sont pas associés aux dimensions financières. Pour recueillir les numéros de compte utilisés dans les transactions validées pour ces programmes, vous pouvez procéder comme suit :

-   **Paramétrer les hiérarchies de catégories et les hiérarchies financières dérivées :** créez une hiérarchie de catégories appelée « Programme pour les employés » avec un nœud parent nommé « Programmes » et deux nœuds enfants nommés « Bien-être des employés » et « Formation des employés ». Affectez le type de catégorie **Hiérarchie financière dérivée** à la hiérarchie de catégories « Programme pour les employés ». Associez la hiérarchie financière dérivée « Programmes pour les employés » à l'entité juridique.
-   **Paramétrer des règles de filtre :** Utilisez la page **Hiérarchies financières dérivées** pour créer des règles de filtre pour les valeurs des comptes principaux et des dimensions financières associées aux nœuds « Bien-être des employés » et « Formation des employés » dans la hiérarchie financière dérivée « Programmes pour les employés ». **Conseil :** pour entrer plusieurs valeurs de dimension dans un filtre, utilisez une virgule sans espaces comme séparateur. Par exemple, entrez 100,110 ou Avantages,Assurance.
-   **Analyser des données de transaction validée :** Dans les résultats de filtre, affichez les numéros de compte et leurs détails de compte et de dimension financière.

 





