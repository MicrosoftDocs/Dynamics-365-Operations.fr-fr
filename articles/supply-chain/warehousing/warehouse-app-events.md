---
title: Événements d’application d’entrepôt
description: Cet article décrit le traitement des événements d’application d’entreposage utilisé pour traiter les messages d’événement de l’application d’entreposage dans le cadre d’un traitement par lots.
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 41b9538d3064bad24c4c5c60d401605e47e9c655
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905452"
---
# <a name="warehouse-app-event-processing"></a>Traitement des événements de l’application d’entreposage

[!include [banner](../includes/banner.md)]

Les traitements par lots exécutés dans Supply Chain Management peuvent utiliser les données d’une file d’attente pour traiter les événements émis par l’application mobile Gestion des entrepôts afin de réagir selon les besoins aux événements signalés. Cette fonctionnalité ajoute les événements pertinents à la file d’attente en réponse à certains types d’actions entreprises par les employés utilisant l’application. Un exemple est l’utilisation de la fonction *Créer et traiter des ordres de transfert depuis l’application d’entreposage* ; l’en-tête et les lignes de l’ordre de transfert sont créés et mis à jour dans le back-end lorsque le système exécute le traitement par lots **Traiter les événements de l’application d’entreposage**.

## <a name="turn-the-process-warehouse-app-events-feature-on-or-off"></a>Activer ou désactiver la fonction Traiter les événements de l’application d’entreposage

À compter de la version 10.0.25 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Remplacer la réservation de production par défaut* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurer un traitement par lots pour traiter les événements de l’application d’entreposage

### <a name="process-warehouse-app-events"></a>Traiter les événements d’application d’entrepôt

Configurez un traitement par lots planifié pour traiter les événements de l’application d’entreposage pour la création de l’ordre de transfert et les mises à jour des lignes.

1. Accédez à **Gestion des entrepôts \> Tâches périodiques \> Traiter les événements de l’application d’entreposage**.
1. La boîte de dialogue Traiter les événements de l’application d’entreposage s’ouvre. Développez l’organisateur **Exécuter en arrière-plan** et définissez **Traitement par lots** sur **Oui**.
1. Dans l’organisateur **Exécuter en arrière-plan**, sélectionnez **Récurrence**.
1. La boîte de dialogue **Définir la récurrence** s’ouvre. Définissez le programme d’exécution selon les besoins de votre entreprise.
1. Sélectionnez **OK** pour revenir à la boîte de dialogue **Traiter les événements de l’application d’entreposage**.
1. Sélectionnez **OK** dans la boîte de dialogue **Traiter les événements de l’application d’entreposage** pour ajouter le traitement par lots à la file d’attente des traitements par lots.

## <a name="query-warehouse-app-events"></a>Interroger les événements de l’application d’entreposage

Vous pouvez afficher la file d’attente et les messages d’événements générés par l’application mobile Gestion des entrepôts en accédant à **Gestion des entrepôts \> Recherches et états \> Journaux des appareils mobiles \> Événements de l’application d’entreposage**.

## <a name="the-standard-event-queue-process"></a>Le processus de file d’attente d’événements standard

La file d’attente des événements de l’application d’entreposage est généralement utilisée avec le flux décrit ci-dessous :

1. Un événement est ajouté à la file d’attente avec un message d’événement. Le nouveau message a initialement un état d’événement de **En attente**, ce qui signifie que le traitement par lots **Traiter les événements de l’application d’entreposage** ne sélectionnera pas ce message et ne le traitera pas.
1. Dès que l’état du message sera actualisé en **En file d’attente**, le traitement par lots **Traiter les événements de l’application d’entreposage** sélectionnera et traitera l’événement.
1. Le traitement par lots actualise les états d’événement soit en **Terminé**, soit en **Échoué**, selon que le processus demandé était possible.
1. Lorsque tous les messages d’événements associés sont **Terminés**, l’événement est supprimé de la file d’attente.

 Pour voir un exemple détaillé, voir [Créer un ordre de transfert à partir du processus de l’application d’entreposage](create-transfer-order-from-warehouse-app.md).

## <a name="handle-event-errors"></a>Gérer les erreurs d’événement

Dans le cadre du traitement des événements d’entrepôt, l’activité de message demandée peut ne pas recevoir de processus du traitement par lots. Dans ce cas, le message d’événement sera changé en **Échoué**. Vous pouvez utiliser les informations du **Journal des traitements par lots** pour savoir pourquoi et prendre les mesures nécessaires pour corriger les éventuels problèmes.

Pour voir un exemple détaillé, voir [Créer un ordre de transfert à partir de l’application d’entreposage](create-transfer-order-from-warehouse-app.md).

Pour réinitialiser un message d’événement d’application d’entreposage ayant échoué :

1. Accédez à **Gestion des entrepôts \> Recherches et états \> Journaux des appareils mobiles \> Événements de l’application d’entreposage**.
1. Dans l’organisateur **Messages d’événement de l’application d’entreposage**, recherchez et sélectionnez un événement pertinent qui affiche **Échoué** dans la colonne **État de l’événement**.
1. Sélectionnez **Réinitialiser** dans la barre d’outils **Messages d’événement de l’application d’entreposage**.
1. Continuez jusqu’à ce que tous les messages pertinents soient réinitialisés.

Vous pouvez également supprimer un message d’événement **Échoué** à l’aide de l’option **Supprimer** de la barre d’outils **Messages d’événement de l’application d’entreposage**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]