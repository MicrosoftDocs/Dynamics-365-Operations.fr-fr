---
title: Comptes pour transactions automatiques
description: Cet article explique comment les comptes pour les transactions automatiques sont utilisés pour la validation via Microsoft Dynamics 365, et fournit des exemples de comptes importants pour les transactions automatiques.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 74e72840fea1f5d89c908b00e2cf572bce6befbe
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880757"
---
# <a name="accounts-for-automatic-transactions"></a>Comptes pour transactions automatiques

La page **Comptes pour transactions automatiques** (**Comptabilité &gt; Paramétrage de la validation &gt; Comptes pour transactions automatiques**) sert à définir le compte principal par défaut utilisé pour chaque type de validation dans le système. Bien que la plupart des types de validation puissent être configurés sur une page spécifique à un module ou à une fonctionnalité, certains types de validation ne peuvent être configurés que sur la page **Comptes pour transactions automatiques**.

Par exemple, vous pouvez spécifier le compte principal utilisé pour le type de validation **Solde client** dans le champ **Résumé** de la page **Profil de validation client** et utiliser un compte principal différent pour chaque profil client. De cette façon, vous avez un contrôle plus granulaire sur les validations. D’autre part, vous ne pouvez spécifier le compte d’erreur que sur la page **Comptes pour transactions automatiques**.

Lorsque vous ouvrez la page **Comptes pour transactions automatiques** dans une nouvelle entité juridique, la liste des comptes sera vide. Vous pouvez ajouter les types de validation les plus courants qui doivent être configurés sur la page en sélectionnant le bouton **Créer des types par défaut**. Ensuite, pour chaque ligne, vous pouvez sélectionner le compte principal dans le champ **Compte principal**. Si vous laissez vierge le champ **Compte principal** pour un type de validation et que vous n’avez pas configuré de compte principal sur une page spécifique à un module ou à une fonctionnalité, vous recevrez un message d’erreur lorsque vous validerez une transaction qui utilise le type de validation. En règle générale, le message sera : « Le compte pour le \[Type de validation\] est introuvable. »

## <a name="default-posting-types"></a>Types de validations par défaut

Le tableau suivant montre des exemples de types de validation par défaut qui sont créés lorsque vous sélectionnez **Créer des types par défaut** sur la page **Comptes pour transactions automatiques**. Il montre des exemples de comptes principaux et des descriptions. La colonne « Débit/crédit ? » indique si la transaction valide généralement un débit ou un crédit. Dans certains cas, une transaction peut afficher soit un débit, soit un crédit. La colonne « Compte de compensation » indique si le type de validation est un compte de compensation. Si le type de validation est un compte de compensation, le montant validé sur le compte est automatiquement annulé lorsqu’une transaction ultérieure est enregistrée.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Différence minime en devise de déclaration | 618160 | Dépenses diverses | Dépenses | Les deux | N° | Ce type de validation est utilisé lorsqu’une différence d’un centime apparaît lorsqu’un montant de transaction dans une devise étrangère est converti dans la devise de déclaration. |
| Différence minime dans la devise comptable | 618160 | Dépenses diverses | Dépenses | Les deux | N° | Ce type de validation est utilisé lorsqu’une différence d’un centime apparaît lorsqu’un montant de transaction dans une devise étrangère est converti dans la devise comptable. |
| Compte d’erreurs | 999999 | Compte d’erreurs | Dépenses | Les deux | N° | Ce type de validation est utilisé lorsqu’une erreur se produit dans le système. Le compte doit être vérifié à chaque période et toute erreur doit être résolue. |
| Résultat de fin d’exercice | 300160 | Bénéfices non répartis | Capitaux propres | Les deux | N° | Ce type de validation est utilisé lors de l’exécution du processus de clôture de fin d’exercice pour déplacer le solde des comptes du type **Profits et pertes** vers le compte principal sélectionné pour le résultat de fin d’exercice. |
| Client – Escompte de règlement | Non applicable | Non applicable | Non applicable | Non applicable | N° | Le type de validation qui est défini sur la page **Comptes pour transactions automatiques** n’est pas utilisé. Un compte principal est requis lorsque les escomptes de règlement sont configurés dans la Comptabilité client.|
| Fournisseur - Escompte de règlement | Non applicable | Non applicable | Non applicable | Non applicable | N° | Le type de validation qui est défini sur la page **Comptes pour transactions automatiques** n’est pas utilisé. Un compte principal est requis lorsque les escomptes de règlement sont configurés dans la Comptabilité fournisseur. |

## <a name="additional-posting-types"></a>Types de validation supplémentaires

Le tableau suivant montre des exemples des types de validation supplémentaires qui doivent être configurés si vous envisagez d’utiliser les fonctionnalités associées. Pour ces types de validation, aucune configuration de profil de validation n’est disponible dans un autre module. La colonne « Débit/crédit ? » indique si la transaction valide généralement un débit ou un crédit. Dans certains cas, une transaction peut afficher soit un débit, soit un crédit. La colonne « Compte de compensation » indique si le type de validation est un compte de compensation. Si le type de validation est un compte de compensation, le montant validé sur le compte est automatiquement annulé lorsqu’une transaction ultérieure est enregistrée.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Compte de solde pour différence de consolidation | 801200 | Profits et pertes - Réévaluation | Dépenses | Les deux | N° | Ce type de validation est utilisé lorsque vous effectuez une consolidation qui implique une réévaluation de devise et que des différences d’un centime apparaissent pendant la réévaluation. |
| Compte de résultat pour les différences de consolidation | 801200 | Profits et pertes - Réévaluation | Dépenses | Les deux | N° | Ce type de validation est utilisé lorsque vous effectuez une consolidation qui implique une réévaluation de devise et que des différences d’un centime apparaissent pendant la réévaluation. |
| Interunités – débit | 133500 | Créances interunités | Actif | Débit | N° | Ce type de validation est utilisé lorsque vous sélectionnez une dimension d’équilibrage sur la page **Comptabilité**, et que la dimension n’est pas équilibrée dans une transaction qui est validée. |
| Interunités - crédit | 233500 | Dettes interunités | Passif | Crédit | N° | Ce type de validation est utilisé lorsque vous sélectionnez une dimension d’équilibrage sur la page **Comptabilité**, et que la dimension n’est pas équilibrée dans une transaction qui est validée. |
