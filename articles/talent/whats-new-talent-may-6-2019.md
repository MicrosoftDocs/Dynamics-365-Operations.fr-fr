---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (6 mai 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4830c5d626e5e10972c81c3445eb54e4b6b00e6c
ms.sourcegitcommit: 0400bfd66e98af50e64444a1c102575099a9312f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2019
ms.locfileid: "1539403"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-may-6-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent (6 mai 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

### <a name="select-optional-documents-upon-offer-creation"></a>Sélectionner les documents facultatifs lors de la création de devis

Lorsque vous sélectionnez un modèle de package d'offre, Attract vous invite désormais à sélectionner les documents applicables et facultatifs de ce modèle de package. Vous pouvez ajouter d'autres documents facultatifs lors de la préparation de l'offre.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut les correctifs de bogues mineurs pour Dynamics 365 Talent : Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2282. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-26"></a>Update 26 de la plateforme

Pour des informations complémentaires sur Platform Update 26, voir [Aperçu des fonctionnalités dans Dynamics 365 for Finance and Operations Platform Update 26 (mai 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26). 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Prise en charge de l'entité Common Data Service pour les champs personnalisés

Dans la version de cette semaine, les entités suivantes prennent désormais en charge les champs personnalisés : Fréquence de calcul des avantages, Taux de calcul des avantages, Type d'avantage, Calendrier de travail, Congés du calendrier de travail, Cycle de paie et Types d'identification des collaborateurs.

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a>Laissez l'inscription collective, la modification de la base de niveau pour « Date d'ancienneté » n'actualise pas le taux de régularisation d'origine (318526)

Lorsque vous inscrivez collectivement des employés et modifiez la base de niveau, la régularisation initiale indique à présent la base de niveau que vous avez sélectionnée.

### <a name="workflow-showing-duplicate-place-holders-313636"></a>Workflow affichant des espaces réservés en double (313636)

Les modifications de cette version éliminent la duplication des espaces réservés quand les notifications de workflow sont envoyées.

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a>Les champs de dimension ne sont pas mis à jour lors de l'utilisation « Ouvrir dans Excel » (176261)

Avec cette version, vous pouvez désormais mettre à jour la dimension financière à l'aide de **Ouvrir dans Excel** sur la page **Collaborateur**. 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a>L'adresse du collaborateur créée dans Common Data Service n'est pas synchronisée avec Talent (317555)

Avec cette modification, les adresses créées dans Common Data Service sont mises à jour dans Talent Core HR.


## <a name="in-preview"></a>En mode aperçu

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nouvelle page pour valider les données de la hiérarchie des postes

Le Ressources humaines (RH) et les administrateurs peuvent maintenant valider la hiérarchie managériale pour toutes les références circulaires qui peuvent avoir été importées par inadvertance. Vous pouvez accéder à cette nouvelle page depuis **Administration de l'organisation > Liens > Postes > Validation de la hiérarchie des postes**.

### <a name="specify-reason-codes-on-leave-types"></a>Spécifier des codes motif sur les types d'absence

Les organisations peuvent nécessiter des informations supplémentaires sur les demandes de congé. Vous pouvez désormais spécifier les codes motif des types de départ et laisser les employés sélectionner un code motif pour leurs demandes de congé.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Codes motif requis pour des types d'absence spécifiques dans les demandes de congés

Les organisations peuvent exiger des codes motif pour certains types d'absence lorsque les employés envoient des demandes de congé. Cette condition peut exister à cause de la stratégie de la société ou des règlementations. Vous pouvez désormais spécifier les types d'absence qui nécessitent un code motif, et vous pouvez exiger que les employés fournissent un code motif pour le type d'absence dans leurs demandes de congé.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fournir une liste de transactions de congé et d'absence pour les RH

La possibilité de suivre les congés des employés et de comprendre le calcul des congés aide non seulement les RH à répondre aux questions des employés, mais aussi de s'assurer de l'attribution exacte des durées de congé aux employés. Les RH disposent désormais d'une nouvelle vision des transactions (dotations, cumuls, ajustements et demandes) afin que le personnel des RH puisse voir les causes des soldes.

## <a name="coming-soon"></a>Prochainement

### <a name="indicate-instance-type-when-provisioning-talent"></a>Indiquer le type d'instance lors de la mise en service de Talent

Lorsque de la mise en service d'une nouvelle instance de Talent, vous pourrez indiquer si le type d'instance est **Production** ou **Bac à sable (sandbox)**, ce qui permet de tester de nouvelles fonctionnalités. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance Production. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance Bac à sable (sandbox), contactez le Support pour initier la demande de modification.
