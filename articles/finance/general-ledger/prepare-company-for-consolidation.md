---
title: Préparer une entité juridique pour le processus de consolidation
description: Lors d'une consolidation, vous devez regrouper les transactions de plusieurs ensembles de comptes d'entités juridiques dans un seul ensemble. Cette rubrique explique comment préparer une entité juridique pour une consolidation.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: f6fce69724945448f961769dd383d1047a5d13c4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990300"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a>Préparer une entité juridique pour le processus de consolidation

[!include [banner](../includes/banner.md)]

Lors d'une consolidation, vous devez regrouper les transactions de plusieurs ensembles de comptes d'entités juridiques dans un seul ensemble. Cette rubrique explique comment préparer une entité juridique pour une consolidation.

> [!NOTE]
> Nous vous recommandons d'utiliser Management Reporter pour Microsoft Dynamics 365 Finance pour combiner les résultats financiers de plusieurs entités juridiques dans un format consolidé. Management Reporter vous permet de créer des rapports financiers consolidés pour toutes les entités juridiques, d'utiliser Excel pour importer des données de consolidation à partir d'autres sources et de convertir des montants dans n'importe quelles devises de déclaration sans avoir à exécuter le processus de consolidation dans Dynamics 365 Finance.

Vous pouvez imprimer des états, tels que des tableaux d'analyse, à partir de l'entité juridique consolidée. Toutefois, vous ne pouvez pas utiliser l'entité juridique consolidée pour les transactions quotidiennes.

Vous pouvez consolider les données des entités juridiques qui utilisent des bases de données autres que l'entité juridique consolidée. Ce processus de consolidation est appelé *consolidation d'importation*. Sinon, les entités juridiques peuvent utiliser la même base de données que l'entité juridique consolidée. Ce processus de consolidation est appelé *consolidation en ligne*.

L'entité juridique consolidée recueille les résultats et les soldes des filiales. Pour préparer une entité juridique consolidée pour une consolidation, procédez comme suit :

1. Accédez à **Comptabilité \> Paramétrage \> Organisation \> Entités juridiques**.
2. Cliquez sur **Nouveau** pour créer une entité juridique qui sera l'entité juridique consolidée.
3. Activez la case à cocher **Utiliser pour le processus de consolidation financière**, puis entrez les informations sur l'entité juridique consolidée. Vous devez entrer ces informations exactement comme vous souhaitez les voir apparaître dans les tableaux d'analyse pour l'entité juridique consolidée.
4. Fermez la page.
5. Sélectionnez l'entité juridique consolidée dans le champ dans le coin supérieur droit de la page, puis sélectionnez **OK**.
6. Accédez à **Comptabilité \> Paramétrage \> Registre**.
7. Sélectionnez le plan comptable, le calendrier fiscal, la monnaie de compte, une devise de déclaration facultative et le type de taux de change par défaut pour l'entité juridique consolidée. 
8. Accédez à **Comptabilité \> Paramétrage \> Devise \> Taux de change des devises**.
9. Paramétrez les taux de change de la devise dans les périodes adéquates pour les devises des entités juridiques filiales.
10. Fermez la page.
11. Si l'entité juridique consolidée a des filiales qui utilisent des devises étrangères, procédez comme suit :

    1. Accédez à **Comptabilité \> Paramétrage \> Validation \> Comptes pour transactions automatiques**.
    2. Dans le champ **Type de validation**, sélectionnez un compte approprié :

        - Si l'entité juridique a des filiales étrangères qui sont dépendantes d'un point de vue financier ou fonctionnel de l'entité juridique parente, sélectionnez un compte approprié pour le type de validation **Compte de pertes et profits pour les différences de consolidation**.
        - Si vous consolidez une filiale qui est indépendante d'un point de vue financier et fonctionnel de l'entité juridique parente, ou une entité juridique qui contient les résultats de plusieurs filiales qui sont dépendantes d'un point de vue financier et fonctionnel de l'entité juridique parente, et si vous utilisez des méthodes de conversion pour consolider les données, sélectionnez un compte approprié pour le type de validation **Compte de bilan pour les différences de consolidation**.

    3. Dans le champ **Compte principal**, sélectionnez les comptes principaux à utiliser pour les ajustements de la réévaluation des comptes en devises.
    4. Fermez la page.

    Si vous créez l'entité juridique consolidée tôt dans une période, vous pouvez réévaluer les montants en devise étrangère à mesure que les taux de change changent au cours de la période de consolidation.

L'entité juridique consolidée est à présent paramétrée pour la tâche périodique **Consolidation**. Vous pouvez soit effectuer une consolidation d'importation ou une consolidation en ligne.

- Pour effectuer une consolidation d'importation, accédez à **Comptabilité \> Périodique \> Consolider \> Consolider \[Importer depuis\]**.
- Pour effectuer une consolidation en ligne, accédez à **Comptabilité \> Périodique \> Consolider \> Consolider \[En ligne\]**.

> [!NOTE]
> Avant de traiter la consolidation, vous devez préparer les entités juridiques filiales à cette fin. Pour plus d'informations, voir [Paramétrer une entité juridique filiale pour la consolidation](set-up-subsidiary-company-for-consolidation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]