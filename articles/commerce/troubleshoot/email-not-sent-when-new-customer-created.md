---
title: L’e-mail de bienvenue n’est pas envoyé lorsque de nouveaux clients sont créés
description: Cet article fournit des conseils de dépannage qui peuvent vous aider si une notification par e-mail de bienvenue n’est pas envoyée lorsqu’un nouveau client est créé dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 5aa7d864555f96194500989e2d7ad200d8892121
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219402"
---
# <a name="welcome-email-isnt-sent-when-new-customers-are-created"></a>L’e-mail de bienvenue n’est pas envoyé lorsque de nouveaux clients sont créés

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de dépannage qui peuvent vous aider si une notification par e-mail de bienvenue n’est pas envoyée lorsqu’un nouveau client est créé dans Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Description

Lorsqu’un nouveau client est créé dans Commerce Headquarters, un e-mail de bienvenue n’est pas envoyé au client, même si une notification par e-mail est configurée pour le type de notification par e-mail **Client créé**.

## <a name="resolution"></a>Résolution

### <a name="associate-an-email-notification-profile-under-commerce-parameters"></a>Associez un profil de notification par e-mail sous les paramètres Commerce

1. Dans Headquarters, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux \> Général**.
2. Dans la liste déroulante **Profil de notification par e-mail**, sélectionnez le profil de notification par e-mail contenant un mappage entre le type de notification créé par le client et un modèle d’e-mail créé par le client.  

> [!NOTE] 
> Lorsque vous activez les notifications créées par le client, les clients créés dans tous les canaux de l’entité juridique recevront un e-mail créé par le client. Actuellement, les notifications créées par les clients ne peuvent pas être limitées à un seul canal.

Pour plus d’informations, voir [Créer des modèles d’e-mail pour les événements transactionnels](../email-templates-transactions.md). 

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un profil de notification par e-mail](../email-notification-profiles.md)
