---
title: Quand réinitialiser un mini-Data Warehouse
description: Cette rubrique répertorie les circonstances qui peuvent être améliorées en réinitialisant un mini-Data Warehouse et les circonstances dans lesquelles la réinitialisation de votre mini-Data Warehouse n'est probablement pas utile.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 71324d4aa2d20dd6ae4729412a017d130ab0144f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563729"
---
# <a name="when-to-reset-a-data-mart"></a>Quand réinitialiser un mini-Data Warehouse

La réinitialisation d'un mini-Data Warehouse peut prendre beaucoup de temps. Selon les circonstances, cette action peut ne pas être la solution nécessaire. Cette rubrique répertorie les circonstances qui peuven être améliorées en réinitialisant un mini-Data Warehouse, ainsi que les circonstances dans lesquelles la réinitialisation de votre mini-Data Warehouse n'est probablement pas utile.  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a>Quand devez-vous effectuer une réinitialisation d'un mini-Data Warehouse ?
Tenez compte des questions suivantes avant de réinitialiser un mini-Data Warehouse. Une réponse affirmative à une ou plusieurs questions peut indiquer que votre organisation peut bénéficier de la réinitialisation du mini-Data Warehouse.

- La base de données de l'application a été restaurée, mais la base de données du mini-data warehouse ne l'a pas été.
- Vous voyez des données incorrectes pour une période comptable, ce qui n'est pas le résultat d'un problème de conception du rapport.
- Vous voyez des données incorrectes pour une période comptable et les enregistrements sont répertoriés sous Tentatives d'intégration dans la page **Statut d'intégration** du concepteur de rapports (démarrez le concepteur de rapports et sélectionnez **Outils > Statut d'intégration**).
- Vous avez ouvert un incident de support et un ingénieur du support vous a demandé de réinitialiser le mini-data warehouse dans le cadre d'une étape de résolution des problèmes.
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a>Quand n'est-il pas approprié de réinitialiser un mini-data warehouse ?
Il est déconseillé de réinitialiser un mini-data warehouse dans certains circonstances. En voici quelques exemples. 

- Chaque fois que la raison n'est pas répertoriée dans cette rubrique.
- Vous rencontrez des problèmes de performances associés à une synchronisation de données. Dans ce cas, la réinitialisation du mini-data warehouse ne sera probablement pas utile.
- Si vous avez un modèle de réinitialisation récurrent pour l'une des raisons suivantes : 
  - **Données manquantes** : tout d'abord, éliminez les problèmes de conception de rapport et les problèmes de temps de synchronisation des données ; par exemple, vous observez que la carte de faits n'a pas été exécutée depuis la validation des données manquantes.
  - **État d'intégration bloqué** : si l'intégration est lente ou semble bloquée, la réinitialisation du mini-data warehouse ne résoudra probablement pas le problème.
  - **Les tentatives de réinitialisation ont échoué** : si plusieurs tentatives de réinitialisation ont été effectuées et ont échoué en raison de données manquantes, nous vous recommandons d'ouvrir un incident de support et d'analyser votre situation avec l'aide d'un ingénieur du support avant de tenter de réinitialiser à nouveau le mini-data warehouse.
  - **Enregistrements périmés** : les enregistrements périmés ne justifient pas nécessairement la réinitialisation du mini-data warehouse. Si vous disposez d'un ensemble de données volumineux, le processus de réinitialisation mettra du temps à s'exécuter, mais il est peu probable qu'il se traduise par une amélioration.
 
## <a name="what-a-data-mart-reset-does-not-do"></a>Ce qu'une réinitialisation du mini-data warehouse ne fait pas  
- Une réinitialisation ne démarre que lorsque les tâches existantes sont terminées. Cela garantit que les anciennes données ne sont pas insérées. À ce stade, vous pouvez voir un message tel que « La réinitialisation du mini-data warehouse n'a pas pu être traitée en raison d'une tâche active. Réessayez ultérieurement. »
- La réinitialisation désactivera les tâches d'intégration et supprimera toutes les données du mini-data warehouse. L'intégration est réactivée.

> [!NOTE]
> Les points suivants spécifient deux choses que la réinitialisation d'un mini-data warehouse *ne fait pas*. <br>
> - Les réinitialisations n'effacent pas les conceptions de rapport. <br>
> - Les réinitialisations n'effacent pas les données de la société ou les données de l'utilisateur, sauf si elles sont sélectionnées.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]