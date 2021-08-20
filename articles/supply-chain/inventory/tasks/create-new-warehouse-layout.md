---
title: Créer une structure d’entrepôt
description: Cette rubrique décrit comment paramétrer les informations pour les emplacements d’un entrepôt.
author: perlynne
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7882d0eee1ff599ade2dacc27edaf53dc149b27f53bfe9ba490bf53fd9399a97
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759573"
---
# <a name="create-a-new-warehouse-layout"></a>Créer une structure d’entrepôt

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment paramétrer les informations pour les emplacements d’un entrepôt. Cela s’applique uniquement aux entrepôts créés à l’aide de « l’entreposage de base » dans le module Gestion des stocks, pas aux entrepôts créés dans le module Gestion des entrepôts. Vous pouvez utiliser cette procédure dans la société USMF fictive ou utiliser vos propres données.


## <a name="set-the-default-location-capacity"></a>Définir la capacité d’emplacement par défaut
1. Dans le volet de navigation, allez dans **Modules > Gestion des stocks > Paramétrage > Paramètres de gestion des stocks et des entrepôts**.
2. Cliquez sur l’onglet **Emplacements**.
3. Entrez un chiffre dans le champ **Largeur standard**.
4. Entrez un chiffre dans le champ **Profondeur standard**.
5. Entrez un chiffre dans le champ **Hauteur standard**.
6. Sélectionnez **Enregistrer**.
7. Fermez la page.

## <a name="define-the-location-name-format"></a>Définir le format du nom d’emplacement
1. Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Paramétrage > Décomposition du stock > Entrepôts**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Entrepôts**, saisissez une valeur.
4. Tapez une valeur dans le champ **Nom**.
5. Dans le champ **Site**, sélectionnez l’enregistrement souhaité dans le champ de recherche.
6. Activez ou désactivez l’extension de la section **Noms d’emplacement**. Les options de cette section définissent le format par défaut pour les noms d’emplacement. Dans notre exemple, le numéro d’allée, le nombre de rayon et le nombre d’étagère sont inclus.  
7. Définissez l’option **Inclure allée** sur **Oui**.
8. Définissez l’option **Inclure rayon** sur **Oui**. 
9. Tapez une valeur pour le rayon dans le champ **Format**.
10. Définissez l’option **Inclure étagère** sur **Oui**.
11. Tapez une valeur pour l’étagère dans le champ **Format**.

## <a name="define-warehouse-locations"></a>Définir les emplacements des entrepôts
1. Cliquez sur **Entrepôt** dans le volet Actions.
2. Sélectionnez **Assistant Emplacement**.
3. Sélectionnez **Suivant**.
4. Annuler la sélection de l’option **Quais d’expédition**
5. Annuler la sélection de l’option **Emplacements de stockage en gros**
6. Sélectionnez **Suivant** jusqu’à arriver à l’option permettant de sélectionner **Terminer**.
7. Fermez la page.
8. Actualisez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]