---
title: Masquer les informations sur la répartition des taxes dans les récapitulatifs de commande
description: Cette rubrique décrit comment masquer les informations de répartition des taxes dans les récapitulatifs de commande sur les pages de panier, de paiement, de confirmation de commande et de détails de commande dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 04/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-03-28
ms.openlocfilehash: 9890b5cd92f8c07e6feabb26f4fdd076cb7a02bc
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645217"
---
# <a name="hide-tax-breakup-information-in-order-summaries"></a>Masquer les informations sur la répartition des taxes dans les récapitulatifs de commande

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique décrit comment masquer les informations de répartition des taxes dans les récapitulatifs de commande sur les pages de panier, de paiement, de confirmation de commande et de détails de commande dans Microsoft Dynamics 365 Commerce.

Par défaut, Dynamics 365 Commerce affiche les informations de répartition des taxes dans les récapitulatifs de commande sur les pages de panier, de paiement, de confirmation de commande et de détails de commande. À partir de la version 10.0.27 de Commerce, le générateur de site Commerce inclut une option qui vous permet de masquer les informations de répartition des taxes dans les récapitulatifs de commande.

L’illustration suivante montre un exemple de deux récapitulatifs de commande. Le premier affiche les informations sur la répartition des taxes et le second les masque.

![Exemples de paniers où les informations sur la répartition des taxes sont affichées et masquées.](media/prices-include-sales-tax-e-Commerce.png)

> [!NOTE]
> - L’option permettant de masquer les informations sur la répartition des taxes dans les récapitulatifs de commande n’est disponible que quand l’option **Les prix incluent la taxe de vente** pour le canal d’e-commerce est définie sur **Oui** dans Commerce headquarters, à **Retail et Commerce \> Canaux \> Magasins \> Tous les magasins**. 
> - Par défaut, l’option **Afficher la répartition des taxes dans le récapitulatif de la commande** est activée dans le générateur de site.

## <a name="hide-tax-breakup-information-in-order-summaries"></a>Masquer les informations sur la répartition des taxes dans les récapitulatifs de commande

Pour masquer les informations sur la répartition des taxes dans les récapitulatifs de commande, procédez comme suit.

1. Dans le générateur de site Commerce, accédez au site que vous souhaitez mettre à jour.
1. Accédez à **Paramètres du site \> Extensions**.
1. Décochez la case **Afficher la répartition des taxes dans le récapitulatif de la commande**.

Pour afficher les informations sur la répartition des taxes dans les récapitulatifs de commande, cochez la case **Afficher la répartition des taxes dans le récapitulatif de la commande**.  

L’illustration suivante affiche la case à cocher **Afficher la répartition des taxes dans le récapitulatif de la commande** en surbrillance et activée dans le générateur de site.

![L’option Afficher la répartition des taxes dans le récapitulatif de la commande dans le générateur de site.](media/prices-include-sales-tax-e-Commerce-site-settings.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des taxes](/finance/general-ledger/indirect-taxes-overview)

[Configurer la taxe pour les commandes en ligne](sales-tax-config.md)

[Résoudre des problèmes : Les taxes sur les commandes en ligne ne sont pas correctement calculées](troubleshoot/tax-miscalculated-online-order.md)
