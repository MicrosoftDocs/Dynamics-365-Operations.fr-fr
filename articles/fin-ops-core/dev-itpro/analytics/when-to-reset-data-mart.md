---
title: FAQ sur les réinitialisations du mini-data warehouse
description: Cette rubrique fournit des réponses à quelques-unes des questions fréquemment posées sur les réinitialisations du mini-data warehouse.
author: jinniew
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e5a40342306eb9888b456a865ab2220dccfe65f8ccecc67bf8fc16f907e06977
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767753"
---
# <a name="data-mart-resets-faq"></a>FAQ sur les réinitialisations du mini-data warehouse

Cette rubrique fournit des réponses à quelques-unes des questions fréquemment posées sur les réinitialisations du mini-data warehouse. Une réinitialisation du mini-data warehouse peut être un processus chronophage et, selon les circonstances, peut ne pas être la solution requise. Par conséquent, cette rubrique inclut des informations sur les circonstances dans lesquelles une réinitialisation du mini-data warehouse peut être utile, ainsi que sur les circonstances dans lesquelles il est peu probable qu’elle soit utile.

## <a name="what-is-a-data-mart-reset"></a>Qu’est-ce que la réinitialisation d’un mini-data warehouse ?

Une réinitialisation du mini-data warehouse désactivera les tâches d’intégration, supprimera toutes les données du mini-data warehouse, puis réactivera l’intégration.

Pour garantir que de anciennes données ne sont pas insérées, une réinitialisation du mini-data warehouse ne peut être démarrée qu’une fois les tâches existantes terminées. Si vous essayez de réinitialiser le mini-data warehouse avant que toutes les tâches ne soient terminées, vous pouvez recevoir un message tel que « La réinitialisation du mini-data warehouse n’a pas pu être traitée en raison d’une tâche active. Réessayez ultérieurement. »

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>Quand dois-je effectuer une réinitialisation d’un mini-data warehouse ?

Si une ou plusieurs des affirmations suivantes s’appliquent à votre situation, votre organisation peut bénéficier d’une réinitialisation du mini-data warehouse :

- La base de données de l’application a été restaurée.
- Vous avez ouvert un ticket de support et un ingénieur du support vous a demandé de réinitialiser le mini-data warehouse dans le cadre d’une étape de résolution des problèmes.
 
> [!NOTE]
> Le processus de réinitialisation d’un mini-data warehouse est affecté par le nombre de transactions de comptabilité et de budget dans votre base de données. Selon le nombre de transactions dans votre système, une réinitialisation du mini-data warehouse peut être effectuée en à peine 15 minutes, ou elle peut prendre jusqu’à quatre heures. Cependant, si votre réinitialisation prend plus de quatre heures, nous vous recommandons de contacter le support.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>Quand la réinitialisation d’un mini-data warehouse est-elle inappropriée ?

Voici certaines des circonstances dans lesquelles il est déconseillé de réinitialiser un mini-data warehouse :

- Vous rencontrez des problèmes de performances associés à une synchronisation des données.
- Vous rencontrez un schéma de réinitialisation récurrent pour l’une des raisons suivantes :

    - **Données manquantes** : si vous remarquez que des données sont manquantes, ouvrez un ticket de support auprès de Microsoft pour examiner le format de l’état et les éventuels problèmes de synchronisation des données.
    - **État d’intégration bloqué**
    - **Enregistrements périmés** : les enregistrements périmés ne justifient pas nécessairement une réinitialisation du mini-data warehouse. Si vous disposez d’un ensemble de données volumineux, le processus de réinitialisation mettra du temps à s’exécuter, mais il est peu probable qu’il conduise à une amélioration.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Si je réinitialise le mini-data warehouse, vais-je perdre les états que j’ai déjà conçus ?

Non. Vos états sont stockés dans des tables SQL qui ne sont pas affectées par une réinitialisation du mini-data warehouse. Si vous craignez de perdre des états que vous avez conçus, vous pouvez sauvegarder les conceptions que vous ne voulez pas perdre. Pour sauvegarder les conceptions, ouvrez Report Designer et accédez à **Entreprise \> Entreprises \> Blocs élémentaires \> Exporter**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Tous les utilisateurs doivent-ils quitter le système avant que je puisse réinitialiser le mini-data warehouse ?

Non. Les utilisateurs peuvent continuer à travailler dans le système pendant la réinitialisation du mini-data warehouse. Cependant, ils ne pourront pas accéder aux états créés avec Financial Reporter tant que la réinitialisation ne sera pas terminée.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
