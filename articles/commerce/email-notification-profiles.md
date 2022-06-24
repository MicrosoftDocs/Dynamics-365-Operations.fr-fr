---
title: Configurer un profil de notification par courrier électronique
description: Cet article décrit comment créer un profil de notification par e-mail dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 02/11/2022
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
ms.openlocfilehash: 109adcc4e8b49c665bd14ecab2b7cc56cebd2291
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878484"
---
# <a name="set-up-an-email-notification-profile"></a>Configurer un profil de notification par courrier électronique

[!include [banner](includes/banner.md)]

Cet article décrit comment créer un profil de notification par e-mail dans Microsoft Dynamics 365 Commerce.

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

### <a name="schedule-a-recurring-email-notification-process-job"></a>Planifier une tâche de processus de notification par e-mail récurrente

Pour envoyer des notifications par e-mail, vous devez disposer du travail **Traiter la notification par e-mail de commande au détail** en cours d’exécution.

Pour mettre en place le travail **Traiter la notification par e-mail de commande au détail** dans Commerce Headquarters si vous ne l’avez pas déjà fait, suivez ces étapes.

1. Accédez à **Retail et Commerce \> Retail et Commerce IT \> E-mail et notifications \> Envoyer une notification par e-mail**.
1. Dans la boîte de dialogue **Traiter la notification par e-mail de commande au détail**, sélectionnez **Récurrence**.
1. Dans la boîte de dialogue **Définir la récurrence**, sélectionnez **Pas de date de fin**.
1. Sous **Modèle de récurrence**, sélectionnez **Minutes**, puis définissez le champ **Nombre** sur **1**. Ces paramètres garantissent que les notifications par e-mail sont traitées aussi rapidement que possible.
1. Sélectionnez **OK** pour revenir à la boîte de dialogue **Traiter la notification par e-mail de commande au détail**.
1. Sélectionnez **OK** pour terminer la configuration de la tâche.

### <a name="next-steps"></a>Étapes suivantes

Avant de pouvoir envoyer des e-mails, vous devez configurer votre service de courrier sortant et configurer un traitement par lots. Pour plus d’informations, voir [Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Vue d’ensemble des canaux](channels-overview.md)

[Conditions préalables au paramétrage du canal](channels-prerequisites.md)

[Vue d’ensemble des organisations et des hiérarchies d’organisation](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
