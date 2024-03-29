---
title: Paramétrer les règles et les paramètres pour le cross-docking et le réassort magasin
description: Cette procédure décrit les étapes pour créer des règles de réapprovisionnement.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 776defca4a9d2a860901efe9e8890fd11ec8ce7302c53dc1507cc77ff501aded
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753050"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a>Paramétrer les règles et les paramètres pour le cross-docking et le réassort magasin

[!include [banner](../includes/banner.md)]

Cette procédure décrit les étapes pour créer des règles de réapprovisionnement. Les règles de réapprovisionnement permettent de contrôler la distribution des produits dans les magasins lors de l’utilisation des procédures de cross-docking et de réassort magasin. Elles peuvent être paramétrées pour des magasins ou des groupes de magasins. Le poids défini pour chaque ligne d’une règle contrôle la manière dont les quantités de produits sont distribuées entre les magasins lors de l’utilisation des règles de réapprovisionnement comme méthode de distribution pour le cross-docking et le réassort magasin. La société fictive USRT sert d’exemple dans cette procédure.

1. Accédez à Règles de réapprovisionnement.
2. Cliquez sur Nouveau.
3. Dans le champ Règle de réapprovisionnement, saisissez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Enregistrer.
6. Cliquez sur Ajouter.
7. Dans la liste, marquez la ligne sélectionnée.
    * Vous pouvez sélectionner Hiérarchie des réapprovisionnements ou Canal comme type. La valeur contrôle si le nom sélectionné est une hiérarchie de canaux ou un canal spécifique.  Pour cet exemple, utilisez l’option Hiérarchie des réapprovisionnements.  
8. Dans le champ Nom, sélectionnez une valeur.
    * La valeur de poids par défaut est renseignée à partir du poids défini dans l’entrepôt.  Ce poids peut être utilisé pour la règle de réapprovisionnement ou vous pouvez saisir un nouveau poids dans le champ Poids.  
9. Dans le champ Poids, saisissez un nombre.
10. Cliquez sur Ajouter.
11. Dans la liste, marquez la ligne sélectionnée.
12. Dans le champ Type, sélectionnez « Canal ».
13. Saisissez ou sélectionnez une valeur dans le champ Nom.
14. Dans le champ Poids, saisissez un nombre.
15. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]