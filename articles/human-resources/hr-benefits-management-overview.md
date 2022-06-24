---
title: Vue d’ensemble de la gestion des avantages sociaux
description: Cet article fournit une vue d’ensemble de la fonctionnalité de gestion des avantages dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/06/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f008c273a3088353c33ae8c4b0b3cbc6b274fbcf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901145"
---
# <a name="benefits-management-overview"></a>Vue d’ensemble de la gestion des avantages


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Pour rester compétitif, vous devez offrir un riche ensemble d’avantages pour attirer et retenir vos meilleurs employés. En plus des avantages standard comme la couverture médicale et dentaire, vous voudrez peut-être également offrir des services étendus comme l’aide à l’adoption, les programmes de loisirs et les allocations vestimentaires. La fonction de gestion des avantages dans Microsoft Dynamics 365 Human Resources offre une solution flexible qui prend en charge une grande variété d’options d’avantages. Human resources inclut également une expérience utilisateur facile à utiliser qui met en valeur vos offres.

- Les régimes d’avantages sociaux améliorés vous permettent de créer et de gérer des régimes d’avantages sociaux uniques et de prendre en charge des tableaux de taux complexes et des niveaux imbriqués. Vous pouvez facilement créer des programmes d’avantages, des offres groupées et des règles d’inscription automatique pour une expérience utilisateur plus facile.
- Les programmes de crédits flexibles vous permettent de répartir au prorata la retraite et d’autres événements de vie.
- Des règles d’éligibilité étendues garantissent que vous offrez les bons avantages aux bons employés.
- L’inscription aux avantages en ligne offre une expérience facile à vos employés.
- Le traitement des événements de vie qualifiés prend en charge les événements de vie futurs.

Si vous souhaitez accéder aux données de démonstration, vous devrez redéployer votre environnement de bac à sable.

> [!NOTE]
> Vous pouvez désormais personnaliser les pages de gestion des avantages sociaux. Des champs personnalisés liés aux taux de couverture peuvent être ajoutés à la page **Option de couverture** pour les régimes d’avantages sociaux. Pour plus d’informations sur l’utilisation des champs personnalisés, voir [Champs personnalisés](hr-developer-custom-fields.md).
>
> ![Champs personnalisés de gestion des avantages sociaux](media/hr-benefits-management-custom-fields.png)

## <a name="enable-benefits-management"></a>Activation de la gestion des avantages sociaux

Cet article décrit comment activer les fonctionnalités dans Human Resources. Il explique également les fonctionnalités existantes dans Human Resources qui sont remplacées par la Gestion des avantages et les fonctionnalités qui sont désactivées après l’activation de la Gestion des avantages.

> [!IMPORTANT]
> Après avoir activé la gestion des avantages sociaux dans un environnement de type **Production**, vous ne pouvez pas le désactiver. Nous vous recommandons d’activer et de tester la gestion des avantages dans un environnement de type **Bac à sable** avant de l’activer dans un environnement de type **Production**. Il existe des différences importantes entre l’ancienne fonctionnalité Avantage et la nouvelle fonctionnalité de gestion des avantages qui nécessitent une configuration supplémentaire et doivent être testées avant d’être mises en production.

Pour plus d’informations, voir [Gérer les fonctionnalités](hr-admin-manage-features.md).

## <a name="process-overview"></a>Vue d’ensemble du processus

Le processus de configuration des avantages implique les tâches suivantes :

1.  Configurer les informations requises sur les avantages.
2.  Configurer les informations facultatives sur les avantages.
3.  Configurer des régimes d’avantages.
4.  Configurer des programmes de crédit flexibles (facultatif).
5.  Configurer les informations requises sur les employés.
6.  Configurer les informations facultatives sur les employés.
7.  Traiter les employés pour déterminer leur admissibilité.
8.  Les employés sélectionnent les régimes via le libre service employé (facultatif).
9.  Confirmer les sélections de régime des employés.
10. Traitement des événements de la vie (facultatif).
11. Mettre à jour les taux (facultatif).

## <a name="set-up-required-benefit-information"></a>Configurer les informations requises sur les avantages

Avant que les employés ne puissent souscrire à des régimes, plusieurs composants doivent être configurés :

- **Paramètres de gestion des avantages** : ces paramètres sont partagés entre les sociétés. Vous pouvez définir des codes motif par défaut, activer l’option **Salaire annuel avec avantages**, définir une fréquence de paiement par défaut pour les nouvelles recrues et activer les événements de la vie. Pour plus d’informations, consultez [Paramètres de la Gestion des avantages](hr-benefits-setup-parameters.md).
- **Options d’admissibilité des contacts personnels** : les contacts personnels sont les personnes qui seront soit à charge, soit bénéficiaires des régimes mis en place. Il s’agit généralement des enfants, des conjoints ou d’organismes de fiducie. Pour en savoir plus, voir [Configurer les options d’éligibilité des contacts personnels](hr-benefits-setup-contact-eligibility-options.md).
- **Options de couverture** : configurez les types de couverture qui seront disponibles pour un régime. Plus particulièrement, définissez qui doit être couvert, ou l’étendue de la couverture disponible. Pour plus d’informations, voir [Créer des options de couverture](hr-benefits-setup-coverage-options.md).
- **Types de régime** : configurez les types de régimes qui seront disponibles lorsque vous créez un régime d’avantages. Des exemples de types de régime sont notamment **Dentaire**, **Vision**, et **Épargne**. Certains paramètres importants du type de régime déterminent les paramètres disponibles dans le régime d’avantages. Pour plus d’informations, voir [Création de types de plan](hr-benefits-setup-plan-types.md).
- **Règles d’admissibilité** : les règles d’admissibilité servent à déterminer si un employé est admissible à un régime. Au moins une règle d’admissibilité doit être associée à chaque régime d’avantages. Pour en savoir plus, voir [Configurer les règle d’admissibilité et les options](hr-benefits-setup-eligibility-rules.md).
- **Fréquences de paiement** : les fréquences de paiement sont requises lorsque des taux d’avantage sont configurés. La fréquence de paiement utilisée sur un taux permet d’identifier le montant que l’employé et/ou l’employeur doit sur une base hebdomadaire, mensuelle ou annuelle. Pour plus d’informations, voir [Paramétrer des fréquences de paiement](hr-benefits-setup-payment-frequencies.md).
- **Taux** : les taux définissent combien un avantage coûtera à l’employé ou à l’employeur. Si de l’argent doit être réaffecté à un employé (par exemple, un crédit pour un abonnement de gym), un taux négatif est entré. Pour plus d’informations, voir [Configurer les taux](hr-benefits-setup-rates.md).
- **Taux échelonnés** : les taux échelonnés sont utilisés lorsqu’un taux doit changer en fonction de certains critères. Le taux échelonné le plus courant est un niveau unique basé sur l’âge. Cependant, il est également possible de configurer des taux à deux niveaux, où le taux peut changer en fonction du sexe, de l’âge ou d’autres critères.
- **Déductions** : les déductions sont essentiellement les informations/codes d’en-tête qui seront transmis au système de paie pour identifier la déduction pour l’avantage. Vous devez mettre en place ces déductions, car elles seront exigées sur le régime d’avantages sociaux. Pour plus d’informations, voir [Configurer les déductions](hr-benefits-setup-deductions.md).
- **Périodes de prestations** : une période de prestations est la période pendant laquelle les employés auront une couverture de prestations. On la désigne aussi comme une année de régime. Les périodes d’ouverture des inscriptions sont également définies ici.

## <a name="set-up-optional-benefit-information"></a>Configurer les informations facultatives sur les avantages

Les composants suivants n’ont pas besoin d’être configurés pour créer un régime d’avantages :

- **Programmes** : un programme est un ensemble de prestations qui sont régies par les mêmes règles d’admissibilité. Par exemple, tout le monde dans le service des ventes peut avoir un téléphone portable.
- **Offres groupées** : une offre groupée est un groupe d’avantages, où un régime doit être sélectionné avant que l’option permettant de sélectionner des plans supplémentaires ne soit disponible. Par exemple, un régime médical à franchise élevée peut être associé à un plan de compte d’épargne santé (HSA).
- **Types d’événements de la vie** : les événements de la vie sont des événements qui permettent de modifier la couverture d’un employé. Les types d’événements de la vie sont liés à un type de régime. Par exemple, un type de régime d’assurance-maladie peut permettre des modifications des régimes en raison d’une naissance ou d’une adoption, ou en raison d’un changement d’état marital. Cependant, un type de régime d’assurance peut ne pas permettre de changements en raison d’événements de la vie. Pour plus d’informations, voir [Configurer les types d’événements de la vie](hr-benefits-setup-life-event-types.md).
- **Jours d’attente et délais d’attente** : une période d’attente de couverture peut être définie pour un régime d’avantages. Par exemple, un employé nouvellement embauché pourrait ne pouvoir s’inscrire à un 401 (k) qu’après trois mois d’emploi. Dans ce cas, le délai d’attente est de trois mois. Les jours d’attente sont utilisés dans le délai d’attente si les nouvelles inscriptions ne peuvent être traitées et soumises au prestataire qu’en un seul jour du mois. Par exemple, si les inscriptions 401 (k) ne peuvent être traitées que le quinze du mois, après trois mois d’emploi, le délai d’attente mis en place est de trois mois et le jour d’attente est le quinze. Pour plus d’informations, consultez [Configurer les jours d’attente](hr-benefits-setup-waiting-days.md) et [Configurer les délais d’attente](hr-benefits-setup-waiting-periods.md).
- **Codes motif** : les codes motif sont utilisés pour expliquer pourquoi un avantage peut évoluer pour un employé. Pour plus d’informations, voir [Configurer des codes motif](hr-benefits-setup-reason-codes.md).

## <a name="set-up-benefit-plans"></a>Configurer des plans d’avantages

Lorsque vous établissez un régime d’avantages, vous devez suivre les étapes suivantes avant que les employés ne puissent y souscrire :

- Affectez une période d’avantage.
- Joignez les options de couverture.
- Définissez une date de début et de fin de validité sur l’onglet **Général**.
- Affectez au moins une règle d’éligibilité.
- Définissez le champ **Autoriser/continuer l’inscription** sur l’onglet **Paramétrage**.

Pour plus d’informations sur la procédure de paramétrage des régimes d’avantages, voir [Configurer des régimes d’avantages](hr-benefits-plans-setup.md).

## <a name="set-up-flex-credit-programs-optional"></a>Configurer des programmes de crédit flexibles (facultatif)

Vous pouvez utiliser des programmes de crédits flexibles pour inscrire les employés aux avantages, sur la base d’un nombre prédéterminé de crédits flexibles. Les employés peuvent choisir comment allouer leurs crédits flexibles. Par exemple, si les employés sont déjà couverts par le régime d’assurance-maladie de leur conjoint, ils n’ont pas à utiliser leurs crédits pour une couverture maladie. Par conséquent, ils peuvent vouloir les utiliser pour d’autres avantages. Pour plus d’informations sur les programmes de crédits flexibles, voir [Configurer des programmes de crédits flexibles](hr-benefits-plans-flex-credit-programs.md).

## <a name="configure-required-employee-information"></a>Configurer les informations requises sur les employés

Avant de pouvoir inscrire des employés aux avantages sociaux, vous devez fournir les informations requises à leur sujet. 

L’employé doit avoir un **Poste** affecté. Un **Poste** peut être affecté à l’employé sur les pages **Collaborateur** ou **Poste** en mettant à jour l’**Affectation du collaborateur**. 

Les employés doivent ensuite souscrire à un régime de rémunération le jour où ils commencent, ou bénéficier d’un **salaire annuel et d’avantages sociaux**. Avant d’attribuer une **Rémunération fixe** à un employé, un **Poste** doit être attribué. 

> [!NOTE] 
> La **Date de début de la rémunération fixe** ne peut pas être antérieure à la **Date d’attribution du poste**.

Sinon, si vous avez un employé qui reçoit une rémunération supplémentaire, comme des commissions, vous pouvez ajouter un montant **Salaire annuel avec avantages** depuis l’enregistrement de l’employé. Human Resources utilise le montant **Salaire annuel avec avantages** lors de la détermination des montants de couverture, au lieu du montant **Rémunération fixe annuelle**. Le **Salaire annuel avec avantages** doit être valide à la date de début de l’employé ou au début de la période de prestation, selon quelle date est la plus récente. Cependant, un poste n’est pas tenu d’attribuer le **Salaire annuel avec avantages**. Pour activer la fonctionnalité **Salaire annuel avec avantages**, allez sur la page **Paramètres partagés de Human Resource**, sur l’onglet **Gestion des avantages**. Cette fonctionnalité est désactivée par défaut.

> [!IMPORTANT]
> Si une **Rémunération fixe** et un **Salaire annuel avec avantages** sont entrés pour un employé, le **Salaire annuel avec avantages** sera utilisé pour déterminer les montants de couverture. Dans la section **Détails de l’emploi** de la page **Collaborateur**, vous devez sélectionner une valeur dans le champ **Fréquence de versement des avantages**.

## <a name="configure-optional-employee-information"></a>Configurer les informations facultatives sur les employés
Lorsque vous créez un régime d’avantages sociaux qui utilise des taux basés sur le sexe ou l’âge, vous devez saisir une date de naissance et un sexe pour l’employé afin de calculer le coût des avantages sociaux.

## <a name="process-employees-to-determine-eligibility"></a>Traiter les employés pour déterminer leur admissibilité
Avant que les employés ne puissent souscrire à des régimes, le traitement de l’admissibilité est exécuté pour déterminer les plans auxquels ils sont éligibles. Vous pouvez afficher les résultats du processus d’admissibilité dans la **Visionneuse des résultats du traitement**. Pour plus d’informations, voir [Traitement de l’admissibilité à l’inscription](hr-benefits-process-enrollment-eligibility.md).

## <a name="employees-select-plans-using-employee-self-service-optional"></a>Les employés sélectionnent les régimes via le **Libre service employé** (facultatif)

Lors des affiliations, lorsque des employés sont embauchés ou qu’un événement de la vie se produit, les employés peuvent sélectionner ou mettre à jour leurs avantages via le **Libre-service employé**. Pour plus d’informations, voir [Configurer le libre-service employé](hr-benefits-setup-employee-self-service.md).

## <a name="confirm-employee-plan-selections"></a>Confirmer les sélections de régime des employés

Les avantages que les employés choisissent doivent être confirmés avant que les employés ne soient considérés comme inscrits. Les avantages peuvent également être sélectionnés au nom d’un employé. Pour sélectionner ou valider des avantages, sur la page **Employé**, sur l’onglet **Avantages**, sélectionnez **Régimes d’avantages du collaborateur**. Pour sélectionner ou confirmer les avantages pour plusieurs employés, utilisez la page **Mise à jour en bloc des régimes d’avantages des collaborateurs**.

## <a name="life-event-processing-optional"></a>Traitement des événements de la vie (facultatif)

Au cours du cycle de vie des employés, chacun peut vivre divers événements de la vie, tels qu’un mariage, des changements d’emploi ou des changements de personnes à charge ou de bénéficiaires. Pour utiliser les événements de la vie, vous devez les activer sur la page **Paramètres partagés des ressources humaines**. Configurez les types d’événements de la vie et les options associées pour les types de régimes.

Avant de pouvoir traiter des événements de la vie, vous devez avoir exécuté l’ouverture des inscriptions au moins une fois au cours d’une période d’embauche. Aux États-Unis, l’ouverture des inscriptions a généralement lieu une fois par an. En dehors des États-Unis, l’ouverture des inscriptions peut avoir lieu au moment de l’embauche. Le traitement des événements de la vie n’exige pas que les collaborateurs choisissent un régime d’avantages. Cependant, les collaborateurs doivent avoir été inclus dans le traitement de l’ouverture des inscriptions. Pour plus d’informations, voir les rubriques suivantes :

- [Traiter les événements de vie](hr-benefits-process-life-events.md)
- [Traiter les modifications des événements de vie](hr-benefits-process-life-event-changes.md)
- [Traiter l’éligibilité aux événements de vie](hr-benefits-process-life-event-eligibility.md)

## <a name="rate-updates-optional"></a>Mettre à jour les taux (facultatif)

Parfois, le taux d’un avantage change pendant la durée du régime. Pour mettre à jour les taux des employés déjà inscrits au régime, vous devez traiter les modifications de taux. Pour plus d’informations, voir [Traiter les modifications de taux](hr-benefits-process-rate-changes.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
