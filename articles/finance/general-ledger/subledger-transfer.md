---
title: Transfert de la comptabilité auxiliaire vers la comptabilité
description: Cette rubrique décrit les fonctionnalités associées au transfert de la comptabilité auxiliaire dans la comptabilité.
author: rcarlson
ms.date: 12/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 213bbc2541c614aa26b0c830431818fb99c7682d
ms.sourcegitcommit: f5885999e008a49fe072d95f15e239905c24918a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900728"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Transfert de la comptabilité auxiliaire vers la comptabilité

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctionnalités liées aux règles permettant le transfert par lots des écritures de journal de la comptabilité auxiliaire.

Dans la version 8.1, des modifications ont été apportées pour permettre le transfert des règles, ce qui a rendu l’option **Synchrone** obsolète. Pour plus d’informations, voir [Fonctionnalités supprimées ou obsolètes pour Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

Les options suivantes sont disponibles pour le transfert par lots de la comptabilité auxiliaire :

- **Asynchrone** : le transfert des écritures de la comptabilité auxiliaire vers la comptabilité est programmé immédiatement. Le N° document de comptabilité est enregistré dès que des ressources sont disponibles pour traiter cette demande sur le serveur.
- **Traitement par lots planifié** : les écritures de la comptabilité auxiliaire qui doivent être transférées sont ajoutées à la file d’attente de traitement de la comptabilité. Les écritures dans la file d’attente seront traitées dans l’ordre dans lequel elles sont reçues. Chaque n° document de comptabilité actualise les comptes au moment programmé si des ressources sont disponibles pour réaliser ce traitement par lots sur le serveur.

Dans la version 10.0.8, des améliorations ont été apportées pour améliorer les performances de l’option **Asynchrone**. Cette fonctionnalité est activée sous le nom **Optimisation des performances du transfert de la comptabilité auxiliaire vers la comptabilité**.

La fonctionnalité de transfert asynchrone des traitements par lots de la comptabilité auxiliaire permet d’améliorer le transfert des données de la comptabilité auxiliaire vers la comptabilité. En regroupant des ensembles de transactions plus petites et en transférant les transactions en groupes, la fonctionnalité traite les transactions plus efficacement. Lorsque les transactions sont regroupées, les ressources du serveur de traitement par lots sont utilisées plus efficacement.

Le transfert asynchrone de lots auxiliaires nécessite que le serveur de lots soit configuré, en ligne et opérationnel, car les tâches de lots sont créées pour une exécution immédiate sur le serveur de lots. Quand la fonctionnalité **Optimisation des performances du transfert de la comptabilité auxiliaire vers la comptabilité** est activée, le traitement par lots du système **Automatisation des processus** intitulé **Tâche système d’interrogation de l’automatisation des processus** doit également être activé. Pour plus d’informations, voir [Automatisation de processus](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

Le changement d’efficacité au niveau du lot utilise un seul traitement par lots récurrent pour toutes les entités juridiques du système. Au moment de l’exécution, une nouvelle tâche de traitement par lots est créée pour traiter les enregistrements requis qui n’ont pas encore été transférés. Il est possible de contrôler davantage de paramètres à partir de la page **Automatisation des processus** dans l’administration système. Sur cette page, vous pouvez modifier le processus d’arrière-plan, changer la fréquence et définir une période de veille.

Pour plus d’informations sur la configuration de l’automatisation des processus, voir [Automatisation des processus](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
