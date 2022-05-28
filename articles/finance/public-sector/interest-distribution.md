---
title: Paramétrer la distribution d’intérêts pour les comptes de disponibilités
description: Cette rubrique explique comment configurer vos comptes de disponibilités participants dans la page de règles de distribution d’intérêts. Vous devez effectuer ce paramétrage avant de distribuer les intérêts.
author: v-kiarnd
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PSNLedgerInterestDistributionRules, PSNLedgerInterestDistributionResults
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-kiarnd
ms.search.validFrom: 2019-6-30
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 7aea8ae00cd2f3817631fc2aa810056fdc949a6e
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735740"
---
# <a name="set-up-interest-distribution-for-cash-accounts"></a>Paramétrer la distribution d’intérêts pour les comptes de disponibilités

[!include[banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Votre agence peut affecter (distribuer) les intérêts sur un compte bancaire à des comptes généraux spécifiques, selon le solde quotidien moyen dans les comptes de disponibilités. Cette procédure vous permet de générer une écriture comptable avancée pour les montants d’intérêts. Sinon, vous pouvez générer les montants d’intérêts pour révision, sans les valider.

Avant distribuiez les intérêts, vous devez paramétrer vos comptes de disponibilités participants dans la page **Règles de distribution d’intérêts**. Chaque combinaison de compte de disponibilités et d’une subvention peut être utilisée pour calculer les intérêts d’un compte d’intérêts différent.

## <a name="add-a-cash-account-for-interest-distribution"></a>Ajouter un compte de disponibilités pour la distribution d’intérêts

1. Accédez à **Comptabilité \> Paramétrage \> Validation \> Règles de distribution d’intérêts**.
2. Sélectionnez **Nouveau** pour ajouter une ligne.
3. Dans le champ **Compte de disponibilités**, entrez le compte de disponibilités qui contient une partie du total des disponibilités regroupées.
4. Facultatif : Dans le champ **Subvention**, entrez la subvention pour les montants de transaction associés à une subvention à inclure dans les calculs de solde des disponibilités pour le compte de disponibilités associé. Si toutes les subventions du compte de disponibilités valident des intérêts dans le même compte, vous pouvez laisser ce champ vide. Toutefois, si vous entrez un compte d’intérêts pour une subvention spécifique, vous devez entrer un compte d’intérêts pour chaque subvention pour le compte de disponibilités.
5. Activez la case à cocher **Participer** pour inclure les comptes de disponibilités dans la distribution d’intérêts. Si cette case à cocher est désactivée, il est impossible de modifier les autres champs de la ligne. Les comptes de disponibilités qui ne participent pas sont inclus dans la page de recherche afin de pouvoir examiner le solde quotidien moyen. Toutefois, vous ne pouvez pas répartir les intérêts sur les comptes de disponibilités.
6. Entrez un compte d’intérêts ou un projet spécifique. La valeur que vous entrez détermine le compte général sur lequel les intérêts sont validés pour le compte de disponibilités associé.

    - Dans le champ **Compte d’intérêts**, entrez un compte spécifique.
    - Dans le champ **ID projet**, entrez un projet à utiliser comme base pour valider les intérêts. Ce compte est utilisé avec d’autres facteurs de compte pour déterminer le compte complet auquel cela est validé.

7. Activez la case à cocher **Intérêts négatifs** pour calculer un montant d’intérêts négatifs lorsque le compte de disponibilités a un solde négatif. Si cette case à cocher est désactivée, le compte de disponibilités indique des intérêts de 0 (zéro) plutôt qu’un montant négatif.
8. Les intérêts d’un compte de disponibilités peuvent recevoir tous les montants de différence minime lorsque la distribution d’intérêts est calculée. Activez la case à cocher **Arrondi** pour ce compte de disponibilités. Vous pouvez marquer un seul compte de disponibilités comme compte d’arrondi.

## <a name="distributing-interest"></a>Répartition des intérêts

1. Accédez à **Comptabilité \> Périodique \> Répartition \> Distribution des intérêts**.
2. Sélectionnez **Paramètres**, puis définissez les champs suivants :

    - Dans le champ **Montant total des intérêts**, entrez le montant total des intérêts à débourser.
    - Dans les champs **Date de début** et **Date de fin**, sélectionnez la plage de dates pour calculer les soldes quotidiens moyens, selon les transactions au cours de cette plage de dates.

3. Sélectionnez **Répartir**.
4. Vérifiez les montants d’intérêts calculés répartis dans les comptes. Vous pouvez mettre à jour les montants dans le champ **Intérêts affectés**.

    Si vous modifiez les montants des intérêts, le champ **Total affecté** doit correspondre au champ **Montant total des intérêts** avant de continuer. Le montant des intérêts calculés peut entraîner une différence dans le montant total affecté avec le montant total des intérêts. Généralement, la différence est d’un centime. Cette différence est appliquée au compte d’intérêts pour le compte de disponibilités marqué comme compte d’arrondi.

    > [!NOTE]
    > Si vous modifiez les montants d’intérêts mais que vous souhaitez ensuite les réinitialiser avec les montants d’intérêts calculés, sélectionnez **Paramètres**, puis **Répartir** pour générer les intérêts à l’aide des données d’origine.

5. Pour valider les intérêts répartis, sélectionnez **Valider les intérêts**, puis définissez les champs suivants :

    - Dans le champ **Date comptable**, entrez la date comptable de l’écriture comptable avancée.
    - Dans le champ **Catégorie de projet**, sélectionnez la catégorie de projet à utiliser pour les éléments de l’écriture comptable avancée. La catégorie de projet détermine également le compte principal auquel l’écriture comptable avancée se valide.
    - Dans le champ **Définition de la validation**, sélectionnez la définition de validation à utiliser pour l’écriture comptable avancée.

6. Cliquez sur **OK**. Un message affiche le numéro de l’écriture comptable avancée qui est automatiquement créée.

## <a name="pre-processing-for-increased-performance"></a>Pré-traitement pour des performances accrues

Si votre organisation modifie fréquemment le plan comptable ou les comptes liés aux comptes de trésorerie, le processus de distribution des intérêts peut prendre beaucoup de temps. Vous pouvez cependant réduire cette durée en utilisant la fonctionnalité **Utiliser le traitement par lots pour mettre à jour les comptes pour la répartition des intérêts** pour configurer le prétraitement pour ces comptes. 
 
Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l’espace de travail **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :
 
- **Module :** Comptabilité
- **Nom de la fonctionnalité :** utilisez le traitement par lots pour mettre à jour les comptes pour la répartition des intérêts
 
Lorsque vous activez la fonctionnalité, le système configure deux traitements par lots. Un premier traitement par lots sera exécuté une fois pour pré-traiter les données et les règles utilisées dans le processus de distribution des intérêts. Un travail par lots récurrent nommé **Exécuter le prétraitement planifié des comptes du grand livre utilisés pour la répartition des intérêts** sera également créé. Par défaut, le processus sera réexécuté tous les soirs. Cependant, vous pouvez modifier la fréquence dans la zone des traitements par lots.

## <a name="calculated-amounts"></a>Montants calculés

Le processus de répartition de la distribution d’intérêts inclut des montants calculés.

| Montant                | Calcul |
|-----------------------|-------------|
| Solde journalier moyen | Somme des soldes quotidiens pour chaque jour de la plage de dates, divisé par le nombre de jours de la plage pour chaque combinaison de compte de disponibilités et de subvention. Les combinaisons sont définies sur la page **Règles de distribution d’intérêts**. |
| Moyenne journalière totale   | Somme de tous les soldes quotidiens moyens, sauf les montants négatifs des comptes de disponibilités qui ne permettent pas des comptes d’intérêts et de disponibilités négatifs qui ne participent pas à la distribution d’intérêts. |
| Pourcentage du total      | Montant du solde quotidien moyen divisé par le montant moyen quotidien total pour chaque combinaison de compte de disponibilité et de subvention. |
| Intérêts affectés    | Montant total des intérêts de la page **Paramètres de distribution d’intérêts**, multiplié par le pourcentage du montant total du compte de disponibilités. Les intérêts ne sont pas répartis sur les comptes de disponibilités ayant des montants négatifs et qui ne permettent pas d’intérêts négatifs. Les intérêts ne sont également pas répartis sur les comptes de disponibilités qui ne participent pas à la distribution d’intérêts. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
