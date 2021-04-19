---
title: Paramétrer une entité juridique filiale pour la consolidation
description: Cette rubrique explique comment utiliser des plans de comptes pour les sociétés de consolidation.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 15050310f355ece683b00a00be9552d32aded17b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832848"
---
# <a name="set-up-a-subsidiary-legal-entity-for-consolidation"></a>Paramétrer une entité juridique filiale pour la consolidation

[!include [banner](../includes/banner.md)]

La méthode que vous utilisez pour préparer les comptes des filiales pour la consolidation dépend en partie de la mesure dans laquelle la structure du plan de comptes dans l’entité juridique filiale réfléchit le plan de comptes de l’entité juridique consolidée.

Avant de commencer une consolidation dans le cadre d’une clôture de fin de période, réalisez les activités préparatoires pour la clôture de fin de période, mais ne clôturez pas les comptes des filiales avant que la consolidation ne soit terminée. Pour plus d’informations sur la clôture en fin de période, voir [Clôturer la comptabilité en fin de période](close-general-ledger-at-period-end.md) et [Clôturer l’exercice](tasks/close-fiscal-year.md).

> [!NOTE]
>  Nous vous recommandons d’utiliser Management Reporter pour Microsoft Dynamics 365 Finance pour combiner les résultats financiers de plusieurs entités juridiques dans un format consolidé. Management Reporter vous permet de créer des rapports financiers consolidés pour toutes les entités juridiques, d’utiliser Excel pour importer des données de consolidation à partir d’autres sources et de convertir des montants dans n’importe quelles devises de déclaration sans avoir à exécuter le processus de consolidation dans Dynamics 365 Finance.

## <a name="map-subsidiary-main-accounts-to-consolidated-main-accounts"></a>Mettre en correspondance les comptes principaux des filiales avec les comptes principaux consolidés

Si le plan de comptes dans l’entité juridique filiale ne correspond pas au plan de comptes de l’entité juridique consolidée, vous pouvez mettre en correspondance les comptes principaux de la filiale et ceux de l’entité juridique consolidée.

1. Dans l’*entité juridique filiale*, allez à **Comptabilité \> Paramétrage**\>**Plan comptable \> Plan comptable**.
2. Sélectionnez un plan comptable. Sur le raccourci **Comptes principaux**, sélectionnez un compte principal, puis sélectionnez **Modifier**.
3. Sélectionnez chaque compte principal de filiale qui doit être mis en correspondance avec un compte principal consolidé. Sur le raccourci **Général**, dans le champ **Compte de consolidation**, entrez le compte de l’entité juridique consolidée vers lequel le solde ou les transactions du compte principal de la filiale sélectionnée doivent être transférés. Vous pouvez entrer le même compte principal consolidé pour plusieurs comptes des filiales.

    > [!NOTE]
    > Si les types de compte principal des comptes des filiales qui sont mis en correspondance diffèrent des types de compte principal des comptes de l’entité juridique consolidée, les valeurs des comptes dont le type de compte principal est **Total** sont remplacées lors de la consolidation.

4. Préparez des rapports et des états financiers pour l’entité juridique consolidée basés sur des dimensions financières. Suivez ces étapes pour mettre en correspondance les dimensions financières utilisées dans les comptes des filiales et les dimensions financières de l’entité juridique consolidée :

    1. Dans l’*entité juridique filiale*, allez dans **Comptabilité \> Paramétrage \> Dimensions financières \> Dimensions financières**, sélectionnez une dimension financière, puis **Valeurs de dimensions financières**.
    2. Sélectionnez la valeur de dimension financière à mettre en correspondance avec une autre valeur de dimension financière dans l’entité juridique consolidée.
    3. Dans le raccourci **Général**, dans le champ **Dimension de groupe**, entrez la dimension financière dans l’entité juridique consolidée. Lors de la consolidation, cette dimension financière sera affectée aux transactions et aux soldes qui utilisent la dimension financière sélectionnée dans l’entité juridique filiale. Les dimensions financières entrées ici doivent être utilisées dans l’entité juridique consolidée. Vous pouvez affecter la dimension financière utilisée comme dimension financière du groupe à plusieurs dimensions financières des filiales.

5. Si vous effectuez une consolidation en ligne, procédez comme suit pour vous assurer que les transferts se déroulent comme vous le souhaitez :

    1. Dans l’*entité juridique consolidée*, allez dans **Comptabilité \> Périodique \> Consolider \> Consolider \[ Exporter vers\]** pour ouvrir la page **Consolider \[En ligne\]**.
    2. Sous l’onglet **Critères**, activez la case à cocher **Utiliser le compte de consolidation**.
    3. Sur l’onglet **Dimensions financières**, sélectionnez les dimensions financières appropriées.
    4. Pour chaque dimension financière sélectionnée, entrez un numéro dans le champ **Ordre des segments** pour indiquer l’ordre d’affichage des dimensions.

## <a name="maintain-the-same-chart-of-accounts-in-the-subsidiary-and-consolidated-legal-entities"></a>Conserver le même plan comptable dans la filiale et les entités juridiques consolidées

Les comptes principaux dans l’entité juridique filiale peuvent avoir les mêmes numéros de compte et la même structure de plan de comptes que les comptes principaux dans l’entité juridique consolidée. Dans ce cas, vous ne devez pas mettre en correspondance manuellement les comptes principaux de la filiale et les comptes principaux de l’entité juridique consolidée.

Avant de commencer la consolidation, procédez comme suit.

1. Dans l’*entité juridique consolidée*, allez dans **Comptabilité \> Périodique \> Consolider \> Consolider \[ Exporter vers\]** pour ouvrir la page **Consolider \[En ligne\]**.
2. Activez la case à cocher **Utiliser le compte de consolidation**. Pendant la consolidation, les transactions et les soldes seront automatiquement transférés vers le bon compte.

> [!NOTE]
> Si les comptes ne correspondent pas, la consolidation est suspendue et vous recevez un message.

## <a name="create-a-chart-of-accounts-for-the-consolidated-legal-entity-based-on-an-existing-chart-of-accounts"></a>Créer un plan comptable pour l’entité juridique consolidée, selon un plan de comptes existant

Vous pouvez effectuer la consolidation même si aucun plan de comptes n’a été créé dans l’entité juridique consolidée.

- Si vous avez prévu la structure de compte à utiliser dans l’entité juridique consolidée, vous pouvez mettre en correspondance les comptes des filiales et cette structure.
- Si vous n’effectuez pas de mise en correspondance sur les comptes des filiales, les comptes de l’entité juridique consolidée sont créés automatiquement lorsque les données des filiales sont transférées vers l’entité juridique consolidée. Ces comptes sont basés sur le compte principal. Les données suivantes sont cumulées dans les comptes dans l’entité juridique consolidée qui a le même numéro de compte que les comptes des filiales.

Indépendamment du fait que vous avez mis les comptes en correspondance, désactivez la case à cocher **Utiliser le compte de consolidation** sur la page **Consolider** de l’entité juridique consolidée avant d’exécuter ce type de consolidation.

> [!NOTE]
> Vous pouvez utiliser cette méthode pour créer un plan de comptes dans l’entité juridique consolidée à partir du plan de comptes d’une des entités juridiques filiales. (Pour plus d’informations, consultez [Groupes de comptes de consolidation et comptes de consolidation supplémentaires](../budgeting/consolidation-account-groups-consolidation-accounts.md).) Attribuez ensuite un principe de conversion de consolidation approprié à chaque compte principal consolidé et exécutez la consolidation pour toutes les entités juridiques filiales.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]