---
title: Création d’une facture client
description: Une facture client pour une commande client est une facture associée à une vente, remise par une organisation à un client.
author: ShivamPandey-msft
ms.date: 03/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0d1221e07f6dc4a5a99aa205c4a7f6fb367f000
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780508"
---
# <a name="create-a-customer-invoice"></a>Création d’une facture client

[!include [banner](../includes/banner.md)]

Une **facture client pour une commande client** est une facture associée à une vente, remise par une organisation à un client. Ce type de facture client est créé sur la base d’une commande client, laquelle comporte des lignes de commande et des numéros d’article. Les numéros d’article sont spécifiés et validés dans la comptabilité. Les écritures de journal de comptabilité auxiliaire ne sont pas disponibles pour une facture client associée à une commande client. Pour plus d’informations, voir [Créer des factures de commande client](tasks/create-sales-order-invoices.md).

Une **facture financière** n’est pas liée à une commande client. Elle contient des lignes de commande comprenant des comptes généraux, des descriptions en texte libre ainsi qu’une valeur de vente que vous entrez. Vous ne pouvez pas entrer de numéro d’article sur ce type de facture. Vous devez entrer les informations de taxe appropriées. Un compte principal associé à la vente figure sur chaque ligne de facture, que vous pouvez répartir entre plusieurs comptes généraux en cliquant sur **Répartir les montants** sur la page **Facture financière**. En outre, le solde du client est validé dans le compte collectif en fonction du profil de validation utilisé pour la facture financière.

Pour plus d’informations, voir :
 - [Créer des factures financières](../accounts-receivable/create-free-text-invoice-new.md)
 - [Créer un modèle de facture financière](../accounts-receivable/create-free-text-invoice-template-new.md)
 - [Affecter un modèle de facture financière à un client](tasks/assign-free-text-invoice-template-customer.md)
 - [Générer et valider les factures financières récurrentes](tasks/post-recurring-free-text-invoices.md)


Une **facture proforma** est une facture préparée comme une estimation des montants de facture réels avant la validation de la facture. Vous pouvez imprimer une **facture proforma** pour une facture client associée à une commande client ou pour une facture financière. 

>[!NOTE]
> En cas d’interruption du système pendant le processus de facturation pro forma des ventes, une facture pro forma peut être orpheline. Une facture pro forma orpheline peut être supprimée en exécutant la tâche périodique **Supprimer manuellement les factures proforma**. Accédez à **Ventes et marketing > Tâches périodiques > Nettoyer > Supprimer manuellement les factures proforma**.

## <a name="using-sales-order-customer-invoice-data-entities"></a>Utilisation d’entités de données de facture client de commande client
Vous pouvez utiliser des entités de données pour importer et exporter des informations sur une facture client pour une commande client. Il existe différentes entités pour les informations sur l’en-tête de facture client et les lignes de facture client.

Les entités suivantes sont disponibles pour les informations sur l’en-tête de la facture client :

- Entité **En-tête du journal des factures client** (SalesInvoiceJournalHeaderEntity)
- Entité **En-têtes de facture client V2** (SalesInvoiceHeaderV2Entity)

Nous vous recommandons d’utiliser l’entité **En-tête du journal des factures de vente**, car elle offre une expérience plus performante pour l’importation et l’exportation d’en-têtes de vente. Cette entité ne contient pas la colonne **Montant de la taxe de vente** (INVOICEHEADERTAXAMOUNT), qui représente la valeur de la taxe de vente sur l’en-tête de la facture client. Si votre scénario d’entreprise nécessite ces informations, utilisez l’entité **En-têtes de facture client V2** pour importer et exporter les informations d’en-tête de la facture client.

Les entités suivantes sont disponibles pour les informations sur les lignes de la facture client :

- Entité **Lignes de facture client** (BusinessDocumentSalesInvoiceLineItemEntity)
- Entité **Lignes de facture client V3** (SalesInvoiceLineV3Entity)

Lorsque vous déterminez l’entité de ligne à utiliser pour les exportations, déterminez si une transmission de type push complète ou de type push incrémentielle sera utilisée. De plus, tenez compte de la composition des données. L’entité **Lignes de facture client V3** prend en charge des scénarios plus complexes (par exemple, le mappage vers les champs d’inventaire). Elle prend également en charge les scénarios d’exportation complète. Pour les transmissions de type incrémentielle, nous vous recommandons d’utiliser l’entité **Lignes de facture client**. Cette entité contient une composition de données beaucoup plus simple que l’entité **Lignes de facture client V3** et est préférable, en particulier si l’intégration du champ d’inventaire n’est pas requise. En raison des différences dans la prise en charge du mappage entre les entités de ligne, l’entité **Lignes de facture client** a généralement des performances plus rapides que l’entité **Lignes de facture client V3**.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a>Validation et impression de factures client individuelles basée sur des commandes client
Ce processus permet de créer une facture sur la base d’une commande client. Vous pouvez procéder ainsi si vous décider de facturer le client avant de livrer des biens ou services. 

Lorsque vous validez une facture, la quantité **Solde de la facture** pour chaque article est mise à jour avec le total des quantités facturées pour la commande client sélectionnée. Si la quantité **Solde de la facture** et la quantité **Livrer quantité restante** pour tous les articles de la commande client ont la valeur 0 (zéro), le statut de la commande client passe à **Facturé**. Si la quantité **Solde de la facture** n’a pas la valeur 0 (zéro), le statut de la commande client reste inchangé et des factures supplémentaires peuvent être entrées pour celle-ci.

Vous pouvez afficher le statut des commandes client sur la page de liste **Toutes les commandes client**. La page de liste **Factures client en cours** vous permet d’afficher les factures que vous avez validées.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a>Validation et impression de factures client individuelles basées sur les bons de livraison et la date
Utilisez ce processus lorsqu’un ou plusieurs bons de livraison ont été validés pour la commande client. La facture client est basée sur ces bons de livraison et reflète les quantités pour ceux‑ci. Les informations financières pour la facture sont basées sur les informations entrées lors de la validation de la facture. 

Vous pouvez créer une facture client basée sur les articles de ligne du bon de livraison qui ont été expédiés jusqu’à présent, même si tous les articles pour une commande client particulière n’ont pas été expédiés. Vous pouvez procéder de la sorte si, par exemple, votre entité juridique émet une facture par client et par mois qui couvre toutes les expéditions que vous avez effectuées au cours de ce mois. Chaque bon de livraison représente l’expédition partielle ou complète des articles sur la commande client. 

Lorsque vous validez la facture, la quantité **Solde de la facture** pour chaque article est mise à jour avec le total des quantités expédiées pour les bons de livraison sélectionnés. Si la quantité **Solde de la facture** et la quantité **Livrer quantité restante** pour tous les articles de la commande client ont la valeur 0 (zéro), le statut de la commande client passe à **Facturé**. Si la quantité **Solde de la facture** n’a pas la valeur 0 (zéro), le statut de la commande client reste inchangé et des factures supplémentaires peuvent être entrées pour celle-ci. 

Les mouvements de stock sont mis à jour avec le numéro de facture et le statut dans le champ **Statut de ligne** de la commande client devient **Facturé**. 

Affichez le statut des commandes client sur la page de liste **Toutes les commandes client**.

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a>Consolidation des commandes client ou des bons de livraison pour la validation
Utilisez ce processus lorsqu’une ou plusieurs commandes client sont prêtes à être facturées, et que vous souhaitez les consolider dans une seule facture. 

Vous pouvez sélectionner plusieurs factures dans la page de liste **Commande client**, puis utiliser **Générer des factures** pour les consolider. Sur la page **Validation de la facture**, vous pouvez modifier le paramètre **Commande de synthèse** pour récapituler par numéro de commande (lorsqu’il existe plusieurs bons de livraison pour une commande client unique) ou par compte de facturation (lorsqu’il existe plusieurs commandes client pour un compte de facturation unique). Utilisez le bouton **Réorganiser** pour consolider des commandes client dans des factures uniques, en fonction des paramètres **Commande de synthèse**.

## <a name="split-sales-order-invoices-by-site-and-delivery-information"></a>Fractionner les factures des commandes clients par site et informations de livraison
Vous pouvez paramétrer le fractionnement des factures clients des commandes clients par site ou par adresse de livraison sur l’onglet **Mise à jour sommaire** de la page **Paramètres des comptes clients**. 
 - Sélectionnez l’option **Fractionner en fonction du site de facturation** pour créer une facture par site lors de la validation. 
 - Sélectionnez l’option **Fractionner en fonction des informations de livraison de la facture** pour créer une facture par adresse de livraison de ligne de commande client lors de la validation. 

## <a name="post-to-revenue-account-for-sales-order-lines-that-have-no-price-and-no-cost"></a>Valider sur le compte Produit pour les lignes de commande client sans prix et de coût nul
Vous aurez la possibilité de mettre à jour le compte **Revenu** en **Comptabilité** pour les lignes de commande client sans prix et de coût nul. 

Pour configurer ou afficher ces informations :
1. Accédez au paramètre **Valider sur le compte Produit pour les lignes de facture de commande client sans prix et de coût nul** dans l’onglet **Comptabilité et taxe** de la page **Paramètres de la comptabilité client**. (**Comptabilité client > Comptabilité client > Paramètres de la comptabilité client**). 
2. Sélectionnez **Oui** pour mettre à jour le compte **Revenu** pour les lignes de facture de commande client qui n’ont pas de prix et de coût nul. 
 - Si cette option est sélectionnée, le justificatif contiendra 0,00 entrées pour les types de validations **Client - Solde** et **Produit**. Un compte de produit est défini sur la page Paramètres de **Comptabilisation de l’inventaire**, sur l’onglet de définition du compte **Bon de commande**. 
 - Si cette option n’est pas sélectionnée, les lignes sans informations de prix ou de coût ne sont pas publiées sur le compte **Produit**. Au lieu de cela, le justificatif contiendra une entrée de 0,00 pour le type de validation **Client – Solde**.

## <a name="line-creation-sequence-number-information"></a>Informations sur le numéro de séquence de création de ligne
Lorsque vous validez des lignes de facture client, vous avez la possibilité de créer des numéros de séquence de création de ligne séquentiels. Les numéros de séquence de création de ligne sont attribués lors du processus de validation. En autorisant la numérotation non séquentielle, vous pouvez contribuer à améliorer les performances de la validation des factures client. Les numéros de séquence de création de ligne peuvent être utilisés par des intégrations tierces qui attendent un ordre séquentiel. Consultez votre service informatique au sujet des extensions qui pourraient s’intégrer aux numéros de séquence de création de ligne.

Pour configurer ou afficher ces informations, sur la page **Paramètres de comptabilité client**, sur l’onglet **Mises à jour**, définissez l’option **Affecter des numéros de ligne séquentiels lors de la validation des lignes de facture client** :

- Définissez l’option sur **Non** pour utiliser une numérotation non séquentielle pour les numéros de séquence de création de ligne.
- Définissez l’option sur **Oui** pour utiliser la numérotation séquentielle. Vous devez définir l’option sur **Oui** pour les personnes morales ayant une adresse principale en Italie. Vous devez également le régler sur **Oui** si le vol **CustInvoiceTransRandLineCreationSeqNumFlight** est désactivé.

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
<li><strong>Tout</strong> – Permet de sélectionner toutes les quantités sur la commande client qui n’ont pas encore été mises à jour par type de document actuel.</li>
<li><strong>Bon de livraison</strong> – Permet de sélectionner toutes les quantités qui ont été mises à jour par un bon de livraison.</li>
<li><strong>Produits prélevés et non inventoriés</strong> – Permet de sélectionner toutes les quantités qui ont été prélevées et toutes les quantités de produits qui ne sont pas stockées.</li>
</ul></td>
</tr>
<tr class="even">
<td>Validation</td>
<td><ul>
<li>Sélectionnez cette option pour journaliser la commande client.</li>
<li>Désactivez cette option pour imprimer une commande client pro forma. <strong>Remarque :</strong> si vous avez créé un accord pour un échéancier de paiement, ce dernier ne s’affiche pas sur la facture client pro forma. Les échéanciers de paiement ne seront visibles que sur les commandes client réelles.</li>
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
<td>Sélectionnez le moment de l’impression des documents :
<ul>
<li><strong>Actuel</strong> – Permet d’imprimer les documents après la mise à jour de chaque facture.</li>
<li><strong>Après</strong> – Permet d’imprimer les documents après la mise à jour de toutes les factures.</li>
</ul>
<strong>Remarque :</strong> le champ <strong>Imprimer</strong> est uniquement disponible si vous sélectionnez l’option <strong>Imprimer la facture</strong>, <strong>Impression de la confirmation</strong>, <strong>Imprimer la liste des prélèvements</strong> ou <strong>Imprimer le bon de livraison</strong>. Par exemple, sur la page <strong>Tri des écrans</strong>, vous avez paramétré le système pour trier les informations par compte de facturation. Vous pouvez alors sélectionner <strong>Après</strong> pour imprimer les documents dans un traitement par lots trié par compte de facturation. Sinon, les documents sont imprimés avant que le traitement soit terminés et ils ne sont pas triés dans l’ordre spécifié sur la page <strong>Tri des écrans</strong>.</td>
</tr>
<tr class="even">
<td>Imprimer la facture</td>
<td>Sélectionnez cette option pour imprimer la facture. Si cette option est désactivée, vous pouvez valider une facture sans l’imprimer.</td>
</tr>
<tr class="odd">
<td>Envoyer un e-mail</td>
<td>Sélectionnez cette option pour envoyer la facture correspondant à une commande client au client en tant que pièce jointe après la validation de la facture. Les pièces jointes sont envoyées sous la forme de fichiers PDF et XML. Cette option est uniquement disponible si vous sélectionnez l’option <strong>Activez les CFD (factures électroniques)</strong> sur la page <strong>Paramètres des factures électroniques</strong>. <strong>Remarque :</strong> (MEX) Ce contrôle est uniquement accessible aux entités juridiques dont l’adresse principale est au Mexique.</td>
</tr>
<tr class="even">
<td>Utiliser la destination de la gestion de l’impression</td>
<td>Sélectionnez cette option pour utiliser les paramètres d’impression qui sont spécifiés pour la transaction, le document ou le module sur la page <strong>Paramétrage de la gestion de l’impression</strong>.</td>
</tr>
<tr class="odd">
<td>Vérifier la limite de crédit</td>
<td>Sélectionnez les informations à analyser lorsqu’une vérification de limite de crédit est effectuée.
<ul>
<li><strong>Aucun(e)</strong> – Le contrôle de la limite de crédit n’est pas nécessaire.</li>
<li><strong>Solde</strong> – La limite de crédit est vérifiée par rapport au solde du client.</li>
<li><strong>Solde + bon de livraison ou accusé de réception de marchandises</strong> – La limite de crédit est vérifiée par rapport au solde client et aux livraisons.</li>
<li><strong>Solde+Tout</strong> – La limite de crédit est vérifiée par rapport au solde du client, aux livraisons et aux commandes en cours.</li>
</ul></td>
</tr>
<tr class="even">
<td>Correction de crédit</td>
<td>Sélectionnez cette option pour afficher l’avoir comme débit dans les pièces comptables.</td>
</tr>
<tr class="odd">
<td>Quantité restante créditrice</td>
<td>Si vous validez un avoir, sélectionnez cette option pour conserver la quantité restante de la commande. Si cette option est désactivée, la quantité restante est définie sur 0 (zéro).</td>
</tr>
<tr class="even">
<td>Mise à jour récapitulative pour</td>
<td>Sélectionnez la manière de récapituler plusieurs commandes client.
<ul>
<li><strong>Aucun(e)</strong> - Permet de ne pas récapituler les commandes client. Par exemple, une facture distincte est créée pour chaque commande client.</li>
<li><strong>Compte de facturation</strong> – Récapitulez toutes les commandes sélectionnées, en fonction des critères paramétrés sur la page <strong>Paramètres de mise à jour récapitulative</strong>.</li>
<li><strong>Commande</strong> – Permet de récapituler une plage sélectionnée de commandes en une seule que vous spécifiez. Les commandes sont récapitulées en fonction des critères définis sur la page <strong>Paramètres de mise à jour récapitulative</strong>. Si vous sélectionnez cette option, vous devez sélectionner une valeur dans le champ <strong>Commande client</strong>.</li>
<li><strong>Synthèse automatique</strong> – Si les mises à jour récapitulatives ont été spécifiées sur la page <strong>Mise à jour récapitulative</strong>, récapitulez toutes les commandes sélectionnées en fonction des critères définis sur la page <strong>Paramètres de mise à jour récapitulative</strong>. Si des mises à jour récapitulatives n’ont pas été spécifiées, la commande est validée séparément.</li>
<li><strong>Bon de livraison</strong> – Permet de récapituler une plage sélectionnée de commandes en une facture pour chaque bon de livraison. Cette option n’est disponible que si l’option <strong>Bon de livraison</strong> est sélectionnée dans le champ <strong>Quantité</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
