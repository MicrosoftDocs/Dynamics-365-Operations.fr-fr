---
title: Vue d'ensemble de la gestion des avantages
description: Présentation de la fonction de gestion des avantages dans Dynamics 365 Human Resources. Offrez à vos employés des options d'avantages étendues avec une expérience en ligne facile à utiliser.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 91a4425b4f020f90843bb3b0b280b7ee28463670
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230152"
---
# <a name="benefits-management-overview"></a>Vue d'ensemble de la gestion des avantages

Pour rester compétitif, vous devez offrir un riche ensemble d'avantages pour attirer et retenir vos meilleurs employés. En plus des avantages standard comme la couverture médicale et dentaire, vous voudrez peut-être également offrir des services étendus comme l'aide à l'adoption, les programmes de loisirs et les allocations vestimentaires. La fonction de gestion des avantages dans Microsoft Dynamics 365 Human Resources vous offre une solution flexible qui prend en charge une grande variété d'options d'avantages. Human resources inclut également une expérience utilisateur facile à utiliser qui met en valeur vos offres.

- Les plans d'avantages améliorés vous permettent de créer et de gérer des plans d'avantages uniques et de prendre en charge des tableaux de taux d'avantages complexes et des niveaux imbriqués. Vous pouvez facilement créer des programmes d'avantages, des offres groupées et des règles d'inscription automatique pour une expérience utilisateur plus facile.

- Les programmes de crédits flexibles vous permettent de répartir au prorata la retraite et d'autres événements de vie.

- Des règles d'éligibilité étendues garantissent que vous offrez les bons avantages aux bons employés.

- L'inscription aux avantages en ligne offre une expérience facile à vos employés.

- Le traitement des événements de vie qualifiés prend en charge les événements de vie futurs.

Si vous souhaitez accéder aux données de démonstration, vous devrez redéployer votre environnement de bac à sable.

## <a name="benefits-management-known-issues"></a>Problèmes connus liés à la gestion des avantages

### <a name="flex-credit-programs"></a>Programmes de crédit flexible

La valeur totale du crédit définie pour un programme de crédit flexible ne s'affiche pas dans le formulaire **Plans d'avantages des collaborateurs**. De plus, si vous définissez un programme de crédit flexible comme ayant une règle de prorata définie sur **Aucune**, vous obtenez une erreur dans le formulaire **Plans d'avantages pour les collaborateurs** lors de la sélection et de la confirmation des plans.

## <a name="enable-benefits-management"></a>Activation de la gestion des avantages

Cet article décrit comment activer les fonctionnalités dans Human Resources. Il indique également les fonctionnalités existantes dans Human Resources que la gestion des avantages remplace ou qui sont désactivées une fois que vous avez activé la gestion des avantages.

> [!IMPORTANT]
> Après avoir activé la gestion des avantages dans un environnement de type **Production**, vous ne pouvez pas le désactiver. Nous vous recommandons d'activer et de tester la gestion des avantages dans un environnement de type **Bac à sable** avant de l'activer dans un environnement de type **Production**. Il existe des différences importantes entre l'ancienne fonctionnalité Avantage et la nouvelle fonctionnalité de gestion des avantages qui nécessitent une configuration supplémentaire et doivent être testées avant d'être mises en production.

- [Gérer les fonctionnalités](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a>Configurer des informations relatives aux employés

Avant de pouvoir inscrire des employés aux avantages sociaux, vous devez fournir les informations requises. Vous devez inscrire un employé dans un **Plan de rémunération fixe** à leur date de début, et vous devez sélectionner une **Fréquence de versement des avantages** dans **Détails de l'emploi** sur le formulaire **Collaborateur**.

Lorsque vous créez un plan d'avantages qui utilise des taux basés sur le sexe ou l'âge, vous devez saisir une date de naissance et un sexe pour l'employé afin de calculer le coût des avantages.

## <a name="configure-benefits-management"></a>Configurer la gestion des avantages

Avant de pouvoir créer des plans d'avantages pour vos employés, vous devez configurer les options des plans.

- [Configuration des paramètres de gestion des avantages](hr-benefits-setup-parameters.md)
- [Configuration des règles et des options d'admissibilité](hr-benefits-setup-eligibility-rules.md)
- [Configurer les options d'éligibilité des contacts personnels](hr-benefits-setup-contact-eligibility-options.md)
- [Créer des options de couverture](hr-benefits-setup-coverage-options.md)
- [Configurer les fréquences de paiement](hr-benefits-setup-payment-frequencies.md)
- [Configurer les types d'événements de vie](hr-benefits-setup-life-event-types.md)
- [Créer des types de plan](hr-benefits-setup-plan-types.md)
- [Paramétrer des codes motif](hr-benefits-setup-reason-codes.md)
- [Configurer les codes de niveau](hr-benefits-setup-tier-codes.md)
- [Configurer les taux](hr-benefits-setup-rates.md)
- [Configurer les déductions](hr-benefits-setup-deductions.md)
- [Configurer les jours d'attente](hr-benefits-setup-waiting-days.md)
- [Configurer les périodes d'attente](hr-benefits-setup-waiting-periods.md)
- [Configurer les règles d'arrondi](hr-benefits-setup-rounding-rules.md)
- [Créer des catégories d'emploi](hr-benefits-setup-employment-categories.md)
- [Configuration des types d'emploi](hr-benefits-setup-employment-types.md)
- [Configuration du libre-service employé](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Création de plans d'avantages

Ces articles montrent comment créer des plans d'avantages, y compris des offres groupées et des programmes de crédits flexibles.

- [Configurer des plans d'avantages](hr-benefits-plans-setup.md)
- [Configurer des programmes de crédit flexibles](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a>Traiter les plans d'avantages

Vous devez traiter certaines de vos modifications pour les rendre actives.

- [Processus d'éligibilité à l'inscription](hr-benefits-process-enrollment-eligibility.md)
- [Traitement des événements de vie](hr-benefits-process-life-events.md)
- [Traitement des changements d'événement de vie](hr-benefits-process-life-event-changes.md)
- [Processus d'éligibilité à un événement de vie](hr-benefits-process-life-event-eligibility.md)
- [Traitement des modifications de taux](hr-benefits-process-rate-changes.md)

