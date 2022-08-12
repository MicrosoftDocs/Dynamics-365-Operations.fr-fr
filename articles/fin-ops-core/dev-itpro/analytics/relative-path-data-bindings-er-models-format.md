---
title: Utiliser un chemin d’accès relatif dans les liaisons de données des modèles et des formats ER
description: L’outil de génération d’états électroniques vous permet de définir des structures de format électronique, puis de décrire la manière dont ces structures doivent être remplies.
author: NickSelin
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: be2c0f921fde13598685553ea01bfcf3f8255362
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108669"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a>Utiliser un chemin d’accès relatif dans les liaisons de données des modèles et des formats ER

[!include[banner](../includes/banner.md)]

L’outil de génération d’états électroniques (ER) permet aux utilisateurs de définir des structures de format électronique, puis de décrire la manière dont ces structures doivent être remplies à l’aide des données et ses algorithmes existants dans l’application. Pour plus d’informations, voir [Créer des configurations de génération d’états électroniques (ER)](electronic-reporting-configuration.md). Pour spécifier le flux de données pour extraire les données de finances et d’opérations et l’utiliser pour générer un document électronique, vous devez effectuer les opérations suivantes :

- Lier les sources de données configurées aux éléments du modèle de données conçu pour le domaine. La structure du modèle et les sources de données sélectionnées peuvent faire partie d’une structure hiérarchique complexe. Pour cette raison, les liaisons finales peuvent être assez étendues et contenir de nombreux éléments de différents types (par exemple, des relations, des tables et des méthodes). Les liaisons peuvent devenir moins lisibles et très complexes à examiner et comprendre, en particulier pour les non propriétaires. 
- Liez les éléments de modèle de données avec des composants de format pour définir les données qui seront renseignées à partir du modèle de données dans la sortie du format généré.

Pour faciliter l’utilisation des concepteurs de mise en correspondance ER, la fonction de [chemin d’accès relatif](er-formula-language.md#relative-path) a été introduite. Par défaut, l’option de représentation du chemin d’accès relatif est activée pour toute nouvelle instance de l’application où l’expérience de conception ER est activée (Microsoft Dynamics 365 Finance, Microsoft Regulatory Configuration Service). Nous avons implémenté le paramètre de chemin relatif afin que les utilisateurs puissent continuer à utiliser le chemin d’accès complet avec cette présentation des liaisons ER.

[![Paramètres utilisateur.](./media/relative-path-01.png)](./media/relative-path-01.png)

 
Lorsque le paramètre de chemin d’accès relatif est activé, un seul caractère @ remplace le chemin d’accès vers l’élément parent dans la liaison de l’élément du modèle actuel. Le chemin d’accès complet de la liaison devient plus court, ce rend toute la mise en correspondance plus lisible et facile à comprendre. Dans la plupart des cas, aucun défilement supplémentaire n’est requis dans le concepteur ER pour afficher toutes les liaisons du modèle de données.

[![Concepteur de mise en correspondance de modèle.](./media/relative-path-02.png)](./media/relative-path-02.png)
 
Lorsque vous commencez à créer une nouvelle expression ER, vous devez entrer un seul caractère pour définir une liaison vers un champ de l’élément parent.

[![Concepteur de formule.](./media/relative-path-03.png)](./media/relative-path-03.png)
 
Lorsque vous décidez de modifier la source de données de l’élément de modèle parent, avec le chemin d’accès absolu, vous devez manuellement re-lier cet élément de modèle, ainsi que tous les éléments imbriqués, avec une nouvelle source de données. Lorsque l’utilisation du chemin d’accès relatif est activée, si vous sélectionnez une nouvelle source de données à lier à un élément parent, vous bénéficiez d’une option pour re-lier automatiquement en un seul clic tous les éléments imbriqués de cet élément parent.

[![Remplacer le message de chemin existant.](./media/relative-path-04.png)](./media/relative-path-04.png)
 
Si vous confirmez la nouvelle liaison des éléments imbriqués, le nouvel élément parent sera placé dans le chemin de chaque élément imbriqué contenant l’élément parent existant.
Cette fonction n’empêche pas la compatibilité ascendante de la structure ER. Toutes les configurations ER précédemment conçues fonctionneront avec cette nouvelle fonction, et aucune mise à niveau ou conversion n’est requise.

> [!NOTE]
> Tous les modifications qui sont introduites par la modification en masse des liaisons des éléments imbriqués dans les mises en correspondance des modèles sont correctement enregistrées dans une configuration delta (un suivi des modifications). Cela permet aux clients de refonder leur version dérivée des mises en correspondance de modèles sur n’importe quelle nouvelle version de base qui a été modifiée à l’aide de cette nouvelle fonction.

## <a name="additional-resources"></a>Ressources supplémentaires

[Langage des formules ER](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

