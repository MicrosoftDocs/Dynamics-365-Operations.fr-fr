---
title: Nouveautés ou modifications dans Dynamics 365 Talent (23 octobre 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/23/2019
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
ms.search.validFrom: 2019-10-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 94243f83121a1306d8f9ae9be23d24e5c9b63a2d
ms.sourcegitcommit: 07e109dec176a93eff0df8a37ba5d875f212e9f1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/25/2019
ms.locfileid: "2662663"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-23-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (23 octobre 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2569. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-30-for-finance-and-operations-apps"></a>Applications Platform update 30 pour Finance and Operations

Pour plus d'informations, voir [Nouveautés ou modifications dans les applications Platform update 30 pour Finance and Operations (novembre 2019)](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/whats-new-platform-update-30).

### <a name="remove-benefits-open-enrollment-preview-feature"></a>Permet de supprimer la fonctionnalité d'aperçu d'inscription en cours aux avantages

Conjointement à notre annonce dans Investissements stratégiques de la publication de blog d'excellence opérationnelle optimisée par Core HR, Microsoft supprime la fonctionnalité d'inscription en cours aux avantages de la version préliminaire publique le 18 octobre 2019. Au lieu de cela, la nouvelle fonctionnalité est lancée à l'avenir. L'utilisation de production de la fonctionnalité d'inscription en cours aux avantages actuellement en version préliminaire publique ne sera pas prise en charge.

### <a name="error-while-selecting-the-countryregion-on-the-worker-form-a-second-time-350294"></a>Erreur lors de la sélection du pays/de la région sur l'écran Collaborateur une seconde fois (350294)

Grâce à la version de cette semaine, le problème a été corrigé lors de la sélection d'un pays/d'une région sous l'écran **Collaborateur**.

### <a name="financial-dimension-values-default-to-the-combination-display-field-when-do-not-allow-manual-entry-is-set-to-true-340097"></a>Les valeurs de dimension financière prennent par défaut la valeur du champ Affichage de combinaison lorsque Ne pas autoriser la saisie manuelle est défini sur true (340097)

Avec cette modification, lors du paramétrage des dimensions financières et de l'utilisation de l'option n'autorisant pas la saisie manuelle, le système prend correctement par défaut la valeur de dimension dans le champ **Affichage de combinaison**.

### <a name="new-relationship-types-should-be-added-to-relationship-lookup-in-the-personal-contacts-form-347691"></a>De nouveaux types de relations doivent être ajoutés à la recherche de relation dans l'écran de contacts personnels (347691)

Cette version inclut de nouvelles capacités pour ajouter de nouveaux types de relations dans la table **Types de relations** et refléter ces modifications de la recherche de relation pour des contacts personnels.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-379599"></a>Les valeurs de liste supplémentaires dans les champs personnalisés ne sont pas reflétées dans Common Data Service (379599)

Avec la version de cette semaine, l'ajout d'une nouvelle valeur de liste à un champ personnalisé existant déjà synchronisé avec Common Data Service, les nouvelles valeurs de la liste de sélection s'affichent maintenant après l'application des modifications à l'entité.

### <a name="on-the-terms-of-employment-page-all-employees-terms-of-employment-appear-after-selecting-open-in-excel-348073"></a>Dans la page Conditions d'emploi, les conditions d'emploi de tous les employés s'affichent après avoir sélectionné Ouvrir dans Excel (348073)

Avec cette version, seuls les conditions d'emploi des employés sélectionnés s'afficheront dans Excel. Toute la sécurité de la société est également respectée.

### <a name="the-association-between-the-work-calendar-holiday-entity-and-the-work-calendar-entity-is-missing-in-common-data-service---324178"></a>L'association entre l'entité Congés du calendrier de travail et l'entité Calendrier de travail est manquante dans Common Data Service - (324178)

Cette relation a été ajoutée au lancement. Cette modification permet aux jours ouvrables d'un employé de s'afficher dans PowerApps. 

### <a name="error-when-using-employee-self-service-workflows-with-configurable-hierarchies-370132"></a>Erreur lors de l'utilisation des workflows en libre service des employés avec des hiérarchies configurables (370132)

Dans cette version, une meilleure communication est disponible sur la procédure de configuration des workflows avec des hiérarchies configurables. 

### <a name="system-allows-creation-of-new-positions-where-the-available-for-assignment-date-is-earlier-than-the-activation-date-340103"></a>Le système permet la création de nouveaux postes dans lesquels la date Disponible pour affectation est antérieure à la date d'activation (340103)

Cette modification affiche un avertissement lorsque la date **Disponible pour affectation** est antérieure à la date **Activation** du poste.

## <a name="coming-soon"></a>Prochainement

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Voir [Imprimer les examens des performances](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) dans Dynamics 365 : 2e partie du lancement 2019.

### <a name="feature-management-workspace"></a>Espace de travail Gestion des fonctionnalités

Les fonctionnalités sont ajoutées et mises à jour dans chaque version. L'expérience de gestion de la fonctionnalité fournit un espace de travail dans lequel vous pouvez afficher une liste des fonctionnalités fournies dans chaque version. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant.

Pour en savoir plus sur les modifications venant avec la gestion des fonctionnalités, voir [Vue d'ensemble de la gestion des fonctionnalités](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
