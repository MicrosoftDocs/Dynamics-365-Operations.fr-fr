---
title: Configurer les règles de répartition des tâches
description: Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs.
author: maertenm
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47747cba7f83d0b43a284750cff232824e00053a
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982404"
---
# <a name="set-up-segregation-of-duties"></a>Configurer les règles de répartition des tâches

[!include [banner](../../includes/banner.md)]

Vous pouvez configurer des règles sur des tâches séparées qui doivent être effectuées par les utilisateurs. Ce concept est appelé répartition des tâches. Par exemple, vous ne souhaitez peut-être pas que cela soit la même personne qui accuse réception des marchandises et qui traite le paiement au fournisseur. La répartition des tâches vous aide à réduire le risque de fraude et également à détecter des erreurs ou des irrégularités. Vous pouvez également utiliser la répartition des tâches pour appliquer des stratégies de contrôle internes. Appliquez la procédure suivante pour créer une règle. Vous devez être administrateur système pour exécuter la procédure. La société fictive de démonstration utilisée pour créer cette procédure est DAT. 

1. Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Répartition des tâches > Règles de répartition des tâches**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Nom**, saisissez une valeur pour la règle.
4. Dans le champ **Première responsabilité**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Sélectionnez la première tâche qui est contrôlée par la règle.
6. Dans le champ **Deuxième responsabilité**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. 
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Sélectionnez la deuxième tâche qui est contrôlée par la règle.
10. Dans le champ **Gravité**, sélectionnez une option. Sélectionnez la gravité du risque qui se produit lorsqu'un même utilisateur ou rôle réalise les deux tâches.  
11. Dans le champ **Risque de sécurité**, tapez une valeur. Entrez une description du risque de sécurité.  
12. Dans le champ **Atténuation de sécurité**, tapez une valeur. Entrez une description des actions que vous prenez pour atténuer le risque de sécurité. Par exemple, vous pouvez atténuer le risque en conduisant des examens plus détaillés du processus, en conduisant une révision décisionnelle mensuelle, ou en partageant des ressources avec d'autres départements.     
13. Cliquez sur **Enregistrer**.

