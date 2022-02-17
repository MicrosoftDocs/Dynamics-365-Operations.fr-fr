---
title: Paramétrer un profil de notification par e-mail
description: Cette rubrique décrit comment créer un profil de notification par e-mail dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 02/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7a7d796a173a6f9dfcd62e1f73e078cac614145e
ms.sourcegitcommit: 2aca3a95d42403c7f5d80dcd5e3ee958dca5c894
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2022
ms.locfileid: "8087865"
---
# <a name="set-up-an-email-notification-profile"></a>Configurer un profil de notification par e-mail

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer un profil de notification par e-mail dans Microsoft Dynamics 365 Commerce.

Lorsque vous créez des canaux, vous pouvez configurer un profil de notification par e-mail. Le profil de notification par e-mail définit les événements d’une transaction de vente (tels que les événements de création de commande, de commande emballée et de commande facturée) pour lesquels vous enverrez des notifications à vos clients. 

Pour plus d’informations sur la configuration de l’e-mail, consultez la rubrique [Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Créer un profil de notification par e-mail

Pour créer un profil de notification par e-mail, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Profil de notification par e-mail de Commerce**.
1. Dans le volet Actions, cliquez sur **Nouveau**.
1. Dans le champ **Profil de notification par e-mail**, entrez un nom pour identifier le profil.
1. Entrez une description pertinente dans le champ **Description**.
1. Paramétrer le commutateur **Actif** sur **Oui**.

### <a name="create-an-email-template"></a>Créer un modèle d’e-mail

Avant qu’un type de notification par e-mail puisse être activé, vous devez créer un modèle d’e-mail d’organisation dans Commerce Headquarters pour chaque type de notification que vous souhaitez prendre en charge. Ce modèle définit l’objet de l’e-mail, l’expéditeur, la langue par défaut et le corps de l’e-mail pour chaque langue prise en charge.

Pour créer un modèle d’e-mail, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Paramètres \> Modèles d’e-mail pour l’organisation**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **ID e-mail**, entrez un ID pour vous aider à identifier ce modèle.
1. Entrez le nom des expéditeurs dans le champ **Nom des expéditeurs**.
1. Entrez une description pertinente dans le champ **Description de l’e-mail**.
1. Dans le champ **E-mail de l’expéditeur**, entrez l’adresse e-mail des expéditeurs.
1. Dans la section **Général**, sélectionnez une langue par défaut pour le modèle d’e-mail. La langue par défaut sera utilisée lorsqu’aucun modèle localisé n’existe pour la langue spécifiée.
1. Élargissez la section **Contenu du message électronique** et sélectionnez **Nouveau** pour créer le contenu du modèle. Pour chaque élément de contenu, sélectionnez la langue et indiquez la ligne d’objet de l’e-mail. Si l’e-mail va avoir un corps, assurez-vous que la case **A un corps** est cochée.
1. Dans le volet Actions, sélectionnez **Message électronique** pour fournir un modèle de corps d’e-mail.

L’image suivante montre quelques exemples de paramètres de modèle d’e-mail.

![Paramètres du modèle d’e-mail.](media/email-template.png)

Pour plus d’informations sur la création et le chargement de modèles d’e-mail, voir [Créer des modèles d’e-mail pour les événements transactionnels](email-templates-transactions.md). 

### <a name="create-an-email-event"></a>Créer un événement d’e-mail

Pour créer un événement d’e-mail, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Profil de notification par e-mail de Commerce**.
1. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. 
1. Sélectionnez le modèle d’e-mail dans la liste déroulante **ID e-mail**.
1. Sélectionnez le bon **Type de notification par e-mail** dans la liste déroulante.
1. Cochez la case **Actif**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’image suivante montre quelques exemples de notification d’événements.

![Paramètres de notification d’événements.](media/email-notification-profile.png)

> [!NOTE]
> Le type de notification créé par le client nécessite la mise en œuvre d’une personnalisation avant qu’une notification par e-mail puisse être envoyée.

### <a name="next-steps"></a>Étapes suivantes

Avant de pouvoir envoyer des e-mails, vous devez configurer votre service de courrier sortant et configurer un traitement par lots. Pour plus d’informations, voir [Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Vue d’ensemble des canaux](channels-overview.md)

[Conditions préalables au paramétrage du canal](channels-prerequisites.md)

[Vue d’ensemble des organisations et des hiérarchies d’organisation](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
