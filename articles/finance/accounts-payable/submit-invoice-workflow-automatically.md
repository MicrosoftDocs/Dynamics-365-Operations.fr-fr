---
title: Soumettre les factures au système de workflow et mettre en correspondance des lignes d’accusé de réception de marchandises
description: Cet article explique le processus d’envoi des factures fournisseur au système de workflow et la mise en correspondance automatiques des lignes de réception des marchandises validées avec les factures fournisseur.
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 960a08eb5e98cac034bbd41335b616ff41bf6fd4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861616"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines"></a>Soumettre les factures au système de workflow et mettre en correspondance des lignes d’accusé de réception de marchandises

[!include [banner](../includes/banner.md)]

Cet article explique le processus d’envoi des factures fournisseur au système de workflow et la mise en correspondance automatiques des lignes de réception des marchandises validées avec les factures fournisseur.

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>Soumission des factures fournisseur importées au système de workflow et mise en correspondance des lignes de réception des marchandises avec les lignes de facture fournisseur en attente

Dans le cadre d’un processus de facturation des comptes fournisseurs sans contact, une facture importée peut être automatiquement soumise au système de workflow. Vous pouvez configurer le processus de soumission des factures importées au système de workflow dans l’onglet **Automatisation des factures fournisseurs** de la page **Paramètres de la comptabilité fournisseur** (**Comptabilité fournisseur \> Configuration \> Paramètres de la comptabilité fournisseur**). Le processus de soumission au workflow s’exécutera en arrière-plan, à la fréquence que vous spécifiez (une fois par heure ou une fois par jour).

Lorsque vous soumettez automatiquement des factures au système de workflow, vous devez commencer par une facture importée. Pour garantir que la facture peut être traitée du début à la fin sans intervention manuelle, vous devez inclure une tâche de validation automatisée dans la configuration du workflow. Les factures liées aux bons de commande, et les factures qui contiennent une catégorie d’approvisionnement sans bon de commande et des lignes non stockées peuvent être automatiquement envoyées au système de workflow. Les factures saisies manuellement doivent être soumises manuellement au système de workflow.

La valeur **Soumis par** dans le workflow est l’ID utilisateur qui a été entré pour la tâche en arrière-plan **Soumettre les factures fournisseurs au workflow** de la page **Automatisation des processus**. L’utilisateur qui possède cet ID utilisateur pourra rappeler la facture à partir du système de workflow, si nécessaire.

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Faire correspondre les réceptions de marchandises aux lignes de facture qui ont une stratégie de rapprochement à trois facteurs

Dans le cadre d’un processus de facturation de la comptabilité fournisseur sans contact, les accusés de réception de marchandises enregistrés peuvent être automatiquement rapprochés des lignes de facture. Une stratégie de rapprochement à trois facteurs doit être définie pour cette tâche. Cette fonction est disponible si la fonction **Automatisation des factures fournisseur** a été activée sur la page **Gestion des fonctionnalités**.

Le processus de mise en correspondance s’exécutera jusqu’à ce que la quantité des marchandises reçues soit égale à la quantité de la facture. Cependant, s’il existe plusieurs reçus de produit pour une seule ligne de facture, vous devrez exécuter le processus plusieurs fois pour obtenir la correspondance de quantité totale. Vous pouvez spécifier le nombre maximal de fois que le système doit essayer de faire correspondre les réceptions de marchandises avec une ligne de facture avant de conclure que le processus a échoué. Le processus s’exécutera en arrière-plan, toutes les heures ou tous les jours. 

Vous pouvez exécuter le processus de mise en correspondance automatique dans le cadre du processus d’envoi des factures au système de workflow. Vous pouvez également l’exécuter en tant que processus autonome. Les paramètre du processus de mise en correspondance des réceptions de marchandises avec les lignes de facture sont configurés dans l’onglet **Automatisation des factures fournisseur** de la page **Paramètres de la comptabilité fournisseur** (**Comptabilité fournisseur \> Configuration \> Paramètres de la comptabilité fournisseur**).

Les lignes de facture qui ont une stratégie de rapprochement à trois facteurs, où la quantité de réception correspondante est inférieure à la quantité de la facture, seront incluses dans le processus automatisé de mise en correspondance avec les réceptions de marchandises.

Pour voir le statut **Dernière correspondance** des factures qui ne font pas partie du processus automatisé de soumission au workflow, ouvrez la facture à partir de la page **Factures fournisseur**. Lorsque vous affichez la facture, les informations de validation correspondantes sont mises à jour. Le statut **Dernière correspondance** peut être mis à jour automatiquement à l’aide de la tâche en arrière-plan **Valider le rapprochement des factures**. Vous pouvez configurer le processus de mise à jour automatique du statut **Dernière correspondance** sur l’onglet **Processus en arrière-plan** de la page **Automatisations de processus** (**Administration système\> Configuration\> Automatisations de processus**).

Une ligne de facture sera exclue du traitement automatisé si l’une des conditions suivantes est remplie :

- La valeur **Statut de la mise en correspondance automatique des réceptions** de la ligne de facture est **Échoué**.
- La facture est utilisée.
- La facture est dans le système de workflow.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
