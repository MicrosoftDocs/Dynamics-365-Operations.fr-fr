---
title: Résoudre les problèmes liés aux commandes fournisseur
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation des commandes fournisseur.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: e55974f65577170880e60095f1ba74ea7366e592
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834356"
---
# <a name="troubleshoot-purchase-orders"></a>Résoudre les problèmes liés aux commandes fournisseur

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation des commandes fournisseur.

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a>Une action ne peut être effectuée qu'après la répartition complète du numéro de ligne.

Ce problème peut se produire en raison d'une incohérence dans les répartitions des commandes fournisseur.

Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l'état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**. Pour plus d'informations, consultez l'article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a>Lorsque les commandes fournisseur sont importées via la gestion des données, les numéros de ligne de commande fournisseur ne suivent pas l'incrément défini dans les paramètres système.

### <a name="issue-description"></a>Description du problème

Par défaut, les numéros de ligne générés automatiquement pour les lignes de commande fournisseur importées via l'entité de données *Lignes de commandes fournisseur V2* n'utilisent pas l'incrément de numéro de ligne système spécifié dans les paramètres système. Si vous créez manuellement une commande fournisseur et ajoutez des lignes via l'interface utilisateur (UI), les numéros de ligne sont incrémentés correctement. Cependant, si vous utilisez Data Management Framework (DMF), ils ne sont pas incrémentés correctement.

Ce problème se produit car, lorsque vous importez des lignes via DMF, si les numéros de ligne ne sont pas déjà affectés dans l'entité importée, le système utilise la méthode du DMF pour les affecter. Cette méthode incrémente toujours les numéros de ligne de Un.

### <a name="issue-workaround"></a>Solution de contournement du problème

Assurez-vous que les numéros de ligne souhaités sont déjà indiqués dans les champs de numéro de ligne d'entité de données lorsque vous importez les lignes de commande fournisseur. Dans ce cas, DMF n'écrasera pas les numéros de ligne.

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a>Un groupe de taxes par défaut et un escompte de règlement par défaut ne sont pas renseignés à partir du compte de facturation.

Si vous utilisez un compte de facturation différent du compte client, un groupe de taxes par défaut et un escompte de règlement par défaut ne sont pas renseignés à partir du compte de facturation lors de la création d'une commande fournisseur.

Ce comportement est fait exprès. Les valeurs par défaut du groupe de taxes, des escomptes de règlement et d'autres informations sur les prix sont basées sur le compte client et non sur le compte de facturation.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Je reçois une erreur "Référence d'objet non définie" lors de la confirmation de la commande fournisseur, ou une exception "Une exception a été levée par la cible d'un appel" se produit lors de la validation de la facture fournisseur.

Ce problème peut se produire en raison d'une incohérence dans les répartitions des commandes fournisseur.

Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l'état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**. Pour plus d'informations, consultez l'article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Une ou plusieurs répartitions comptables sont sur-réparties ou sous-réparties.

### <a name="issue-description"></a>Description du problème

Vous recevez l'erreur suivante : "Une ou plusieurs répartitions comptables sont sur-réparties ou sous-réparties."

### <a name="issue-resolution"></a>Résolution du problème

Ce problème peut se produire en raison d'une incohérence dans les répartitions des commandes fournisseur.

Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l'état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**. Pour plus d'informations, consultez l'article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>Puis-je afficher uniquement les commandes fournisseur que j'ai créées ?

Cette fonctionnalité n'est pas disponible actuellement.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>Puis-je réserver du stock et créer des transactions par rapport au stock enregistré sur une commande fournisseur ?

### <a name="issue-description"></a>Description du problème

Même lorsque les articles sont dans un état *Enregistré* sur une commande fournisseur, vous pouvez toujours réserver le stock. En d'autres termes, vous pouvez créer des transactions par rapport au stock enregistré.

### <a name="reproduce-the-issue"></a>Reproduire le problème

La procédure suivante montre comment reproduire le problème.

1. Création d'une commande fournisseur.
2. Enregistrez la ligne de commande fournisseur.
3. Notez que vous pouvez générer des réservations ou des transactions par rapport au stock enregistré.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est fait exprès. On s'attend à ce que les articles enregistrés soient physiquement arrivés dans l'entrepôt ou dans le stock, et qu'ils soient donc disponibles pour réservation.

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>Les commandes fournisseur ne reflètent pas les paramètres linguistiques de l'entité juridique.

### <a name="issue-description"></a>Description du problème

Le nom du produit sur une commande fournisseur est affiché dans la langue du système au lieu de la langue définie pour l'entité juridique dans laquelle la commande fournisseur a été créée.

### <a name="reproduce-the-issue"></a>Reproduire le problème

La procédure suivante montre comment reproduire le problème.

1. Définissez la langue du système sur *EN-US* (Anglais américain).
1. Assurez-vous qu'il y a un produit où les langues *EN-US* et *DE* (Allemand) sont tenues à jour pour les traductions du nom du produit.
1. Changez la langue d'une entité juridique en *DE*.
1. Dans l'entité juridique où *DE* est défini comme langue, créez une commande fournisseur qui inclut le produit.
1. Notez que le nom du produit est toujours affiché en anglais américain (la langue du système).

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est fait exprès. Sur les commandes fournisseur, le produit est toujours affiché dans la langue du système. La langue de la commande fournisseur est utilisée lors de la création d'un journal de confirmation.

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a>La liste des fournisseurs agréés par entité de produit ne permet pas de modifier la date d'effet.

### <a name="issue-description"></a>Description du problème

Un produit a un fournisseur agréé qui a, par exemple, une date d'effet au 11 janvier 2018 (*11/01/2018*) et une date d'expiration à *Jamais*. Si vous essayez de modifier la date d'effet au 10 janvier 2018 (*10/01/2018*) ou au 12 janvier 2018 (*12/01/2018*), vous recevez l'erreur suivante :

> Impossible de créer un enregistrement dans la liste des fournisseurs agréés (PdsApproveVendorList). La valeur "Expiration" doit être supérieure ou égale à la valeur "Effet".

### <a name="issue-resolution"></a>Résolution du problème

Vous ne pouvez prolonger que la période pour laquelle le fournisseur est agréé. Les règles suivantes s'appliquent :

- Pour modifier la date d'effet afin qu'elle soit antérieure à l'un des enregistrements (périodes) existants pour le fournisseur de l'article, la date d'expiration de la nouvelle période doit être antérieure à toutes les dates d'expiration des enregistrements existants.
- Pour modifier la date d'expiration afin qu'elle soit postérieure à l'une des périodes existantes, la date d'effet doit être postérieure à la dernière date d'expiration de tout enregistrement existant.
- Pour réduire la période globale pour laquelle le fournisseur est agréé, vous devez supprimer ou modifier les enregistrements existants. Vous pouvez également utiliser le commutateur **Tronquer** lors de l'importation. Ce commutateur supprime tous les enregistrements existants dans la table pour les fournisseurs agréés par article.

Pour l'exemple de scénario décrit dans la description du problème, où un enregistrement a une date d'effet au *11/01/2018* et une date d'expiration à *Jamais*, vous pouvez importer un nouvel enregistrement dont la date d'effet est le *10/01/2018* et la date d'expiration *Jamais*. Cependant, vous ne pouvez pas réduire la période pour que la date d'effet soit mise à jour au *12/01/2018* via la gestion des données. Vous devez effectuer cette modification via l'interface utilisateur.

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-nameisnt-synced"></a>Après avoir modifié l'adresse de livraison sur un en-tête de commande fournisseur, le nom de livraison n'est pas synchronisé.

### <a name="issue-description"></a>Description du problème

L'adresse figurant dans l'en-tête d'une commande fournisseur est mise à jour sur une adresse qui n'est pas une adresse de livraison. Bien que l'adresse soit mise à jour sur la commande fournisseur, le nom de livraison n'est pas mis à jour en fonction de l'adresse mise à jour.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est fait exprès. L'adresse sélectionnée doit être classée comme adresse de livraison. Sinon, le nom de livraison n'est pas mis à jour en fonction de l'adresse sélectionnée.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>Puis-je trouver l'utilisateur qui a annulé une commande fournisseur ?

Ces informations ne sont suivies que si la commande fournisseur fait l'objet d'une gestion des modifications. Si vous utilisez la gestion des modifications, vous pouvez voir qui a envoyé la modification (l'annulation) et qui l'a approuvée.
