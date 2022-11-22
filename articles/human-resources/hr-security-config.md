---
title: Concepts de configuration de la sécurité pour les intégrations basées sur des tables virtuelles
description: Cet article explique une architecture pour construire une intégration entre Microsoft Dynamics 365 Human Resources et d’autres systèmes.
author: twheeloc
ms.date: 11/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 219ceb0adae0cee5f74a39140ab74af9fdac1eb6
ms.sourcegitcommit: ea79bf014bbf495ac8e28db29502c8bd85a75f32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2022
ms.locfileid: "9759652"
---
# <a name="security-configuration-concepts-for-virtual-table-based-integrations"></a>Concepts de configuration de la sécurité pour les intégrations basées sur des tables virtuelles

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit une architecture pour utiliser des [tables virtuelles Microsoft Dataverse (entités)](/dev-itpro/power-platform/virtual-entities-overview) afin de construire une intégration entre Dynamics 365 Human Resources et un système tiers. L’article se concentre sur la configuration de la sécurité et sur les aspects d’authentification et d’autorisation requis entre les limites du système pour créer un système fonctionnel et sécurisé.

## <a name="prerequisite-reference-articles"></a>Articles de référence préalables

Les articles suivants fournissent plus d’informations sur les concepts dans cet article :

- [Vue d’ensemble des entités virtuelles](/dev-itpro/power-platform/virtual-entities-overview)
- [Démarrer avec les tables virtuelles (entités)](/developer/data-platform/virtual-entities/get-started-ve)
- [Utiliser l’authentification serveur à serveur à plusieurs locataires (Microsoft Dataverse)](/developer/data-platform/use-multi-tenant-server-server-authentication)
- [Utiliser l’authentification OAuth avec Microsoft Dataverse (Dataverse)](/developer/data-platform/authenticate-oauth)
- [Flux d’informations d’identification du client OAuth 2.0 sur la plateforme d’identité Microsoft](/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow)
- [Authentification et autorisation](/dev-itpro/power-platform/authentication-and-authorization)

## <a name="architecture"></a>Architecture 

Le diagramme architectural suivant montre les principaux concepts impliqués dans une intégration qui utilise des tables virtuelles (entités).

![Intégration basée sur des tables virtuelles.](./media/Hosts.jpg)

Voici l’explication de certains des éléments présentés dans le diagramme précédent :

- **Microsoft** : Microsoft héberge et exploite les différents produits Dynamics 365 pour le compte des clients.

    - **Locataire C Azure Active Directory (Azure AD)**  : locataire Azure AD qui appartient à Microsoft. Il s’agit du locataire dans lequel les applications Dynamics 365 sont enregistrées.

- **Partenaire d’intégration**

    - **Système d’intégration** : système intégré à Dynamics 365. Soit un système de paie, soit tout système reposant sur les données stockées dans Dynamics 365.
    - **Adaptateur** : logiciel ou service responsable de l’interaction avec Dynamics 365 et le système d’intégration.

        > [!NOTE]
        > Si un adaptateur est destiné à être utilisé par plusieurs clients Dynamics 365, on s’attend à ce qu’il soit enregistré en tant qu’application mutualisée dans Azure AD.

    - **Locataire A Azure AD** : locataire Azure AD qui appartient au partenaire d’intégration. Il s’agit du locataire dans lequel l’ID des applications de l’adaptateur est enregistré.

- **Client commun** : client qui met en œuvre Dynamics 365 Human Resources et la solution du partenaire d’intégration.

    - **Dynamics 365 Finance ou Human Resources** : instance spécifique au client de Dynamics 365 Finance ou Human Resources qui contient les données client requises par le système d’intégration.
    - **Dataverse** : environnement Dataverse spécifique au client lié à Finance ou Human Resources. Dataverse fournit une API web pour l’interaction avec les données Dynamics 365.
    - **Locataire B Azure AD** : locataire Azure AD du client. Il fonctionne comme fournisseur d’identité (serveur d’autorisation) et émet des jetons qui autorisent les appelants à appeler l’instance Dataverse du client.

## <a name="basic-request-flow"></a>Flux de requête de base

Cette section décrit le flux de base d’une requête classique impliquée dans une intégration. Il fait référence au diagramme architectural présenté plus haut dans cet article.

Une requête classique nécessite que l’adaptateur interroge Dynamics 365 pour obtenir les données, puis qu’il enregistre et synchronise ces données avec le système d’intégration.

1. L’adaptateur appelle l’API web Dataverse pour interroger les données pertinentes.

    > [!NOTE]
    > L’authentification est une condition préalable et l’acquisition de jetons est une partie importante du processus. L’authentification sera décrite dans la section [Authentification et autorisation aux limites du système](#authentication-and-authorization-at-system-boundaries).

    Cet appel est effectué sur l’API web Dataverse pour interroger les données d’application exposées via une table virtuelle. (Voir « 2. Synchronisation initiale » et « 3. Synchronisation delta » dans le diagramme.)

2. Dataverse gère la requête en interrogeant la table virtuelle via le plug-in d’entité virtuelle (« Proxy de la table virtuelle » dans le diagramme). La requête Dataverse est transmise au service d’entité virtuelle Finance ou Human Resources pour interroger les données physiquement stockées dans la base de données Finance ou Human Resources.
3. Le service d’entité virtuelle Finance ou Human Resources traduit la requête auprès de l’entité virtuelle en une requête auprès de l’entité Finance ou Human Resources qui soutient l’entité virtuelle Dataverse. Les données sont extraites de la base de données, retraduites dans la représentation de l’entité Dataverse, puis renvoyées à l’appelant.
4. L’adaptateur termine tout mappage et traduction de données requis, puis appelle le système d’intégration pour conserver les données dans la base de données du système d’intégration. (Voir « 4. Enregistrer les données » dans le diagramme.)

## <a name="authentication-and-authorization-at-system-boundaries"></a>Authentification et autorisation aux limites du système

L’*authentification* valide l’identité d’un utilisateur ou d’une application, puis confirme que l’utilisateur ou l’application est bien celui ou celle prétendu(e). L’*autorisation* accorde à l’utilisateur ou à l’application le droit d’accéder à certaines autorisations au niveau de l’application. Pour plus d’informations, voir [Comparatif authentification et autorisation](/azure/active-directory/develop/authentication-vs-authorization).

La plupart des appels inter-systèmes du diagramme architectural présenté plus haut dans cet article impliquent l’adaptateur. L’adaptateur doit s’authentifier pour effectuer les appels suivants :

- L’appel au Dataverse
- L’appel au système d’intégration

Regardez les limites du système dans le diagramme. Chaque requête web entre les systèmes doit être authentifiée et les vérifications d’autorisation au niveau de l’application doivent être réussies avant que les données ne soient renvoyées vers l’appelant. Pour une requête sur une table virtuelle Dynamics 365 soutenue par Finance ou Human Resources, les vérifications d’authentification et d’autorisation sont appliquées aux limites du système suivantes :

- L’appel entre l’adaptateur et le point de terminaison (OData) de l’API web Dataverse
- L’appel entre le plug-in d’entité virtuelle Dataverse et le service d’entité virtuelle Finance ou Human Resources

Dans les deux cas, les vérifications d’authentification sont effectuées en premier. Ensuite, les vérifications d’autorisation au niveau de l’application sont effectuées pour s’assurer que l’utilisateur ou l’application authentifié(e) dispose des privilèges appropriés au niveau de l’application pour récupérer les données demandées.

L’authentification pour appeler Dataverse est gérée via un jeton du porteur qui doit être inclus en tant qu’en-tête HTTP dans la requête web pour Dataverse. L’adaptateur doit obtenir un jeton de l’instance Azure AD du locataire B. (Voir « 1. Obtenir un jeton » dans le diagramme.) Azure AD agit en tant que fournisseur d’identité dans le flux d’authentification.

L’adaptateur s’authentifie en fournissant son identité d’application (non secrète, telle qu’enregistrée dans le locataire A Azure AD) et un secret d’application ou un certificat que seule l’application de l’adaptateur possède.

Une fois que l’utilisateur ou l’application sont authentifiés pour passer des appels vers Dataverse, les vérifications d’autorisation au niveau de Dataverse sont effectuées pour chaque demande. Ces vérifications permettent de s’assurer que l’appelant (identité de l’application de l’adaptateur appelée « \<guid A\> » dans le diagramme) dispose des autorisations d’application appropriées. L’autorisation au niveau de l’application est gérée dans Dataverse via un utilisateur d’application qui représente l’ID d’application de l’adaptateur. Les autorisations au niveau de l’application sont gérées en accordant l’accès à des rôles d’application définis dans Dataverse. Ces rôles fournissent des privilèges granulaires à l’application.

Pour des instructions plus détaillées, voir [Utiliser l’authentification serveur à serveur à plusieurs locataires](/power-apps/developer/data-platform/use-multi-tenant-server-server-authentication).

Si les vérifications d’autorisation au niveau de l’application Dataverse sont réussies, le plug-in d’entité virtuelle appelle le point de terminaison de service d’entité virtuelle dans l’environnement Finance ou Human Resources. L’authentification de serveur à serveur (S2S) est utilisée pour passer cet appel. Il utilise l’identité et le secret configurés dans l’enregistrement de configuration de la source de données virtuelle des finances et des opérations.

![Enregistrement de configuration de la source de données virtuelle des finances et des opérations dans l’environnement sandbox.](./media/sandbox.jpg)

Pour plus d’informations, voir [Configurer les entités virtuelles Dataverse](/dev-itpro/power-platform/admin-reference).

L’appel du plug-in d’entité virtuelle Dataverse à Finance ou Human Resources inclut l’identité de l’adaptateur de l’appel d’origine à Dataverse depuis l’adaptateur (identité appelée « \<guid A\> » dans le diagramme architectural). Si la source de données de l’entité virtuelle est correctement configurée et que les vérifications d’authentification S2S sont réussies, le service d’entité virtuelle dans Finance ou Human Resources exécute la requête dans le contexte de l’appelant d’origine (l’adaptateur, \<guid A\>). Les contrôles d’autorisation d’application au niveau de Finance ou Human Resources sont effectués pour s’assurer que l’adaptateur dispose des privilèges requis pour accéder aux entités de données demandées via la requête.

La sécurité de Finance et Human Resources est gérée de la manière suivante :

1. En mappant l’identité de l’adaptateur (\<guid A\>) à un utilisateur Finance ou Human Resources spécifique. Ce mappage est réalisé sur la page **Applications Azure Active Directory**. Pour plus d’informations, voir [Inscrire votre application externe](/dev-itpro/data-entities/services-home-page.md#register-your-external-application).
2. En accordant à l’utilisateur Finance ou Human Resources les rôles, devoirs et privilèges appropriés au niveau de l’application. Pour plus d’informations, voir [Sécurité basée sur les rôles](/dev-itpro/sysadmin/role-based-security).

Si l’application de l’adaptateur (\<guid A\>) reçoit les privilèges nécessaires pour accéder aux données demandées, voici ce qui se passe :

1. La requête est exécutée.
2. Les données sont retraduites dans leur page d’entité Dataverse.
3. Les données sont renvoyées à l’adaptateur.

> [!IMPORTANT]
> Pendant le développement, l’adaptateur peut être exécuté à l’aide d’un utilisateur Finance ou Human Resources humaines doté du rôle Administrateur. Cependant, dans un environnement de production, l’adaptateur ne doit jamais être exécuté avec des privilèges Administrateur.

## <a name="key-takeaways"></a>Points clés à retenir

Voici quelques-unes des implications importantes de la table virtuelle ou de l’architecture d’entité :

- La configuration de la sécurité pour les tables virtuelles soutenues par Human Resources est gérée dans Human Resources.
- Le client (« Client commun » dans le diagramme architectural présenté plus haut dans cet article) a un contrôle total sur les privilèges accordés à l’identité de l’adaptateur d’intégration (appelée « \<guid A\> » dans le diagramme).
- Le client est responsable de la configuration correcte de la sécurité de son environnement Human Resources. Le partenaire d’intégration qui crée l’adaptateur doit fournir des instructions sur les privilèges requis par l’adaptateur.
