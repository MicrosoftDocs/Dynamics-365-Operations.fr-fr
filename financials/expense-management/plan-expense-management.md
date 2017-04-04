---
title: "Configurer la gestion des dépenses"
description: "Cet article décrit les considérations et les décisions que vous devez prendre au cours du processus de planification avant de configurer la gestion des dépenses dans Microsoft Dynamics AX. Dans la zone de gestion des dépenses, vous pouvez stocker des informations sur les modes de paiement, des demandes de voyage, états de dépenses, et des stratégies, notamment."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: af7e7288f741b3c519227e2778c4c4311c3a2012
ms.openlocfilehash: 88cdf531b6da615034f9982d3503b9add0100479
ms.lasthandoff: 03/31/2017


---

# <a name="configure-expense-management"></a>Configurer la gestion des dépenses

Cet article décrit les considérations et les décisions que vous devez prendre au cours du processus de planification avant de configurer la gestion des dépenses dans Microsoft Dynamics AX. Dans la zone de gestion des dépenses, vous pouvez stocker des informations sur les modes de paiement, des demandes de voyage, états de dépenses, et des stratégies, notamment. 

Étant donné qu'un bon nombre des décisions que vous prenez lorsque vous planifiez la configuration de la gestion des dépenses sont basées sur la hiérarchie et la structure financière de votre organisation, vous devez vous référer aux documents de planification pour ces domaines.

## <a name="intercompany-expenses"></a>Dépenses intersociétés
Lorsque vous activez les dépenses intersociétés, vous autorisez les entités juridiques et les employés à effectuer des dépenses au nom d'une autre entité juridique au sein de votre organisation, ainsi qu'à recueillir des paiements en sa provenance . Par exemple, un employé de l'entité juridique A accomplit un projet pour l'entité juridique B. Si les dépenses intersociétés sont activées, l'employé peut alors adresser une feuille de temps à l'entité juridique B et être payé par celle-ci. Si votre organisation ne comporte pas plusieurs entités juridiques, vous n'avez pas besoin d'activer les dépenses intersociétés. **Décision :** souhaitez-vous activer les dépenses intersociétés ?

## <a name="financial-management"></a>Gestion financière
La gestion des dépenses est étroitement intégrée à la gestion financière de votre organisation. Une grande partie de votre configuration de la gestion des dépenses sera basée sur les décisions que vous avez prises en ce qui concerne les finances de votre organisation. Les sections suivantes décrivent les différents domaines nécessitant une planification et des décisions basées sur les décisions financières de votre organisation et les consignes de votre équipe de direction.

### <a name="per-diems"></a>Indemnités journalières

Vous devez définir les indemnités journalières des employés proposées par votre organisation. Étant donné que les indemnités journalières sont généralement utilisés pour couvrir des dépenses telles que les repas, l'hébergement, ainsi que d'autres dépenses fortuites, vous pouvez créer des règles pour les indemnités journalières que votre organisation propose. Les taux d'indemnités journalières peuvent être basés sur la période de l'année ou sur la destination du déplacement, voire sur les deux. Lorsque vous définissez une règle d'indemnité journalière, vous pouvez indiquer qu'un pourcentage du taux d'indemnité journalière soit retenu si un collaborateur bénéficie de repas ou de services gratuits. Vous pouvez également définir des catégories de taux d'indemnités journalières afin de paramétrer un nombre d'heures minimal et maximal pendant lequel le taux d'indemnité journalière peut être appliqué dans le cadre du déplacement d'un collaborateur. **Décisions : **

-   Règles d'indemnités journalières par défaut pour le premier et dernier jours :
    -   Quel est le nombre d'heures minimal qu'un employé peut déclarer pour un jour et recevoir quand même une indemnité journalière ?
    -   Y a-t-il une réduction du montant proposé pour les repas pour le premier et le dernier jours ? Dans ce cas, quel est le pourcentage de la réduction ?
    -   Y a-t-il une réduction du montant proposé pour un hôtel pour le premier et le dernier jours ? Dans ce cas, quel est le pourcentage de la réduction ?
    -   Y a-t-il une réduction du montant proposé pour les autres dépenses encourues le premier et le dernier jours ? Dans ce cas, quel est le pourcentage de la réduction ?
-   Règles d'indemnités journalières par défaut :
    -   Y a-t-il un pourcentage de réduction de l'indemnité journalière pour chaque repas si, par exemple, le repas est gratuit ? Dans ce cas, quel est le pourcentage de réduction pour chaque repas ?
    -   La réduction concernant les repas est-elle calculée par jour, par déplacement, ou par nombre de repas par jour ?
    -   Les montants des indemnités journalières doivent-ils être arrondis normalement ou arrondis au chiffre supérieur ?
    -   Les indemnités journalières sont-elles calculées sur une période de 24 heures ou sur un jour civil ?
-   Règles d'indemnités journalières basée sur un emplacement :
    -   Les taux des indemnités journalières varient-ils selon l'emplacement et quels sont les emplacements inclus ?
    -   Si les taux des indemnités journalières varient selon l'emplacement, pour chaque emplacement, quel pourcentage du montant est réservé pour :
        -   les repas
        -   l'hôtel
        -   les autres dépenses

### <a name="expense-management-journals-and-accounts"></a>Journaux et comptes de gestion des dépenses

La gestion des dépenses exige que vous utilisiez plusieurs journaux et comptes. Vous devez décider si, par exemple, le même compte est utilisé pour les avances de disponibilités et les litiges de paiement de carte de crédit. **Décisions :**

-   Dans quel journal comptable les états de dépenses approuvés sont-ils validés ?
-   Quel compte est-il utilisé pour les avances de disponibilités ?
-   Les avances de disponibilités doivent-elles être validées immédiatement ?

### <a name="payment-methods"></a>Modes de paiement

Lorsque vous autorisez les employés à encourir des dépenses au nom de votre entreprise, vous devez définir les modes de paiement qu'ils sont autorisés à utiliser. Par exemple, vous pouvez autoriser vos employés à utiliser des disponibilités en liquide ou une carte de crédit professionnelle. Vous pouvez également autoriser vos employés à utiliser leurs cartes de crédit personnelles, et les rembourser par la suite. Vous devez prendre les décisions suivantes pour chaque mode de paiement que vous autorisez. **Décisions :**

-   Quels modes de paiement sont-ils autorisés ?
-   Qui est propriétaire des dépenses du mode de paiement ?
-   Existe-t-il un type de compte de contrepartie ? Dans ce cas, quel est-il ?
-   S'il existe un compte de contrepartie, quel est ce compte ?
-   Si le mode de paiement est une carte de crédit, le mode de paiement doit-il uniquement être utilisé avec les transactions importées ?

### <a name="expense-categories-and-shared-categories"></a>Catégories de dépenses et catégories partagées

Lorsque les employés créent un état de dépenses, chaque dépense qu'ils enregistrent doit être associée à une catégorie de dépense. Les catégories de dépenses sont dérivées des catégories partagées qui peuvent être partagées par toutes les entités juridiques de votre organisation. Ces catégories peuvent également être partagées dans le module Gestion et comptabilité des projets, selon la façon dont votre organisation est définie. Selon la définition de votre organisation et les instructions de l'équipe d'implémentation, déterminez si les catégories utilisées dans le cadre de la gestion des dépenses doivent être utilisées exclusivement en matière de dépenses ou si elles sont partagées entre le projet et les dépenses. Notez que ces catégories peuvent être partagées entre le projet et les dépenses ou entre le projet et la production, mais pas entre les dépenses et la production. Vous devez prendre les décisions suivantes pour chaque catégorie de dépense. **Décisions :**

-   Quelle est la catégorie de dépense ? Par exemple, les vols, l'hôtel ou le kilométrage.
-   Cette catégorie de dépense peut-elle être utilisée dans le module Gestion et comptabilité des projets ?
-   Quel est le type de dépense ?
-   Quel est le mode de paiement par défaut pour la catégorie de dépense ?
-   Les dépenses de cette catégorie doivent-elles être détaillées ?
-   Quel est le compte principal par défaut pour la catégorie de dépense ?
-   Quel est le groupe de taxe d’article par défaut pour la catégorie de dépense ?
-   Des modes de paiement supplémentaires sont-ils autorisés pour cette catégorie de dépense ? Dans ce cas, quels sont-ils ?
-   Cette catégorie de dépense comporte-t-elle des sous-catégories ? Si c'est le cas :
    -   Certaines sous-catégories sont-elles exclues du recouvrement fiscal ?
    -   Quel est le groupe de taxe d’article de la sous-catégorie ?

    Si cette catégorie de dépense est également utilisée dans le module Gestion et comptabilité des projets, répondez aux questions restantes. Sinon, vous en avez terminé avec cette section.
-   Quels comptes de coût seront-ils utilisés pour les éléments suivants ?
    -   Charge
    -   Répartition des salaires
    -   Travaux en cours - coût
    -   Coût - Article
    -   Travaux en cours - coût - article
    -   Perte à recevoir
    -   Travaux en cours - perte à recevoir
-   Quels comptes de produit seront-ils utilisés pour les éléments suivants ?
    -   Produit facturé
    -   Produit à recevoir - Prix de vente
    -   Travaux en cours - prix de vente
    -   Produit à recevoir - production
    -   Travaux en cours - production
    -   Produit à recevoir - profit
    -   Travaux en cours - Profit
    -   Produit à recevoir - abonnement
    -   Travaux en cours - Abonnement

 

### <a name="taxes"></a>Taxes

Pour les taxes relatives aux dépenses, vous devez déterminer ce qui est inclus ou activé dans les états de dépenses. **Décisions :**

-   La taxe est-elle inclue aux montants des dépenses.
-   Le recouvrement fiscal doit-il être activé pour les dépenses ?

Notez que si, lors de votre planification de la comptabilité, vous avez décidé d'appliquer les règles de la taxe américaine et de la taxe d'utilisation, opération effectuée en faisant basculer la valeur du champ **Appliquer les règles de taxe** sur Oui, vous ne pouvez pas activer le recouvrement fiscal pour les dépenses.

## <a name="policies"></a>Stratégies
Vous pouvez créer des stratégies d'état de dépenses de sorte que votre organisation puisse gagner du temps et économiser de l'argent lorsque les employés encourent des dépenses en son nom. Les stratégies garantissent que les employés ne dépassent pas le budget, fournissent toutes les informations requises, et dépensent de l'argent uniquement lorsque cela est nécessaire. Vous devez prendre les décisions suivantes pour chaque stratégie d'état de dépenses et chaque stratégie d'approbation d'état de dépenses que vous créez. **Décisions : **

-   Quel est le nom de la stratégie ?
-   À quoi sert la stratégie de dépenses ?
-   Si vous avez précédemment décidé d'activer les dépenses intersociétés, à quelles sociétés de votre organisation cette stratégie s'applique-t-elle ?
-   Quand la stratégie entre-t-elle en vigueur ?
-   Quand la stratégie arrive-t-elle à expiration ?
-   Quelle est la règle de stratégie ?
-   Quel est le résultat de la règle de stratégie ?



