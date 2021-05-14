---
title: Résoudre les problèmes des opérations d’entrepôt entrantes
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d’opérations d’entrepôts entrantes dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 6f6d689c596b4ec924cb50ec3bea8ce907e6dc6b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920985"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a>Résoudre les problèmes des opérations d’entrepôt entrantes

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d’opérations d’entrepôts entrantes dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a>Je reçois le message d’erreur suivant : "Ordre de qualité %1 a été généré. Profil de groupement introuvable. Vérifiez votre configuration."

### <a name="issue-description"></a>Description du problème

Ce message d’erreur est lié à un processus de réception où la gestion de la qualité (QMS) est activée. Selon les configurations de votre environnement, des détails supplémentaires sur la transaction qui génère le message d’erreur peuvent aider à résoudre le problème.

### <a name="issue-resolution"></a>Résolution du problème

Tout d’abord, examinez la configuration du [prélèvement de cluster](set-up-cluster-picking.md) et assurez-vous que vos profils de cluster sont correctement configurés. Vous ne pouvez pas utiliser d’élément de menu d’appareil mobile pour la sélection de cluster à moins que des profils de cluster ne soient configurés. En fonction de votre environnement, vous devrez peut-être également examiner d’autres configurations associées.

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a>La réception de contenant mixte ne fonctionne pour aucun code de disposition, sauf le crédit.

### <a name="issue-description"></a>Description du problème

Quand le champ **Action** d’un code de disposition est défini sur *Crédit* ou *Rebut*, vous ne pouvez utiliser que l’élément de menu [Réception de contenant mixte](mixed-license-plate-receiving.md) pour traiter les éléments retournés.

### <a name="issue-resolution"></a>Résolution du problème

Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité. Actuellement, seuls les [codes de disposition](../service-management/set-up-disposition-codes.md) où le champ **Action** est défini sur *Crédit* ou *Rebut* sont pris en charge pour la réception de contenants mixtes.

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a>Lorsque j’exécute la tâche périodique Mettre à jour les reçus de produits, les commandes fournisseur non confirmés sont confirmés.

### <a name="issue-description"></a>Description du problème

Après avoir exécuté la tâche périodique *Mettre à jour les réceptions de produits*, le système confirme automatiquement les commandes fournisseur non confirmés dont le statut de transaction de stock est *Inscrit*.

### <a name="issue-resolution"></a>Résolution du problème

Une nouvelle fonctionnalité de gestion des charges entrantes, *À réception des quantités de chargement*, résout ce problème. Pour activer cette fonctionnalité, accédez à l'espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez les fonctionnalités suivantes (dans l’ordre de la liste) :

1. Associer les mouvements de stock de commande fournisseur au chargement
1. Réception excédentaire des quantités de chargement

Pour plus d’informations, consultez [Afficher les quantités de produits enregistrées par rapport aux commandes fournisseur](inbound-load-handling.md#post-registered-quantities).

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a>Lorsque j’enregistre des commandes entrantes, je reçois le message d’erreur suivant : « La quantité n’est pas valide ».

### <a name="issue-description"></a>Description du problème

Si le champ **Stratégie de regroupement de contenants** est défini sur *Défini par l’utilisateur* pour un élément de menu de l’appareil mobile utilisé pour enregistrer les commandes entrantes, vous recevez un message d’erreur (« La quantité n’est pas valide ») et vous ne pouvez pas terminer l’enregistrement.

### <a name="issue-cause"></a>Cause du problème

Lorsque l’option *Défini par l’utilisateur* est utilisé comme stratégie de regroupement de contenants, le système divise l’inventaire entrant en contenants distincts, comme indiqué par le groupe de séquences d’unités. Si des numéros de lot ou de série sont utilisés pour suivre l’article qui est reçu, les quantités de chaque lot ou série doivent être spécifiées pour chaque contenant enregistré. Si la quantité spécifiée pour un contenant dépasse la quantité qui doit encore être reçue pour les dimensions actuelles, vous recevez le message d’erreur.

### <a name="issue-resolution"></a>Résolution du problème

Lorsque vous enregistrez un article à l’aide d’un élément de menu d’appareil mobile où le champ **Stratégie de regroupement de contenants** est défini sur *Défini par l’utilisateur*, le système peut exiger que vous confirmiez ou saisissiez des numéros de contenant, des numéros de lot ou des numéros de série.

Sur la page de confirmation du contenant, le système affichera la quantité allouée pour le contenant actuel. Sur les pages de confirmation de lot ou de série, le système affichera la quantité qui doit encore être reçue sur le contenant actuel. Il comprendra également un champ dans lequel vous pourrez saisir la quantité à enregistrer pour cette combinaison de contenant et de numéro de lot ou de série. Dans ce cas, assurez-vous que la quantité enregistrée pour le contenant ne dépasse pas la quantité qui doit encore être reçue.

Sinon, si trop de contenants sont générés lors de l’enregistrement de la commande entrante, la valeur du champ **Stratégie de regroupement des contenants** peut être changée en *Regroupement de contenants*, un nouveau groupe de séquences d’unités peut être affecté à l’article, ou l’option **Regroupement de contenants** pour le groupe de séquences d’unités peut être désactivée.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
