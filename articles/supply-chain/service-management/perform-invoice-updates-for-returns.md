---
title: Exécution de mises à jour de factures pour les retours
description: Cette fonctionnalité prend également en charge les processus entreprise de nombreuses organisations qui décident d’avoir des ordres de retour et des commandes client facturés en même temps et par la même personne.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3890ea31ee899f021405fb5475b20f9dd63c1e2e103b63af8b53bccc53d0781f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730152"
---
# <a name="perform-invoice-updates-for-returns"></a>Exécution de mises à jour de factures pour les retours 

[!include [banner](../includes/banner.md)]


Un ordre de retour est un type de commande client marquée comme retour marchandises. C’est pourquoi, la page de liste **Toutes les commandes client** est utilisée pour générer des factures pour les ordres de retour à la place de l’écran **Ordres de retour**. Cette fonctionnalité prend également en charge les processus entreprise de nombreuses organisations qui décident d’avoir des ordres de retour et des commandes client facturés en même temps et par la même personne.

Étant donné que la facture pour un article retourné a un montant négatif, elle est appelée avoir.

Lorsque vous paramétrez la mise à jour de facture pour un traitements par lots, la commande client du type **Retour marchandises** doit avoir un statut de ligne de retour **Reçu**, ce qui indique que le bon de livraison de la commande a été mis à jour.

## <a name="post-an-invoice-for-a-return-order"></a>Validation d’une facture pour un ordre de retour

1.  Cliquez sur **Comptabilité client** \> **Commun** \> **Commandes client** \> **Toutes les commandes client**.

2.  Sélectionnez une commande client pour laquelle la valeur **Commande retournée** est affichée dans le champ **Type de commande**.

3.  Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, cliquez sur **Facture**.

4.  Sous l’onglet **Paramètres**, activez la case à cocher **Validation**.

5.  Consultez les informations sur l’écran et effectuez les changements nécessaires.

6.  Cliquez sur **OK**. L’avoir est validé.

## <a name="see-also"></a>Voir également :

[Mettre à jour des bons de livraison pour les retours](packing-slip-updates-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]