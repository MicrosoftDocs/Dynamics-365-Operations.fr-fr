---
title: L’e-mail de bienvenue n’est pas envoyé lorsque de nouveaux clients sont créés
description: Cette rubrique fournit des conseils de dépannage qui peuvent vous aider si une notification par e-mail de bienvenue n’est pas envoyée lorsqu’un nouveau client est créé dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 1a4faf6cd189f69232e7f9ab8d0e79b320cfe2d9
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349964"
---
# <a name="welcome-email-is-not-sent-when-new-customers-are-created"></a>L’e-mail de bienvenue n’est pas envoyé lorsque de nouveaux clients sont créés

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des conseils de dépannage qui peuvent vous aider si une notification par e-mail de bienvenue n’est pas envoyée lorsqu’un nouveau client est créé dans Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Description

Lorsqu’un nouveau client est créé dans Commerce Headquarters, un e-mail de bienvenue n’est pas envoyé au client, même si une notification par e-mail est configurée pour le type de notification par e-mail **Client créé**.

## <a name="resolution"></a>Résolution

### <a name="set-the-correct-email-id-value-for-the-customer-created-email-notification-type"></a>Définir la valeur d’identifiant de messagerie correcte pour le type de notification par e-mail créé par le client

Pour définir la valeur **Identifiant de messagerie** exacte pour le type de notification par e-mail **Client créé** dans Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Configuration de Headquarters \> Profil de notification par e-mail Commerce**.
1. Dans le volet de navigation de gauche, sélectionnez le profil de notification par e-mail.
1. Sous **Paramètres des notifications d’événements Retail**, pour le type de notification par e-mail **Client créé**, définissez le champ **Identifiant de messagerie** sur **NewCust**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un profil de notification par e-mail](../email-notification-profiles.md)
