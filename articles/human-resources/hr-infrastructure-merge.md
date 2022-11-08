---
title: Vue d’ensemble de la fusion de l’infrastructure Dynamics 365 Human Resources
description: Cet article décrit la fusion de l’infrastructure de Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f79ef3ed5db7583eb44b99e49c010778ce8524d1
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2022
ms.locfileid: "9733449"
---
# <a name="dynamics-365-human-resources-infrastructure-merge"></a>Fusion de l’infrastructure de Dynamics 365 Human Resources 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="dynamics-human-resources-365"></a>Dynamics 365 Human Resources

Microsoft Dynamics 365 Human Resources fournit des outils qui aident les équipes RH à accroître l’agilité organisationnelle, à transformer l’expérience des employés et à optimiser les programmes RH pour créer un lieu de travail où les personnes et l’entreprise peuvent prospérer. Pour en savoir plus sur Dynamics 365 Human Resources, voir [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Révolutionnez l’expérience des employés.** Retenez les meilleurs en responsabilisant les managers et les employés grâce à des expériences de libre-service connectées qui stimulent l’engagement et la croissance.
- **Optimiser les programmes RH.** Réduisez les coûts opérationnels et créez des programmes de gestion des congés et des absences, du temps, des avantages sociaux et de la rémunération centrés sur les personnes.
- **Augmenter l’agilité organisationnelle.** Permettez aux RH de fonctionner avec la dextérité dont l’entreprise a besoin en utilisant Dataverse et Microsoft Power Platform pour centraliser les données des personnes et étendre facilement Dynamics 365 Human Resources.
- **Découvrir les informations sur la main-d’œuvre.** Prenez des décisions basées sur les données grâce à la capacité d’analyser et de visualiser les données des personnes sur des tableaux de bord riches disponibles sur n’importe quel appareil.

## <a name="human-resources-infrastructure-merge"></a>Fusion de l’infrastructure Human Resources

Dynamics 365 Human Resources est une application autonome qui utilise actuellement une infrastructure différente des autres applications de finances et d’opérations, telles que Dynamics 365 Finance ou Dynamics 365 Supply Chain Management. La fusion des infrastructures permet d’intégrer Dynamics 365 Human Resources dans la même infrastructure que les autres applications de finances et d’opérations.

Pour en savoir plus sur la fusion de l’infrastructure de Human Resources, voir [Fusion des offres HR](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers/). Pour obtenir des réponses aux questions fréquentes, consultez la [FAQ sur la fusion de l’infrastructure de Human Resources](./hr-infrastructure-merge-faq.md).

## <a name="customer-migration-vs-customer-merge"></a>Comparaison entre la migration client et la fusion client

Dans le cadre de la fusion des infrastructures, toutes les fonctionnalités de l’application Human Resources ont été rendues disponibles dans les environnements de finances et d’opérations. Les clients peuvent migrer leurs environnements Human Resources à l’aide des outils de migration disponibles dans Microsoft Dynamics Lifecycle Services. Ils peuvent également éventuellement fusionner leurs données avec leur environnement de finances et d’opérations existant. 

La migration client et la fusion client diffèrent de la manière suivante :

- **Migration client** : l’outil de migration automatisé est utilisé pour effectuer une migration « lift-and-shift » (déplacement) de la base de données client depuis l’infrastructure Human Resources vers l’infrastructure des finances et des opérations. Le résultat est un nouvel environnement de finances et d’opérations qui utilise la base de données Human Resources du client. 
- **Fusion client** : cette étape supplémentaire n’est pas requise par Microsoft. Elle s’effectue à la discrétion du client et selon son propre calendrier. Au cours de cette étape, les données client sont déplacées vers un environnement existant, tel qu’un environnement Finance ou Project Operations. Elle est principalement manuelle et peut être effectuée à l’aide d’entités de données DMF (Data Management Framework). 

## <a name="planning-a-human-resources-environment-migration"></a>Planification de la migration d’un environnement Human Resources

Dans le cadre de la fusion de l’infrastructure, tous les clients devront migrer leurs environnements Human Resources existants à partir de l’infrastructure autonome. Pour faciliter ce processus, nous vous recommandons d’utiliser les outils de migration automatisés de Lifecycle Services pour déplacer vos environnements actuels vers la nouvelle infrastructure. 

Les sections suivantes fournissent plus de détails sur l’utilisation des outils Lifecycle Services pour migrer un environnement Human Resources autonome. 

Les clients qui planifient une migration peuvent avoir les attentes suivantes :

- Tous les clients devront migrer un environnement bac à sable avant de pouvoir migrer leur environnement de production. 
- Les outils de migration permettent uniquement de migrer des environnements bac à sable vers des environnements bac à sable, et des environnements de production vers des environnements de production. Par conséquent, votre type d’environnement déterminera quel environnement peut être migré de manière appropriée. 
- Les clients peuvent migrer autant d’environnements bac à sable que nécessaire avant de migrer leur environnement de production, à condition qu’un environnement bac à sable cible soit disponible. Les clients peuvent également supprimer un environnement bac à sable migré ou le remigrer plusieurs fois. 
- Si une migration bac à sable échoue ou si vous souhaitez recommencer, vous pouvez supprimer un environnement sur l’infrastructure des finances et des opérations et remigrer le même environnement.
- L’URL de votre environnement Human Resources sera différente après la migration.
- Planifiez une durée d’indisponibilité appropriée pour la migration de votre environnement de production. Le délai estimé pour l’achèvement du processus de migration automatisé est de trois à quatre heures. Ce délai varie en fonction des données de votre organisation. Vérifiez la durée nécessaire pendant la migration de vos environnements bac à sable et prévoyez du temps pour les éventuelles tâches manuelles supplémentaires qui doivent être effectuées.

> [!IMPORTANT] 
> Lorsqu’un environnement de production est migré avec succès vers l’infrastructure des finances et des opérations, l’environnement de production autonome source est automatiquement supprimé. Vous ne devez pas supprimer l’environnement de production migré. 

Le processus de migration est principalement automatique. Cependant, vos utilisateurs professionnels devront effectuer certaines étapes manuelles, ainsi que des vérifications après la migration.

Les étapes manuelles suivantes doivent être effectuées :

- Créez un projet Lifecycle Services pour la migration.
- Révisez toutes les intégrations de votre ancien environnement vers le nouvel environnement en faisant pointer l’intégration vers la nouvelle URL ou les nouveaux points de terminaison, en fonction de chaque configuration d’intégration.
- Actualisez la banque de données pour les rapports Power BI intégrés.
- Actualisez la liste des entités de données à partir de l’espace de travail DMF.
- Lien vers Lifecycle Services pour obtenir de l’aide.
- Créez des calendriers fiscaux.

Au cours du processus automatique, les actions suivantes sont réalisées et doivent être validées :

- Données :

    - Configurations
    - Rôles de sécurité (y compris les rôles personnalisés)
    - Flux de travail
    - Personnalisations et vues enregistrées
    - Transactions
    - Champs personnalisés
    - Pièces jointes

- Gestion des données – Apportez votre propre base de données (BYOD).
- Gestion des fonctions – Activez/désactivez des fonctions.
- Power Apps incorporé.
- Environnement attaché au centre d’administration Power Platform (production uniquement).
- Traitements par lots.
- Un registre vide est créé pour chaque entité juridique. Le type de taux de change et la devise comptable par défaut sont définis pour chaque registre.
- Un nouveau plan comptable est automatiquement créé et lié à la page **Registre** de chaque entité juridique. Les dimensions financières configurées dans votre environnement Human Resources seront automatiquement ajoutées à une nouvelle structure de compte et liées au registre comptable. 

> [!NOTE]
> Un registre comptable est requis dans l’infrastructure de finances et d’opérations dans le cadre du produit Dynamics 365 Finance. Le contrôleur de dimension personnalisé qui existait dans l’application autonome Dynamics 365 Human Resources n’est pas disponible. L’infrastructure fusionnée pour Human Resources dépend de la logique de Finance pour afficher les dimensions financières dans le module **Human Resources**. Pour en savoir plus sur le plan comptable et les dimensions financières, reportez-vous [ici](../finance/general-ledger/plan-chart-of-accounts.md). 

## <a name="considerations"></a>Observations

- La migration vers des environnements se fera toujours sur la dernière version en disponibilité générale (GA). En fonction de votre plan de migration et de test, si la validation de votre migration pour les environnements bac à sable concernait une version différente, nous vous recommandons de valider une migration d’environnement bac à sable sur la même version que celle de votre environnement de production. 
- Lors de la migration, les environnements migrés seront placés dans la même région que les environnements Human Resources autonomes sources.

## <a name="licensing"></a>Gestionnaire de licences

La licence de Dynamics 365 Human Resources ne subit aucune modification dans les domaines suivants : 

- **Exigence d’achat d’un nombre minimum de licences**
- **Licences pour un environnement de production et un environnement bac à sable** : si vous disposez de licences Human Resources autonomes existantes qui octroient un environnement de production et un environnement bac à sable, le même nombre de licences sera disponible sur l’infrastructure de finances et d’opérations, sans coût supplémentaire.
- **Licences bac à sable supplémentaires** : si vous avez acheté des licences bac à sable supplémentaires pour l’application Human Resources autonome, le même nombre de licences bac à sable est disponible pour un environnement de test d’acceptation utilisateur standard (bac à sable) sur l’infrastructure de finances et d’opérations, sans coût supplémentaire. 
