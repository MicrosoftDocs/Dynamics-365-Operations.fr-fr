---
title: Authentification de serveur à serveur pour l’API d’intégration ATS
description: Cette rubrique décrit comment configurer l’authentification de serveur à serveur pour les intégrations par rapport à l’API d’intégration du système de suivi des candidats (ATS) Dynamics 365 Human Resources.
author: jaredha
ms.date: 06/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 350fb5a00b85f28fa8aef2ca50cf1f277b8f635e
ms.sourcegitcommit: e4cc43b06ef3f0f562849e2c960025cb244d6017
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2022
ms.locfileid: "8743539"
---
# <a name="server-to-server-authentication-for-the-ats-integration-api"></a>Authentification de serveur à serveur pour l’API d’intégration ATS


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit comment configurer l’authentification de serveur à serveur pour les intégrations d’applications par rapport à l’API d’intégration du système de suivi des candidats (ATS) Dynamics 365 Human Resources. Il y a quelques couches de sécurité qui doivent être gérées pour que le principal du service puisse accéder à la table virtuelle Microsoft Dataverse et aux données associées. L’utilisateur doit avoir accès à la table virtuelle Dataverse dans Microsoft Power Platform et accès aux données dans Dynamics 365 Human Resources.

## <a name="enable-access-to-dataverse-virtual-tables-in-power-platform"></a>Activer l’accès aux tables virtuelles Dataverse dans Power Platform

La première étape pour accéder aux tables virtuelles Dataverse dans Power Platform consiste à configurer votre application dans Power Platform pour l’authentification par rapport à des points de terminaison de tables virtuelles Dataverse. Les étapes à suivre sont décrites dans le [Guide du développeur Microsoft Dataverse](/powerapps/developer/data-platform).

  - Pour les enregistrements d’applications à locataire unique : [Utiliser l’authentification serveur à serveur à locataire unique](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication)
  - Pour les enregistrements d’applications à plusieurs locataires : [Utiliser l’authentification serveur à serveur à plusieurs locataires](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication)

### <a name="creating-a-security-role-for-ats-integrations"></a>Création d’un rôle de sécurité pour les intégrations ATS

L’une des étapes après la création de l’utilisateur de l’application consiste à attribuer à l’utilisateur un rôle de sécurité qui définit l’accès que l’application aura aux points de terminaison. Il s’agit de l’étape 7 dans [Création d’utilisateurs de l’application](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication#application-user-creation) pour les enregistrements d’applications à locataire unique, et [Créer un rôle de sécurité pour l’utilisateur de l’application](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication#create-a-security-role-for-the-application-user) pour les inscriptions à plusieurs locataires. 

Le rôle auquel vous attribuez l’utilisateur de l’application doit avoir accès aux entités de données utilisées pour votre intégration ATS. Cela n’existe pas par défaut, un nouveau rôle de sécurité devra donc être créé. Le nouveau rôle peut être créé en suivant les étapes décrites dans [Créer un rôle de sécurité](/power-platform/admin/create-edit-security-role#create-a-security-role).

Pour le nouveau rôle, un accès approprié doit être attribué, au minimum, aux entités suivantes dans l’onglet **Entités personnalisées** du nouveau rôle. Notez que vous devrez peut-être ajouter des entités supplémentaires si l’intégration utilise des données d’application plus étendues. Une fois le nouveau rôle créé, il peut être attribué à l’utilisateur de l’application.

  - Collaborateur de base (mshr)
  - Candidat à l’embauche (mshr)
  - Compétence – Certificat (mshr)
  - Type de certificat (mshr)
  - Société
  - Fonction de rémunération (mshr)
  - Type de fonction de rémunération (mshr)
  - Pays/régions (mshr)
  - Service (mshr)
  - Compétence en éducation (mshr)
  - Diplôme d’études (mshr)
  - Disciplines de formation (mshr)
  - Exigences scolaires (mshr)
  - Identification (mshr)
  - Type d’identification (mshr)
  - Établissement (mshr)
  - Agence émettrice (mshr)
  - Rémunération du poste (mshr)
  - Postes (mshr)
  - Niveau d’études (mshr)
  - Contacts de la partie (mshr)
  - Personnes (mshr)
  - Adresses des personnes (mshr)
  - Filtrage de la personne (mshr)
  - Type de poste (mshr)
  - Postes V2 (mshr)
  - Compétence expérience professionnelle (mshr)
  - Niveau de classement (mshr)
  - Modèles de classement (mshr)
  - Codes de motif (mshr)
  - Demande de recrutement (mshr)
  - Emplacement de la demande de recrutement (mshr)
  - Poste de la demande de recrutement (mshr)
  - Compétences de la demande de recrutement (mshr)
  - Type de filtrage (mshr)
  - Compétence (mshr)
  - Qualifications (mshr)
  - Titres (mshr)
  - Statut de vétéran (mshr)
  - Collaborateur (mshr)

## <a name="granting-application-permissions-to-human-resources-data"></a>Accorder des autorisations d’application aux données des ressources humaines

La deuxième étape consiste à s’assurer que l’application dispose des autorisations appropriées sur les données des ressources humaines en la liant à un utilisateur dans l’application des ressources humaines. Pour un utilisateur d’application, les appels de serveur à serveur via les tables virtuelles Dataverse sont effectués dans le contexte de l’identité de l’utilisateur (app) dans Dataverse qui invoque l’action. Le service d’adaptateur de table virtuelle recherche ensuite l’utilisateur associé dans les ressources humaines et exécute la requête dans le contexte de cet utilisateur. Cela signifie qu’un utilisateur doit être créé dans les ressources humaines avec les bons rôles attribués afin de fournir un accès aux données dont l’application d’intégration aura besoin.

L’utilisateur des ressources humaines devra également disposer des autorisations appropriées pour les données dans les ressources humaines. Le rôle **Demande de recrutement** (HcmRecruitingIntegrator) est disponible avec des privilèges sur les entités principales requises pour l’intégration avec les données de recrutement. Ce rôle peut être attribué à l’utilisateur de l’application sur la page **Utilisateurs** pour accorder un accès approprié aux données. Pour plus d’informations sur les rôles de sécurité des ressources humaines, consultez [Sécurité basée sur les rôles](/dynamics365/fin-ops-core/dev-itpro/sysadmin/role-based-security).

### <a name="set-up-the-new-user-with-appropriate-permissions"></a>Configurer le nouvel utilisateur avec les autorisations appropriées

Pour configurer le nouvel utilisateur avec les autorisations appropriées, suivez les étapes ci-après :

  1. Ouvrez la page **Utilisateurs** dans les ressources humaines et sélectionnez **Nouveau**.
  2. Entrez un **Identifiant d’utilisateur** et un **Nom d’utilisateur** pour le nouvel utilisateur de l’application. Par exemple, vous pouvez entrer « IntégrationRecrutement ».

      > [!NOTE]
      > Si l’application n’a pas de compte d’utilisateur ou d’adresse e-mail Microsoft Azure Active Directory (Azure AD), vous pouvez mettre quelque chose comme « AppRecrutement » dans les champs d’adresse e-mail et de fournisseur pour l’utilisateur.

  3. Dans le raccourci **Rôle de l’utilisateur**, sélectionnez l’action **Affecter des rôles**.
  4. Dans le volet **Attribuer des rôles à l’utilisateur**, sélectionnez **Demande de recrutement**, puis sélectionnez **OK**.
  5. Enregistrez le nouvel enregistrement d’utilisateur.

### <a name="link-the-new-human-resources-user-to-the-application"></a>Lier le nouvel utilisateur des ressources humaines à l’application

Une fois l’utilisateur créé, un enregistrement doit être créé pour l’application dans le formulaire **Applications Azure Active Directory** pour lier l’application à l’utilisateur des ressources humaines.

  1. Ouvrez le formulaire **Applications Azure Active Directory** et sélectionnez **Nouveau**.
  2. Dans le champ **Identité du client**, entrez l’ID client de l’utilisateur de l’application créé pour l’application.
  3. Dans le champ **Nom**, entrez le nom de l’application d’intégration.
  4. Dans le champ **Identifiant utilisateur**, sélectionnez le nouvel utilisateur des ressources humaines créé pour l’intégration du recrutement.
  5. Enregistrez le nouvel enregistrement.

L’application aura alors accès aux données des ressources humaines, limitées uniquement aux données nécessaires aux intégrations d’applications de recrutement.

## <a name="see-also"></a>Voir également :

[Recruter des candidats à un poste](hr-personnel-recruit.md)<br>
[Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Utiliser l’API Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>
[Créer et mettre à jour des ensembles d’options à l’aide de l’API Web](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
