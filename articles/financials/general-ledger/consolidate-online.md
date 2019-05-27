---
title: Consolidations financières en ligne
description: Cette rubrique décrit les consolidations financières en ligne dans le module Comptabilité.
author: aprilolson
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: fd29dc5f932c9cd274a42923e1ff659dd5d8e9d6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567304"
---
# <a name="consolidate-online"></a>Consolidation en ligne

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les consolidations financières en ligne dans le module Comptabilité. Avant de lire cette rubrique, veillez à lire la rubrique [Consolidations financières et conversion de devises](financial-consolidations-currency-translation.md).

Après avoir terminé votre paramétrage, entrez les détails de la consolidation dans la page **Consolidation [En ligne]**. Lorsque vous avez terminé, vous pouvez cliquer sur **OK** ou **Traitement par lots** pour traiter la consolidation.

## <a name="criteria"></a>Critères
Sous l'onglet **Critères** de la page **Consolidation [En ligne]**, définissez les comptes, les périodes et le type de données consolidées.

![Onglet Critères](./media/criteria-consolidate-online.png "Onglet Critères")

Voici une explication des différents champs de cet onglet :

- **Description** – Entrez une description précise de la période de consolidation.
- **Compte principal** – Utilisez les champs de cette section pour définir les comptes principaux qui seront traités.

    - **De** et **À** – Spécifiez une plage de comptes à traiter. Si vous ne renseignez pas ces champs, tous les comptes de toutes les sociétés seront déplacés vers la société de consolidation. Par conséquent, si vous consolidez quatre sociétés et que chaque société a un plan de comptes différent, tous les comptes des quatre sociétés seront créés dans la société de consolidation.
    - **Compte de consolidation** – Si vous définissez cette option sur **Oui**, le champ **Sélectionner le compte de consolidation dans** devient disponible. Dans ce champ, indiquez si tous les comptes doivent être consolidés dans le compte de consolidation défini dans la page **Comptes principaux**, ou si vous souhaitez sélectionner un compte dans l'un des groupes de comptes de consolidation.
    - **Groupe de comptes de consolidation** – Sélectionnez le groupe à utiliser pour la mise en correspondance du compte principal pour la consolidation.

- **Période de consolidation** – Utilisez les champs de cette section pour définir la période de consolidation.

    - **De** et **À** – Spécifiez une plage de dates pour la consolidation. Si vous ne renseignez pas ces champs, la consolidation sera traitée pour toutes les périodes définies dans le calendrier comptable de la société. Il n'est pas recommandé de laisser ces champs vides.
    - **Inclure les montants réels** – Définissez cette option sur **Oui** pour consolider vos données réelles.
    - **Inclure les montants du budget** – Définissez cette option sur **Oui** pour consolider les données du registre budgétaire.
    - **Regénérer les soldes lors du processus de consolidation** – Il n'est pas recommandé de définir cette option sur **Oui**. À la place, régénérez les soldes en tant que traitement par lots distinct.

- **Modèles de budget** – Si vous avez choisi de consolider les données du budget, utilisez les champs de cette section pour définir les modèles de budget.

    - **De** et **À** – Spécifiez la plage de modèles à utiliser.
    - **Type de taux du budget** – Sélectionnez le type de taux budgétaire à utiliser pour la conversion en devises des données du budget.

## <a name="financial-dimensions"></a>Dimensions financières
Sous l'onglet **Dimensions financières**, définissez les dimensions qui doivent être incluses dans la société de consolidation. Pour sélectionner une dimension, définissez le champ **Spécification** sur **Dimension**, puis définissez l'ordre de la dimension dans la société de consolidation.

![Onglet Dimensions financières](./media/financial-dimensions-cons.png "Onglet Dimensions financières")

Quel que soit l'ordre que vous définissez, le champ **Compte principal** sera toujours le premier segment.

## <a name="legal-entities"></a>Entités juridiques
Sous l'onglet **Entités juridiques**, définissez les sociétés qui doivent être incluses dans la société de consolidation. Définissez également le pourcentage de participation de ces sociétés. Si vous spécifiez moins de 100 % de participation, le pourcentage spécifié sera cumulé dans la société de consolidation. Pour les différences de conversion, le champ **Type de compte des différences de conversion** permet de sélectionner le compte principal à partir des paramètres de la page **Comptes pour transactions automatiques**.

![Onglet Entités juridiques](./media/legal-entities-cons.png "Onglet Entités juridiques")

![Page Comptes pour transactions automatiques](./media/accounts%20for%20automatic%20(cons).png "Page Comptes pour transactions automatiques")

## <a name="elimination"></a>Élimination
Sous l'onglet **Élimination**, trois options de traitement des éliminations sont disponibles :

- Sélectionnez la règle d'élimination, puis, dans le champ **Options de proposition**, sélectionnez **Proposition uniquement**. Cette option traitera l'élimination pendant le processus de consolidation, mais n'effectuera pas de validation globale en une seule étape. Vous pouvez valider le journal ultérieurement.
- Sélectionnez la règle d'élimination, puis, dans le champ **Options de proposition**, sélectionnez **Valider uniquement**. Cette option traitera l'élimination pendant le processus de consolidation et effectuera une validation globale en une seule étape.
- Exécutez une proposition d'élimination séparément du processus de consolidation à l'aide du journal d'élimination.

![Onglet Élimination](./media/elimination-cons-onl.png "Onglet Élimination")

Pour plus d'informations sur les éliminations, voir [Règles d'élimination](./elimination-rules.md).

## <a name="currency-translation"></a>Conversion de devises
Sous l'onglet **Conversion de devises**, définissez l'entité juridique, le compte, le type de taux de change et le taux. Trois options sont disponibles dans le champ **Appliquer le taux de change de** :

- **Date de consolidation** – La date de la consolidation sera utilisée pour obtenir le taux de change. Ce taux est équivalent au taux au comptant ou en fin de mois. Vous verrez un aperçu du taux, mais vous ne pourrez pas le modifier.
- **Date de transaction** – La date de chaque transaction sera utilisée pour sélectionner un taux de change. Cette option est le plus souvent utilisée pour les immobilisations et est souvent appelée un taux historique. Il est impossible d'afficher un aperçu du taux, car plusieurs taux seront disponibles pour les différentes transactions dans la plage de comptes.
- **Taux défini par l'utilisateur** – Une fois cette option sélectionnée, vous pouvez entrer le taux de change souhaité. Cette option peut être utile pour les taux de change moyens ou si un taux de change fixe est utilisé pour la consolidation.

![Onglet Conversion de devises](./media/currency-translation-cons-online.png "Onglet Conversion de devises")

## <a name="additional-resources"></a>Ressources supplémentaires

Pour plus d'informations sur la consolidation et les conversions de devises, consultez la rubrique parent de cette rubrique [Consolidations financières et conversion de devises](./financial-consolidations-currency-translation.md).

Pour plus d'informations sur les scénarios où vous pouvez générer des tableaux d'analyse consolidés, voir [Générer des tableaux d'analyse consolidés](./generating-consolidated-financial-statements.md).
