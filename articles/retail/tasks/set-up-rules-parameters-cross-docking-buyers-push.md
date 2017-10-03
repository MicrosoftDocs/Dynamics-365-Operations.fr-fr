--- 
title: " Paramétrer les règles et les paramètres pour le cross-docking et le réassort magasin"
description: "Cette procédure décrit les étapes pour créer des règles de réapprovisionnement."
author: josaw1
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 946f648eccd4ba856cc5a77d031add359fa23618
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a> Paramétrer les règles et les paramètres pour le cross-docking et le réassort magasin

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure décrit les étapes pour créer des règles de réapprovisionnement. Les règles de réapprovisionnement permettent de contrôler la distribution des produits dans les magasins lors de l'utilisation des procédures de cross-docking et de réassort magasin. Elles peuvent être paramétrées pour des magasins ou des groupes de magasins. Le poids défini pour chaque ligne d'une règle contrôle la manière dont les quantités de produits sont distribuées entre les magasins lors de l'utilisation des règles de réapprovisionnement comme méthode de distribution pour le cross-docking et le réassort magasin. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Règles de réapprovisionnement.
2. Cliquez sur Nouveau.
3. Dans le champ Règle de réapprovisionnement, saisissez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Enregistrer.
6. Cliquez sur Ajouter.
7. Dans la liste, marquez la ligne sélectionnée.
    * Vous pouvez sélectionner Hiérarchie des réapprovisionnements ou Canal comme type. La valeur contrôle si le nom sélectionné est une hiérarchie de canaux ou un canal spécifique.  Pour cet exemple, utilisez l'option Hiérarchie des réapprovisionnements.  
8. Dans le champ Nom, sélectionnez une valeur.
    * La valeur de poids par défaut est renseignée à partir du poids défini dans l'entrepôt.  Ce poids peut être utilisé pour la règle de réapprovisionnement ou vous pouvez saisir un nouveau poids dans le champ Poids.  
9. Dans le champ Poids, saisissez un nombre.
10. Cliquez sur Ajouter.
11. Dans la liste, marquez la ligne sélectionnée.
12. Dans le champ Type, sélectionnez « Canal ».
13. Saisissez ou sélectionnez une valeur dans le champ Nom.
14. Dans le champ Poids, saisissez un nombre.
15. Cliquez sur Enregistrer.

