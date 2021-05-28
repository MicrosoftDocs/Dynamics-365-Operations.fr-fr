---
title: Quand réinitialiser un mini-Data Warehouse
description: Cette rubrique répertorie les circonstances qui peuvent être améliorées en réinitialisant un mini-Data Warehouse et les circonstances dans lesquelles la réinitialisation de votre mini-Data Warehouse n’est probablement pas utile.
author: jinniew
ms.date: 05/06/2021
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
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2021
ms.locfileid: "5988990"
---
# <a name="when-to-reset-a-data-mart"></a>Quand réinitialiser un mini-Data Warehouse

La réinitialisation d’un mini-Data Warehouse peut prendre beaucoup de temps. Selon les circonstances, cette action peut ne pas être la solution nécessaire. Cette rubrique répertorie les circonstances qui peuven être améliorées en réinitialisant un mini-Data Warehouse, ainsi que les circonstances dans lesquelles la réinitialisation de votre mini-Data Warehouse n’est probablement pas utile.  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a>Quand dois-je effectuer une réinitialisation d’un mini-Data Warehouse ?
Tenez compte des questions suivantes avant de réinitialiser un mini-Data Warehouse. Une réponse affirmative à une ou plusieurs questions peut indiquer que votre organisation peut bénéficier de la réinitialisation du mini-Data Warehouse.

- La base de données de l'application a-t-elle été restaurée ?
- Si vous avez ouvert un incident de support et qu'un ingénieur du support vous a demandé de réinitialiser le mini-data warehouse dans le cadre d’une étape de résolution des problèmes.
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a>Quand n’est-il pas approprié de réinitialiser un mini-data warehouse ?
Il est déconseillé de réinitialiser un mini-data warehouse dans certains circonstances. En voici quelques exemples. 

- Vous rencontrez des problèmes de performances associés à une synchronisation de données. 
- Si vous avez un modèle de réinitialisation récurrent pour l’une des raisons suivantes : 
  - **Données manquantes** 
  - **État d'intégration bloqué** 
  - **Enregistrements périmés** : les enregistrements périmés ne justifient pas nécessairement la réinitialisation du mini-data warehouse. Si vous disposez d’un ensemble de données volumineux, le processus de réinitialisation mettra du temps à s’exécuter, mais il est peu probable qu’il se traduise par une amélioration.
 
## <a name="what-is-a-data-mart-reset"></a>Qu'est-ce que la réinitialisation d'un mini-data warehouse ?
- Une réinitialisation ne démarre que lorsque les tâches existantes sont terminées. Cela garantit que les anciennes données ne sont pas insérées. À ce stade, vous pouvez voir un message tel que « La réinitialisation du mini-data warehouse n’a pas pu être traitée en raison d’une tâche active. Réessayez ultérieurement. »
- La réinitialisation désactivera les tâches d’intégration et supprimera toutes les données du mini-data warehouse. L’intégration est réactivée.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Si je réinitialise le mini-data warehouse, vais-je perdre les rapports que j'ai déjà conçus ? 
Non, vos rapports sont stockés dans des tables SQL qui ne sont pas affectées par une réinitialisation du mini-data warehouse. Si vous craignez de perdre des rapports que vous avez conçus, vous pouvez sauvegarder les conceptions que vous ne voulez pas perdre. Pour les sauvegarder, ouvrez le Concepteur de rapports et accédez à **Entreprise > Entreprises> Blocs élémentaires > Exporter**.
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a>Est-il nécessaire que tous les utilisateurs quittent le système pour réinitialiser le mini-data warehouse ?
Non, les utilisateurs peuvent continuer à travailler dans le système pendant la réinitialisation du mini-data warehouse. Cependant, ils ne pourront pas accéder aux rapports créés avec Financial Reporter tant que la réinitialisation ne sera pas terminée. 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
