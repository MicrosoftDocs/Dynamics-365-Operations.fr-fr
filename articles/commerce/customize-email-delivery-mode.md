---
title: Personnalisez les e-mails transactionnels par mode de livraison
description: Cette rubrique décrit comment configurer des modèles d’e-mail personnalisés pour des types de notification et des modes de livraison spécifiques dans Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: d15e7c5c7050ad373cb45da72de59416e85a5f2034f7a11b007d497b2e2b98bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749905"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a>Personnaliser les e-mails transactionnels par mode de livraison

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment configurer des modèles d’e-mail personnalisés pour des types de notification et des modes de livraison spécifiques dans Microsoft Dynamics 365 Commerce.

Les e-mails transactionnels peuvent désormais être personnalisés pour une combinaison d’un type de notification (par exemple, **Commande créée**, **Commande conditionnée**, ou **Commande facturée**) et un mode de livraison (par exemple, la nuit, le retrait en magasin ou le retrait à un point-relais). Les e-mails transactionnels personnalisés permettent aux détaillants de proposer à leurs clients des expériences de traitement adaptées au mode de livraison de la commande. Par exemple, l’événement "commande conditionnée" peut être personnalisé de manière à fournir des instructions de retrait en point-relais pour les clients qui choisissent ce mode de retrait. Il peut également fournir des informations sur le transporteur et la livraison aux clients qui choisissent de faire expédier leur commande.

> [!NOTE]
> Pour utiliser la fonctionnalité des e-mails transactionnels personnalisés, vous devez d’abord activer la fonctionnalité **Personnaliser les modèles d’e-mails transactionnels par mode de livraison** en allant à **Espaces de travail \> Gestion des fonctionnalités** au siège de Commerce.

Les e-mails peuvent être personnalisés par mode de livraison pour les types de notification suivants :

- **Annulation de la commande** – Ce type de notification par e-mail est nouveau.
- **Commande créée**
- **Commande confirmée**
- **Commande facturée** – Ce type de notification par e-mail est nouveau. Il peut être utilisé à la place du type de notification **Commande expédiée** qui enverra une notification pour tout événement de facturation qui a un mode de livraison expédié (pas un retrait, à emporter ou un mode de livraison électronique).
- **Commande retirée**
- **Commande conditionnée**
- **Commande prête pour le retrait** – Ce type de notification ne peut être personnalisé par mode de livraison que si la fonctionnalité **Prise en charge de plusieurs modes de livraison par retrait** est activée. Dans ce cas, ce type de notification est fonctionnellement équivalent au type de notification **Commande conditionnée**.
- **Échec du paiement**
- **Ordre de remplacement créé**

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a>Configurer des modèles d’e-mails pour des modes de livraison spécifiques

Pour cette procédure, on suppose que vous avez déjà créé vos modèles d’e-mails personnalisés et les avez ajoutés à la page **Modèles d’e-mail d’organisation**. Pour plus d’informations sur la création et le chargement de modèles d’e-mail, voir [Créer des modèles d’e-mail pour les événements transactionnels](email-templates-transactions.md).

Pour configurer des modèles d’e-mail pour des modes de livraison spécifiques au siège de Commerce, procédez comme suit.

1. Aller à **Profil de notification par e-mail Commerce**.
1. Sous **Paramètres de notification des événements de vente au détail**, sélectionnez un type de notification existant.
1. Pendant que le type de notification est toujours sélectionné, sélectionnez **Configurer les modes de livraison**.
1. Dans la boîte de dialogue **Modes de livraison**, sélectionnez **Nouveau**.
1. Dans la nouvelle ligne du champ **Mode de livraison**, sélectionnez un mode de livraison.
1. Dans le champ **ID e-mail**, sélectionnez le modèle d’e-mail à mapper au mode de livraison.
1. Cochez la case **Actif**.
1. Répétez les étapes 4 à 7 pour ajouter d’autres modes de livraison.
1. Lorsque vous avez terminé, sélectionnez **OK**.

> [!NOTE]
> - Lorsque plusieurs modes de livraison sont présents sur les lignes d’une commande client, le modèle par défaut est utilisé. Le modèle par défaut est le modèle qui est mappé au type de notification sur la page **Profil de notification par e-mail Commerce**.
> - Si une commande client a un mode de livraison qui n’a pas été configuré pour un modèle d’e-mail personnalisé, le modèle d’e-mail par défaut sera utilisé.

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer des commandes de centre d’appels](tasks/create-call-center-orders.md)

[Modifier le mode de livraison dans le PDV](pos-change-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]