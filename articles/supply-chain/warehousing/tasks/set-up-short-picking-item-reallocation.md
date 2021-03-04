---
title: Paramétrer la réaffectation des articles pour les prélèvements partiels
description: Cette rubrique décrit comment les magasiniers peuvent trouver rapidement d’autres emplacements si le stock n’est pas suffisant à l’emplacement où ils ont été redirigés.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e8f5c23f82e96145f411ec993f766a90137b5b8
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428243"
---
# <a name="set-up-short-picking-item-reallocation"></a>Paramétrer la réaffectation des articles pour les prélèvements partiels

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment les magasiniers peuvent trouver rapidement d’autres emplacements si le stock n’est pas suffisant à l’emplacement où ils ont été redirigés. 

Le processus de réaffectation est contrôlé par une **Exception de travail** et utilisé par le **manutentionnaire.**

Il est possible d’utiliser les processus de réallocation Automatique, Manuelle ou les deux :

- Réallocation automatique - Les directives d’emplacement sont utilisées pour déterminer si les marchandises sont disponibles à un autre emplacement. Si possible, le travail sera mis à jour et l’utilisateur de l’entrepôt sera dirigé vers un autre emplacement.
- Réallocation manuelle - Permet à l’utilisateur de l’entrepôt de sélectionner un ou plusieurs emplacements avec des quantités de marchandises non réservées. 
- Automatique et manuelle - Si le système n’est pas en mesure d’effectuer une réaffectation automatique et que des emplacements sont disponibles avec des quantités non réservées, l’utilisateur sera invité à sélectionner un emplacement.

## <a name="set-up-work-exceptions"></a>Définir des exceptions de travail
Il est possible de définir plusieurs exceptions de travail avec différentes stratégies de réaffectation des articles pour permettre au magasinier d’en choisir une selon les besoins de l’expédition qu’il traite.

Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Dans le **Volet de navigation**, accédez à **Gestion des entrepôts > Paramétrage > Travail > Exceptions de travail**.
2. Cliquez sur **Nouveau**. 
3. Dans le champ **Code d’exception de travail**, tapez une valeur. Ce sera le titre de cette exception . Par exemple, Prélèvement partiel manuel.
4. Tapez une valeur dans le champ **Description**. Ce sera une brève description de l’utilisation de cette exception. Par exemple, Prélèvement partiel - article non disponible.
5. Dans le champ **Type d’exception**, sélectionnez **Prélèvement partiel**.
6. Activez la case à cocher **Ajuster le stock**. Si cette option est sélectionnée, cela signifie que le stock est automatiquement ajusté sur 0 à l’emplacement de prélèvement partiel.
7. Dans le champ **Code type d’ajustement par défaut**, entrez ou sélectionnez une valeur. Par exemple, dans USMF, vous pouvez sélectionner **Supprimer Res Adj Out**. Chaque code de type d’ajustement contient quatre caractéristiques : nom, description, nom du journal de stock et **Supprimer les réservations**. Si **Supprimer les réservations** est activé, les réservations de la ligne de commande sélectionnée seront supprimées.  
8. Dans le champ **Réaffectation des articles**, sélectionnez une valeur, comme Manuelle. Si vous sélectionnez Manuel ou Automatique et manuel, le magasinier doit être autorisé à utiliser la réaffectation manuelle.

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Paramétrer un collaborateur pour utiliser la réaffectation manuelle des articles

Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Fermez la page.
2. Dans le **Volet de navigation**, accédez à **Gestion des entrepôts > Paramétrage > Agent**.
3. Cliquez sur **Modifier**.
4. Dans la liste, sélectionnez un collaborateur. Par exemple, Julia Funderburk.
5. Développez l’organisateur **Utilisateurs**.
6. Dans la liste, sélectionnez un **Identifiant utilisateur**. Par exemple, 24.
7. Développez l’organisateur **Travail**.
8. Sélectionnez **Oui** dans le champ **Autoriser la réaffectation manuelle des articles**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]