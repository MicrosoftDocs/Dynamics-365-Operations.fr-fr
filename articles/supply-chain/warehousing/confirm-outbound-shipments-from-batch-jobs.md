---
title: Confirmer les expéditions sortantes des traitements par lots
description: Cette rubrique décrit comment configurer un traitement par lots qui confirme automatiquement les expéditions des ordres de transfert sortants pour les chargements prêts à être expédiés.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: d47b88fcc5e25fc85377b52fa9832916a4bb2217
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572383"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Confirmer les expéditions sortantes des traitements par lots

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment configurer un traitement par lots qui confirme automatiquement les expéditions des ordres de transfert sortants pour les chargements prêts à être expédiés. Le traitement par lots décrit ici s’applique uniquement aux expéditions des ordres de transfert, et non aux commandes client.

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a>Activer la fonctionnalité Confirmer les expéditions sortantes des traitements par lots

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser la page [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. La fonctionnalité est répertoriée comme suit :

- **Module** - *Gestion des entrepôts*
- **Nom de la fonctionnalité** - *Confirmer les expéditions sortantes des traitements par lots*

## <a name="process-outbound-shipments"></a>Traiter les expéditions sortantes

Pour paramétrer un traitement par lots planifié pour exécuter la confirmation des expéditions sortantes pour les chargements prêts à être expédiés :

1. Allez dans **Gestion des entrepôts \> Tâches périodiques \> Traiter les expéditions sortantes**.
1. La boîte de dialogue **Confirmer l’expédition** s’ouvre. Dans l’organisateur **Enregistrements à inclure**, sélectionnez **Filtre**.
1. La boîte de dialogue de l’éditeur de requêtes s’ouvre. Dans l’onglet **Plage**, ajoutez une ligne avec les valeurs suivantes :
    - **Table** - *Chargements*
    - **Table dérivée** - *Chargements*
    - **Champ** - *Statut du chargement*
    - **Critères** - *Chargé*
1. Cliquez sur **OK** pour revenir à la boite de dialogue **Confirmer l’expédition**.
1. Dans l’organisateur **Exécuter en arrière-plan**, définissez **Traitement par lots** sur **Oui**.
1. Dans l’organisateur **Exécuter en arrière-plan**, sélectionnez **Récurrence**.
1. La boîte de dialogue **Définir la récurrence** s’ouvre. Définissez le programme d’exécution selon les besoins de votre entreprise.
1. Cliquez sur **OK** pour revenir à la boite de dialogue **Confirmer l’expédition**.
1. Cliquez sur **OK** dans la boîte de dialogue **Confirmer l’expédition** pour ajouter le traitement par lots à la file d’attente des traitements par lots.

Pour plus d’informations, voir [Vue d’ensemble du traitement par lots](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]