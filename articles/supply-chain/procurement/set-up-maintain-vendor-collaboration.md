---
title: Paramétrer et mettre à jour la collaboration fournisseur
description: Cette rubrique explique comment paramétrer la collaboration fournisseur dans Dynamics 365 Supply Chain Management. Il explique également comment provisionner de nouveaux utilisateurs de collaboration de fournisseurs et gérer les rôles de sécurité pour ces utilisateurs.
author: Henrikan
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirExternalRole, SysUserRequestListPage, VendVendorPortalUsers, WorkflowTableListPageRnr
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 220774
ms.assetid: 69d05e8b-7dc2-48ea-bc24-bea9ac963579
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b635255fffa6fd3c6612cd248dc692df204aa76d
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2021
ms.locfileid: "7651996"
---
# <a name="set-up-and-maintain-vendor-collaboration"></a>Paramétrer et mettre à jour la collaboration fournisseur

[!include [banner](../includes/banner.md)]

L'interface de collaboration avec les fournisseurs expose un ensemble limité d'informations sur les bons de commande, les factures et le stock en consignation aux utilisateurs de fournisseurs externes. À partir de cette interface, un fournisseur peut également répondre aux demandes de devis (RFQ) et afficher et modifier les informations de base de l'entreprise.

Cette rubrique explique comment paramétrer la collaboration fournisseur dans Dynamics 365 Supply Chain Management. Il explique également comment configurer un flux de travail pour provisionner de nouveaux utilisateurs de collaboration fournisseur et comment gérer les rôles de sécurité pour ces utilisateurs.

> [!NOTE]
> Les informations sur la configuration des rôles de sécurité pour la collaboration avec les fournisseurs s'appliquent uniquement à la version actuelle de Finance and Operations. Dans Microsoft Dynamics AX 7.0 (février 2016) et dans la version de l’application 7.0.1 de Microsoft Dynamics AX, vous collaborez avec les fournisseurs à l’aide du module **Portail fournisseur**. Pour plus d'informations sur les autorisations des utilisateurs pour le portail des fournisseurs dans Microsoft Dynamics AX, voir [Sécurité des utilisateurs du portail fournisseur](configure-security-vendor-portal-users.md).

## <a name="set-up-vendor-collaboration-security-roles"></a>Configurer les rôles de sécurité de collaboration avec les fournisseurs

Un professionnel de l'approvisionnement ou un fournisseur qui dispose de suffisamment d'autorisations peut demander qu'une personne de contact soit configurée en tant qu'utilisateur en activant **Mettre en service un utilisateur fournisseur** sur la fiche de la personne de contact. Au cours du processus d'approvisionnement, les autorisations utilisateur sont sélectionnées pour le nouvel utilisateur externe et la nouvelle demande d'utilisateur fournisseur est soumise. Il est important que vous configuriez correctement les autorisations d'utilisateur disponibles pour la sélection dans la demande d'utilisateur du fournisseur. Sinon, les fournisseurs pourraient avoir accès à des informations auxquelles ils ne devraient pas avoir accès dans Supply Chain Management.

### <a name="set-up-the-security-roles-that-are-available-for-selection-when-a-new-user-request-is-used-for-a-contact-person"></a>Configurer les rôles de sécurité disponibles pour la sélection lorsqu'une nouvelle demande d'utilisateur est utilisée pour une personne de contact

1. Sélectionnez **Administration du système** &gt; **Sécurité** &gt; **Rôles externes**.
2. Sélectionnez **Nouveau**, puis sélectionnez un rôle de sécurité et le rôle de partie **Fournisseur**.

Vous voudrez peut-être ajouter les rôles **Administrateur du fournisseur (externe)** et **Fournisseur (externe)** qui sont fournis dans Supply Chain Management. Vous pouvez également utiliser les rôles de sécurité que votre entreprise a créés.

Vous devriez faire le rôle **Administrateur du fournisseur (externe)** disponible uniquement si les fournisseurs doivent être en mesure de créer de nouveaux contacts, de soumettre des demandes d'utilisateur de collaboration de fournisseur pour de nouveaux utilisateurs et des modifications des informations utilisateur, et de gérer ces demandes via un flux de travail.

Si vous envisagez de configurer manuellement les contacts et les utilisateurs des fournisseurs, vous pourriez rendre simplement le **Rôle du fournisseur (externe)** disponible. Ce rôle sera alors le seul rôle qui peut être demandé via une demande d'utilisateur fournisseur.

> [!NOTE]
> Le rôle **SystemUser** est automatiquement octroyé lorsque vous créez manuellement un nouveau compte utilisateur. Par conséquent, vous devez supprimer ce rôle et attribuer le rôle **SystemExternalUser**. Si de nouveaux comptes d'utilisateurs sont créés via le workflow initié par une demande d'utilisateur fournisseur pour provisionner un nouvel utilisateur, un ou plusieurs des rôles que vous avez configurés pour la collaboration fournisseur et le rôle **SystemExternalUser** seront attribués.

#### <a name="vendor-admin-external-security-role"></a>Rôle de sécurité de l'administrateur du fournisseur (externe)

Le rôle **Administrateur du fournisseur (externe)** peut être utilisé pour les fournisseurs externes qui gèrent les informations de contact des fournisseurs et font des demandes pour provisionner de nouveaux utilisateurs de collaboration avec les fournisseurs. Les utilisateurs externes qui ont ce rôle de sécurité peuvent effectuer les tâches suivantes :

- Affichez et modifiez les informations de la personne de contact, telles que le titre, l'adresse e-mail et le numéro de téléphone de la personne.
- Ajoutez une personne de contact nouvelle ou existante aux comptes de fournisseur pour lesquels elle est un contact.
- Supprimez toute personne de contact qu'ils ont créée.
- Activer ou désactiver l'association entre une personne de contact et un compte fournisseur. Une fois l'association entre une personne de contact et un compte fournisseur désactivée, la personne de contact ne peut pas être mentionnée sur les nouveaux bons de commande ou autres documents.
- Interdisez ou autorisez l'accès d'une personne de contact aux documents sur l'interface de collaboration fournisseur qui sont spécifiques au compte fournisseur. Une fois l'association entre une personne de contact et un compte fournisseur désactivée, l'accès aux documents spécifiques au compte fournisseur est toujours refusé.
- Demander un nouveau compte utilisateur pour une personne de contact en utilisant l'action **Utilisateur de provision**.
- Demander la désactivation du compte utilisateur d'une personne de contact.
- Demander que le compte d'utilisateur d'une personne de contact soit modifié pour ajouter ou supprimer des rôles de sécurité.
- Afficher les appels d'offres.

#### <a name="vendor-external-security-role"></a>Rôle de sécurité du fournisseur (externe)

Le **Rôle du fournisseur (externe)** peut être utilisé pour les fournisseurs externes qui travailleront avec les bons de commande. Les utilisateurs externes qui ont ce rôle de sécurité peuvent effectuer les tâches suivantes :

- Répondre et afficher les informations sur les commandes d'achat.
- Mettre à jour les factures de collaboration fournisseur.
- Afficher le stock de consignation.
- Afficher et répondre aux appels d'offres.
- Consulter les informations sur le fournisseur.

## <a name="set-up-security-roles-that-are-used-when-prospective-vendors-are-onboarded"></a>Configurer les rôles de sécurité qui sont utilisés lorsque les fournisseurs potentiels sont intégrés

Pour intégrer des fournisseurs initiés via une demande d'enregistrement de fournisseur potentiel, vous devez configurer un rôle de sécurité externe. Ce rôle sera attribué aux nouveaux utilisateurs au cours du processus d'approvisionnement qui est contrôlé par le flux de travail du type **Workflow de demande des utilisateurs (plateforme)**. Pour plus d'informations, consultez la section [Configurer des workflows pour traiter les demandes des utilisateurs de collaboration avec les fournisseurs](#set-up-workflows-to-process-vendor-collaboration-user-requests) plus loin dans cette rubrique.

Pour plus d'informations sur l'intégration de fournisseurs potentiels, consultez [Fournisseurs intégrés](vendor-onboarding.md).

### <a name="set-up-a-security-role-that-is-used-when-a-new-prospective-vendor-user-request-is-submitted"></a>Configurer un rôle de sécurité qui est utilisé lorsqu'une nouvelle demande d'utilisateur fournisseur potentiel est soumise

1. Sélectionnez **Administration du système** > **Sécurité** > **Rôles externes**.
2. Sélectionnez **Nouveau**, puis sélectionnez un rôle de sécurité et le rôle de partie **Fournisseur potentiel**.

Vous devez ajouter le rôle **Prospect fournisseur (externe)** qui est fourni dans Supply Chain Management.

Le rôle de sécurité n'accordera l'accès qu'à l'assistant d'enregistrement du nouveau fournisseur.

## <a name="set-up-workflows-to-process-vendor-collaboration-user-requests"></a>Configurer des workflows pour traiter les demandes des utilisateurs de collaboration avec les fournisseurs

Pour garantir que toutes les tâches pertinentes sont terminées et que les approbations appropriées sont données, vous devez configurer des workflows pour gérer les demandes des utilisateurs de collaboration avec les fournisseurs.

Les demandes d'utilisateurs de collaboration avec les fournisseurs sont soumises soit par des fournisseurs externes qui ont le rôle de sécurité **Administrateur du fournisseur (externe)** ou des autorisations similaires, ou par des professionnels des achats de votre entreprise. Ils peuvent également être générés à partir de demandes d'enregistrement de fournisseurs potentiels pendant le processus d'intégration des fournisseurs.

Il existe trois types de demandes :

- Demandes de provisionnement d'un nouvel utilisateur
- Demandes de désactivation d'un utilisateur existant
- Demandes de modification des rôles de sécurité d'un utilisateur existant

Pour plus d’informations sur les demandes des utilisateurs de collaboration avec les fournisseurs, voir [Gérer les utilisateurs de la fonctionnalité de collaboration du fournisseur](manage-vendor-collaboration-users.md).

Vous devez créer au moins deux workflows pour traiter les trois types de demandes d'utilisateurs de collaboration fournisseur. De nouveaux workflows sont créés sur la page **Flux de travail utilisateur**.

### <a name="example-of-a-workflow-for-provisioning-new-users-and-modifying-security-roles"></a>Exemple de workflow pour l'approvisionnement de nouveaux utilisateurs et la modification des rôles de sécurité

Pour gérer les demandes d'utilisateurs du fournisseur pour créer de nouveaux utilisateurs et modifier les rôles de sécurité, vous pouvez placer une condition de branchement au début du workflow. De cette façon, une branche différente du workflow est utilisée, selon que la demande est de créer un nouvel utilisateur ou de modifier un utilisateur existant.

Pour configurer ce branchement, créez un nouveau workflow du type **Workflow de demande d'utilisateur (plateforme)**. Les branches de ce workflow peuvent contenir les éléments suivants.

#### <a name="branch-to-provision-new-users"></a>Branche pour provisionner de nouveaux utilisateurs

1. Attribuez une tâche d'approbation à la personne chargée d'approuver que les nouveaux utilisateurs doivent avoir accès aux informations de collaboration des fournisseurs.
2. Attribuez une tâche à la personne chargée de demander de nouveaux comptes d'utilisateurs Microsoft Azure Active Directory (Azure AD) dans le portail Azure. Utilisez la tâche **Envoyer une invitation utilisateur Azure B2B** prédéfinie pour cette étape. Les utilisateurs B2B peuvent être automatiquement exportés vers Azure AD. Utilisez **Configurer l'utilisateur B2B Azure AD** prédéfini. Pour plus d’informations, consultez [Exporter des utilisateurs B2B dans Azure AD](../../fin-ops-core/dev-itpro/sysadmin/implement-b2b.md).
3. Attribuez une tâche d'approbation à la personne qui télécharge vers Azure. Si un compte n'est pas créé avec succès, cette personne rejette la tâche et met fin au workflow. Cette tâche d'approbation peut être ignorée si vous avez inclus l'étape qui exporte automatiquement les nouveaux comptes d'utilisateurs vers Azure via l'interface de programmation d'applications (API) B2B.
4. Ajoutez une tâche automatisée qui provisionne un nouvel utilisateur. Utilisez la tâche **Utilisateur configuré automatiquement** prédéfinie pour cette étape.
5. Ajoutez une tâche qui avertit le nouvel utilisateur. Vous souhaiterez peut-être envoyer au nouvel utilisateur un e-mail de bienvenue comprenant une URL pour Supply Chain Management. Cet e-mail peut utiliser un modèle que vous créez sur la page **Messages électroniques**, puis sélectionnez dans la page **Paramètres de workflow utilisateur**. Le modèle peut inclure la balise **%portalURL%**. Lorsque l'email de bienvenue est généré, cette balise sera remplacée par l'URL du client Supply Chain Management.

    > [!NOTE]
    > Ce flux de travail peut être utilisé dans plusieurs scénarios impliquant l'intégration des utilisateurs. Par exemple, il peut être utilisé lorsque des fournisseurs potentiels ou des personnes à contacter ont besoin d'un compte de collaboration fournisseur. Par conséquent, vous devez formuler l'e-mail comme une déclaration générale pouvant être utilisée à plusieurs fins.

#### <a name="branch-to-modify-security-roles"></a>Branche pour modifier les rôles de sécurité

1. Attribuez une tâche d'approbation à la personne chargée d'approuver les modifications apportées aux rôles de sécurité.
2. Ajoutez une tâche automatisée qui ajoute ou supprime les rôles de sécurité pertinents. Utilisez la tâche **Utilisateur configuré automatiquement** prédéfinie pour cette étape.

### <a name="example-of-a-workflow-for-inactivating-a-user"></a>Exemple de workflow pour désactiver un utilisateur

Créer un flux de travail du type **Désactiver la plateforme de workflow de demande d'utilisateur**, puis ajoutez les tâches suivantes.

1. Attribuez une tâche d'approbation à la personne chargée d'accepter les demandes de désactivation des utilisateurs. Vous pouvez ajouter des conditions pour automatiser cette étape d'approbation.
2. Ajoutez une tâche automatisée qui désactive l'utilisateur. Utilisez la tâche **Désactivation des utilisateurs automatisée** prédéfinie pour cette étape.
3. Ajoutez toutes les tâches de nettoyage requises. Par exemple, vous pouvez ajouter une tâche qui supprime le compte de votre annuaire dans le portail Azure.

## <a name="enable-vendor-collaboration-for-a-specific-vendor"></a>Activer la collaboration fournisseur pour un fournisseur spécifique

Avant de créer un compte utilisateur pour quelqu'un qui utilisera la collaboration fournisseur, vous devez configurer le fournisseur afin qu'il puisse utiliser la collaboration fournisseur. Sur la page **Fournisseurs**, sous l’onglet **Général**, définissez le champ **Activation de la collaboration**. Les options suivantes sont disponibles :

- **Actif (la CF est confirmée automatiquement)**- Les commandes fournisseur sont automatiquement confirmées si le fournisseur les accepte sans demander de modifications.
- **Actif (la CF n’est pas confirmée automatiquement)** – Votre organisation doit confirmer manuellement les commandes fournisseur une fois que le fournisseur les a acceptées.

> [!NOTE]
> Les professionnels des achats de votre entreprise peuvent également effectuer cette tâche.

## <a name="troubleshoot-the-provisioning-of-new-vendor-collaboration-users"></a>Résoudre les problèmes liés à l'approvisionnement des nouveaux utilisateurs de collaboration avec les fournisseurs

Les nouveaux utilisateurs de collaboration fournisseur sont provisionnés via le workflow que vous avez configuré pour traiter les demandes des utilisateurs de collaboration fournisseur du type **Utilisateur fournisseur d'approvisionnement**.

Si l'adresse e-mail d'un nouvel utilisateur de collaboration fournisseur appartient à un domaine enregistré auprès d'Azure en tant que client (c'est-à-dire s'il s'agit d'un compte de domaine géré), l'adresse e-mail doit être un compte Azure AD existant. Sinon, le processus d'approvisionnement ne peut pas être terminé.

Pour plus d'informations sur le processus utilisé dans la tâche **Envoyer une invitation utilisateur Azure B2B** dans le workflow pour la gestion des comptes Azure AD, voir [Collaboration B2B Azure Active Directory](/azure/active-directory/external-identities/what-is-b2b).

## <a name="additional-resources"></a>Ressources supplémentaires

[Collaboration fournisseur avec des fournisseurs externes](vendor-collaboration-work-external-vendors.md)

Regardez une courte vidéo sur le processus d'intégration des fournisseurs :[Intégrer un nouveau fournisseur](https://www.youtube.com/watch?v=0KUc3AGaTKk&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
