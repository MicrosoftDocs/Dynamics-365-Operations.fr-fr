---
title: Configurer les règles de répartition des tâches
description: Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68e1a4419eaa11a59e1b634deb8e76a2bb9b6fdf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "318785"
---
# <a name="set-up-segregation-of-duties"></a>Configurer les règles de répartition des tâches

[!include [task guide banner](../../includes/task-guide-banner.md)]

Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs. Ce concept est appelé répartition des tâches. Par exemple, vous ne souhaitez peut-être pas que cela soit la même personne qui accuse réception des marchandises et qui traite le paiement au fournisseur. La répartition des tâches vous aide à réduire le risque de fraude et également à détecter des erreurs ou des irrégularités. Vous pouvez également utiliser la répartition des tâches pour appliquer des stratégies de contrôle internes. Appliquez la procédure suivante pour créer une règle. Vous devez être administrateur système pour exécuter la procédure. La société fictive de démonstration utilisée pour créer cette procédure est DAT. 

1. Accédez à Administration système > Sécurité > Répartition des tâches > Règles de répartition des tâches.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
    * Entrer un nom pour la règle.  
4. Dans le champ Première responsabilité, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la première tâche qui est contrôlée par la règle.  
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Dans le champ Deuxième responsabilité, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la deuxième tâche qui est contrôlée par la règle.  
9. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
10. Dans le champ Gravité, sélectionnez une option.
    * Sélectionnez la gravité du risque qui se produit lorsqu'un même utilisateur ou rôle réalise les deux tâches.  
11. Dans le champ Risque de sécurité, tapez une valeur.
    * Entrez une description du risque de sécurité.  
12. Dans le champ Atténuation de sécurité, tapez une valeur.
    * Entrez une description des actions que vous prenez pour atténuer le risque de sécurité. Par exemple, vous pouvez atténuer le risque en conduisant des examens plus détaillés du processus, en conduisant une révision décisionnelle mensuelle, ou en partageant des ressources avec d'autres départements.  
13. Cliquez sur Enregistrer.

