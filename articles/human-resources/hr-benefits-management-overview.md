---
title: Vue d'ensemble de la gestion des avantages
description: Présentation de la fonction d'aperçu de la gestion des avantages dans Dynamics 365 Human Resources. Offrez à vos employés des options d'avantages étendues avec une expérience en ligne facile à utiliser.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029461"
---
# <a name="benefits-management-overview"></a>Vue d'ensemble de la gestion des avantages

[!include [banner](includes/preview-feature.md)]

Pour rester compétitif, vous devez offrir un riche ensemble d'avantages pour attirer et retenir vos meilleurs employés. En plus des avantages standard comme la couverture médicale et dentaire, vous voudrez peut-être également offrir des services étendus comme l'aide à l'adoption, les programmes de loisirs et les allocations vestimentaires. La fonction d'aperçu de la gestion des avantages dans Microsoft Dynamics 365 Human Resources vous offre une solution flexible qui prend en charge une grande variété d'options d'avantages. Human resources inclut également une expérience utilisateur facile à utiliser qui met en valeur vos offres.

- Les plans d'avantages améliorés vous permettent de créer et de gérer des plans d'avantages uniques et de prendre en charge des tableaux de taux d'avantages complexes et des niveaux imbriqués. Vous pouvez facilement créer des programmes d'avantages, des offres groupées et des règles d'inscription automatique pour une expérience utilisateur plus facile.

- Les programmes de crédits flexibles vous permettent de répartir au prorata la retraite et d'autres événements de vie.

- Des règles d'éligibilité étendues garantissent que vous offrez les bons avantages aux bons employés.

- L'inscription aux avantages en ligne offre une expérience facile à vos employés.

- Le traitement des événements de vie qualifiés s'intègre au libre-service employé et prend également en charge les événements de vie futurs.

Si vous souhaitez accéder aux données de démonstration, vous devrez redéployer votre environnement de bac à sable.

Vous pouvez envoyer des commentaires directs ou signaler des problèmes à : D365BenefitsPreview@microsoft.com.

## <a name="benefits-management-known-issues"></a>Problèmes connus liés à la gestion des avantages

### <a name="eligibility-processing"></a>Traitement de l'éligibilité

Lors de l'exécution de l'éligibilité aux avantages qui utilisent un salaire de 1 à 5X, un pourcentage du salaire et un montant forfaitaire, vous devez définir la date **Détails de l'avantage** sur la **Date de début de contrat de l'employé** dans l'**Historique des emplois**. Vous devez également inclure **Heures travaillées**, **Fréquence de paiement** et **Montant du salaire annuel des avantages**. Si le collaborateur a une rémunération fixe, entrez **Heures travaillées**et **Fréquence de paiement**. Le montant du salaire annuel sera calculé. Si l'employé est salarié, il est inutile d'entrer les **Heures travaillées**. Nous recommandons que lors de la création de nouveaux employés, vous entriez d'abord la rémunération fixe. Pour mettre à jour l'enregistrement des détails des avantages, accédez à **Collaborateur > Historique du collaborateur > Détails de l'emploi**. Ajustez la date selon la date de début du collaborateur.

### <a name="employee-self-service"></a>Libre service employé

Le montant de l'employé n'est pas calculé lors de la mise à jour du montant de la couverture d'assurance-vie. Par exemple, lorsqu'un employé se voit proposer un régime d'assurance-vie, il peut sélectionner jusqu'à 50 000 $ de couverture au coût de 0,36 $ par 1 000 $ de couverture.  Lorsque l'employé met à jour le montant de la couverture, le coût associé pour l'employé reste nul.

Pour un plan d'avantages qui ne permet qu'une seule sélection de ce type de plan, l'utilisateur reçoit une erreur s'il tente de renoncer à un plan après l'avoir sélectionné. Par exemple, un utilisateur sélectionne un plan médical et le place dans son panier. L'utilisateur sélectionne ensuite **Renoncer** pour un autre plan médical. L'utilisateur recevra une erreur.

## <a name="enable-benefits-management"></a>Activation de la gestion des avantages

La gestion des avantages est une fonction d'aperçu et elle n'est disponible que dans les environnements **Bac à sable**. Ces articles décrivent comment activer les fonctionnalités d'aperçu dans Human Resources. Ils indiquent également les fonctionnalités existantes dans Human Resources que la gestion des avantages remplace ou qui sont désactivées une fois que vous avez activé la gestion des avantages.

- [Gérer les fonctionnalités](hr-admin-manage-features.md)
- [Fonctionnalité en préversion : gestion des avantages](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a>Configuration de la gestion des avantages

Avant de pouvoir créer des plans d'avantages pour vos employés, vous devez configurer les options des plans.

- [Configuration des paramètres de gestion des avantages](hr-benefits-setup-parameters.md)
- [Configuration des règles et des options d'admissibilité](hr-benefits-setup-eligibility-rules.md)
- [configuration des options d'éligibilité des contacts personnels](hr-benefits-setup-contact-eligibility-options.md)
- [Créer des options de couverture](hr-benefits-setup-coverage-options.md)
- [Paramétrage des fréquences de paiement](hr-benefits-setup-payment-frequencies.md)
- [Configuration des types d'événements de vie](hr-benefits-setup-life-event-types.md)
- [Création de types de plan](hr-benefits-setup-plan-types.md)
- [Paramétrer des codes motif](hr-benefits-setup-reason-codes.md)
- [Paramétrage des codes de niveau](hr-benefits-setup-tier-codes.md)
- [Configuration des taux](hr-benefits-setup-rates.md)
- [Configuration des déductions](hr-benefits-setup-deductions.md)
- [Configuration des jours d'attente](hr-benefits-setup-waiting-days.md)
- [Configuration des périodes d'attente](hr-benefits-setup-waiting-periods.md)
- [Paramétrage des règles d'arrondi](hr-benefits-setup-rounding-rules.md)
- [Création de catégories d'emploi](hr-benefits-setup-employment-categories.md)
- [Configuration des types d'emploi](hr-benefits-setup-employment-types.md)
- [Configuration du libre-service employé](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Création de plans d'avantages

Ces articles montrent comment créer des plans d'avantages, y compris des offres groupées et des programmes de crédits flexibles.

- [Paramétrage de plans d'avantages](hr-benefits-plans-setup.md)
- [Création de plans d'avantages pour les collaborateurs](hr-benefits-plans-worker.md)
- [Configuration de programmes de crédits flexibles](hr-benefits-plans-flex-credit-programs.md)
- [Configuration des événements de vie futurs](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a>Traitement des plans d'avantages

Vous devez traiter certaines de vos modifications pour les rendre actives.

- [Processus d'éligibilité à l'inscription](hr-benefits-process-enrollment-eligibility.md)
- [Traitement des événements de vie](hr-benefits-process-life-events.md)
- [Traitement des changements d'événement de vie](hr-benefits-process-life-event-changes.md)
- [Processus d'éligibilité à un événement de vie](hr-benefits-process-life-event-eligibility.md)
- [Traitement des modifications de taux](hr-benefits-process-rate-changes.md)

