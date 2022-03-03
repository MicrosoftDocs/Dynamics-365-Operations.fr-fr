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
ms.openlocfilehash: f68dcfc0c1454ee5b095e186c52faa6c83bf8dc6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103913"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Confirmer les expéditions sortantes des traitements par lots

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment configurer un traitement par lots qui confirme automatiquement les expéditions des ordres de transfert sortants pour les chargements prêts à être expédiés. Le traitement par lots décrit ici s’applique uniquement aux expéditions des ordres de transfert, et non aux commandes client.

## <a name="turn-the-confirm-outbound-shipments-from-batch-jobs-feature-on-or-off"></a>Activer ou désactiver la fonctionnalité Confirmer les expéditions sortantes des traitements par lots

Pour utiliser la fonctionnalité décrite dans cette rubrique, la fonctionnalité *Confirmer les expéditions sortantes à partir des tâches par lots* doit être activée pour votre système. À compter de la version 10.0.21 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire et peut être désactivée. Si vous exécutez une version antérieure à 10.0.25, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Confirmer les expéditions sortantes à partir des tâches par lots* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

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