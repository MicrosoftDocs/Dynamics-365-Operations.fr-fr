---
title: Vue d’ensemble des alertes
description: Cette rubrique fournit des informations générales sur les alertes. Vous pouvez utiliser les alertes pour rester informé des événements que vous voulez suivre durant votre journée de travail.
author: RichdiMSFT
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.custom: intro-internal
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: f114e6bd04622dcac668d15ad6c55f7de70b4e7e
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6336740"
---
# <a name="alerts-overview"></a>Vue d’ensemble des alertes

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a>À propos des alertes
Les alertes constituent un système de notification pour des événements critiques dans le système. Vous pouvez utiliser les alertes pour rester informé des événements que vous voulez suivre durant votre journée de travail. Vous pouvez facilement créer votre propre ensemble de règles d’alerte pour être prévenu des livraisons en retard, des suppressions de commandes, des modifications de prix et d’autres événements nécessitant une réaction de votre part.

Dans un système ERP (Enterprise Resource Planning), il existe plusieurs scénarios standard où la fonction d’alertes peut être utilisée. Voici quelques exemples.

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a>Scénario 1 : création d’une règle d’alerte pour les nouvelles commandes client

1. Ouvrez la page **Toutes les commandes client**.
2. Dans le volet Actions, sous l’onglet **Options**, dans le groupe **Partager**, sélectionnez **Créer une alerte personnalisée**.
3. Dans la boîte de dialogue **Créer une règle d’alerte**, dans l’organisateur **Alertez-moi quand**, dans le champ **Événement**, sélectionnez **L’enregistrement a été créé**.

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a>Scénario 2 : création d’une règle d’alerte pour l’ajournement d’une date de livraison

1. Ouvrez la page **Toutes les commandes fournisseur**.
2. Sélectionnez un ID commande fournisseur pour accéder aux détails de la commande fournisseur.
3. Développez l’organisateur **En-tête de commande fournisseur**.
4. Dans le volet Actions, sous l’onglet **Options**, dans le groupe **Partager**, sélectionnez **Créer une alerte personnalisée**.
5. Dans la boîte de dialogue **Créer une règle d’alerte**, dans l’organisateur **Alertez-moi quand**, dans le champ **Champ**, sélectionnez **Date de livraison**.
6. Dans le champ **Événement**, sélectionnez **a été reporté**.
    
Après avoir fermé la boîte de dialogue **Créer une règle d’alerte**, votre règle apparaît sur la page **Gérer les règles d’alerte**. Vous pouvez utiliser la page **Gérer les règles d’alerte** pour mettre à jour vos règles d’alerte existantes. Par exemple, vous pouvez modifier les déclencheurs d’événement, mettre à jour les notifications d’événement et mettre à jour les dates d’expiration. Pour ouvrir la page **Gérer les règles d’alerte**, utilisez le bouton **Alertez-moi** sous l’onglet **Options** du volet Actions.

## <a name="what-occurs-when-an-alert-rule-is-created"></a>Que se passe-t-il lors de la création d’une règle d’alerte ?

Lorsque vous créez des règles d’alerte, vous pouvez associer un événement prédéfini à un champ spécifique. Par exemple, la date spécifiée dans le champ arrive, ou le contenu du champ change. Vous pouvez également associer un événement aux enregistrements d’une page spécifique. Par exemple, un enregistrement est créé ou supprimé.

Lorsque l’événement sélectionné se produit pour le champ ou pour un événement de la page, une alerte vous est envoyée. Par exemple, vous créez une règle dans laquelle vous associez le champ **Date de livraison** sur une ligne de commande fournisseur spécifique à l’événement **était due il y a autant de temps**. Vous définissez la période à cinq jours. Dans ce cas, une alerte est envoyée cinq jours après la date de livraison de cette ligne de commande fournisseur.

En outre, vous pouvez affiner les règles d’alerte en définissant des conditions. Par exemple, vous pouvez être alerté à propos des nouvelles commandes fournisseur créées pour les comptes fournisseur spécifiques.

## <a name="preparing-for-an-alert"></a>Préparation pour une alerte

Avant de définir une règle d’alerte, déterminez quand ou dans quelles situations vous souhaitez recevoir des alertes. Après avoir déterminé l’événement dont vous souhaitez être averti, recherchez la page où les données causant cet événement apparaissent. L’événement peut être une date qui arrive ou une modification spécifique qui se produit. Par conséquent, vous devez rechercher la page dans laquelle la date est spécifiée, ou dans laquelle le champ modifié ou le nouvel enregistrement créé apparaît. Une fois que vous disposez de ces informations, vous pouvez créer la règle d’alerte.

## <a name="components-of-an-alert-rule"></a>Composants d’une règle d’alerte

Une règle d’alerte a cinq composants :

- **Événement** – L’événement qui déclenche une règle d’alerte peut être une date qui arrive ou une modification spécifique qui se produit. Vous définissez des événements dans l’organisateur **Envoyer des alertes par e-mail en cas de changement de statut d’une tâche** de la boîte de dialogue **Créer une règle d’alerte**.
- **Condition** – Dans l’organisateur **Alertez-moi pour** de la boîte de dialogue **Créer une règle d’alerte**, vous pouvez sélectionner la portée de la condition pour contrôler les moments où vous recevez une alerte à propos d’événements. Vous pouvez appliquer la règle à l’enregistrement actuel uniquement ou à tous les enregistrements visibles sur la page. Si la règle s’applique à plusieurs entités juridiques, vous pouvez définir l’option **À l’échelle de l’organisation** sur **Oui**.
- **Expiration d’une règle** – Dans l’organisateur **Alertez-moi jusqu’à** de la boîte de dialogue **Créer une règle d’alerte**, vous pouvez spécifier la durée pendant laquelle la règle d’alerte doit être active.
- **Contenu** – Dans l’organisateur **Alertez-moi avec** de la boîte de dialogue **Créer une règle d’alerte**, vous pouvez spécifier l’objet et le texte du message que les messages d’alerte doivent utiliser.
- **Utilisateur** – Dans l’organisateur **Personne à alerter** de la boîte de dialogue **Créer une règle d’alerte**, vous pouvez spécifier l’utilisateur qui doit recevoir les messages d’alerte. Par défaut, votre ID utilisateur est sélectionné.

    > [!NOTE]
    > Cette option est limitée aux administrateurs de l’organisation.

## <a name="videos"></a>Vidéos

### <a name="how-to-use-alerts-to-monitor-filtered-data"></a>Comment utiliser les alertes pour surveiller les données filtrées

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3DWZ3]

La vidéo [Comment utiliser les alertes pour surveiller les données filtrées](https://youtu.be/ZYKMcv6kl9s) (présentée ci-dessus) est incluse dans la liste de lecture [Finance and Operations ](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)disponible sur YouTube.

### <a name="alert-rule-options"></a>Options de règle d’alerte

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E4PV]

La vidéo [Options de règle d’alerte](https://youtu.be/cpzimwOjicM) (présentée ci-dessus) est incluse dans la liste de lecture [Finance and Operations ](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]