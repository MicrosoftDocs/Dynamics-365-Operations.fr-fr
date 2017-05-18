---
title: "Création d&quot;une facture client"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 055670a5aed0078a1157bd081af9f4617b1d1d76
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="create-a-customer-invoice"></a>Création d'une facture client

[!include[banner](../includes/banner.md)]




Une **facture client pour une commande client** est une facture associée à une vente, remise par une organisation à un client. Ce type de facture client est créé sur la base d'une commande client, laquelle comporte des lignes de commande et des numéros d'article. Les numéros d'article sont spécifiés et validés dans la comptabilité. Les écritures de journal de comptabilité auxiliaire ne sont pas disponibles pour une facture client associée à une commande client. 

Une **facture financière** n'est pas liée à une commande client. Elle contient des lignes de commande comprenant des comptes généraux, des descriptions en texte libre ainsi qu'une valeur de vente que vous entrez. Vous ne pouvez pas entrer de numéro d'article sur ce type de facture. Vous devez entrer les informations de taxe appropriées. Un compte principal associé à la vente figure sur chaque ligne de facture, que vous pouvez répartir entre plusieurs comptes généraux en cliquant sur **Répartir les montants** sur la page **Facture financière**. En outre, le solde du client est validé dans le compte collectif en fonction du profil de validation utilisé pour la facture financière.

Une **facture pro forma** est une facture préparée comme une estimation des montants de facture réels avant la validation de la facture. Vous pouvez imprimer une facture pro forma pour une facture client associée à une commande client ou pour une facture financière.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a>Validation et impression de factures client individuelles basée sur des commandes client
Ce processus permet de créer une facture sur la base d'une commande client. Vous pouvez procéder ainsi si vous décider de facturer le client avant de livrer des biens ou services. 

Lorsque vous validez une facture, la quantité **Solde de la facture** pour chaque article est mise à jour avec le total des quantités facturées pour la commande client sélectionnée. Si la quantité **Solde de la facture** et la quantité **Livrer quantité restante** pour tous les articles de la commande client ont la valeur 0 (zéro), le statut de la commande client passe à **Facturé**. Si la quantité **Solde de la facture** n'a pas la valeur 0 (zéro), le statut de la commande client reste inchangé et des factures supplémentaires peuvent être entrées pour celle-ci.

Vous pouvez afficher le statut des commandes client sur la page de liste **Toutes les commandes client**. La page de liste **Factures client en cours** vous permet d'afficher les factures que vous avez validées.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a>Validation et impression de factures client individuelles basées sur les bons de livraison et la date
Utilisez ce processus lorsqu'un ou plusieurs bons de livraison ont été validés pour la commande client. La facture client est basée sur ces bons de livraison et reflète les quantités pour ceux‑ci. Les informations financières pour la facture sont basées sur les informations entrées lors de la validation de la facture. 

Vous pouvez créer une facture client basée sur les articles de ligne du bon de livraison qui ont été expédiés jusqu'à présent, même si tous les articles pour une commande client particulière n'ont pas encore été expédiés. Vous pouvez procéder de la sorte si, par exemple, votre entité juridique émet une facture par client et par mois qui couvre toutes les expéditions que vous avez effectuées au cours de ce mois. Chaque bon de livraison représente l'expédition partielle ou complète des articles sur la commande client. 

Lorsque vous validez la facture, la quantité **Solde de la facture** pour chaque article est mise à jour avec le total des quantités expédiées pour les bons de livraison sélectionnés. Si la quantité **Solde de la facture** et la quantité **Livrer quantité restante** pour tous les articles de la commande client ont la valeur 0 (zéro), le statut de la commande client passe à **Facturé**. Si la quantité **Solde de la facture** n'a pas la valeur 0 (zéro), le statut de la commande client reste inchangé et des factures supplémentaires peuvent être entrées pour celle-ci. 

Les mouvements de stock sont mis à jour avec le numéro de facture et le statut dans le champ **Statut de ligne** de la commande client devient **Facturé**. 

Affichez le statut des commandes client sur la page de liste **Toutes les commandes client**.

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a>Consolidation des commandes client ou des bons de livraison pour la validation
Utilisez ce processus lorsqu'une ou plusieurs commandes client sont prêtes à être facturées, et que vous souhaitez les consolider dans une seule facture. 

Vous pouvez sélectionner plusieurs factures dans la page de liste **Commande client**, puis utiliser **Générer des factures** pour les consolider. Sur la page **Validation de la facture**, vous pouvez modifier le paramètre **Commande de synthèse** pour récapituler par numéro de commande (lorsqu'il existe plusieurs bons de livraison pour une commande client unique) ou par compte de facturation (lorsqu'il existe plusieurs commandes client pour un compte de facturation unique). Utilisez le bouton **Réorganiser** pour consolider des commandes client dans des factures uniques, en fonction des paramètres **Commande de synthèse**.

## <a name="additional-settings-that-change-the-posting-behavior"></a>Paramètres supplémentaires qui modifient le comportement de validation
Les champs suivants modifient le comportement du processus de validation.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Champ</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Quantité</td>
<td>Sélectionnez les quantités sur lesquelles baser la validation du document. Les options disponibles varient en fonction du type de document que vous validez, comme un bon de livraison ou une facture.
<ul>
<li><strong>Livrer maintenant</strong> – Permet de sélectionner toutes les quantités entrées dans le champ <strong>Livrer maintenant</strong>. Cette option vous permet de procéder à une confirmation ou une livraison de commande partielle.</li>
<li><strong>Prélevé</strong> – Permet de sélectionner toutes les quantités qui ont été prélevées.</li>
<li><strong>Tout</strong> – Permet de sélectionner toutes les quantités sur la commande client qui n'ont pas encore été mises à jour par type de document actuel.</li>
<li><strong>Bon de livraison</strong> – Permet de sélectionner toutes les quantités qui ont été mises à jour par un bon de livraison.</li>
<li><strong>Produits prélevés et non inventoriés</strong> – Permet de sélectionner toutes les quantités qui ont été prélevées et toutes les quantités de produits qui ne sont pas stockées.</li>
</ul></td>
</tr>
<tr class="even">
<td>Validation</td>
<td><ul>
<li>Sélectionnez cette option pour journaliser la commande client.</li>
<li>Désactivez cette option pour imprimer une commande client pro forma. <strong>Remarque :</strong> si vous avez créé un accord pour un échéancier de paiement, ce dernier ne s'affiche pas sur la facture client pro forma. Les échéanciers de paiement ne seront visibles que sur les commandes client réelles.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Sélection ultérieure</td>
<td>Sélectionnez cette option pour appliquer la requête sélectionnée ultérieurement. Cette option est utilisée pour les traitements par lots. La requête est exécutée lorsque le traitement par lots est exécuté.</td>
</tr>
<tr class="even">
<td>Réduire la quantité</td>
<td>Sélectionnez cette option pour réduire automatiquement la quantité livrée lorsque le document est validé, de sorte que la quantité livrée est égale au stock disponible.</td>
</tr>
<tr class="odd">
<td>Imprimer</td>
<td>Sélectionnez le moment de l'impression des documents :
<ul>
<li><strong>Actuel</strong> – Permet d'imprimer les documents après la mise à jour de chaque facture.</li>
<li><strong>Après</strong> – Permet d'imprimer les documents après la mise à jour de toutes les factures.</li>
</ul>
<strong>Remarque :</strong> le champ <strong>Imprimer</strong> est uniquement disponible si vous sélectionnez l'option <strong>Imprimer la facture</strong>, <strong>Impression de la confirmation</strong>, <strong>Imprimer la liste des prélèvements</strong> ou <strong>Imprimer le bon de livraison</strong>. Par exemple, sur la page <strong>Tri des écrans</strong>, vous avez paramétré le système pour trier les informations par compte de facturation. Vous pouvez alors sélectionner <strong>Après</strong> pour imprimer les documents dans un traitement par lots trié par compte de facturation. Sinon, les documents sont imprimés avant que le traitement soit terminés et ils ne sont pas triés dans l'ordre spécifié sur la page <strong>Tri des écrans</strong>.</td>
</tr>
<tr class="even">
<td>Imprimer la facture</td>
<td>Sélectionnez cette option pour imprimer la facture. Si cette option est désactivée, vous pouvez valider une facture sans l'imprimer.</td>
</tr>
<tr class="odd">
<td>Envoyer un e-mail</td>
<td>Sélectionnez cette option pour envoyer la facture correspondant à une commande client au client en tant que pièce jointe après la validation de la facture. Les pièces jointes sont envoyées sous la forme de fichiers PDF et XML. Cette option est uniquement disponible si vous sélectionnez l'option <strong>Activez les CFD (factures électroniques)</strong> sur la page <strong>Paramètres des factures électroniques </strong>. <strong>Remarque :</strong> (MEX) Ce contrôle est uniquement accessible aux entités juridiques dont l'adresse principale est au Mexique.</td>
</tr>
<tr class="even">
<td>Utiliser la destination de la gestion de l'impression</td>
<td>Sélectionnez cette option pour utiliser les paramètres d'impression qui sont spécifiés pour la transaction, le document ou le module sur la page <strong>Paramétrage de la gestion de l'impression</strong>.</td>
</tr>
<tr class="odd">
<td>Vérifier la limite de crédit</td>
<td>Sélectionnez les informations à analyser lorsqu'une vérification de limite de crédit est effectuée.
<ul>
<li><strong>Aucun(e)</strong> – Le contrôle de la limite de crédit n'est pas nécessaire.</li>
<li><strong>Solde</strong> – La limite de crédit est vérifiée par rapport au solde du client.</li>
<li><strong>Solde + bon de livraison ou accusé de réception de marchandises</strong> – La limite de crédit est vérifiée par rapport au solde client et aux livraisons.</li>
<li><strong>Solde+Tout</strong> – La limite de crédit est vérifiée par rapport au solde du client, aux livraisons et aux commandes en cours.</li>
</ul></td>
</tr>
<tr class="even">
<td>Correction de crédit</td>
<td>Sélectionnez cette option pour afficher l'avoir comme débit dans les transactions de N° document.</td>
</tr>
<tr class="odd">
<td>Quantité restante créditrice</td>
<td>Si vous validez un avoir, sélectionnez cette option pour conserver la quantité restante de la commande. Si cette option est désactivée, la quantité restante est définie sur 0 (zéro).</td>
</tr>
<tr class="even">
<td>Mise à jour récapitulative pour</td>
<td>Sélectionnez la manière de récapituler plusieurs commandes client.
<ul>
<li><strong>Aucun(e)</strong> – Permet de ne pas récapituler les commandes client. Par exemple, une facture distincte est créée pour chaque commande client.</li>
<li><strong>Compte de facturation</strong> – Récapitulez toutes les commandes sélectionnées, en fonction des critères paramétrés sur la page <strong>Paramètres de mise à jour récapitulative</strong>.</li>
<li><strong>Commande</strong> – Permet de récapituler une plage sélectionnée de commandes en une seule que vous spécifiez. Les commandes sont récapitulées en fonction des critères définis sur la page <strong>Paramètres de mise à jour récapitulative</strong>. Si vous sélectionnez cette option, vous devez sélectionner une valeur dans le champ <strong>Commande client</strong>.</li>
<li><strong>Synthèse automatique</strong> – Si les mises à jour récapitulatives ont été spécifiées sur la page <strong>Mise à jour récapitulative</strong>, récapitulez toutes les commandes sélectionnées en fonction des critères définis sur la page <strong>Paramètres de mise à jour récapitulative</strong>. Si des mises à jour récapitulatives n'ont pas été spécifiées, la commande est validée séparément.</li>
<li><strong>Bon de livraison</strong> – Permet de récapituler une plage sélectionnée de commandes en une facture pour chaque bon de livraison. Cette option n'est disponible que si l'option <strong>Bon de livraison</strong> est sélectionnée dans le champ <strong>Quantité</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>






