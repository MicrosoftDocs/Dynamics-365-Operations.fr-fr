---
title: Créer et gérer des utilisateurs du portail client
description: Cette rubrique explique comment créer des comptes d’utilisateur du portail client et définir des autorisations pour eux.
author: dasani-madipalli
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 38b479a72ce6d9446e04b14ed939b63d41d3b94b299f195974a84ca7c8ad0d65
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763985"
---
# <a name="create-and-manage-customer-portal-users"></a>Créer et gérer des utilisateurs du portail client

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Dans l’implémentation prête à l’emploi, les utilisateurs ne peuvent pas s’auto-enregistrer pour les sites web créés à l’aide du portail client. Pour se connecter et utiliser un site Web, les utilisateurs doivent être invités par l’administrateur. Microsoft a intentionnellement bloqué la capacité des utilisateurs à s’auto-enregistrer.

Avant qu’un utilisateur puisse utiliser un site web, un enregistrement de contact doit être créé pour cet utilisateur. Cet enregistrement indique à quel compte client et quelle entité juridique l’utilisateur appartient. Ces informations sont essentielles pour garantir que l’utilisateur peut créer et afficher des commandes client.

Lorsque les utilisateurs s’auto-enregistrent, des enregistrements de contacts sont automatiquement créés pour eux. Par conséquent, vous ne pouvez pas vous assurer qu’un utilisateur sélectionne le bon compte client et la bonne entité juridique. D’autre part, le processus d’invitation permet à un administrateur d’attribuer le compte client et l’entité juridique appropriés à l’enregistrement de contact avant l’envoi d’une invitation. Si vous songez à personnaliser la solution afin que les utilisateurs puissent s’auto-enregistrer, assurez-vous d’envisager les conséquences possibles.

## <a name="video"></a>Vidéo
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ADkI]

La vidéo [Inviter les clients à s’enregistrer et à utiliser votre portail client](https://youtu.be/drGUYHX9QIQ) (présentée ci-dessus) est incluse dans la [liste de lecture Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.

## <a name="prerequisite-setup"></a>Paramétrage requis au préalable

Les contacts dans les portails Power Apps sont stockés sous forme d’enregistrements dans la table **Contacts** dans Microsoft Dataverse. La double écriture synchronise ensuite ces enregistrements avec Microsoft Dynamics 365 Supply Chain Management, selon les besoins.

![Schéma du système pour les contacts du portail client.](media/customer-portal-contacts.png "Schéma du système pour les contacts du portail client")

Avant de commencer à inviter de nouveaux clients, assurez-vous que vous avez activé le mappage de la table **Contact** en double écriture.

## <a name="the-invitation-process"></a>Le processus d’invitation

Pour inviter un contact existant sur le portail client, suivez les étapes de la section [Inviter des contacts sur vos portails](/powerapps/maker/portals/configure/invite-contacts) dans la documentation des portails Power Apps.

Avant d’inviter un client à rejoindre le portail client, assurez-vous que son [enregistrement de contact](/powerapps/maker/portals/configure/configure-contacts) est disponible et configuré de la manière suivante :

1. Définissez le champ **Société** sur l’entité juridique à laquelle vous souhaitez que le client appartienne dans Supply Chain Management.
2. Définissez le champ **Numéro de compte** sur le numéro de compte client que vous souhaitez qu’ait le client dans Supply Chain Management.

Une fois le contact créé, vous devriez pouvoir le voir dans Supply Chain Management.

Pour plus d’informations, voir [Configurer un contact à utiliser dans un portail](/powerapps/maker/portals/configure/configure-contacts) dans la documentation des portails Power Apps.

## <a name="out-of-box-web-roles-and-table-permissions"></a>Rôles web et autorisations de table prêts à l’emploi

Les rôles utilisateur dans les portails Power Apps sont définis par les [rôles web](/powerapps/maker/portals/configure/create-web-roles) et les [autorisations de table](/powerapps/maker/portals/configure/assign-entity-permissions). Quelques rôles sont définis et prêts à l’emploi pour le portail client. Vous pouvez créer de nouveaux rôles et modifier ou supprimer des rôles existants.

### <a name="out-of-box-web-roles"></a>Rôles web prêts à l’emploi

Cette section décrit les rôles web fournis avec le portail client.

Pour plus d’informations sur la modification des rôles d’utilisateur prêts à l’emploi, consultez [Créer des rôles web pour les portails](/powerapps/maker/portals/configure/create-web-roles) et [Ajouter une sécurité basée sur les enregistrements en utilisant des autorisations de table pour les portails](/powerapps/maker/portals/configure/assign-entity-permissions) dans la documentation des portails Power Apps.

#### <a name="administrator"></a>Administrator

L’administrateur supervise et gère le site web. Cette personne approvisionne et configure le portail client. L’administrateur gère les aspects informatiques et de sécurité du portail et s’assure que tout se déroule correctement. L’administrateur peut également personnaliser et/ou modifier le portail en ajoutant de nouvelles fonctionnalités, en créant de nouveaux rôles, etc.

#### <a name="customer-representative"></a>Représentant du client

Un représentant client travaille pour une entreprise cliente et est responsable de la gestion des commandes que passe l’entreprise. Le représentant client peut voir toutes les commandes passées pour l’entreprise et les utilisateurs qui les ont passées. En outre, le représentant client peut voir des informations sur le compte global et les contacts qui peuvent passer des commandes au nom de ce compte.

#### <a name="authorized-users"></a>Utilisateurs autorisés

Les utilisateurs autorisés peuvent passer des commandes et afficher le statut des commandes qu’ils ont passées. Cependant, ils ne peuvent pas voir le statut des commandes que d’autres utilisateurs de leur entreprise ont passées.

#### <a name="unauthorized-users"></a>Utilisateurs non autorisés

Les utilisateurs non autorisés ne peuvent afficher aucune donnée. Ils ne peuvent voir que les informations publiques, telles que les conditions générales et les détails sur l’entreprise qui exécute le portail client.

#### <a name="example"></a>Exemple

Le tableau suivant montre quelles commandes client les utilisateurs de chaque rôle web peuvent voir dans le système.

| Commandes client | Administrator | Représentant client pour le client&nbsp;X | Utilisateur autorisé : Jane | Utilisateur autorisé : Sam | Utilisateur non autorisé : May |
|---|---|---|---|---|---|
| Client&nbsp;X Auteur de la commande :&nbsp;Jane | Oui | Oui | Oui | N° | N° |
| Client&nbsp;X Auteur de la commande :&nbsp;Sam | Oui | Oui | N° | Oui | N° |
| Client&nbsp;Y Auteur de la commande :&nbsp;May | Oui | N° | N° | N° | N° |

> [!NOTE]
> Même si Sam et Jane sont des contacts qui travaillent pour le client X, ils ne peuvent voir que les commandes qu’ils ont eux-mêmes passées et rien d’autre. Bien que May ait une commande dans le système, elle ne peut pas voir cette commande dans le portail client, car elle est un utilisateur non autorisé. (De plus, elle doit avoir passé la commande par un autre canal que le portail client.)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]