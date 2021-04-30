---
title: Résoudre les problèmes de prix, de remises, d’accords et de rabais
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des prix, des remises, des accords et des rabais.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2ccc1d52b83f9319af1c6336c1876c795c70028a
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908517"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a>Résoudre les problèmes de prix, de remises, d’accords et de rabais

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des prix, des remises, des accords et des rabais.

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a>Je ne peux pas lier un contrat d’achat à une ligne de commande fournisseur après la création du bon de commande.

Un contrat d’achat doit être associé à une ligne de commande fournisseur quand le bon de commande est créé. Sinon, les lignes de la commande fournisseur ne peuvent pas être associées aux lignes du contrat d’achat.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Quel contrôle déclenche le message "Mettre à jour les prix et remises saisis manuellement ou via un document externe" ?

Lorsque vous modifiez la date d’expédition, vous pouvez recevoir un message indiquant "Mettre à jour les prix et les remises saisis manuellement ou via un document externe". Vous recevez ce message car, si la date d’expédition est modifiée, un autre accord de vente ou commercial peut être déclenché et entraîner une modification de prix. Une modification de la date d’expédition peut également affecter les planning d’entrepôt et d’autres informations connexes.

Le message est déclenché chaque fois que l’une des dates ou certains autres paramètres sont modifiés. Le but du message est de vous assurer que vous êtes au courant des changements de prix qui peuvent survenir en raison de ces changements.

Le message est l’invite d’évaluation de l’accord commercial (TAE). Pour une description complète, voir [Politiques d’évaluation des accords commerciaux](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>Un accusé de réception de commande fournisseur n’inclut pas tous les frais.

### <a name="reproduce-the-issue"></a>Reproduire le problème

La procédure suivante montre comment reproduire le problème.

1. Sur la page **Paramètres d’approvisionnements**, sur l’onglet **Livraison**, assurez-vous que l’option **Générer des frais sur l’accusé de réception de marchandises** est définie sur *Oui*.
1. Créez une commande fournisseur qui inclut des frais.
1. Confirmez la commande fournisseur.
1. Recevez la commande fournisseur.
1. Regardez le total de l’accusé de réception et comparez-le au total attendu.
1. Notez que tous les frais ne sont pas inclus sur l’accusé de réception de la commande.

### <a name="issue-resolution"></a>Résolution du problème

La résolution dépend de la manière dont les frais divers ont été configurés. Pour plus d’informations sur la configuration des frais divers pour répondre à vos besoins, consultez l’article de blog suivant : [Valider des frais divers au moment de la réception des produits](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a>Les prix et les remises des accords commerciaux ne sont pas appliqués aux lignes de commande fournisseur ou client importées via la gestion des données.

### <a name="issue-description"></a>Description du problème

Les accords commerciaux qui sont applicables aux lignes de commande fournisseur ou client ne sont pas appliqués sur les lignes importées via la gestion des données. Cependant, les mêmes accords commerciaux sont appliqués sur les lignes de commande client ou fournisseur créées manuellement.

### <a name="reason-for-the-issue"></a>Raison du problème

Si les lignes de commande fournisseur importées via la gestion des données incluent déjà des informations de prix, l’accord commercial ne sera pas réévalué pour ces lignes. Par exemple, si **Pourcentage de remise de ligne** ou l’une des valeurs de prix et de remise est définie pour une ligne, les accords commerciaux ne seront pas recherchés pour cette ligne.

### <a name="issue-workaround"></a>Solution de contournement du problème

Ce comportement est attendu et est similaire pour les commandes client et les commandes fournisseur.

Pour contourner le problème, importez les lignes de commande fournisseur sans définir aucune information de prix. Les accords commerciaux seront alors appliqués et les lignes de commande fournisseur seront mises à jour en fonction des accords commerciaux définis.

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>Une remise fournisseur n’est pas cumulée en fonction des factures.

### <a name="issue-description"></a>Description du problème

Si les factures validées ont des dates d’échéance différentes, ces factures ne sont pas reflétées dans les remises fournisseur générées à partir d’elles.

### <a name="issue-resolution"></a>Résolution du problème

Par défaut, la date d’échéance n’est pas prise en compte lors du calcul de la remise fournisseur. Envisagez de personnaliser le système afin que la date d’échéance et la relation avec la facture soient plus apparentes par rapport à la remise fournisseur réelle.

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>Les prix unitaires sur les commandes fournisseur ne sont pas calculés en fonction de la conversion des unités.

### <a name="issue-description"></a>Description du problème

Lorsqu’une unité est modifiée sur une commande fournisseur, les prix de l’accord commercial ne sont pas recalculés en fonction des définitions de la conversion d’unité.

### <a name="issue-resolution"></a>Résolution du problème

Les prix sont toujours obtenus à partir d’accords commerciaux (ou d’autres paramètres de prix dans le système, tels que les accords de vente ou les prix des articles) et ils sont définis pour une unité.

Si l’unité est modifiée sur une ligne de commande, le système recherche un prix pour la nouvelle unité et applique ce prix. Si aucun prix n’est trouvé pour l’unité, le système n’applique pas de prix. La conversion d’unité ne peut pas être utilisée pour recalculer le prix dans une autre unité. Théoriquement, le prix d’une boîte de dix pourrait ne pas être égal à dix fois le prix d’une boîte.

### <a name="issue-workaround"></a>Solution de contournement du problème

Une façon de contourner ce problème consiste à vous assurer qu’il existe des accords commerciaux pour les unités qui, selon vous, seront utilisées sur les lignes de commande de l’article.

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a>Des problèmes de conversion de devises surviennent avec les accords commerciaux.

Les prix des accords commerciaux ne sont pas recalculés en fonction de la devise lorsque la devise diffère sur une commande fournisseur.

La fonction *Devise générique* vous permet de définir les prix et les remises dans une seule devise. Vous pouvez ensuite convertir vers d’autres devises selon vos besoins. En outre, une fois la conversion terminée, la fonction peut automatiquement appliquer un arrondi intelligent.

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a>Lorsque j’ouvre la page Contrat d’achat en mode d’affichage de ligne, je ne peux pas personnaliser la page en ajoutant le champ Unité de prix dans l’aperçu de la ligne.

Certains champs partagés dans le cadre de l’accord ne peuvent pas être inclus dans les personnalisations. Cette limitation se produit en raison du modèle de données implémenté. Par conséquent, vous ne pouvez pas personnaliser le champ **Unité de prix**.

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a>La limite maximale d’un contrat d’achat n’est pas effective sur une demande d’achat.

### <a name="issue-description"></a>Description du problème

Lorsqu’une demande d’achat est liée à un contrat d’achat, la limite maximale du contrat d’achat n’est pas effective sur la demande d’achat. Les informations de prix par défaut sont correctement saisies, mais la limite maximale du contrat d’achat peut être dépassée dans la demande d’achat.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est attendu. Étant donné que les demandes d’approvisionnement ne sont pas toujours approuvées, une quantité ou un montant ne doit pas être réservé sur le contrat d’achat. Par conséquent, vous ne respecterez pas la limite maximale du contrat d’achat.

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a>Des accords commerciaux peuvent être créés à partir d’appels d’offres rejetés. Par conséquent, le système n’empêche pas la création de journaux d’accords commerciaux si la ligne d’appel d’offres n’a pas été acceptée.

Vous pouvez créer des accords commerciaux pour toutes les réponses à un appel d’offres, qu’elles aient été acceptées ou rejetées. Pour plus d’informations, voir [Vue d’ensemble des appels d’offre](request-quotations.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]