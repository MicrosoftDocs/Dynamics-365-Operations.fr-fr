---
title: Remise sur expédition
description: Cet article décrit les fonctionnalités de remise sur les frais d’expédition dans Microsoft Dynamics 365 Commerce et la configuration requise pour les utiliser.
author: ShalabhjainMSFT
ms.date: 08/23/2020
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2019-01-31
ms.openlocfilehash: 74cfe5246ad72cbdedd0ed4e3b3394bf7277919e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473848"
---
# <a name="shipping-discount"></a>Remise sur expédition

[!include [banner](includes/banner.md)]

Cet article décrit les fonctionnalités de remise sur les frais d’expédition dans Microsoft Dynamics 365 Commerce et la configuration requise pour les utiliser.

La livraison gratuite ou à prix réduit est un facteur qui influence les décisions d’achat en ligne des clients. Pour augmenter leurs revenus par transaction, de nombreux détaillants utilisent la livraison gratuite pour motiver les clients à augmenter la taille de leur panier.

Commerce prend en charge une capacité de remise sur les frais d’expédition qui permet aux détaillants de configurer un pourcentage de remise sur les frais d’expédition pour une méthode d’expédition spécifique lorsque le montant total des ventes d’articles qualifiés dans la transaction répond à des critères spécifiques. Un exemple de scénario qui utilise la fonctionnalité de remise sur les frais d’expédition est « Dépensez $50 ou plus pour bénéficier d’une livraison gratuite le lendemain ».

## <a name="prerequisites"></a>Conditions préalables

La capacité de remise d’expédition est prise en charge par les caractéristiques [recharges automatiques avancées omnicanales](/dynamics365/unified-operations/retail/omni-auto-charges) de Commerce. Pour que la capacité de remise sur les frais d’expédition fonctionne, vous devez activer la configuration **Utiliser les frais automatiques avancés** dans l'onglet **Commandes clients** de la page **Paramètres commerciaux** de Commerce headquarters. Les détaillants peuvent utiliser la caractéristique avancée de frais automatiques pour configurer divers types de frais, tels que la manutention, l’installation et l’élimination.

Les remises sur expédition s’appliquent uniquement aux frais d’expédition. Par conséquent, un détaillant doit spécifier quels frais sont des frais d’expédition. Pour spécifier les frais d’expédition, dans Commerce headquarters, accédez à **Configuration du canal\> Charges\> Codes des charges**, et définissez l'option des **Frais d'expédition** sur **Oui** pour les frais souhaités.

![Spécification d’une charge comme frais d’expédition.](./media/Specify_shipping_charge.png)

## <a name="configuration"></a>Configuration

La capacité de remise d’expédition est basée sur le niveau et ne prend en charge que le type de calcul du **Pourcentage de réduction**. Pour configurer une remise sur les frais d’expédition, dans Commerce headquarters, accédez à **Tarifs et remises \> Remise sur le seuil d’expédition**. Vous pouvez ensuite spécifier le mode de livraison auquel s’applique la remise, définir un ou plusieurs seuils de montant et définir le pourcentage de remise pour chaque seuil. Vous pouvez également configurer une liste de catégories ou de produits en tant qu’articles qualifiés. De cette façon, seul le montant des ventes par rapport à ces articles dans une transaction sera compté lorsque le moteur de tarification évaluera si le total de la transaction atteint le seuil.

> [!NOTE]
> Contrairement aux autres types de remise, la remise sur les frais d’expédition ne crée pas de lignes de remise. Au lieu de cela, elle modifie directement les frais d’expédition et ajoute le nom de la remise à la description des frais.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
