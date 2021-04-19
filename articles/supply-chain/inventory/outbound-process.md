---
title: Vue d’ensemble du processus sortant
description: Cette rubrique fournit une vue d’ensemble du processus sortant dans la Gestion des stocks.
author: perlynne
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: e9f9da7d6e3ede9816757fb57f0b802ce4d41360
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825937"
---
# <a name="outbound-process-overview"></a>Vue d’ensemble du processus sortant

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d’ensemble du processus sortant dans la Gestion des stocks.

## <a name="output-orders"></a>Ordres de sortie

Les ordres de sortie permettent de lier les lignes de commande client et les lignes d’ordre de transfert avec les processus sortants de prélèvement qui utilisent des prélèvements.

Lorsque des prélèvements sont générés à partir de commandes client ou d’ordres de transfert, des ordres de sortie et des expéditions sont automatiquement créés. Un prélèvement a une relation de 1 à 1 avec une expédition. L’expédition de l’ordre de transfert ou le bon de livraison de la commande client peut être traité(e) à l’expédition. 

Le diagramme suivant présente une vue d’ensemble du processus relatif aux ordres de sortie. 

[![Vue d’ensemble du processus relatif aux ordres de sortie](./media/outbound-order.png)](./media/outbound-order.png)

Vous pouvez paramétrer des règles sortantes pour définir la manière dont le programme doit gérer le processus sortant. Vous pouvez utiliser ces règles pour contrôler le processus d’expédition. En particulier, vous pouvez utiliser les règles pour contrôler à quel stade du processus une expédition peut être effectuée. Les paramètres suivants définissent la manière dont les processus sortants sont gérés.

## <a name="picking-route-status-for-sales-and-transfer-orders"></a>Statut du parcours de prélèvement pour les commandes client et les ordres de transfert 

Accédez à **Comptabilité client** \> **Paramétrage** \> **Paramètres de comptabilité client**, puis, dans l’onglet **Mises à jour**, sélectionnez une valeur dans le champ **Statut du parcours de prélèvement**.

[![Champ Statut du parcours de prélèvement pour les commandes client](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)

Si le champ **Statut du parcours de prélèvement** est défini sur **Terminé**, le processus de prélèvement s’effectue automatiquement dans le cadre du processus de génération des prélèvements. Si le champ est défini sur **Activé**, les lignes de prélèvement doivent être manuellement mises à jour.

Le même paramétrage s’applique aux ordres de transfert. Accédez à **Gestion des stocks** \> **Paramétrage** \> **Paramètres de gestion des stocks et des entrepôts**, puis, dans l’onglet **Transport**, sélectionnez une valeur dans le champ **Statut du parcours de prélèvement**.

[![Champ Statut du parcours de prélèvement pour les ordres de transfert](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)

## <a name="end-output-inventory-orders"></a>Fin de la commande de stock sortante

Accédez à **Gestion des stocks** \> **Paramétrage** \> **Paramètres de gestion des stocks et des entrepôts**, puis, dans l’onglet **Général**, définissez l’option **Fin de la commande de stock sortante**.

[![Option Fin de la commande de stock sortante](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)

Lorsque le magasinier réduit les quantités de prélèvements, les quantités de la commande de stock correspondantes sont supprimées de l’expédition. Lorsque le prélèvement est mis à jour à un moment donné, les quantités restantes sont déclarées et reviennent au niveau de la commande si l’option **Fin de la commande de stock sortante** est définie sur **Oui**. Si l’option **Fin de la commande de stock sortante** est définie sur **Non**, les quantités restantes sont conservées comme quantité d’ordre de sortie ouvert et doivent être ajoutées à un nouveau prélèvement dans le cadre de la fonctionnalité **Ouvrir les ordres de sortie**. 

[![Commande Ouvrir les ordres de sortie du menu Fonctions](./media/open-output-order.png)](./media/open-output-order.png)

[![Menu Fonctions de la page Ouvrir les ordres de sortie](./media/open-output-order-function.png)](./media/open-output-order-function.png)

## <a name="reduce-quantity"></a>Réduire la quantité

Le troisième paramètre que vous pouvez utiliser dans le cadre du processus de génération des prélèvements est le paramètre **Réduire la quantité**. La définition de ce paramètre fonctionne avec le paramètre **Réservation** qui déclenche un processus de réservation dans le cadre de la libération dans l’entrepôt.

[![Paramètre Réduire la quantité](./media/reduce-quantity.png)](./media/reduce-quantity.png)

## <a name="example-of-an-outbound-process-for-a-sales-order"></a>Exemple d’un processus sortant pour une commande client

Pour cet exemple, il existe une commande client pour deux articles. Lors de la génération des prélèvements, sélectionnez le paramètre **Réduire la quantité**. Par conséquent, vous lancez et créez des lignes de prélèvement uniquement pour le stock disponible. Le prélèvement doit être déclaré via un processus d’enregistrement des prélèvements (**Statut du parcours de prélèvement** = **Activé**).

Le stock qui n’a pas encore été réservé est réservé lors de la génération du prélèvement. Le stock disponible peut être supprimé de la commande client ou libéré vers l’entrepôt pour traitement sortant ultérieurement, lorsque le stock est disponible pour le prélèvement.

[![Mettre à jour les prélèvements](./media/update-picking-list.png)](./media/update-picking-list.png)

Dès que toutes les lignes de prélèvement sont prélevées sur la page **Confirmation prélèvement**, l’expédition associée est terminée. Le processus pour les bons de livraison de commande client peut ensuite être initialisé selon le stock prélevé.

[![Mettre à jour les expéditions sortantes](./media/outbound-shipments.png)](./media/outbound-shipments.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]