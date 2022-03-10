---
title: Planifier votre de plan comptable local
description: Cette rubrique fournit des informations qui vous aideront à planifier le plan comptable lorsque vous devez respecter des exigences légales/locales pour votre organisation.
author: VeselinaE
ms.date: 10/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount, DimensionDetails, MainAccountDetails
ROBOTS: ''
audience: Application User
ms.devlang: ''
ms.reviewer: roschlom
ms.tgt_pltfrm: ''
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.search.industry: ''
ms.author: veneva
ms.search.validFrom: 10/07/2021
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e224a2e24b4ba293c953c6c883307038128e2f04
ms.sourcegitcommit: ba10ba2cd4fb4267afb5aacae4f6a52aa2456e7e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2021
ms.locfileid: "7798294"
---
# <a name="plan-your-local-chart-of-accounts"></a>Planifier votre de plan comptable local

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations qui vous aideront à planifier le plan comptable lorsque votre organisation comprend des entités juridiques qui doivent répondre aux exigences des localités spécifiques où elles exercent leurs activités. Cette rubrique utilise les termes suivants pour décrire les plans comptables :

- **Global** – Plan comptable que l’organisation utilise à l’échelle mondiale. Dans la plupart des cas, vous consoliderez ce plan comptable.
- **Local** – Plan comptable que les entités juridiques d’un pays ou d’une région spécifique utilisent.
- **Partagé** – Plan comptable que plusieurs entités juridiques peuvent utiliser. Le plan comptable global et les plans comptables locaux peuvent être partagés.

Vous pouvez créer et partager plusieurs plans comptables. Un plan comptable partagé peut être utilisé par plusieurs entités juridiques, mais un seul plan comptable peut être affecté à chaque entité juridique. Le plan comptable qui est utilisé par une entité juridique est défini sur la page **Comptabilité**.

Lorsqu’elles conçoivent le plan comptable, de nombreuses organisations visent un plan comptable global. La fonctionnalité de plan comptable partagé permet de créer un plan comptable global. Il y a des avantages à créer et à utiliser un seul plan comptable. Par exemple, la gouvernance et le contrôle, la maintenance et le reporting sont plus faciles.

La plupart des organisations préfèrent un plan comptable global. C’est d’ailleurs le type le plus simple à mettre en œuvre. Néanmoins, certaines entités légales exigent un plan comptable local pour les raisons suivantes :

- Exigences légales locales
- Exigences des normes comptables locales
- Exigences du secteur
- Exigences de reporting et d’analyse spécifiques à l’entreprise

Si votre organisation exige qu’une entité juridique utilise un plan comptable local, deux options s’offrent à vous pour le mettre en œuvre :

- Attribuez le plan comptable global et définissez d’autres moyens de répondre aux exigences locales.
- Affectez un plan comptable local à l’entité juridique et définissez les relations avec le plan comptable global.

La structure organisationnelle et la structure hiérarchique déterminent l’option utilisée.

[![Diagramme montrant comment la structure de l’organisation détermine s’il faut utiliser un plan comptable global ou local](./media/local-chart-of-accounts-diagram.png)](./media/local-chart-of-accounts-diagram.png)

Si le plan comptable global est affecté à l’entité juridique, les options suivantes sont disponibles pour répondre aux exigences locales en matière de rapports :

- Effectuer des consolidations locales.
- Utiliser une dimension financière pour suivre le plan comptable local.
- Créer des comptes principaux locaux dans le plan comptable global.
- Effectuer un mappage externe avec le plan comptable local.

Si un plan comptable local est affecté à l’entité juridique, la seule option qui est actuellement disponible pour répondre aux exigences globales en matière de rapports est la consolidation globale.

## <a name="global-chart-of-accounts-assigned-to-a-legal-entity"></a>Plan comptable global affecté à une entité juridique

Si vous devez affecter le plan comptable global à une entité juridique, quatre options sont disponibles pour configurer le système, comme décrit précédemment. Pour les quatre options, un seul plan comptable est configuré et lié à chaque entité juridique sur la page **Comptabilité**. Chaque option utilise ensuite une approche différente pour répondre aux exigences de localisation. Les sections suivantes décrivent les principales étapes pour configurer le système pour les exigences de localisation. Elles décrivent également les avantages et les inconvénients de chaque option.

### <a name="do-local-consolidation"></a>Effectuer des consolidations locales

La consolidation locale est l’approche recommandée pour répondre aux exigences du plan comptable local et tirer parti des fonctionnalités du système conçues à cet effet.

#### <a name="set-up-consolidation-for-a-local-chart-of-accounts"></a>Paramétrer la consolidation d’un plan comptable local

1. Créez un plan comptable global unique qui inclut tous les comptes principaux requis.
2. Dans chaque entité juridique, affectez le plan comptable global sur la page **Comptabilité**.
3. Créez une entité juridique de consolidation pour chaque localisation requise.
4. Utilisez l’une des procédures suivantes :

    - Si une seule localisation est requise, configurez le compte de consolidation sur la page **Compte principal**, ou utilisez les pages **Groupes de consolidation** et **Comptes de consolidation supplémentaires**.
    - Si plusieurs localisations sont requises, ou si le numéro du compte et le nom du compte nécessitent une traduction, utilisez les pages **Groupes de consolidation** et **Comptes de consolidation supplémentaires** pour représenter les exigences de localisation.

5. Exécutez le processus de consolidation pour transformer la valeur de l’entité juridique source qui utilise le plan comptable global vers la société de consolidation qui utilise le plan comptable local.

#### <a name="advantages"></a>Avantages

- Cette approche offre une méthode de travail cohérente dans l’ensemble de l’organisation.
- Une traduction de la position locale est effectuée.
- Cette approche prend en charge la traduction de l’ID du compte principal et du nom de chaque compte principal.
- Elle prend en charge plusieurs localisations.

#### <a name="disadvantages"></a>Inconvénients

- Une société de consolidation supplémentaire est créée.
- Un processus consolidation supplémentaire est terminé.
- Cette approche ne peut générer des rapports sur le graphique localisé qu’une fois le processus de consolidation terminé.

### <a name="use-a-financial-dimension-to-track-the-local-chart-of-accounts"></a>Utiliser une dimension financière pour suivre le plan comptable local

Cette approche utilise une dimension financière où les valeurs de dimension financière représentent les comptes principaux locaux requis pour la localisation. Cette approche est efficace si une seule localisation est requise. Cependant, elle devient moins facile à utiliser à mesure que vous ajoutez des localisations et des dimensions financières.

#### <a name="set-up-a-financial-dimension-for-a-local-chart-of-accounts"></a>Configurer une dimension financière pour un plan comptable local

1. Créez un plan comptable global unique qui inclut tous les comptes principaux requis.
2. Dans chaque entité juridique, affectez le plan comptable global sur la page **Comptabilité**.
3. Créez une dimension financière qui représente le plan comptable local.
4. Créez les valeurs de dimension financière qui représentent les comptes principaux dans le plan comptable local.
5. Mettre à jour la structure du compte pour qu’elle intègre la dimension financière "plan comptable local".
6. Assurez-vous que la dimension financière "plan comptable local" a toujours une valeur, et qu’elle n’autorise pas de valeur vide. Envisagez d’utiliser des dimensions dérivées ou des dimensions fixes.
7. Créez un ensemble de dimensions financières où la dimension financière "plan comptable local" est la première dimension financière sélectionnée. L’ensemble de dimensions financières peut être utilisé lors de la génération de la balance comptable.

#### <a name="advantages"></a>Avantages

- Les principaux comptes des plans comptables mondiaux et locaux existent au niveau des transactions. Le compte principal est global et la valeur de la dimension financière est locale.
- Cette approche fournit des rapports en temps réel et des vues à la fois de la position financière mondiale et de la position financière locale.

#### <a name="disadvantages"></a>Inconvénients

- Dans les paramètres de Comptabilité, si le champ **Valeurs utilisées pour le compte collectif** est défini sur **Répartitions comptables**, les dimensions financières qui représentent le compte principal pour la dépense/l’actif/le revenu seront utilisées à tort pour le compte collectif Comptabilité client et Comptabilité fournisseur. Nous vous recommandons plutôt de définir le champ sur un document source pour vous assurer que les valeurs de dimension financière correctes sont utilisées.
- Si de nombreux plans comptables locaux sont requis et qu’une dimension financière est utilisée pour chacun d’eux, la liste des valeurs de dimension financière qui sont utilisées peut devenir longue et difficile à utiliser.
- Si de nombreux plans comptables locaux sont requis et qu’une dimension financière distincte est utilisée pour représenter chaque plan, la facilité d’utilisation et les performances du système peuvent être affectées lorsque des dimensions financières et des ensembles de dimensions financières sont ajoutés.
- Nous vous recommandons d’examiner attentivement le nombre de dimensions financières dont vous avez besoin, le nombre de valeurs dans chacune et le nombre d’ensembles de dimensions financières, car tous ces facteurs peuvent affecter les performances du système.

### <a name="create-local-main-accounts-in-the-global-chart-of-accounts"></a>Créer des comptes principaux locaux dans le plan comptable global

*Ce que le réviseur a demandé :* Dans cette approche, les comptes principaux locaux dans le plan comptable global incluent les comptes principaux du plan comptable local dans le plan comptable global.

*Version originale :* Dans l’approche CoA globale, les comptes principaux locaux impliquent que les comptes principaux CoA locaux sont inclus dans le CoA global.

*Signification :* Dans cette approche, les comptes principaux locaux du plan comptable local sont intégrés au plan comptable global.


#### <a name="set-up-local-main-accounts-in-the-global-chart-of-accounts"></a>Configurer des comptes principaux locaux dans le plan comptable global

1. Créez un plan comptable unique qui comprend les comptes principaux à la fois pour le plan comptable global et le plan comptable local.
2. Dans chaque entité juridique, affectez le plan comptable sur la page **Comptabilité**.
3. Créez des comptes totaux dans le plan comptable pour additionner les comptes principaux qui représentent le même objectif.
4. Créez des remplacements d’entité juridique sur chaque compte local pour empêcher les transactions d’autres entités juridiques pour lesquelles le compte local n’a pas été conçu.
5. Créez des remplacements d’entité juridique sur chaque compte global pour empêcher les transactions des entités juridiques de localisation.

#### <a name="advantages"></a>Avantages

- Une vue en temps réel de la position financière globale et de la position financière locale est disponible sur des rapports spécifiques et dans des vues spécifiques du système, telles qu’un état financier du bilan. Il est également accessible à l’aide du bouton **Période** sur le compte total.
- Vous n’avez pas de segment supplémentaire dans le compte général.

#### <a name="disadvantages"></a>Inconvénients

- L’utilisation des comptes de type Total et la visibilité sont limitées. Par exemple, les comptes de type Total ne sont pas visibles sur la page de liste **Balance comptable**.
- La maintenance implique un effort supplémentaire.
- La création d’états financiers implique un effort manuel supplémentaire.

### <a name="do-external-mapping-to-the-local-chart-of-accounts"></a>Effectuer un mappage externe avec le plan comptable local

L’adoption d’un plan comptable global suppose que vous gérez le mappage et les localisations en dehors du système. Dans cette approche, vous créez simplement un plan comptable unique global dans Microsoft Dynamics 365 Finance et gérez les exigences en dehors du système.

#### <a name="set-up-external-mapping-to-a-local-chart-of-accounts"></a>Configurer un mappage externe avec un plan comptable local

1. Créez un plan comptable global unique qui inclut tous les comptes principaux requis.
2. Dans chaque entité juridique, affectez le plan comptable global sur la page **Comptabilité**.
3. Effectuer le mappage avec le plan comptable local en dehors de Finance.

#### <a name="advantages"></a>Avantages

- Cette approche offre une méthode de travail cohérente dans l’ensemble de l’organisation.

#### <a name="disadvantages"></a>Inconvénients

- Aucun rapport local du système n’est disponible.
- Cette approche peut causer des erreurs lors de la création des rapports financiers.

## <a name="local-chart-of-accounts-assigned-to-legal-entity"></a>Plan comptable local affecté à une entité juridique

Si votre organisation décide de ne pas utiliser un plan comptable global sur les entités juridiques, un plan comptable distinct est créé pour chaque plan comptable local unique. Chaque entité juridique est ensuite liée au plan comptable correspondant sur la page **Comptabilité**.

### <a name="do-global-consolidation"></a>Effectuer une consolidation globale

Dans cette approche, une société de consolidation est utilisée pour cumuler et combiner les soldes de chaque société locale source dans le plan comptable global combiné de la société de consolidation. Cette approche nécessite que vous mainteniez un mappage de chaque plan comptable local avec le plan comptable global dans la société de consolidation.

#### <a name="set-up-global-consolidation"></a>Configurer une consolidation globale

1. Créez un plan comptable distinct pour chaque entité juridique ayant un plan comptable local différent. Si des entités juridiques ont le même plan comptable local, un seul plan comptable local est requis et il peut être partagé.
2. Dans chaque entité juridique, affectez le plan comptable correspondant sur la page **Comptabilité**.
3. Facultatif : Créez un plan comptable pour le plan comptable global de chaque société de consolidation ayant un plan comptable global différent.
4. Créez une entité juridique de consolidation pour chaque niveau de consolidation requis et affectez le plan comptable approprié sur la page **Comptabilité**.
5. Utilisez l’une des procédures suivantes :

    - Si une seule consolidation est requise, configurez le compte de consolidation sur la page **Compte principal**.
    - Si plusieurs consolidations sont requises, ou si le numéro du compte et le nom du compte nécessitent une traduction, utilisez les pages **Groupes de consolidation** et **Comptes de consolidation supplémentaires** pour représenter les exigences des plans comptables globaux.

6. Exécutez le processus de consolidation pour transférer les soldes des entités juridiques locales vers l’entité juridique consolidée. Cette entité juridique consolidée utilise les comptes de consolidation que vous avez définis à l’étape 5.

#### <a name="advantages"></a>Avantages

- Le format des normes comptables locales est appliqué nativement.
- Cette approche permet à l’équipe financière locale de travailler plus facilement.

#### <a name="disadvantages"></a>Inconvénients

- Aucune vue en temps réel de la position globale n’est disponible.
- Le processus de consolidation peut être exécuté plus souvent.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Plan de comptes](plan-chart-of-accounts.md)
- [Configurer les registres](configure-ledger.md)
- [Dimensions financières et validation](Default-dimensions.md#balancing-dimension)
- [Ensembles de dimensions financières](financial-dimension-sets.md)
- [Vue d’ensemble de la consolidation et de l’élimination](../budgeting/consolidation-elimination-overview.md)
- [Groupes de comptes de consolidation et comptes de consolidation supplémentaires](../budgeting/consolidation-account-groups-consolidation-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
