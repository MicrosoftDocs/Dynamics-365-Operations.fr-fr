---
title: FAQ sur les réinitialisations du mini-data warehouse
description: Cette rubrique fournit des réponses à quelques-unes des questions fréquemment posées sur les réinitialisations du mini-data warehouse.
author: jinniew
ms.date: 03/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 61c7047096f42e71cde5e9ba1ddc59785383795a
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714127"
---
# <a name="data-mart-resets-faq"></a>FAQ sur les réinitialisations du mini-data warehouse

Cette rubrique fournit des réponses à quelques-unes des questions fréquemment posées sur les réinitialisations du mini-data warehouse. Une réinitialisation du mini-data warehouse peut être un processus chronophage et, selon les circonstances, peut ne pas être la solution requise. Par conséquent, cette rubrique inclut des informations sur les circonstances dans lesquelles une réinitialisation du mini-data warehouse peut être utile, ainsi que sur les circonstances dans lesquelles il est peu probable qu’elle soit utile.

## <a name="what-is-a-data-mart-reset"></a>Qu’est-ce que la réinitialisation d’un mini-data warehouse ?

Une réinitialisation du mini-data warehouse désactivera les tâches d’intégration, supprimera toutes les données du mini-data warehouse, puis réactivera l’intégration.

Pour garantir que de anciennes données ne sont pas insérées, une réinitialisation du mini-data warehouse ne peut être démarrée qu’une fois les tâches existantes terminées. Si vous essayez de réinitialiser le mini-data warehouse avant que toutes les tâches ne soient terminées, vous pouvez recevoir un message tel que « La réinitialisation du mini-data warehouse n’a pas pu être traitée en raison d’une tâche active. Réessayez ultérieurement. »

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>Quand dois-je effectuer une réinitialisation d’un mini-data warehouse ?

Si une ou plusieurs des affirmations suivantes s’appliquent à votre situation, votre organisation peut bénéficier d’une réinitialisation du mini-data warehouse :

- **La base de données de l’application a été restaurée**
- **Vous avez ouvert un ticket de support** - Un ingénieur du support vous a demandé de réinitialiser le mini-data warehouse dans le cadre d’une étape de résolution des problèmes.
- **Grand pourcentage d’enregistrements périmés** - Lréinitialiseres enregistrements périmés ne justifient pas nécessairement une réinitialisation du mini-data warehouse. Des pourcentages élevés de données obsolètes peuvent dégrader les performances globales de génération et d’intégration de rapports et entraîner une utilisation supplémentaire de l’espace de la base de données. Nous vous recommandons d’effectuer une réinitialisation du magasin de données pour supprimer les données périmées lorsqu’il y a plus de 80 % de données périmées dans le magasin de données.
 
> [!NOTE]
> Le processus de réinitialisation d’un mini-data warehouse est affecté par le nombre de transactions de comptabilité et de budget dans votre base de données. Selon le nombre de transactions dans votre système, une réinitialisation du mini-data warehouse peut être effectuée en à peine 15 minutes, ou elle peut prendre jusqu’à quatre heures. Cependant, si votre réinitialisation prend plus de quatre heures, nous vous recommandons de contacter le support.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>Quand la réinitialisation d’un mini-data warehouse est-elle inappropriée ?

Voici certaines des circonstances dans lesquelles il est déconseillé de réinitialiser un mini-data warehouse :

- Vous rencontrez des problèmes de performances d’intégration de données.
- Votre intégration Financial Reporter n’est pas activée. 

    - Cela signifie que les données du grand livre ne sont plus synchronisées avec votre magasin de données Financial Reporting. Votre instance Financial Reporter n’obtient peut-être pas des chiffres à jour pour vos états financiers. Cela se produit généralement si vous n’avez pas utilisé Financial Reporter pendant une longue période.
    - Vous serez invité à activer l’intégration en réinitialisant le magasin de données. Vous pouvez continuer en sélectionnant **Oui**. Vous pouvez également choisir de réinitialiser le magasin de données ultérieurement. Une fois l’intégration activée, vos données de comptabilité sont à nouveau synchronisées dans Financial Reporter. 
- Vous rencontrez un schéma de réinitialisation récurrent pour l’une des raisons suivantes :

    - **Données manquantes ou inattendues dans le rapport** - Si vous remarquez que des données sont manquantes, ouvrez un ticket de support auprès de Microsoft pour examiner le format de l’état et les éventuels problèmes de synchronisation des données.
    - **État d’intégration bloqué** - Si vous remarquez que l’état de l’intégration est bloqué en cours d’exécution, cela peut être dû à un grand volume de transactions dans le système. Cet état se résoudra de lui-même. Cependant, si vous remarquez que le statut d’intégration est bloqué pendant plus de quatre heures, ouvrez un ticket de support auprès de Microsoft. 
   
## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Si je réinitialise le mini-data warehouse, vais-je perdre les états que j’ai déjà conçus ?

Non. Vos états sont stockés dans des tables SQL qui ne sont pas affectées par une réinitialisation du mini-data warehouse. Si vous craignez de perdre des états que vous avez conçus, vous pouvez sauvegarder les conceptions que vous ne voulez pas perdre. Pour sauvegarder les conceptions, ouvrez Report Designer et accédez à **Entreprise \> Entreprises \> Blocs élémentaires \> Exporter**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Tous les utilisateurs doivent-ils quitter le système avant que je puisse réinitialiser le mini-data warehouse ?

Non. Les utilisateurs peuvent continuer à travailler dans le système pendant la réinitialisation du mini-data warehouse. Cependant, ils ne pourront pas accéder aux états créés avec Financial Reporter tant que la réinitialisation ne sera pas terminée.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
