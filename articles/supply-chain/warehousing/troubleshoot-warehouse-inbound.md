---
title: Résoudre les problèmes des opérations d’entrepôt entrantes
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d'opérations d'entrepôts entrantes dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 71f590ec01b757de298bd2692fdbdb0324843376
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970244"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a>Résoudre les problèmes des opérations d’entrepôt entrantes

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d'opérations d'entrepôts entrantes dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a>Je reçois le message d'erreur suivant : "Ordre de qualité %1 a été généré. Profil de groupement introuvable. Vérifiez votre configuration."

### <a name="issue-description"></a>Description du problème

Ce message d'erreur est lié à un processus de réception où la gestion de la qualité (QMS) est activée. Selon les configurations de votre environnement, des détails supplémentaires sur la transaction qui génère le message d'erreur peuvent aider à résoudre le problème.

### <a name="issue-resolution"></a>Résolution du problème

Tout d'abord, examinez la configuration du [prélèvement de cluster](set-up-cluster-picking.md) et assurez-vous que vos profils de cluster sont correctement configurés. Vous ne pouvez pas utiliser d'élément de menu d'appareil mobile pour la sélection de cluster à moins que des profils de cluster ne soient configurés. En fonction de votre environnement, vous devrez peut-être également examiner d'autres configurations associées.

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a>La réception de contenant mixte ne fonctionne pour aucun code de disposition, sauf le crédit.

### <a name="issue-description"></a>Description du problème

Quand le champ **Action** d'un code de disposition est défini sur *Crédit* ou *Rebut*, vous ne pouvez utiliser que l'élément de menu [Réception de contenant mixte](mixed-license-plate-receiving.md) pour traiter les éléments retournés.

### <a name="issue-resolution"></a>Résolution du problème

Microsoft a évalué ce problème et a déterminé qu'il s'agissait d'une limitation de fonctionnalité. Actuellement, seuls les [codes de disposition](../service-management/set-up-disposition-codes.md) où le champ **Action** est défini sur *Crédit* ou *Rebut* sont pris en charge pour la réception de contenants mixtes.

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a>Lorsque j'exécute la tâche périodique Mettre à jour les reçus de produits, les commandes fournisseur non confirmés sont confirmés.

### <a name="issue-description"></a>Description du problème

Après avoir exécuté la tâche périodique *Mettre à jour les réceptions de produits*, le système confirme automatiquement les commandes fournisseur non confirmés dont le statut de transaction de stock est *Inscrit*.

### <a name="issue-resolution"></a>Résolution du problème

Une nouvelle fonctionnalité de gestion des charges entrantes, *À réception des quantités de chargement*, résout ce problème. Pour activer cette fonctionnalité, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez les fonctionnalités suivantes (dans l'ordre de la liste) :

1. Associer les mouvements de stock de commande fournisseur au chargement
1. Réception excédentaire des quantités de chargement

Pour plus d'informations, consultez [Afficher les quantités de produits enregistrées par rapport aux commandes fournisseur](inbound-load-handling.md#post-registered-quantities).
