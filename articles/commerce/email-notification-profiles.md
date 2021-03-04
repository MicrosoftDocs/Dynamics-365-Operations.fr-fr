---
title: Paramétrer un profil de notification par e-mail
description: Cette rubrique décrit comment créer un profil de notification par e-mail dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c0ab56c15a37313d0a88b1174d5bcf51d391dcec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412181"
---
# <a name="set-up-an-email-notification-profile"></a>Paramétrer un profil de notification par e-mail


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer un profil de notification par e-mail dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Avant de créer des canaux, vous souhaiterez configurer un profil pour vous assurer que les notifications par e-mail peuvent être envoyées pour divers événements, tels que la création de commande, l'état d'expédition de la commande et l'échec du paiement.

Pour plus d'informations sur la configuration de l'e-mail, consultez la rubrique [Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Créer un profil de notification par e-mail

Pour créer un profil de notification par e-mail, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Profil de notification par e-mail de Commerce**.
1. Dans le volet Actions, cliquez sur **Nouveau**.
1. Dans le champ **Profil de notification par e-mail**, entrez un nom pour identifier le profil.
1. Entrez une description pertinente dans le champ **Description**.
1. Paramétrer le commutateur **Actif** sur **Oui**.

### <a name="create-an-email-template"></a>Créer un modèle d'e-mail

Avant de pouvoir créer une notification par e-mail, vous devez créer un modèle de courrier électronique pour l'organisation qui contient les informations d'e-mail de l'expéditeur et le modèle d'e-mail.

Pour créer un modèle d'e-mail, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Paramètres \> Modèles d'e-mail pour l'organisation**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **ID e-mail**, entrez un ID pour vous aider à identifier ce modèle.
1. Entrez le nom des expéditeurs dans le champ **Nom des expéditeurs**.
1. Entrez une description pertinente dans le champ **Description de l'e-mail**.
1. Dans le champ **E-mail de l'expéditeur**, entrez l'adresse e-mail des expéditeurs.
1. Dans la section **Général**, remplissez toutes les informations facultatives nécessaires (telles que la priorité des e-mails).
1. Élargissez la section **Contenu du message électronique** et sélectionnez **Nouveau** pour créer le contenu du modèle. Pour chaque élément de contenu, sélectionnez la langue et indiquez la ligne d'objet de l'e-mail. Si l'e-mail va avoir un corps, assurez-vous que la case **A un corps** est cochée.
1. Dans le volet Actions, sélectionnez **Message électronique** pour fournir un modèle de corps d'e-mail.

L'image suivante montre quelques exemples de paramètres de modèle d'e-mail.

![Paramètres du modèle d'e-mail](media/email-template.png)

### <a name="create-an-email-event"></a>Créer un événement d'e-mail

Pour créer un événement d'e-mail, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Configuration du siège \> Profil de notification par e-mail de Commerce**.
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. 
1. Sélectionnez le modèle d'e-mail dans la liste déroulante **ID e-mail**.
1. Sélectionnez le bon **Type de notification par e-mail** dans la liste déroulante.
1. Cochez la case **Actif**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L'image suivante montre quelques exemples de notification d'événements.

![Paramètres de notification d'événements](media/email-notification-profile.png)

### <a name="next-steps"></a>Étapes suivantes

Avant de pouvoir envoyer des e-mails, vous devez configurer votre service de courrier sortant et configurer un traitement par lots. Pour plus d'informations, voir [Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).


## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Vue d'ensemble des canaux](channels-overview.md)

[Conditions préalables au paramétrage du canal](channels-prerequisites.md)

[Vue d'ensemble des organisations et des hiérarchies d'organisation](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]