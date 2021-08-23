---
title: Notifications d’alerte de client par e-mail
description: Cette rubrique offre des informations sur la manière de configurer des règles qui envoient des notifications par e-mail lorsque des événements prédéfinis se produisent.
author: RichdiMSFT
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 4e2205ba3bdf5ec2a4e6d9390007eaf1098293c3dd2a5b2ff1b3c73c7de5a83f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734612"
---
# <a name="client-alert-notifications-by-email"></a>Notifications d’alerte du client par e-mail

[!include [banner](../includes/banner.md)]

Vous pouvez définir des règles d’alerte personnalisées qui surveillent les vues filtrées des données et qui envoient automatiquement les notifications par e-mail lorsque des événements prédéfinis surviennent. L’option d’envoi de notifications par e-mail est disponible pour tous les types d’alerte pris en charge et vous pouvez également les activer pour les règles d’alerte existantes.

Vous pouvez utiliser les contrôles intégrés pour créer des règles d’alerte qui supervisent les vues filtrées des traitements par lots du système. En surveillant la valeur du champ **Statut**, vous pouvez également configurer les règles d’alerte qui envoient un e-mail en cas d’échec d’un traitement par lots. Une fois ces règles d’alerte créées, vous n’avez plus à vérifier les états relatifs aux modifications apportées aux données commerciales. Au lieu de cela, vous pouvez laisser le service de détection intelligente des modifications faire le contrôle pour vous.

Les alertes de client dépendent du sous-système d’e-mail fourni via l’intégration avec Microsoft Office. Nous vous recommandons d’utiliser le fournisseur SMTP afin que la distribution d’e-mail n’ait pas à se reposer sur un client de courrier local.

Pour envoyer des notifications par e-mail, les clients doivent configurer des services d’e-mail intégrés. Les notifications par e-mail sont envoyées aux destinataires pour le compte de propriétaires d’alerte.

Pour plus d’informations sur la configuration de l’e-mail, consultez la rubrique [Configurer et envoyer un e-mail](../organization-administration/configure-email.md).

L’image suivante présente la boîte de dialogue **Créer une règle d’alerte**, qui comprend désormais une option **Envoyer un e-mail**.

[![Créer la boîte de dialogue de règle d’alerte, où l’option Envoyer un e-mail est définie sur Oui.](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)

> [!NOTE]
> Lorsque l’option **Envoyer un e-mail** est définie sur **Oui**, les notifications d’alerte continuent d’être fournies depuis le centre d’action.

## <a name="alert-notification-email-templates"></a>Modèles d’e-mail de notification d’alerte

Le service envoie des notifications par e-mail à l’aide de modèles d’e-mail prédéfinis qui offrent les détails de base de la notification d’alerte.

L’image suivante présente la structure des notifications d’alerte lorsqu’elles sont reçues par e-mail.

[![Notifications d’alerte basées sur un modèle pour la création des enregistrements, les modifications de champ et la suppression du modèle.](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]