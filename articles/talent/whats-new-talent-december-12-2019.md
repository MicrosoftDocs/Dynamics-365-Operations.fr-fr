---
title: Nouveautés ou modifications dans Dynamics 365 Talent (10 décembre 2019)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/10/2019
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
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 18f86f5d87b780d5d4ffc83330d389077987dda6
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528169"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-10-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (10 décembre 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2660. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Espace de travail Gestion des fonctionnalités

L'espace de travail **Gestion des fonctions** fournit une liste des fonctions fournies dans chaque lancement. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant. Pour plus d'informations sur la gestion des fonctions, voir [Présentation de la gestion des fonctions](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Toutes les nouvelles fonctionnalités restent dans la version préliminaire pendant au moins 30 jours, et généralement entre 30 et 60 jours. Les fonctionnalités principales sont généralement disponibles en octobre et en avril chaque année suivant la période de version préliminaire. Dès que vous voyez de nouvelles fonctionnalités dans l'espace de travail **Gestion des fonctions**, vous pouvez les activer. Certaines fonctionnalités peuvent être activées par défaut.
 
Parfois, une fonctionnalité intégrale sera activée par défaut et ne pourra pas être désactivée (par exemple, l'espace de travail **Gestion des fonctions**).
 
Une fois qu’une fonction est généralement disponible, elle peut être activée ou désactivée dans les environnements de production. L'espace de travail **Gestion des fonctions** indique quand une fonction d'aperçu devient obligatoire. Cette date est généralement le 1er octobre ou le 1er avril pour s’aligner avec les plans de lancement semi-annuels. Vous ne pouvez pas désactiver les fonctions obligatoires. Tant qu'elle n'est pas obligatoire, vous pouvez activer et désactiver une fonction dans tous les environnements.

### <a name="streamlined-worker-form-has-moved-to-the-feature-management-workspace-390583"></a>Le formulaire de collaborateur simplifié a été déplacé vers l'espace de travail Gestion des fonctionnalités (390583)

Avec cette modification, le formulaire de collaborateur simplifié peut désormais être activé dans l'espace de travail **Gestion des fonctionnalités**. Cette fonctionnalité a été déplacée depuis le formulaire **Paramètres système** dans **Administration du système**.

### <a name="prevent-hcmworkerpayrollinfo-records-from-being-written-without-a-worker-value-394526"></a>Empêcher l'écriture des enregistrements HcmWorkerPayrollInfo sans valeur de collaborateur (394526)

Avec cette version, les enregistrements **HcmWorkerPayrollInfo** ne sont plus créés sans référence de travailleur dans ce scénario. 

### <a name="message-log-associated-to-the-action-isnt-populated-when-the-action-fails-to-complete-374007"></a>Le journal des messages associé à l'action n'est pas rempli lorsque l'action ne se termine pas (374007)

Cette version inclut une modification pour remplir le journal des messages d'action lorsqu'une action échoue dans certains scénarios. 

### <a name="common-data-service-integration-batch-job-creation-388030"></a>Création de traitements par lots d'intégration de Common Data Service (388030)

Avec cette modification, les traitements par lots pour l'intégration de Common Data Service sont créés lorsque le service est activé.

### <a name="additional-pick-list-values-to-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Les valeurs de liste de prélèvement supplémentaires des champs personnalisés ne sont pas reflétées dans Common Data Service après avoir cliqué sur appliquer sur le formulaire Champs personnalisés (379599)

Avec cette modification, les nouvelles valeurs de liste de prélèvement entrées dans Talent sont maintenant synchronisées avec Common Data Service lorsque vous appliquez vos modifications.

### <a name="update-to-common-data-service-for-then-leave-bank-transaction-entity-turns-into-an-insert-on-talent-side-352938"></a>Mise à jour de Common Data Service, car l'entité Transaction bancaire de congé se transforme en encart côté Talent (352938)

Cette modification corrige un problème où une mise à jour d'une Transaction bancaire de congé crée un enregistrement dans Talent.

## <a name="in-preview"></a>En mode aperçu

Les fonctions d'aperçu sont disponibles uniquement dans des environnements de **bac à sable**.

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Voir [Imprimer les examens des performances](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) dans Dynamics 365 : 2e partie du lancement 2019.

