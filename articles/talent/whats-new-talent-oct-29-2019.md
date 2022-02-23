---
title: Nouveautés ou modifications dans Dynamics 365 Talent (29 octobre 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 09d53c82b4244f20d0d7f301691b01263258a32f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529682"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (29 octobre 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2586. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a>Supprimer les parties sans rôles doit être activée par défaut (371233)

Lorsque vous mettez un nouvel environnement en service dans Talent, **Supprimer les parties si aucun rôle n'existe** est activée par défaut. Lorsque vous supprimez un employeur, la partie associée à l'employeur n'est pas supprimée tant que ce paramètre est activé. Cette modification limite les doublons dans le carnet d'adresses global lorsque vous devez importer, modifier, ou réimporter les employeurs.

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a>Les demandes de congés annulées et provisoires doivent être autorisées pour suppression dans Common Data Service (376999)

Avec cette modification, vous pouvez désormais supprimer des demandes de congés avec un statut **Brouillon** ou **Annulé** dans Common Data Service.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Les valeurs de liste supplémentaires dans les champs personnalisés ne sont pas reflétées dans Common Data Service après avoir cliqué sur le formulaire Champs personnalisés (379599)

Lorsque vous ajouter de nouvelles valeurs de liste à un champ personnalisé existant qui est déjà synchronisé avec Common Data Service, elles sont désormais disponibles dans Common Data Service une fois que vous appliquez vos modifications dans le formulaire **Champs personnalisés**.

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a>Appliquer les listes de contrôle d'intégration entre les entités juridiques lorsque plusieurs emplois existent (371270)

Dans la version de cette semaine, vous pouvez appliquer des listes de contrôle aux employés avec plusieurs emplois dans **Écran collaborateur > Listes de contrôle**.

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a>Permet de supprimer la fonctionnalité d'aperçu d'inscription qui a été supprimée

Conjointement à notre annonce dans la publication de blog [Investissements stratégiques dans Core HR optimisent l'excellence opérationnelle](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), Microsoft a supprimé la fonctionnalité d'inscription en cours aux avantages de la version préliminaire publique. La nouvelle fonctionnalité est lancée à l'avenir. L'utilisation en production des avantages de la fonctionnalité d'inscription en cours n'est pas prise en charge.

## <a name="coming-soon"></a>Prochainement

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Voir [Imprimer les examens des performances](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) dans Dynamics 365 : 2e partie du lancement 2019.

### <a name="feature-management-workspace"></a>Espace de travail Gestion des fonctionnalités

Les fonctionnalités sont ajoutées et mises à jour dans chaque version. L'expérience de gestion de la fonctionnalité fournit un espace de travail dans lequel vous pouvez afficher une liste des fonctionnalités fournies dans chaque version. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant.

Pour en savoir plus sur les modifications venant avec la gestion des fonctionnalités, voir [Vue d'ensemble de la gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
