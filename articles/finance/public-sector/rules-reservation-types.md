---
title: Paramétrer des règles de réservation budgétaire générale et des types de réservation
description: Cette rubrique explique la procédure de paramétrage et de modification des règles de réservation budgétaire générale et des types de réservations pour le secteur public.
author: AlexRenney
ms.date: 04/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetReservation_PSN, BudgetReservationType_PSN
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 12a25ffff05a4d1e0ae71480115ddc209379c9f7
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346361"
---
# <a name="set-up-general-budget-reservation-rules-and-reservation-types"></a>Paramétrer des règles de réservation budgétaire générale et des types de réservation

[!include [banner](../includes/banner.md)]

Les entités du secteur public utilisent souvent des réservations budgétaires générales pour répartir ou réserver des fonds budgétés afin qu’ils soient disponibles pour d’autres fins. Pour utiliser les réservations budgétaires générales, vous devez spécifier des règles budgétaires et vous devez également paramétrer au moins un type de réservation budgétaire générale.

> [!NOTE]
> Si votre organisation réside en France, vous utilisez des engagements à la place des réservations budgétaires générales.

L’illustration suivante indique comment paramétrer le système pour utiliser des réservations budgétaires générales. Chaque étape numérotée correspond à une section de cette rubrique.

![Paramétrage de la réservation budgétaire générale.](media/gbr-rules-reservations-process.jpg "Paramétrage de la réservation budgétaire générale")

## <a name="prerequisites"></a>Conditions préalables

Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.

<table>
<thead>
<tr>
<th>Catégorie</th>
<th>Logiciel requis</th>
</tr>
</thead>
<tbody>
<tr>
<td>Tâches de configuration associées</td>
<td>
<ul>
<li>Vous devez utiliser des définitions de validation, à moins que vous n’activiez pas la comptabilité d’engagements.</li>
<li>La configuration du contrôle budgétaire et le contrôle budgétaire doivent être activés et un budget d’origine doit être confirmé.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="set-up-budgeting-parameters-for-regulatory-accounting"></a>Définir des paramètres budgétaires pour la comptabilité réglementaire

Pour définir des paramètres budgétaires pour la comptabilité réglementaire, suivez les étapes ci-dessous.

1. Accédez à **Budgétisation \> Paramétrage \> Budgétisation de base \> Paramètres de budgétisation**.
2. Sous l’onglet **Budget**, sous l’organisateur **Réglementation**, définissez l’option **Réservations budgétaires générales** sur **Oui**.
3. Facultatif : Dans l’organisateur **Contrôle des engagements**, définissez les options **Empêcher les reports d’augmentation des engagements** et **Utiliser la date de la session pour la comptabilité GBR** sur **Oui**.
4. Facultatif : Dans l’organisateur **Corrections de l’exercice précédent pour la réservation budgétaire générale**, définissez l’option **Autoriser les corrections de l’exercice précédent** sur **Oui**.

## <a name="select-source-documents-for-budget-control"></a>Sélectionner les documents source pour le contrôle budgétaire

Pour réserver des fonds budgétaires pour cette méthode d’achat, configurez la réservation budgétaire générale en tant que document source. 

Pour sélectionner les documents sources, procédez comme suit.

1. Accédez à **Budgétisation \> Paramétrage \> Contrôle budgétaire \> Configuration du contrôle budgétaire**.
2. Sélectionnez **Créer un brouillon**.
3. Dans l’onglet **Documents et journaux**, activez les cases à cocher **Réservation budgétaire générale** et **Contrôler au niveau de la saisie des lignes**.
4. Sur l’onglet **Activer le contrôle budgétaire**, sélectionnez **Activer**.

Lorsque vous créez une réservation budgétaire générale, les écritures de suivi de la source budgétaire et les résultats associés de la vérification budgétaire sont également créés. La vérification budgétaire est effectuée lorsque vous créez une ligne ou validez une réservation.

## <a name="set-up-general-ledger-information-for-general-budget-reservations"></a>Paramétrer les informations de comptabilité pour les réservations budgétaires générales

Pour garantir l’exactitude des comptes généraux, vous devez configurer la manière dont les réservations budgétaires générales sont utilisées pour enregistrer les engagements comptables.

Pour paramétrer les informations de comptabilité pour les réservations budgétaires générales, procédez comme suit.

1. Accédez à **Comptabilité \> Paramétrage de la comptabilité \> Paramètres de comptabilité**.
2. Sous l’onglet **Comptabilité**, dans l’organisateur **Règles comptables**, définissez l’option **Utiliser les définitions de validation** sur **Oui**. Ensuite, dans la boîte de message de confirmation qui apparaît, sélectionnez **Oui**.
3. Activez la case à cocher **Réservations budgétaires générales**. Puis fermez la notification.

    Lorsque vous activez la case à cocher **Réservations budgétaires générales**, les cases à cocher **Activer le processus d’engagement** et **Activer le processus d’engagement préalable** sont automatiquement activées et ne sont pas disponibles. Ces deux processus sont obligatoires lorsque des réservations budgétaires générales sont utilisées.

## <a name="create-posting-definitions"></a>Création de définitions de validation

Vous pouvez configurer les définitions de validation des transactions pour mettre à jour différents comptes généraux pour plusieurs types de réservation budgétaire générale.

Pour créer des définitions de validation pour les réservations budgétaires générales, procédez comme suit.

1. Accédez à **Comptabilité \> Paramétrage de la validation \> Définitions de validation**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Définition de validation**, entrez un bref code pour la définition (par exemple, **GBREnc**).
4. Dans le champ **Description**, entrez une description (par exemple **Engagement GBR**).
5. Dans le champ **Module**, sélectionnez **Réservation budgétaire**.
6. Définissez les champs restants dans la page comme vous le souhaitez.
7. Dans le volet Actions, sous l’onglet **Définition de validation**, dans le groupe **Afficher**, sélectionnez **Définitions de validation de transaction**.
8. Dans la page **Définitions de validation de transaction**, sous l’onglet **Réservation budgétaire**, dans le groupe de champ **Sélectionner**, **Réservation budgétaire générale** est sélectionné par défaut. Sélectionnez **Clôture de fin d’exercice de la réservation budgétaire générale** Si cette option est appropriée.
9. Sélectionnez **Nouveau**.
10. Dans le champ **Type de réservation**, sélectionnez l’une des valeurs suivantes :

    - Pour entrer une nouvelle définition de validation de transaction qui s’applique à tous les types de réservation, sélectionnez **Tout**. Ensuite, dans le champ **Définition de validation**, sélectionnez la définition créée précédemment.
    - Pour entrer une nouvelle définition de validation de transaction qui s’applique à un seul type de réservation, sélectionnez **Table**. Puis, dans le champ **Groupe de types de réservations**, sélectionnez un type de réservation. Dans le champ **Définition de validation**, sélectionnez la définition créée précédemment.

11. Répétez les étapes 2 à 10 pour créer autant de définitions de validation supplémentaires que vous le souhaitez, puis sélectionnez **Clôturer**.

## <a name="set-up-the-reservation-number-sequence"></a>Paramétrer la souche de numéros de réservation

Pour paramétrer la souche de numéros que les réservations budgétaires générales utilisent, procédez comme suit.

1. Accédez à **Budgétisation \> Paramétrage \> Budgétisation de base \> Paramètres de budgétisation**.
2. Dans l’onglet **Souches de numéros**, dans la colonne **Référence**, sélectionnez l’entrée des réservations budgétaires générales.
3. Dans la colonne **Code souche de numéros**, sélectionnez un code.

    Vous pouvez également attribuer des souches de numéros uniques par type de réservation.

## <a name="create-a-general-budget-reservation-type"></a>Créer un type de réservation budgétaire générale

Le type de réservation détermine la nature d’une réservation budgétaire générale, comme le type de document qui exonère la réservation budgétaire, le workflow utilisé pour approuver la réservation et la souche de numéros utilisée.

Pour créer un type de réservation budgétaire générale, procédez comme suit.

1. Accédez à **Budgétisation \> Paramétrage \> Réservations budgétaires générales \> Type de réservation**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Type de réservation**, entrez un nom pour le type de réservation.
4. Entrez une description dans le champ **Description**.
5. Dans le champ **Document d’allègement**, **Demande d’achat** est sélectionné par défaut. Sélectionnez une valeur différente comme vous le souhaitez. Ce champ affiche le type de document qui allègera la réservation budgétaire générale.

    > [!NOTE]
    > Après avoir créé une réservation budgétaire générale à l’aide du type de réservation, vous ne pouvez pas remplacer la réservation par un autre type.

6. Dans l’organisateur **Report de budget**, définissez l’option **Réduire le report de budget** sur **Oui** si tout report de budget restant associé à une réservation budgétaire générale doit être réduit à 0 (zéro) lorsque la réservation est finalisée.
7. Facultatif : Si une tâche d’approbation ou une autre tâche est nécessaire avant que la réservation puisse être validée, sous l’organisateur **Workflow**, dans le champ **Workflow**, sélectionnez un workflow de réservation budgétaire générale. Si vous laissez ce champ vide, un workflow n’est pas obligatoire afin de valider des réservations budgétaires générales de ce type.
8. Facultatif : Si différents types de réservations utilisent des souches de numéros uniques, dans l’organisateur **Souche de numéros**, dans le champ **Code souche de numéros**, sélectionnez le code souche de numéros que ce type de réservation doit utiliser.

    Si aucune souche de numéros n’est configurée pour un type de réservation, la souche de numéros des paramètres budgétaires est utilisée.

9. Répétez les étapes 2 à 8 pour créer tous autres types de réservations dont vous avez besoin.

## <a name="next-step"></a>Étape suivante

Après avoir défini des règles, vous pouvez créer des réservations budgétaires générales. Les réservations s’appliquent aux documents requis pour la méthode d’achat sélectionnée (demande d’achat, commande fournisseur ou facture fournisseur).

## <a name="technical-information-for-system-administrators"></a>Informations destinées aux administrateurs système

Si vous n’avez pas accès aux pages qui vous permettent d’effectuer cette tâche, contactez votre administrateur système et fournissez les informations répertoriées dans le tableau suivant.

| Catégorie                  | Logiciel requis                                                  |
|---------------------------|---------------------------------------------------------------|
| Clé de configuration des licences | Secteur public \> Réservation budgétaire générale                   |
| Rôles de sécurité            | Vous devez être membre du rôle de sécurité **Responsable du budget**. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]