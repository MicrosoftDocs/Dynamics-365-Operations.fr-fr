---
title: Paramètres de conversation instantanée proactive du module Commerce Chat
description: Cet article décrit les paramètres de conversation instantanée proactive des modules de conversation instantanée Commerce dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: f3cff89a25ff84414e7fdd32cbb26404c2080187
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691058"
---
# <a name="commerce-chat-module-proactive-chat-parameters"></a>Paramètres de conversation instantanée proactive du module Commerce Chat

[!include [banner](includes/banner.md)]

Cet article décrit les paramètres de conversation instantanée proactive de la conversation Commerce avec Omnicanal pour Customer Service et Commerce Chat avec les modules de conversation instantanée Power Virtual Agents dans Microsoft Dynamics 365 Commerce.

## <a name="proactive-chat-properties"></a>Propriétés de conversation instantanée proactive

Les propriétés de conversation instantanée proactive se situent dans le volet de propriétés de Commerce Chat avec Omnicanal pour Customer Service et Commerce Chat avec les modules Power Virtual Agents dans le générateur de sites Commerce.

> [!NOTE]
> Par défaut, toutes les propriétés de conversation instantanée proactive qui sont répertoriées ici sont vides. Nous vous recommandons d’en savoir plus sur ces propriétés et de ne les définir que si elles sont nécessaires. Cette approche aide à réduire le déclenchement de conversations instantanées proactives erronées.

### <a name="proactive-chat"></a>Conversation instantanée proactive

| Nom convivial | Description | Valeur par défaut |
|---------------|-------------|---------------|
| Activé(e) | Engagez les clients de manière proactive, en fonction de différents déclencheurs. | Désactivé |
| Accueil de conversation instantanée | Message d’accueil utilisé lorsqu’une conversation instantanée proactive a été déclenchée. | Blanc |

### <a name="wait-time-proactive-chat"></a>Temps d’attente (conversation instantanée proactive)

| Nom convivial | Description |
|---------------|-------------|
| Temps d’attente (sec) | Le temps (en secondes) que les utilisateurs du site passent sur une page du site avant qu’une conversation instantanée proactive ne soit déclenchée. |
| Accueil de conversation instantanée | Message d’accueil utilisé lorsqu’une conversation instantanée proactive a été déclenchée. |

### <a name="number-of-page-visits-proactive-chat"></a>Nombre de visites de pages (conversation instantanée proactive)

| Nom convivial | Description |
|---------------|-------------|
| Nombre de pages visitées | Le nombre de visites de pages avant qu’une conversation instantanée proactive ne soit déclenchée. Les utilisateurs du site doivent d’abord accepter l’invite dans la bannière de consentement aux cookies. |
| Accueil de conversation instantanée | Message d’accueil utilisé lorsqu’une conversation instantanée proactive a été déclenchée. |

### <a name="specific-pages-proactive-chat"></a>Pages spécifiques (conversation instantanée proactive)

| Nom convivial | Description |
|---------------|-------------|
| Page(s) | Une liste des pages qui déclenchent une conversation instantanée proactive lorsqu’elles sont visitées. |
| Accueil de conversation instantanée | Message d’accueil utilisé lorsqu’une conversation instantanée proactive a été déclenchée. |

### <a name="from-specific-pages-proactive-chat"></a>Page(s) spécifique(s) d’origine (conversation instantanée proactive)

| Nom convivial | Description |
|---------------|-------------|
| Page(s) | Une liste des pages qui déclenchent une conversation instantanée proactive lorsque les utilisateurs s’éloignent d’elles. |
| Accueil de conversation instantanée | Message d’accueil utilisé lorsqu’une conversation instantanée proactive a été déclenchée. |

### <a name="specific-countryregion-proactive-chat"></a>Pays/région spécifique (conversation instantanée proactive)

| Nom convivial | Description |
|---------------|-------------|
| Code pays | Les utilisateurs qui visitent des pays ou des régions spécifiés déclenchent une conversation instantanée proactive. Les codes pays/région doivent être constitués de deux lettres majuscules (par exemple : **FR**). |
| Accueil de conversation instantanée | Message d’accueil utilisé lorsqu’une conversation instantanée proactive a été déclenchée. |

### <a name="date-range-proactive-chat"></a>Plage de dates (conversation instantanée proactive)

| Nom convivial | Description |
|---------------|-------------|
| Date de début (jj/mm/aaaa) | La date à laquelle ou après laquelle une conversation instantanée proactive est déclenchée. |
| Date de fin (jj/mm/aaaa) | La date à laquelle ou avant laquelle une conversation instantanée proactive est déclenchée. |
| Accueil de conversation instantanée | Message d’accueil utilisé lorsqu’une conversation instantanée proactive a été déclenchée. |

### <a name="total-amount-in-cart-proactive-chat"></a>Montant total dans le panier (conversation instantanée proactive)

| Nom convivial | Description |
|---------------|-------------|
| Minimale | Le montant monétaire minimum (inclus) dans le panier qui déclenche une conversation instantanée proactive lorsque les utilisateurs visitent la page du panier. |
| Maximale | Le montant monétaire maximum (inclus) dans le panier qui déclenche une conversation instantanée proactive lorsque les utilisateurs visitent la page du panier. |
|Accueil de conversation instantanée | Message d’accueil utilisé lorsqu’une conversation instantanée proactive a été déclenchée. |

### <a name="total-number-of-items-in-cart-proactive-chat"></a>Nombre total d’articles dans le panier (conversation instantanée proactive)

| Nom convivial | Description |
|---------------|-------------|
| Minimale | Le montant monétaire minimum d’articles (inclus) dans le panier qui déclenche une conversation instantanée proactive lorsque les utilisateurs visitent la page du panier. |
| Maximale | Le montant monétaire maximum d’articles (inclus) dans le panier qui déclenche une conversation instantanée proactive lorsque les utilisateurs visitent la page du panier. |
| Accueil de conversation instantanée | Message d’accueil utilisé lorsqu’une conversation instantanée proactive a été déclenchée. |

### <a name="specific-products-in-cart-proactive-chat"></a>Produits spécifiques dans le panier (conversation instantanée proactive)

| Nom convivial | Description |
|---------------|-------------|
| ID/SKU des produits | Une liste des identifiants de produits/numéros d’unités de gestion des stocks (SKU) qui déclenchent une conversation instantanée proactive lorsque les utilisateurs visitent la page du panier. |
| Accueil de conversation instantanée | Message d’accueil utilisé lorsqu’une conversation instantanée proactive a été déclenchée. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation des fonctionnalités de conversation instantanée Commerce](commerce-chat-overview.md)

[Commerce Chat avec le module Omnicanal pour Customer Service](commerce-chat-module.md)

[Module de conversation instantanée avec le module Power Virtual Agents](chat-module-pva.md)
