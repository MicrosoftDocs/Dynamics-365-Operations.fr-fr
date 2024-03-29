---
title: Exécution de mises à jour de factures pour les retours
description: Cette fonctionnalité prend également en charge les processus entreprise de nombreuses organisations qui décident d’avoir des ordres de retour et des commandes client facturés en même temps et par la même personne.
author: sorenva
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
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32a108694c11a2ebd922a71d5c82691584bbb397
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014747"
---
# <a name="perform-invoice-updates-for-returns"></a>Exécution de mises à jour de factures pour les retours 

[!include [banner](../includes/banner.md)]


Un ordre de retour est un type de commande client marquée comme retour marchandises. C’est pourquoi, la page de liste **Toutes les commandes client** est utilisée pour générer des factures pour les ordres de retour à la place de l’écran **Ordres de retour**. Cette fonctionnalité prend également en charge les processus entreprise de nombreuses organisations qui décident d’avoir des ordres de retour et des commandes client facturés en même temps et par la même personne.

Étant donné que la facture pour un article retourné a un montant négatif, elle est appelée avoir.

Lorsque vous paramétrez la mise à jour de facture pour un traitements par lots, la commande client du type **Retour marchandises** doit avoir un statut de ligne de retour **Reçu**, ce qui indique que le bon de livraison de la commande a été mis à jour.

## <a name="post-an-invoice-for-a-return-order"></a>Validation d’une facture pour un ordre de retour

1.  Cliquez sur **Comptabilité client** \> **Commandes** \> **Toutes les commandes client**.

2.  Sélectionnez une commande client pour laquelle la valeur **Commande retournée** est affichée dans le champ **Type de commande**.

3.  Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, cliquez sur **Facture**.

4.  Sous l’onglet **Paramètres**, activez la case à cocher **Validation**.

5.  Consultez les informations sur l’écran et effectuez les changements nécessaires.

6.  Cliquez sur **OK**. L’avoir est validé.

## <a name="see-also"></a>Voir également :

[Mettre à jour des bons de livraison pour les retours](packing-slip-updates-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]