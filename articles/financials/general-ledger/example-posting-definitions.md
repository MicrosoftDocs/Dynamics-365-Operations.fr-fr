---
title: "Définitions de validation"
description: "Cet article fournit des exemples décrivant la manière dont les définitions de validation sont utilisées pour les engagements de commande fournisseur et les affectations budgétaires."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 10015952773ce0ae6ab36912df636919b572704d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="posting-definition-examples"></a>Exemples de définitions de validation

[!INCLUDE [banner](../includes/banner.md)]

Cet article fournit des exemples décrivant la manière dont les définitions de validation sont utilisées pour les engagements de commande fournisseur et les affectations budgétaires.

Avant de lire cette rubrique, vous devez être familiarisé avec les définitions de validation et de validation de transaction. Pour plus d'informations, voir [Définitions de validation](posting-definitions.md). Les exemples suivants peuvent être configurés dans la page **Définitions de validation**. Chaque exemple contient les sections suivantes :

-   Définition de validation – Critères de rapprochement
-   Définition de validation – Entrées générées
-   Transactions avec les comptes, valeurs de dimension et montants
-   Écritures comptables générées à partir de la définition de validation

Lorsqu'une correspondance existe entre les comptes et les valeurs de dimension dans le volet **Critère de rapprochement** de la définition de validation, ainsi qu'entre les comptes et les valeurs de dimension de la transaction, les écritures comptables sont générées selon le contenu du volet **Entrées générées** pour la définition de validation. 
> [!NOTE]
> Pour associer une définition de validation à un type de transaction spécifique, utilisez la page **Définitions de validation de transaction**. Après avoir associé une définition de validation à un type de transaction et sélectionné l'option **Utiliser les définitions de validation** sur la page **Paramètres de comptabilité**, toutes les transactions du type sélectionné doivent utiliser les définitions de validation.

## <a name="example-purchase-order-encumbrances"></a>Exemple : engagements de commande fournisseur
Lorsque vous activez le processus d'engagement en sélectionnant **Activer le processus d'engagement** dans la page **Paramètres de comptabilité**, les définitions de validation doivent être utilisées pour enregistrer les engagements dans la comptabilité pour tous les comptes devant être réservés. Dans la plupart des cas, tous les comptes de dépenses sont réservés sur le compte de bilan. 

Les définitions de validation des engagements sont paramétrées pour le module **Achat en cours** dans la page **Définitions de validation**. Puis, dans la zone **Achat en cours** de la page **Définitions de validation de transaction**, vous pouvez sélectionner le type de transaction **Commande fournisseur** pour associer la définition de validation aux commandes fournisseur. 

Toutes les transactions de N° document pour les engagements de commandes fournisseur doivent être équilibrées (c'est-à-dire, le débit doit être égal au crédit) dans chaque dimension unique d'un N° document.

### <a name="posting-definition--match-criteria"></a>Définition de validation – Critères de rapprochement

| Structure de compte       | Numéro de compte de rapprochement | Priorité |
|-------------------------|----------------------|----------|
| Structure de compte - Résultat | \*                   | 1        |

<em>Une valeur vide dans le champ **Numéro de compte de rapprochement</em>* signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

### <a name="posting-definition--generated-entries"></a>Définition de validation – Entrées générées

| Structure de compte | Numéro de compte généré                    | Débit/crédit généré |
|-------------------|---------------------------------------------|------------------------|
| Solde           | 300143 - -(Compte d'engagement)             | Idem                   |
| Solde           | 300144 - -(Réserver pour le compte d'engagement) | Balancement              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transactions avec les comptes, valeurs de dimension et montants

Les comptes et valeurs de dimension proviennent des répartitions comptables saisies pour une ligne de commande fournisseur ou des comptes et dimensions générés automatiquement en fonction des paramètres par défaut pour les modèles de fournisseurs, d'articles, de catégories et de dimensions.

| Compte + dimensions           | Débit  | Crédit | Commentaire |
|--------------------------------|--------|--------|---------|
| 606400-OU\_1-OU\_3566-Training | 250,00 |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Écritures comptables générées à partir de la définition de validation

Les écritures comptables générées sont créées pour enregistrer les engagements.

| Compte + dimensions           | Débit  | Crédit | Commentaire |
|--------------------------------|--------|--------|---------|
| 300143-OU\_1-OU\_3566-Training | 250,00 |        |         |
| 300144-OU\_1-OU\_3566-Training |        | 250,00 |         |

Dans cet exemple, toutes les parties de compte de la structure de compte - Résultat correspondent aux critères de définition de validation. Toutefois, lors de l'évaluation de 606500-OU\_1-OU\_3566-Training, les écritures générées sont créées pour les comptes définis dans le volet **Entrées générées** pour la définition de validation.

## <a name="example-budget-appropriations"></a>Exemple : affectations du budget
Lorsque vous activez l'affectation budgétaire en sélectionnant **Activer l'affectation budgétaire** dans la page **Paramètres de comptabilité**, vous devez utiliser les définitions de validation pour enregistrer les écritures de registre budgétaires dans la comptabilité. Lorsqu'une configuration de contrôle budgétaire est active, vous pouvez utiliser les définitions de validation et les définitions de validation de transaction pour prendre en charge l'enregistrement des écritures d'affectations, de révisions, de transferts, de projets, d'immobilisations, d'approvisionnements et de prévisions de la demande dans la comptabilité. 

Pour paramétrer une définition de validation pour les écritures de registre budgétaires dont le type de budget est **Budget d'origine** et pour lesquelles les affectations sont activées, sélectionnez le module **Budget** dans la page **Définitions de validation**. Puis, dans la zone **Budget** de la page **Définitions de validation de transaction**, vous pouvez utiliser les codes budget pour associer la définition de validation aux écritures de registre budgétaires dotées d'un budget de type **Budget d'origine**. 

Lorsque les définitions de validation et les affectations budgétaires sont activées, les écritures de registre budgétaires sont enregistrées pour le contrôle budgétaire, ainsi que dans la comptabilité.

### <a name="posting-definition--match-criteria"></a>Définition de validation – Critères de rapprochement

| Structure de compte       | Numéro de compte de rapprochement | Priorité |
|-------------------------|----------------------|----------|
| Structure de compte - Résultat | \*                   | 1        |

<em>Une valeur vide dans le champ **Numéro de compte de rapprochement</em>* signifie que tous les comptes correspondants de la structure de compte définie appartiennent à la règle de rapprochement.

### <a name="posting-definition--generated-entries"></a>Définition de validation – Entrées générées

| Structure de compte | Numéro de compte généré              | Débit/crédit généré |
|-------------------|---------------------------------------|------------------------|
| Structure de compte | 300145 - -(Compte Produit estimé) | Idem                   |
| Structure de compte | 300146 - -(Compte Affectations)     | Balancement              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transactions avec les comptes, valeurs de dimension et montants

La page de liste **Écriture de registre budgétaire** vous permet d'entrer les comptes, les valeurs de dimension et les montants pour l'écriture de compte budgétaire.

| Compte + dimensions           | Débit | Crédit | Commentaire |
|--------------------------------|-------|--------|---------|
| 606400-OU\_1-OU\_3566-Training |       | 250,00 |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Écritures comptables générées à partir de la définition de validation

Les écritures comptables générées sont créées pour enregistrer le budget d'origine dans chaque dimension.

| Compte + dimensions           | Débit  | Crédit | Commentaire |
|--------------------------------|--------|--------|---------|
| 300145-OU\_1-OU\_3566-Training |        | 250,00 |         |
| 300146-OU\_1-OU\_3566-Training | 250,00 |        |         |

Dans cet exemple, toutes les parties de compte de la structure de compte - Résultat correspondent aux critères de définition de validation. Donc, lorsque 606400-OU\_1-OU\_3566-Training est évalué, les écritures comptables générées sont créées.






