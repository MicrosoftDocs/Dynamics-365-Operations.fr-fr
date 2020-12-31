---
title: Paramétrage de la gestion du crédit
description: Cette rubrique décrit la configuration requise pour la gestion des crédits.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: d1d33dbbd37daaa75f4b64359194a2328728b27f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443043"
---
# <a name="credit-management-setup"></a>Paramétrage de la gestion du crédit 

[!include [banner](../includes/banner.md)]

## <a name="credit-management-workflows"></a>Workflow de gestion du crédit

Allez à **Crédit et relances \> Configuration \> Workflows de gestion de crédit** pour définir les workflows utilisés pour gérer les ajustements de limite de crédit.

- Vous pouvez créer un workflow qui vous permet d’approuver un lot d’ajustements de limites de crédit via une seule approbation.
- Vous pouvez ajouter un workflow au niveau de la ligne afin que les ajustements de limite de crédit puissent être approuvés individuellement.
- Vous pouvez créer un workflow de lancement qui achemine automatiquement les blocages vers un processus de workflow.

## <a name="blocking-rules"></a>Règles de blocage

### <a name="ranking-payment-terms"></a>Classement des modalités de paiement

Vous pouvez mettre une commande client en attente si les modalités de paiement de la commande ne correspondent pas à celles par défaut du client. Cependant, parfois les modalités de paiement diffèrent mais sont suffisamment similaires pour que vous ne souhaitiez pas mettre la commande en attente. Vous pouvez classer les modalités de paiement de sorte que certaines d’entre elles aient le même rang, tandis que d’autres ont un rang supérieur ou inférieur.

Si le classement des modalités de paiement est actif et si les modalités de paiement sur la commande ont un rang supérieur à celles par défaut du client, la commande client sera mise en attente.

Pour configurer le classement des modalités de paiement, accédez à **Crédits et recouvrements \> Paramétrer \> Paramétrage de la gestion de crédits \>Classer les modalités de paiement.**  

### <a name="ranking-settlement-discounts"></a>Classement des remises de règlement

Vous pouvez mettre une commande client en attente si l’escompte de règlement de la commande ne correspond pas à celui par défaut du client. Cependant, parfois les escomptes de règlement diffèrent mais sont suffisamment similaires pour que vous ne souhaitiez pas mettre la commande en attente. Vous pouvez classer les escomptes de règlement de sorte que certains d’entre eux aient le même rang, tandis que d’autres ont un rang supérieur ou inférieur.

Si le classement des remises de règlement est actif, les commandes client seront mises en attente si l’escompte de règlement de la commande a un rang supérieur à celui par défaut du client.

Pour configurer le classement des modalités de paiement, accédez à **Crédits et recouvrements \> Paramétrer \> Paramétrage de la gestion de crédits \>Classer les remises de règlement.**  

## <a name="reasons"></a>Motifs

Plusieurs types de motifs sont utilisés dans la gestion du crédit :

- Les motifs de mise en attente indiquent pourquoi une commande client a été mise en attente.
- Les motifs de lancement sont attribués à une commande lorsqu’elle est libérée de la mise en attente.
- Les motifs de statut indiquent pourquoi un statut de compte a été attribué à un client.

Vous pouvez paramétrer des motifs sur la page **Motifs de la gestion du crédit** (**Crédits et recouvrements \> Paramétrer \> Configuration de la gestion du crédit \> Motifs de la gestion du crédit**).

1. Dans le champ **Type de motif**, sélectionnez le type de motif : **En attente**, **Lancement** ou **Statut**.
2. Dans le champ **Motif**, entrez un nom pour le motif.
3. Dans le champ **Description**, entrez une description du code motif.

## <a name="credit-management-groups"></a>Groupes de gestion du crédit

Les groupes de gestion de crédit sont utilisés pour identifier des clients ou des groupes de clients qui ont les mêmes propriétés de gestion de crédit. Par exemple, des groupes de gestion de crédit peuvent être utilisés pour déterminer les règles de gestion de crédit de blocage et d’exclusion pour les clients.

Vous pouvez créer des groupes de gestion de crédit dans la page **Groupes de gestion de crédit** (**Crédits et recouvrements \> Paramétrer> Paramétrage de la gestion de crédits \> Groupes de gestion de crédit**).

1. Sélectionnez **Nouveau** pour créer une ligne.
2. Entrez un ID pour le groupe. L’ID peut contenir jusqu’à 10 caractères.
3. Dans le champ **Description**, entrez un nom pour le groupe. Le nom peut contenir jusqu’à 60 caractères.

Le groupe de gestion des crédits est affecté à un client sur le raccourci **Crédit et relances** de la page **Tous les clients** (**Comptabilité fournisseur \> Clients \> Tous les clients**).

## <a name="account-statuses"></a>Statut de comptes

Vous pouvez créer des statuts de compte pour identifier la solvabilité d’un compte client. Vous pouvez définir un statut et son effet sur les processus de facturation et de mise en attente de livraison. Les statuts de compte peuvent également être utilisés pour déterminer les règles de blocage pour un client.

Vous pouvez créer des statuts de compte sur la page **Statuts du compte** (**Crédits et recouvrements \> Paramétrer> Paramétrage de la gestion de crédits \> Statuts du compte**).

1. Ajoutez un statut de compte et entrez une description qui représente la solvabilité d’un client. Par exemple, utilisez **Normal** pour indiquer qu’un client est en règle et que les commandes en cours sont soumises à un traitement standard de gestion du crédit.
2. Dans les champs **Facturation** et **Livraison en attente**, sélectionnez le type de blocage qui doit se produire pour les clients ayant ce statut de compte. Vous pouvez suspendre tous les traitements, suspendre uniquement le traitement des factures ou ne conserver aucun traitement lorsque les règles de limite de crédit sont appliquées.

## <a name="scoring-groups"></a>Groupes de scores

Vous pouvez configurer des groupes de notation pour définir les facteurs de risque et les critères utilisés pour les mesurer. Lorsque des informations sur un client sont appliquées à un groupe de notation, un score est calculé pour chaque facteur de risque et utilisé pour placer le client dans un groupe de risques. Le groupe de risques peut être utilisé pour identifier la solvabilité et calculer les limites de crédit automatiques.

Vous pouvez créer des groupes de notation sur la page **Groupes de notation** (**Crédits et recouvrements \> Paramétrer \> Paramétrage de la gestion de crédits \> Risque \> Groupes de notation**).

1. Créez un groupe de notation et donnez-lui un nom.
2. Entrez une description pour décrire plus en détail le groupe de notation.
3. Sélectionnez un type de groupe. Il existe huit types prédéfinis. Vous pouvez également sélectionner **Défini par l’utilisateur** pour définir un type de groupe mieux adapté à votre organisation.
4. Sélectionnez un type de score pour définir comment le groupe de notation calcule le score de risque. Les options suivantes sont disponibles :

    - **Plage** - Utilisez cette option pour définir une plage de valeurs à utiliser pour calculer un score.
    - **Défini par l’utilisateur** - Utilisez cette option pour définir manuellement une liste de valeurs à utiliser pour le score.

5. Si vous avez sélectionné **Plage** comme type de score, ajoutez des lignes pour définir la plage de valeurs et les scores correspondants.

    1. Dans le champ **Valeur de début**, spécifiez la valeur la plus basse de la plage.
    2. Dans le champ **Valeur de fin**, spécifiez la valeur la plus élevée de la plage.
    3. Dans le **Score**, entrez le score à attribuer lorsque la valeur fournie se situe dans la plage « début »/« Fin ».

    Si vous avez sélectionné **Défini par l’utilisateur** comme type de score, ajoutez des lignes pour définir les valeurs définies par l’utilisateur et les scores correspondants.

    1. Dans le champ **Valeur**, entrez la valeur définie par l’utilisateur qui doit être fournie à partir des informations client.
    2. Dans le **Score**, entrez le score à attribuer lorsque la valeur fournie se situe dans la plage « début »/« Fin ».

## <a name="risk-classification"></a>Classification du risque

Vous pouvez définir des évaluations des risques qui peuvent être attribuées aux clients, en fonction de leur score de risque. Un score de risque est calculé en comparant les informations client à chaque groupe de notation. Les scores sont additionnés et le score total est comparé aux valeurs de la configuration du groupe de risques pour identifier le groupe de risques auquel appartient le client. Le score du groupe de risque est ensuite utilisé pour définir les règles de blocage et d’exclusion de la gestion du crédit pour le client.

Vous pouvez paramétrer des groupes de risques sur la page **Évaluations des risques** (**Crédits et recouvrements \> Paramétrage \> Paramétrage de la gestion de crédits \> Risque \> Classification des risques**).

1. Saisissez un ID de groupe de risques.
2. Entrez une description pour expliquer plus en détail le groupe de risques.
3. Entrez une plage de scores qui est utilisée pour déterminer quels clients appartiennent au groupe de risques.
4. Sélectionnez un indicateur de groupe de risques pour spécifier le symbole qui représente le groupe de risques.

## <a name="guaranteeinsurance-types"></a>Types de garantie/assurance

Vous pouvez paramétrer des types de garantie/assurance dans la page **Types de garantie/assurance** (**Crédits et recouvrement \> Paramétrage \> Paramétrage de la gestion de crédits \> Assurance et garanties \> Types de garantie/assurance**).

1. Saisissez un type de garantie ou d’assurance qui identifie le nom du garant ou du courtier d’assurance.
2. Entrez une description pour décrire le garant/courtier d’assurance.

## <a name="coverage-types"></a>Types de couverture

Des types de couverture peuvent être utilisés pour classer davantage les polices d’assurance. Ils ne peuvent pas être utilisés avec des garanties.

Vous pouvez ajouter des types de couverture sur la page **Types de couverture** (**Crédits et recouvrements \> Paramétrage \> Paramétrage de la gestion de crédits \> Assurance et garanties \> Types de couverture**).

1. Saisissez un type de couverture pour identifier le type de couverture à ajouter en tant qu’assurance ou garantie.
2. Entrez une description pour décrire le type de couverture.

## <a name="automatic-credit-limits"></a>Limites de crédit automatiques

Vous pouvez créer des critères pour les limites de crédit automatiques sur la page **Limites de crédit automatiques** (**Crédits et recouvrements \> Paramétrer \> Paramétrage de la gestion de crédits \> Risque \> Limites de crédit automatiques**).

1. Sélectionnez un groupe de risques auquel la limite de crédit automatique doit être affectée.
2. Sélectionnez la devise pour la limite de crédit automatique. Vous pouvez créer plusieurs limites de crédit automatiques dans différentes devises pour le même groupe de risques.
3. Entrez le montant des revenus qui représente le revenu maximum de l’entreprise qui peut être utilisé pour cette limite de crédit automatique. Lorsque des limites de crédit sont créées, le montant des revenus est comparé à une valeur de revenus qui se trouve sur la page **Finances** (**Comptabilité client \> Tous les clients \> Sélectionnez un client \> Général \> Statistiques \> Financier**). Le système utilise la dernière valeur de la section **Aperçu**.

Suivez ces étapes pour ajouter des lignes qui représentent la limite de crédit qui sera générée en fonction des critères sélectionnés.

1. Sélectionnez le groupe de notation qui définit les informations client à utiliser pour calculer la limite de crédit.
2. Sélectionnez l’opérateur de comparaison qui définit la manière dont les informations du groupe de notation doivent être évaluées.
3. Entrez la valeur qui doit être comparée à la valeur spécifiée pour le groupe de notation.
4. Saisissez la limite de crédit à attribuer si les informations client correspondent à la valeur spécifiée pour le groupe de notation. Par exemple, vous créez une limite de crédit automatique pour le groupe de notation **Faible**. Si les années d’activité font partie des groupes de notation, vous pouvez définir une ligne qui affecte une limite de 100 000 crédits si le client est en activité depuis cinq ans et une autre ligne qui affecte une limite de 200 000 crédits si le client est en activité depuis 10 ans.
