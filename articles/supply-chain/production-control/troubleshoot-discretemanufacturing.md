---
title: Résoudre le problème de fabrication discrète
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation de la fabrication discrète.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: b9c43d59e8022a365853f4b9cbb32ac3c3074e3f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810916"
---
# <a name="troubleshoot-discrete-manufacturing"></a>Résoudre le problème de fabrication discrète

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation de la fabrication discrète.

## <a name="i-receive-the-following-error-message-warehouse-management-processes-are-currently-being-used-if-work-lines-are-not-yet-registered-you-can-cancel-the-created-work-and-any-load-or-shipment-lines-and-then-continue-with-the-picking-or-shipping-process"></a>Je reçois le message d’erreur suivant : « Les processus de gestion d’entrepôt sont actuellement utilisés. Si les lignes de travail ne sont pas encore enregistrées, vous pouvez annuler le travail créé et toutes les lignes de chargement ou d’expédition, puis poursuivre le processus de retrait ou d’expédition. »

### <a name="issue-description"></a>Description du problème

Ce problème se produit si vous essayez de réserver ou de libérer du travail pour une ligne, mais que la transaction de stock a un statut de *Retiré*, ce qui indique que le matériel a été retiré.

### <a name="issue-resolution"></a>Résolution du problème

Pour régler ce problème, exécutez l’une des étapes ci-dessous.

- Redéfinissez le statut de l’ordre de fabrication sur *Estimé* ou *Libéré*.
- Ouvrez la page de détails de la l’ordre de fabrication concerné. Dans le volet Actions, sur l’onglet **Entrepôt**, dans le groupe **Arrêt**, sélectionnez **Arrêter et annuler le retrait** pour annuler el retrait de toutes les transactions retirées. Puis sélectionnez **Supprimer l’arrêt** pour traiter l’ordre de fabrication.

Voici une explication des fonctions *Annuler le retrait* et *Arrêter* :

- **Annuler le retrait** – Cette fonction inverse le statut des mouvements de stock pour les lignes de nomenclature (BOM) et les lignes de formule qui ont un statut de *Retiré* par le biais de *En commande*. Lorsque le travail de prélèvement des matières premières est terminé, le statut des lignes est défini sur *Retiré*. Ce statut empêche la remise à zéro de l’ordre de fabrication sur le statut *Créé*. Dans ce cas, vous pouvez utiliser la fonction *Annuler le retrait* pour annuler les transactions du statut *Retiré*, puis réinitialisez l’ordre de fabrication sur le statut *Créé*.
- **Arrêter** – Cette fonction définit un indicateur **Arrêté** sur l’ordre de fabrication pour empêcher toute mise à jour du statut de la commande. Vous pouvez trouver l’indicateur **Arrêté** sur le raccourci **Entrepôt** de la page de détails de l’ordre de fabrication.

> [!NOTE]
>
> - Les boutons ne sont visibles que lorsque l’ordre de fabrication est créé pour les articles activés pour les processus d’entrepôt.
> - Le groupe **Arrêter** est visible uniquement sur l’onglet **Entrepôt** du volet Actions de la page des détails de l’ordre de fabrication. Ce n’est pas visible sur le raccourci **Entrepôt** de la page de liste **Ordres de fabrication**.

## <a name="the-matching-resource-name-isnt-updated-after-i-change-a-worker-name-in-the-global-address-book"></a>Le nom de ressource correspondant n’est pas mis à jour une fois que j’ai modifié le nom d’un collaborateur dans le carnet d’adresses global.

### <a name="issue-description"></a>Description du problème

Si vous modifiez le nom d’un collaborateur dans le carnet d’adresses global, le nom de la ressource correspondante n’est pas mis à jour dans le générique du groupe de ressources.

### <a name="issue-resolution"></a>Résolution du problème

Ce scénario n’est pas actuellement prise en charge. Pour résoudre le problème, vous devez mettre à jour manuellement le nom de la ressource.

## <a name="when-i-create-a-new-production-order-i-dont-receive-the-following-message-insert-the-active-version-of-bill-of-material-and-route"></a>Lorsque je crée un ordre de fabrication, je ne reçois pas le message suivant : « Insérer la version active de la nomenclature et de la gamme ? »

### <a name="issue-description"></a>Description du problème

Lorsque vous créez un ordre de fabrication, après avoir saisi le numéro d’article, les champs **Site** et **Entrepôt** sont automatiquement définis sur le site et l’entrepôt par défaut défini sur la page **Paramètres de commande par défaut** pour l’article de produits finis. De plus, le numéro de nomenclature et le numéro de gamme actifs sont automatiquement saisis. Vous ne recevez pas le message suivant qui vous invite à saisir ces valeurs :

> Insérer la version active pour la nomenclature et la gamme ?

### <a name="issue-resolution"></a>Résolution du problème

Vous n’êtes pas invité à insérer des numéros de nomenclature et de gamme si vous sélectionnez un produit pour lequel un site et un entrepôt sont définis sur la page **Paramètres de commande par défaut**. Vous êtes invité uniquement si ces valeurs ne sont pas définies pour le produit sélectionné.

## <a name="production-orders-arent-shown-on-the-marking-page"></a>Les ordres de fabrication ne sont pas affichés sur la page de marquage.

### <a name="issue-description"></a>Description du problème

Certains ordres de fabrication ne sont pas affichés sur la page de **marquage**.

### <a name="issue-resolution"></a>Résolution du problème

Les produits qui ont la configuration suivante ne sont pas disponibles pour le marquage. Par conséquent, ils ne seront pas affichés sur la page de **marquage** :

- Les produits sont définis comme des produits du type *Poids variable*.
- Ils sont activés pour les processus d’entrepôt avancés.
- Ils sont configurés pour être contrôlés par le principe *Coût standard*.

## <a name="when-i-try-to-end-a-production-order-i-receive-the-following-error-message-calculating-bom-consumptioncost-value-must-be-negative-upon-issue-from-inventory"></a>Lorsque j’essaie de mettre fin à un ordre de fabrication, je reçois le message d’erreur suivant : « Le calcul de la valeur de consommation de la nomenclature doit être négatif lors de la sortie du stock. »

Ce problème a été résolu dans la version 10.0.15.

## <a name="when-the-status-of-a-production-order-is-changed-from-reported-as-finished-to-end-i-receive-the-following-error-messages-update-conflict-the-standard-cost-does-not-match-with-the-financial-inventory-value-after-the-update-and-a-critical-error-has-occurred-in-function-inventcostmovementcheckvariance"></a>Lorsque le statut d’un ordre de fabrication passe de Signalé comme terminé à Fin, je reçois les messages d’erreur suivants : « Conflit de mise à jour. Le coût standard ne correspond pas à la valeur de stock financière après la mise à jour » et « Une erreur critique s’est produite dans la fonction InventCostMovement.checkVariance ».

Ce problème se produit car les données sous-jacentes ont été modifiées par un autre processus. Le processus essaiera de mettre à jour les données jusqu’à cinq fois. Si le conflit persiste après cinq tentatives, vous recevrez les messages d’erreur suivants :

> Conflit de mise à jour. Le coût standard ne correspond pas à la valeur de stock financière après la mise à jour.

> Une erreur critique s’est produite dans la fonction InventCostMovement.checkVariance.

Ce comportement est fait exprès. Pour corriger le problème, reprenez le traitement par lots. Il devrait finir de s’exécuter.

Si le traitement par lots échoue systématiquement après sa reprise, vérifiez que la précision d’arrondi de la devise par défaut de la comptabilité est conforme à l’arrondi appliqué aux valeurs de la table InventSum. Si la précision d’arrondi a été remplacée par une valeur non conforme, vous devez probablement la remettre à une valeur conforme. Recherchez **ModifiedDateTime**. Dans ce cas, la valeur indiquera généralement que la précision d’arrondi a été récemment modifiée.

## <a name="when-i-release-to-a-warehouse-i-receive-the-following-error-message-item-rm-could-not-be-fully-reserved-ensure-that-the-full-quantity-is-available-or-reserve-the-items-manually-if-the-reservation-field-on-the-bom-line-is-set-to-manual-or-started-could-not-release-the-order-to-warehouse-because-some-materials-could-not-be-reserved-however-the-status-is-updated-to-released"></a>Lorsque je libère dans un entrepôt, je reçois le message d’erreur suivant : « L’article RM n’a pas pu être entièrement réservé. Assurez-vous que la quantité totale est disponible ou réservez les articles manuellement si le champ Réservation de la ligne de nomenclature est défini sur Manuel ou Démarré. Impossible de libérer la commande dans l’entrepôt, car certaines matières premières n’ont pas pu être réservées. » Cependant, le statut est mis à jour sur Validé.

### <a name="issue-description"></a>Description du problème

Si tous les articles de ligne de nomenclature ne sont pas physiquement disponibles lorsqu’un ordre de fabrication est lancé, la stratégie **Libération dans l’entrepôt** est définie sur *Exiger une réservation complète* sur l’ordre de fabrication, vous recevrez le message d’erreur suivant :

> L’article RM n’a pas pu être entièrement réservé. Assurez-vous que la quantité totale est disponible ou réservez les articles manuellement si le champ Réservation de la ligne de nomenclature est défini sur Manuel ou Démarré. Impossible de libérer la commande dans l’entrepôt, car certaines matières premières n’ont pas pu être réservées.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est fait exprès et fonctionne comme prévu.

## <a name="when-i-try-to-end-a-production-order-and-report-as-finished-i-receive-the-following-error-message-total-good-quantity-reported-as-finished-for-the-production-will-be-1-feedback-for-the-last-operation-is-000-in-total"></a>Lorsque j’essaie de mettre fin à un ordre de fabrication et de signaler que la production est terminée, je reçois le message d’erreur suivant : « La quantité totale correcte rapportée comme terminée pour la production sera %1. Rétroaction pour la dernière opération de 0,00 au total. »

### <a name="issue-description"></a>Description du problème

Lorsque vous essayez de publier un rapport en tant que journal terminé sur un ordre de fabrication, vous recevez le message d’erreur suivant :

> La quantité correcte totale déclarée terminée en production sera %1. Rétroaction pour la dernière opération de 0,00 au total.

### <a name="possible-cause"></a>Raison possible

Ce problème se produit si les quantités enregistrées lors des dernières opérations étaient incorrectes. Par exemple, si la production est lancée, mais que la quantité à démarrer n’est pas allouée, le journal des fiches production sera enregistré sans aucune ligne. Pour confirmer la situation, ouvrez l’ordre de fabrication, puis, dans le volet Actions, sur l’onglet **Afficher**, sélectionnez **Fiche production**.

### <a name="workaround"></a>Solution de contournement

Vous pouvez résoudre ce problème en publiant des journaux supplémentaires pour les opérations pour lesquelles les journaux n’ont pas été correctement validés. Redémarrez l’ordre de fabrication et sélectionnez pour valider les journaux supplémentaires. Cette action ne lancera pas l’ordre de fabrication, mais enregistrera les journaux. La fiche production doit alors indiquer les quantités enregistrées et vous devez être en mesure de terminer les ordres de fabrication avec succès.

## <a name="can-i-report-a-production-order-as-finished-while-i-report-the-error-quantity-but-not-while-i-report-the-time-or-material-quantity"></a>Puis-je déclarer un ordre de fabrication comme terminé pendant que je signale la quantité d’erreur, mais pas pendant que je signale le temps ou la quantité de matériel ?

Vous ne pouvez pas signaler la quantité d’erreur sur un ordre de fabrication, sauf si vous déclarez également la quantité correcte. Ce scénario n’est **pas** pris en charge. La mise à jour de déclarer comme terminé finira par échouer lorsque vous essaierez de mettre fin à l’ordre de fabrication et vous recevrez le message d’erreur suivant :

> Quantité déclarée terminée manquante.

## <a name="can-i-trace-the-serial-numbers-of-finished-goods-against-the-serial-numbers-of-consumed-goods"></a>Puis-je effectuer le suivi des numéros de série des produits finis par rapport aux numéros de série des produits consommés ?

Vous ne pouvez pas effectuer le suivi des numéros de série des produits finis par rapport aux numéros de série des articles qu’un ordre de fabrication consomme pour fabriquer ces produits finis. Ce scénario n’est pas actuellement prise en charge. La solution consiste à créer des ordres de fabrication pour une quantité de 1.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]