---
title: FAQ sur l'intégration de LinkedIn
description: Cette rubrique répond aux questions que vous pourriez avoir sur l'intégration entre LinkedIn et Microsoft Microsoft Dynamics 365 Talent - Attract.
author: hasrivas
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 35428da709f480e1d3842b7e92deacba200326ee
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461131"
---
# <a name="linkedin-integration-faq"></a>FAQ sur l'intégration de LinkedIn

[!include [banner](includes/banner.md)]

LinkedIn est le plus grand réseau professionnel en ligne du monde. Microsoft Dynamics Talent : Attract s'intègre à LinkedIn pour vous permettre d'avoir accès aux meilleurs talents au monde. Attract permet de publier des offres d'emploi directement dans LinkedIn, mais aussi de faire passer des informations sur le candidat de LinkedIn dans Attract.

## <a name="for-recruiters-and-hiring-managers"></a>Pour les recruteurs et les responsables du recrutement

Voici les réponses aux questions fréquentes sur l'utilisation d'Attract et de LinkedIn ensemble.

### <a name="what-linkedin-features-do-i-get-with-attract"></a>Quelles sont les fonctionnalités de LinkedIn auxquelles j'ai accès avec Attract ?

L'intégration d'Attract avec LinkedIn permet d'effectuer les tâches suivantes :

- [Publier des offres d'emploi sur LinkedIn](./attract-post-jobs-to-linkedin.md) (sous la forme d'offres d'emploi limitées gratuites).
- [Identifier des candidats avec LinkedIn Recruiter dans Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md#export-linkedin-candidates-to-attract-with-one-click).
- [Paramétrer l'intégration avec LinkedIn pour Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md#set-up-apply-with-linkedin-in-attract).

### <a name="what-do-i-need-before-i-can-post-jobs-to-linkedin"></a>De quoi ai-je besoin pour publier des offres d'emploi dans LinkedIn ?

Votre administrateur doit [configurer l'intégration de LinkedIn dans Attract](./attract-admin-linkedin.md#configure-job-posting-to-linkedin). Vous êtes ensuite prêt à démarrer.

### <a name="how-do-i-post-jobs-to-linkedin-from-attract"></a>Comment publier des postes sur LinkedIn à partir d'Attract ?

Après avoir créé un poste dans Attract, il vous simplement de sélectionner le bouton **Publier maintenant** correspondant dans LinkedIn. Pour plus d'informations, voir [Publier des postes sur LinkedIn à partir de Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md#post-jobs-to-linkedin).

### <a name="can-i-get-candidate-information-from-linkedin-into-attract"></a>Puis-je transférer des informations sur le candidat entre LinkedIn et Attract ?

Oui. Si vous découvrez un bon candidat dans LinkedIn, vous pouvez facilement exporter ses informations dans Attract. Pour plus d'informations, voir [Identifier des candidats avec LinkedIn Recruiter dans Microsoft Dynamics 365 Talent - Attract](attract-linkedin-recruiter.md).

### <a name="how-can-i-get-help-accessing-linkedin-from-attract"></a>Comment obtenir de l'aide pour accéder à LinkedIn à partir d'Attract ?

Si vous avez des problèmes pour vous connecter ou pour publier une offre d'emploi sur LinkedIn à partir d'Attract, voir [Résoudre les problèmes d'intégration avec LinkedIn et Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md).

Pour toute autre question sur Attract, voir [Obtenir de l'aide sur Microsoft Dynamics 365 Talent](./talent-support.md). Pour obtenir de l'aide sur LinkedIn, voir la [page de support LinkedIn](https://www.linkedin.com/help).

## <a name="for-admins-and-developers"></a>Pour les administrateurs et les développeurs

Voici les réponses aux questions fréquentes sur la configuration de l'intégration entre Attract et LinkedIn.

### <a name="how-do-i-configure-attract-so-that-recruiters-and-hiring-managers-can-post-jobs-to-linkedin"></a>Comment configurer Attract afin que les recruteurs et les responsables du recrutement puissent publier des offres d'emploi dans LinkedIn ?

Vous pouvez configurer les options disponibles dans l'onglet **Intégration de LinkedIn** du centre d'administration. Pour plus d'informations, voir [Paramétrer l'intégration avec LinkedIn pour Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md).

### <a name="can-i-export-candidate-information-from-linkedin"></a>Puis-je exporter des informations sur le candidat à partir de LinkedIn ?

Oui, mais vous devez d'abord configurer l'intégration avec LinkedIn Recruiter. Pour plus d'informations, voir [Paramétrer l'intégration avec LinkedIn pour Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md).

### <a name="how-can-i-post-jobs-to-premium-job-slots-on-linkedin"></a>Comment puis-je publier des offres d'emploi Job Slots Premium dans LinkedIn ?

Même si Attract offre une solution puissante pour publier des offres d'emploi sur LinkedIn, vous pouvez avoir besoin de plus de souplesse. Vous pouvez par exemple avoir besoin de publier des offres d'emploi Job Slots Premium en plus des offres d'emploi limitées gratuites ou que LinkedIn traite vos publications d'offre d'emploi plusieurs fois par jour.

#### <a name="types-of-linkedin-job-posts"></a>Types de publication d'offre d'emploi LinkedIn

LinkedIn propose les types de publication d'offre d'emploi suivants :

- **Offres d'emploi limitées** : Publications d'offre d'emploi gratuites qui apparaissent dans les résultats de la recherche lorsque des candidats recherche des postes sur LinkedIn et sur la page LinkedIn d'une société. Les offres d'emploi limitées ciblent les chercheurs d'emploi actifs. Ce type de liste est celui qu'Attract fournit à LinkedIn. Vous ne pouvez pas promouvoir des offres d'emploi limitées sur LinkedIn. Pour promouvoir des offres d'emploi limitées, vous devez contacter LinkedIn pour activer la diffusion automatique des offres d'emploi. Pour plus d'informations sur la diffusion automatique des offres d'emploi, voir [Offres d'emploi limitées et job slots Premium pour la diffusion automatique des offres d'emploi](https://www.linkedin.com/help/recruiter/answer/79049/limited-listings-vs-premium-job-slots-for-job-wrapping) et [FAQ sur la diffusion automatique des offres d'emploi](https://www.linkedin.com/help/recruiter/answer/79050/job-wrapping-frequently-asked-questions).
- **Job Slots Premium** : Publications achetées qui apparaissent dans divers endroits dans l'LinkedIn, comme le flux de LinkedIn, les e-mails et l'encadré **Des offres d’emploi qui pourraient vous intéresser**. Les Job Slots Premium visent les candidats passifs, mais ils figurent également dans les recherches de poste.

Attract publie des offres d'emploi sur LinkedIn (sous la forme d'offres d'emploi limitées). Pour utiliser les Job Slots Premium , vous devez utiliser la diffusion automatique des offres d'emploi via LinkedIn Recruiter. La diffusion automatique des offres d'emploi nécessite un contrat pour la diffusion automatique des offres d'emploi avec LinkedIn. Pour plus d'informations, voir [Diffusion automatique des offres d'emploi via LinkedIn Recruiter - Présentation](https://www.linkedin.com/help/recruiter/answer/79037).

#### <a name="frequency-of-batch-processing-on-linkedin"></a>Fréquence du traitement par lots sur LinkedIn

LinkedIn traite les publications d'offre d'emploi par lot via Attract une fois par jour. La publication des offres sur LinkedIn peut prendre jusqu'à 48 heures après leur publication via Attract. Pour que les offres d'emploi soient publiées avant sur LinkedIn, ou si vous avez besoin de flexibilité supplémentaire, vous pouvez utiliser l'interface de programmation d'applications (API) Recruiter System Connect de LinkedIn. Pour plus d'informations, voir [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect).

#### <a name="table-of-options-for-job-posting-to-linkedin"></a>Tableau des options pour la publication des offres d'emploi dans LinkedIn

Le tableau suivant décrit les différentes options pour la publication des offres d'emploi dans LinkedIn. Il inclut les avantages de chaque option et des informations supplémentaires.

|  | Attract | Diffusion automatique des offres d'emploi via LinkedIn Recruiter | API Recruiter System Connect |
|---|---|---|---|
| **Description** | Attract publie des offres d'emploi sur LinkedIn en tant que flux XML. | La société établit un contrat avec LinkedIn et fournit un flux XML pour publier des offres d'emploi. | Le client utilise l'API pour synchroniser les informations entre Attract et LinkedIn Recruiter. |
| **Quel type d'offre d'emploi puis-je publier ?** | Liste limitée | Job Slots Premium ou Liste limitée | Liste limitée |
| **Puis-je promouvoir une offre d'emploi sur LinkedIn ?** | Non | Job slots Premium : Oui<br>Offres d'emploi limitées : Non | Non |
| **Quelle est la fréquence de publication des offres d'emploi de LinkedIn ?** | Une fois par jour | Une fois par jour | Plusieurs fois par jour, comme défini par l'API |
| **Recommandé par LinkedIn ?** | Non | Oui | Non |
| **De quoi ai-je besoin ?** | Acheter Attract | D'un contrat pour la diffusion automatique des offres d'emploi avec LinkedIn et de l'achat de Job Slots Premium | D'un accord API avec LinkedIn | 
| **Où puis-je trouver plus d'informations ?** | [Paramétrer l'intégration avec LinkedIn pour Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md) | [Diffusion automatique des offres d'emploi via LinkedIn Recruiter - Présentation](https://www.linkedin.com/help/recruiter/answer/79037) | [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect) |

> [!NOTE]
> Vous n'avez pas besoin de licence LinkedIn Recruiter System Connect pour valider des offres d'emploi dans LinkedIn avec Attract.

## <a name="see-also"></a>Voir également :

[Paramétrer l'intégration avec LinkedIn pour Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md)

[Publier des postes sur LinkedIn à partir de Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md)

[Identifier des candidats avec LinkedIn Recruiter dans Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md)

[Résoudre les problèmes d'intégration avec LinkedIn et Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]