---
title: "Créer des alertes"
description: "Cette rubrique fournit des informations sur les alertes et décrit la procédure de création d'une règle d'alerte pour être informé d'événements, par exemple une date qui arrive ou une modification spécifique qui se produit."
author: tjvass
manager: AnnBe
ms.date: 03/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.translationtype: HT
ms.sourcegitcommit: 454368ab5a467002ebf973db97fd98e31885dfe0
ms.openlocfilehash: 5bcd02e08a4ce5b601615b39bf95362cf92d3fec
ms.contentlocale: fr-fr
ms.lasthandoff: 03/23/2018

---

# <a name="create-alerts"></a>Créer des alertes

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [banner](../includes/pre-release.md)]

## <a name="getting-started"></a>Mise en route
Avant de définir une règle d'alerte, déterminez quand ou dans quelles situations vous souhaitez recevoir des alertes. Après avoir déterminé l'événement dont vous souhaitez être averti, dans Microsoft Dynamics 365 for Finance and Operations, recherchez la page où les données causant cet événement apparaissent. L'événement peut être une date qui arrive ou une modification spécifique qui se produit. Par conséquent, vous devez rechercher la page dans laquelle la date est spécifiée, ou dans laquelle le champ modifié ou le nouvel enregistrement créé apparaît. Une fois que vous disposez de ces informations, vous pouvez créer la règle d'alerte.

Lorsque vous créez une règle d'alerte, vous définissez les critères devant être remplis pour qu'une alerte soit déclenchée. Vous pouvez imaginer les critères comme une correspondance entre l'occurrence d'un événement et l'accomplissement d'une condition spécifique. Quand un événement se produit, le système vérifie s'il répond aux conditions définies dans Finance and Operations.

## <a name="events"></a>Événements
L'événement qui déclenche une règle d'alerte peut être une date qui arrive ou une modification spécifique qui se produit. Les déclencheurs des événements sont définis dans l'organisateur **Alertez-moi quand** de la boîte de dialogue **Créer une règle d'alerte**. Les événements disponibles pour un champ spécifique dépendent du déclencheur sélectionné.

Par exemple, si vous configurez une règle d'alerte pour le champ **Date de début**, les événements de date d'échéance sont appropriés. Par conséquent, le type d'événement **est prévue dans** est disponible pour ce champ. Toutefois, pour un champ tel que **Centre de coût**, un événement de date d'échéance n'est pas approprié. Par conséquent, le type d'événement **est prévue dans** n'est pas disponible. Le type d'événement **a été modifié** est disponible à la place.

## <a name="event-types"></a>Types d'événement
Trois types d'événements sont possibles :

- **Événements de type Création et de type Suppression** – Ces événements déclenchent une alerte lorsqu'un enregistrement est créé ou supprimé.
- **Événements de type Mise à jour** – Ces événements déclenchent une alerte lorsque les données d'un champ spécifique sont modifiées.
- **Événements de type Date d'échéance** – Ces événements déclenchent une alerte lorsqu'une date arrive.
    
Les modifications peuvent être apportées par un utilisateur. Par exemple, un utilisateur modifie la date de livraison d'une commande fournisseur. Les modifications peuvent aussi se produire dans le cadre d'un processus. Par exemple, le champ **Statut** d'une page change pour refléter le cycle de vie de divers processus dans le système.

## <a name="conditions"></a>Conditions
Dans l'organisateur **Alertez-moi pour** de la boîte de dialogue **Créer une règle d'alerte**, vous pouvez utiliser les conditions pour contrôler les moments où vous recevez une alerte à propos d'événements.

Par exemple, vous pouvez spécifier que le système vous prévienne en cas de modification du statut des commandes fournisseur, mais uniquement si le statut correspond à un ensemble spécifique de conditions. Spécifiquement, vous souhaitez être averti lorsque le statut d'une commande fournisseur est défini sur **Reçu**. La modification de ce statut est l'événement qui déclenche l'alerte.

Ensuite, vous devez décider à propos de quelles commandes fournisseur vous souhaitez être alerté. Vous pouvez par exemple sélectionner l'une des options suivantes : Ces options définissent les conditions de la règle d'alerte.

- **Enregistrement actuel sélectionné** – Vous recevez une alerte lorsque le statut d'une commande fournisseur spécifique devient **Reçu**.
- **Tous les enregistrements** – Vous recevez une alerte lorsque le statut d'une commande fournisseur est modifié pour un article dans la vue de page active. Vous pouvez utiliser le filtrage avancé disponible sur la page pour créer des règles pour un ensemble spécifique d'enregistrements. Par exemple, vous pouvez créer une alerte qui est déclenchée pour toutes les commandes fournisseur des clients d'un groupe de clients spécifique.
    
## <a name="expiry-of-rule"></a>Expiration d'une règle
Dans l'organisateur **Alertez-moi jusqu'à** de la boîte de dialogue **Créer une règle d'alerte**, vous pouvez spécifier la durée pendant laquelle la règle d'alerte doit être active.

## <a name="alert-contents"></a>Contenu des alertes
Dans l'organisateur **Alertez-moi avec** de la boîte de dialogue **Créer une règle d'alerte**, vous pouvez spécifier l'objet et le texte du message que les messages d'alerte doivent utiliser.

## <a name="user-id"></a>ID d'utilisateur
Dans l'organisateur **Alertez-moi avec** de la boîte de dialogue **Créer une règle d'alerte**, vous pouvez spécifier l'utilisateur qui doit recevoir les messages d'alerte. Par défaut, votre ID utilisateur est sélectionné. Cette option est limitée aux administrateurs de l'organisation.

## <a name="create-an-alert-rule"></a>Créer une règle d'alerte
1. Ouvrez la page qui contient les données à contrôler.
2. Dans le volet Actions, sous l'onglet **Options**, dans le groupe **Partager**, sélectionnez **Créer une règle d'alerte**.
3. Dans la boîte de dialogue **Créer une règle d'alerte**, dans le champ **Champ**, sélectionnez le champ à contrôler.
4. Dans le champ **Événement**, sélectionnez le type d'événement.
5. Dans l'organisateur **Alertez-moi pour**, sélectionnez une option.
6. Si la règle d'alerte doit devenir inactive à une date spécifique, dans l'organisateur **Alertez-moi jusqu'à**, sélectionnez une date de fin.
7. Dans l'organisateur **Alertez-moi avec**, dans le champ **Objet**, acceptez l'objet par défaut du message e-mail, ou entrez-en un nouveau. Le texte est utilisé comme objet pour le message e-mail que vous recevez en cas de déclenchement d'alerte.
8. Dans le champ **Message**, entrez un message facultatif. Le texte sera le message envoyé en cas de déclenchement d'alerte.
9. Sélectionnez **OK** pour enregistrer les paramètres et créer la règle d'alerte.

