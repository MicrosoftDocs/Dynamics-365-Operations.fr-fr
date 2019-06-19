---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (13 mai 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-05-13
ms.dyn365.ops.version: Talent
ms.openlocfilehash: dac453ee83492655b6681b9784af4712bf39fc2a
ms.sourcegitcommit: 2bbc0eeca6826c529fb729b82d16f287c1ce05bb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2019
ms.locfileid: "1591500"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-may-13-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent (13 mai 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 for Talent.

## <a name="coming-soon-in-attract"></a>Bientôt dans Attract

### <a name="job-approvals-on-home-page"></a>Approbations de missions dans la page d'accueil

Les approbations apparaissent dans une section **Approbations** du tableau de bord. Les approbateurs peuvent analyser leurs approbations sous **Affecté à vous**, qui affiche l'ID de mission, le titre, d'autres approbateurs, et la date affectée. Les utilisateurs qui soumettent une mission pour approbation peuvent analyser leurs missions sous **Demandé par vous**, qui affiche les approbateurs qui doivent toujours approuver la mission envoyée.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut les correctifs de bogues mineurs pour Dynamics 365 Talent : Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2297. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="indicate-instance-type-when-provisioning-talent"></a>Indiquer le type d'instance lors de la mise en service de Talent

Lorsque de la mise en service d'une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est **Production** ou **Bac à sable (sandbox)**, ce qui permet de tester de nouvelles fonctionnalités. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance **Production**. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance **Bac à sable** (sandbox), contactez le [Support](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/talent-support) pour initier la demande de modification.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Prise en charge de l'entité Common Data Service pour les champs personnalisés

Dans la version de cette semaine, les entités Common Data Service suivantes prennent désormais en charge les champs personnalisés : Emploi, Fréquence de calcul des avantages, Taux de calcul des avantages, Congés du calendrier de travail et Types d'identification.

### <a name="common-data-service-integration-page"></a>Page d'intégration à Common Data Service

Cette version fournit une nouvelle option dans **Administration du système > Liens > Intégrations > Configuration de Common Data Service**. L'option **Configuration de Common Data Service** permet à un administrateur ou à une administrateur de gestion des données une certaine flexibilité et des informations avec Common Data Service. Avec cette option, vous pouvez activer ou désactiver l'intégration de Common Data Service à une instance Talent et afficher les détails de synchronisation entre l'instance Talent et Common Data Service.

### <a name="import-performance-data-with-final-employee-rating-316710"></a>Importation des données de performance avec le classement d'employé final (316710)

Dans cette version, vous pouvez importer les données de classement historiques de l'employé. Le champ **FinalEmployeeRatingId** a désormais accès en écriture.

### <a name="cant-create-worker-address-in-common-data-service-and-sync-it-with-talent-317555"></a>Impossible de créer l'adresse du collaborateur dans Common Data Service et de la synchroniser avec Talent (317555)

Cette modification permet aux données d'adresse créées dans Common Data Service de se synchroniser avec Talent.

## <a name="in-preview"></a>En mode aperçu

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nouvelle page pour valider les données de la hiérarchie des postes

Le Ressources humaines (RH) et les administrateurs peuvent valider la hiérarchie managériale pour toutes les références circulaires qui peuvent avoir été importées par inadvertance. Vous pouvez accéder à cette nouvelle page depuis **Administration de l'organisation > Liens > Postes > Validation de la hiérarchie des postes**.

### <a name="specify-reason-codes-on-leave-types"></a>Spécifier des codes motif sur les types d'absence

Les organisations peuvent nécessiter des informations supplémentaires sur les demandes de congé. Vous pouvez désormais spécifier les codes motif des types de départ et laisser les employés sélectionner un code motif pour leurs demandes de congé.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Codes motif requis pour des types d'absence spécifiques dans les demandes de congés

Les organisations peuvent exiger des codes motif pour certains types d'absence lorsque les employés envoient des demandes de congé. Cette condition peut exister à cause de la stratégie de la société ou des règlementations. Vous pouvez spécifier les types d'absence qui nécessitent un code motif, et vous pouvez exiger que les employés fournissent un code motif pour le type d'absence dans leurs demandes de congé.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fournir une liste de transactions de congé et d'absence pour les RH

La possibilité de suivre les congés des employés et de comprendre le calcul des congés aide non seulement les RH à répondre aux questions des employés, mais aussi de s'assurer de l'attribution exacte des durées de congé aux employés. Les RH disposent désormais d'une nouvelle vision des transactions (dotations, cumuls, ajustements et demandes) afin que le personnel des RH puisse voir les causes des soldes de congés.
