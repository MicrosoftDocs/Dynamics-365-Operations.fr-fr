---
title: Résoudre des problèmes de planification
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation de la planification.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 44291f5bcd9ffedf717150f8efe32e9eeda02f2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011345"
---
# <a name="troubleshoot-master-planning"></a>Résoudre des problèmes de planification

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation de la planification.

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a>La distribution de nomenclatures se comporte différemment pour les ordres de fabrication confirmés et pour les ordres de fabrication estimés pour le travail créé manuellement.

### <a name="issue-description"></a>Description du problème

Lorsqu'un ordre de fabrication est confirmé, les articles ne sont pas distribués lorsque vous distribuez la nomenclature (BOM). Cependant, lorsque vous créez manuellement un ordre de travail et que vous estimez ensuite l'ordre de fabrication, les postes sont répartis.

### <a name="issue-resolution"></a>Résolution du problème

Le système fonctionne comme prévu. La distribution qui se produit lorsque l'ordre de fabrication est confirmé pointera vers l'ordre planifié, mais il ne semble pas que l'ordre planifié soit actuellement confirmé dans ce cas. Cependant, si l'ordre de fabrication a été estimé, l'explosion est déclenchée à partir de l'ordre de fabrication lancé lorsqu'il n'existe aucun ordre planifié.

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a>La valeur Délai n'est pas mise à jour lorsque je replanifie un ordre planifié.

Pour mettre à jour le délai des ordres planifiés, ouvrez la boîte de dialogue **Replanification** pour l'ordre planifié. Dans l'organisateur **Répartition**, assurez-vous que l'option **Traiter la vague au lancement dans l’entrepôt** est définie sur *Oui*.

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a>La planification de la production ne prend pas en compte les marges de sécurité définies sur la couverture des articles pour l'approvisionnement indexé.

### <a name="issue-description"></a>Description du problème

La planification tient compte des marges de sécurité. Cependant, les marges de sécurité sont ignorées lors de la planification des ordres de fabrication planifiés.

### <a name="issue-resolution"></a>Résolution du problème

Les marges ne sont prises en compte que lors de la planification, pas lors de la planification manuelle. Les marges sont conçues pour agir comme un tampon pendant la phase de planification, pour donner une certaine "marge" pour le processus réel.

Pour obtenir le résultat souhaité, vous pouvez supprimer la marge. L'itinéraire doit ensuite être mis à jour pour inclure l'heure souhaitée (par exemple, en tant que durée de la file d'attente). La planification et la planification manuelle devraient alors produire le même résultat.

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a>Les commandes planifiées sont générées même si nous avons des articles en stock et que des ordres de fabrication existent déjà pour eux.

Vous pourrez peut-être résoudre ce problème en augmentant la valeur **Jours positifs** pour les groupes concernés sur la page **Groupe de couverture**. Ce changement amènera le système à déterminer si le stock disponible peut être utilisé pour la demande. Ensuite, un nouvel ordre planifié ne sera pas généré pour les articles en stock.

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a>La planification générale ne semble pas respecter les limites de capacité et prévoit plus que la capacité disponible.

### <a name="issue-description"></a>Description du problème

Lorsque vous utilisez la planification des opérations là où il y a une capacité limitée et où l'itinéraire spécifie un mélange d'exigences pour un groupe de ressources et des ressources individuelles, il existe un faible risque de surréservation en raison de la façon dont l'algorithme valide les conflits de capacité. Cette surréservation peut se produire lorsque vous utilisez des assistants pour exécuter la planification générale. Il est plus probable que cela se produise s'il existe de nombreux travaux dont la durée d'exécution est relativement courte.

### <a name="issue-resolution"></a>Résolution du problème

S'il est essentiel qu'aucune surréservation ne se produise pour la planification des opérations, vous pouvez faire de la planification une partie de la planification mono-thread en activant l'option **Capacité finie précise pour la planification des opérations** sur la page **Paramètres de planification**. Cette option n'est pas disponible par défaut. Vous devez l'ajouter manuellement à la page à l'aide des fonctionnalités de personnalisation. Lorsque vous utilisez cette option, la planification s'exécute plus lentement en raison du manque de traitement parallèle.

## <a name="planned-orders-take-a-long-time-to-update"></a>Les commandes planifiées prennent du temps à se mettre à jour.

### <a name="issue-description"></a>Description du problème

Lors de la mise à jour de la quantité requise et/ou de la date de livraison d'un ordre planifié, il faut généralement au moins 30 secondes par commande pour enregistrer la mise à jour.

### <a name="issue-resolution"></a>Résolution du problème

Il s'agit d'un problème connu avec le moteur de planification intégré. Cela est dû à la distribution automatique sous-jacente à travers la structure de la nomenclature lors des modifications. Ce problème est résolu dans l'Optimisation de la planification, où un planificateur peut mettre à jour et approuver les commandes pertinentes et, s'il le souhaite, déclencher un cycle de planification pour mettre à jour les ordres planifiés pour la structure de nomenclature sous-jacente.

Une façon d'améliorer les performances avec le moteur de planification intégré consiste à effectuer les opérations suivantes :

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Sélectionnez un plan.
1. Développez le raccourci **Plage de gestion en jours**.
1. Définissez **Répartition** sur *Oui* et définissez le champ sous ce paramètre sur 0 (zéro).

> [!NOTE]
> Cela limitera la période des distributions effectuées pour ce plan à une seule journée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]