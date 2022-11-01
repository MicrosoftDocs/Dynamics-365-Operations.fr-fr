---
title: FAQ sur la fusion d’infrastructure de Dynamics 365 Human Resources
description: Cet article répond aux questions fréquemment posées sur la fusion d’infrastructure pour Microsoft Dynamics 365 Human Resources et les applications de finances et d’opérations.
author: twheeloc
ms.date: 09/13/2021
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
ms.openlocfilehash: 32698d887b4d228ded588984b09068e3e2fef9a4
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702065"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>FAQ sur la fusion d’infrastructure de Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="what-is-dynamics-365-human-resources"></a>Qu'est-ce que Dynamics 365 Human Resources ?

Microsoft Dynamics 365 Human Resources fournit des outils qui aident les équipes RH à accroître l’agilité organisationnelle, à transformer l’expérience des employés et à optimiser les programmes RH pour créer un lieu de travail où les personnes et l’entreprise peuvent prospérer. Pour en savoir plus sur Dynamics 365 Human Resources, voir [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Révolutionnez les expériences des employés.** Retenez les meilleurs en responsabilisant les managers et les employés grâce à des expériences de libre-service connectées qui stimulent l’engagement et la croissance.
- **Optimiser les programmes RH.** Réduisez les coûts opérationnels et créez des programmes de gestion des congés et des absences, du temps, des avantages sociaux et de la rémunération centrés sur les personnes.
- **Augmenter l’agilité organisationnelle.** Permettez aux RH de fonctionner avec la dextérité dont l’entreprise a besoin en utilisant Dataverse et Microsoft Power Platform pour centraliser les données des personnes et étendre facilement Dynamics 365 Human Resources.
- **Découvrir les informations sur la main-d’œuvre.** Prenez des décisions basées sur les données grâce à la capacité d’analyser et de visualiser les données des personnes sur des tableaux de bord riches disponibles sur n’importe quel appareil.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Valeur ajoutée et avantages de la fusion des infrastructures

### <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Qu’est-ce que la fusion d’infrastructure pour Dynamics 365 Human Resources ?

Il existe actuellement deux ensembles distincts de fonctionnalités RH sur deux infrastructures différentes dans Dynamics 365 :

- **Dynamics 365 Human Resources** – Une application autonome qui s’exécute sur une infrastructure indépendante. Lorsque cette application a été lancée, l’infrastructure était séparée des autres applications d’opérations Dynamics 365. Nos clients utilisent cette application pour accroître l’agilité organisationnelle, optimiser les programmes RH, transformer les expériences des employés et obtenir des informations sur la main-d’œuvre.
- **Module RH** – Un ensemble de fonctionnalités héritées qui faisait auparavant partie de l’unité de gestion des stocks de licences des opérations unifiées (SKU). Le module RH s’exécute sur l’infrastructure de finances et d’opérations, qui est la même dans toutes les applications d’exploitation. Ces applications incluent Dynamics 365 Finance, Dynamics 365 Project Operations et Dynamics 365 Supply Chain Management. Les clients ont reçu les fonctionnalités RH dans le cadre de Dynamics 365 Finance ou Dynamics 365 Supply Chain Management.

Au cours des trois dernières années, Microsoft n’a ajouté aucune nouvelle fonctionnalité ou amélioration au module RH. Au lieu de cela, les investissements de notre feuille de route se sont concentrés sur l’application Dynamics 365 Human Resources.

En réunissant ces deux ensembles de fonctionnalités sur la même infrastructure, nous aiderons nos clients à bénéficier des avantages suivants :

- Les améliorations qui ont été ajoutées à Dynamics 365 Human Resources au cours des trois dernières années, y compris l’amélioration des congés et des absences, la gestion des avantages sociaux et la production de rapports.
- Extensibilité améliorée grâce à Microsoft Power Platform et la possibilité d’étendre la logique métier pour personnaliser les pages.
- Le déploiement amélioré, les mises à jour et la maintenance sont cohérents en termes d’Application Lifecycle Management (ALM), de Lifecycle Services (LCS), de disponibilité géographique, etc.
- Davantage d’innovation technologique, car notre équipe d’ingénieurs utilise des services partagés, des outils et des coûts de plate-forme réduits.

Cette transition affectera les clients qui utilisent actuellement soit Dynamics 365 Human Resources ou l’ancien module RH.

## <a name="glossary-of-terms-used-in-this-faq"></a>Glossaire des termes utilisés dans cette FAQ

- **Dynamics 365 Human Resources** – Notre produit actuel et futur qui offre des capacités RH au marché.
- **Module RH** – Un ensemble de fonctionnalités héritées qui faisait auparavant partie de l’unité de gestion des stocks de licences des opérations unifiées (SKU). Les fonctionnalités sont activées lorsqu’un client possède Dynamics 365 Finance ou Dynamics 365 Supply Chain Management.
- **Infrastructure de finances et d’opérations** : l’architecture de développement utilisée par le portefeuille des opérations, y compris Dynamics 365 Finance, Dynamics 365 Supply Chain Management et Dynamics 365 Project Operations. Cette infrastructure est celle qui sera utilisée à l’avenir. Dans cette FAQ, le terme *infrastructure fusionnée* fait référence à l’environnement de finances et d’opérations.
- **Infrastructures de Human Resources** : l’architecture de développement historiquement utilisée pour l’application Dynamics 365 Human Resources. Le projet de fusion des infrastructures permet d’intégrer Dynamics 365 Human Resources dans la même infrastructure que les autres applications de finances et d’opérations. L’infrastructure autonome sera abandonnée.

## <a name="general-questions-about-the-infrastructure-merge"></a>Questions générales sur la fusion des infrastructures

### <a name="will-customers-lose-any-features-or-capabilities"></a>Les clients perdront-ils des fonctionnalités ou des capacités ?

Notre objectif est de minimiser l’impact de cette transition sur les clients. Nous ne supprimerons aucune fonctionnalité ou capacité. Il y aura une parité fonctionnelle entre Dynamics 365 Human Resources et le module HR. Dans les cas où une fonctionnalité existe dans les deux infrastructures, l’expérience Dynamics 365 Human Resources sera utilisée.

### <a name="will-the-user-experience-change"></a>L’expérience utilisateur changera-t-elle ?

L’expérience utilisateur sera cohérente avec l’expérience standard de la plateforme Dynamics 365. Bien que l’expérience générale du tableau de bord et des menus reste similaire, elle sera alignée sur l’expérience standard de l’application Dynamics 365 Finance. La navigation comprendra à la fois des modules et des espaces de travail, autorisera les favoris, etc. Les espaces de travail Dynamics 365 Human Resources, tels que **Gestion du personnel** et **Personnes**, fusionnera avec l’infrastructure de finances et d’opérations. À l’avenir, de nouvelles fonctionnalités seront fournies via la gestion des fonctionnalités, qui permet aux clients de visualiser les nouvelles fonctionnalités et de décider lesquelles ils souhaitent utiliser. Pour plus d’informations, voir [Présentation de la gestion des fonctionnalités](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et [Documentation de l’interface utilisateur](../fin-ops-core/fin-ops/get-started/user-interface-elements.md?toc=/dynamics365/human-resources/toc.json).

### <a name="when-will-the-dynamics-365-human-resources-infrastructure-merge-be-completed"></a>Quand est-ce que la fusion des infrastructures Dynamics 365 Human Resources sera-t-elle achevée ?

La fusion des infrastructures se déroulera en plusieurs phases pour donner aux clients le temps de planifier et d’effectuer les étapes nécessaires. Nous avons commencé à déployer des fonctionnalités dans la 2è vague de lancement de Dynamics 2021. Nous prévoyons d’achever tous les efforts de développement de produits pour ce projet d’ici la fin de la 2è vague de lancement 2022. Notez que les délais sont sujets à changement. Pour des informations à jour, consultez les [Programmes de lancement](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="what-training-and-resources-will-be-available-to-help-with-the-infrastructure-merge"></a>Quelles formations et ressources seront disponibles pour faciliter la fusion des infrastructures ?

Une documentation complète sera fournie pour décrire en détail chaque étape du processus de fusion. Nous fournirons des ressources de formation supplémentaires, telles que des vidéos et des ateliers, si nécessaire pour aider les clients et les partenaires à effectuer une transition en douceur.

### <a name="will-there-be-changes-in-development-capabilities-after-the-infrastructure-merge-is-completed"></a>Y aura-t-il des changements dans les capacités de développement une fois la fusion de l’infrastructure terminée ?

Pour en savoir plus sur les capacités de développement, consultez [Développer et personnaliser la page d’accueil](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

## <a name="feature-availability-questions"></a>Questions sur la disponibilité des fonctionnalités

### <a name="will-the-linkedin-talent-hub-integration-work-on-the-finance-and-operations-infrastructure"></a>L’intégration de LinkedIn Talent Hub fonctionnera-t-elle après la migration vers la nouvelle infrastructure de finances et d’opérations ?

Non, l’intégration de LinkedIn Talent Hub ne fera pas partie de l’infrastructure fusionnée. Des interfaces de programmation d’applications (API) publiques sont disponibles pour créer des intégrations avec des solutions de recrutement et de suivi des candidatures. Les clients qui envisagent d’utiliser LinkedIn Talent Hub doivent travailler avec leur partenaire Microsoft pour s’intégrer à l’aide des API fournies. Pour plus d’informations sur les API d’intégration du système de suivi des candidatures (ATS), consultez [Présentation de l’API d’intégration du système de suivi des candidatures](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-capabilities-that-are-currently-available-only-in-dynamics-365-human-resources-for-example-leave-management-and-benefits-management-be-available-after-the-merge-is-completed"></a>Les fonctionnalités actuellement disponibles uniquement dans Dynamics 365 Human Resources (par exemple, la gestion des congés et des avantages sociaux) sera disponible une fois la fusion terminée ?

Oui. Toutes les fonctionnalités de l’application Dynamics 365 Human Resources sont apportées à l’infrastructure de finances et d’opérations. Les fonctionnalités seront mises à disposition selon une approche progressive. Pour obtenir des informations à jour sur la disponibilité des fonctionnalités pour l’infrastructure fusionnée, consultez régulièrement les [plans de lancement](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="will-ceridian-integrations-with-dynamics-365-human-resources-be-available-after-the-infrastructure-merge-is-completed"></a>Les intégrations Ceridian à Dynamics 365 Human Resources -seront-elles disponibles une fois la fusion des infrastructures terminée ?

Ceridian est en train de créer une intégration V2 avec Dynamics 365 Human Resources qui tire parti des API de paie. L’intégration basée sur des fichiers qui existe actuellement dans Dynamics 365 Human Resources ne sera pas migrée vers l’infrastructure de finances et d’opérations. Pour plus d’informations, voir [Vue d’ensemble de l’API de paie](./hr-admin-integration-payroll-api-introduction.md).

### <a name="will-applicant-tracking-or-onboardingoffboarding-of-employees-functionality-be-included"></a>Est-ce que le suivi des candidats ou l’intégration/le départ des fonctionnalités de l’employé seront inclus ?

Dans les versions précédentes, nous avons créé l’API d’intégration ATS pour permettre aux partenaires et aux clients de créer des intégrations ATS avec Human Resources. Des fonctionnalités supplémentaires liées à l’ATS sont devenues disponibles dans la 1è vague de lancement 2022. Nous continuerons à améliorer ces API dans les prochaines versions.

La fonctionnalité RH qui existe actuellement dans l’infrastructure de finances et d’opérations comprend certaines fonctionnalités de gestion du recrutement qui n’existent pas dans Dynamics 365 Human Resources. Lorsque la fusion des infrastructures est achevée, cette fonctionnalité sera disponible auprès de tous les clients Human Resources. Cette fonctionnalité fournit une fonctionnalité ATS légère. Cependant, nous ne prévoyons pas d’étendre cette fonctionnalité à l’avenir. Les clients qui ont besoin de fonctionnalités plus avancées peuvent tirer parti des intégrations ATS partenaires. Pour plus d’informations sur les API d’intégration du système de suivi des candidatures (ATS), consultez [Présentation de l’API d’intégration du système de suivi des candidatures](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-dynamics-ax-2012-upgrade-tools-be-used-to-upgrade-the-hr-module-in-ax-2012-to-the-dynamics-365-human-resources-app"></a>Les outils de mise à niveau Dynamics AX 2012 actuellement disponibles seront-ils utilisés pour mettre à niveau le module HR de AX 2012 vers l’application Dynamics 365 Human Resources ?

Oui. Une mise à niveau de Dynamics AX 2012 vers Dynamics 365 Human Resources utilisera le même chemin de mise à niveau et les mêmes outils que ceux utilisés pour la mise à niveau d’autres applications d’opérations Dynamics 365, telles que Dynamics 365 Finance ou Dynamics 365 Supply Chain Management.

Pour plus d’informations sur la migration vers l’infrastructure de finances et d’opérations, voir [FAQ sur la migration des clients Human Resource](./customer-migration.md).
