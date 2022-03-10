---
title: Paramétrer un modèle de configuration de produit
description: Cet article décrit les étapes de paramétrage et de création d’un modèle de configuration de produit.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 4051
ms.assetid: 00df5537-b148-4e32-a248-3e35876ad4e1
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dc9f46d91dc298a5c8babee2b370fea09f61741
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578222"
---
# <a name="set-up-a-product-configuration-model"></a>Paramétrer un modèle de configuration de produit

[!include [banner](../includes/banner.md)]

Cet article décrit les étapes de paramétrage et de création d’un modèle de configuration de produit.

| Tâche                                                        | Description                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Créer un produit générique.                                    | Permet de créer un produit générique depuis la liste **Produit générique**. Lancez le produit générique dans toutes les sociétés appropriées. Pour un produit générique utilisé comme version pour un modèle de configuration de produit ou comme sous-composant, **Configuration basée sur les contraintes** doit être sélectionné comme technologie de configuration, et la dimension de configuration doit être sélectionnée uniquement pour le groupe de dimensions de produit. |
| Créer des composants.                                          | Permet de créer des composants sur la page **Composants**. Les composants sont les éléments constitutifs d’un modèle de configuration de produit et peuvent être réutilisés dans plusieurs modèles de configuration de produit.                                                                                                                                                                                                                      |
| Créer des types d’attributs.                                     | Permet de créer des types d’attribut sur la page **Types d’attributs**. Les types d’attributs spécifient l’ensemble des types de données pour tous les attributs utilisés dans des modèles de configuration de produit. Les attributs dont la valeur est de type **Booléen**, **Texte** avec une liste fixe, et **Entier** avec des types de plage répertorient les valeurs disponibles lorsque vous configurez une variante de produit en fonction d’un modèle de configuration de produit.       |
| Créer un modèle de configuration de produit.                       | Permet de créez un modèle de configuration de produit sur la page **Nouveau modèle de configuration de produits**.                                                                                                                                                                                                                                                                                                              |
| Ajouter des attributs à un modèle de configuration de produit.            | Permet de créer un attribut sur l’organisateur **Attributs** sur la page **Détails du modèle de configuration de produits basée sur les contraintes**. Les attributs décrivent les fonctionnalités du modèle de configuration de produit.                                                                                                                                                                                                       |
| Ajouter des contraintes à un modèle de configuration de produit.           | Permet de créer des contraintes sur l’organisateur **Contraintes** sur la page **Détails du modèle de configuration de produits basée sur les contraintes**. Les contraintes sont des limites qu’un modèle de configuration de produit doit remplir. Les contraintes sont des contraintes d’expression ou des contraintes de table.                                                                                                                                 |
| Ajouter des sous-composants à un modèle de configuration de produit.         | Permet de créer des sous-composants sur l’organisateur **Sous-composants** sur la page **Détails du modèle de configuration de produits basée sur les contraintes**. Les sous-composants sont liés aux composants et sont associés aux articles qui représentent le sous-composant.                                                                                                                                                                       |
| Ajouter des besoins d’utilisateur à un modèle de configuration de produit.     | Les besoins d’utilisateur sont similaires aux sous-composants, mais ils ne font pas référence à un article. Envisagez les besoins d’utilisateur comme une nomenclature fantôme. Toutes les lignes de nomenclature ou opérations de gamme placées directement sous le besoin d’utilisateur seront réduites dans le composant parent.                                                                                                                       |
| Ajouter des lignes de nomenclature à un modèle de configuration de produit.             | Permet de créer des lignes de nomenclature sur l’organisateur **Lignes de nomenclature** sur la page **Détails du modèle de configuration de produits basée sur les contraintes**. Les lignes de nomenclature représentent une pièce requise pour construire une variante du produit.                                                                                                                                                                                                 |
| Ajouter des opérations de gamme à un modèle de configuration de produit.      | Permet de créer des opérations de gamme sur l’organisateur **Opérations de gamme** sur la page **Détails du modèle de configuration de produits basée sur les contraintes**. Les opérations de gamme représentent une étape dans une succession d’étapes nécessaires pour établir une variante du produit.                                                                                                                                                    |
| Créer une version active d’un modèle de configuration de produit. | Permet de créer une version active du modèle de configuration de produit sur la page **Versions**. Une version est la relation qui existe entre un modèle de configuration de produit et un produit générique. Un modèle de configuration de produit disposant d’une version active peut être configuré à partir d’une commande client, d’un devis de vente, d’une commande fournisseur, ou d’un ordre de fabrication.                                                               |
| Tester un modèle de configuration de produits.                         | Permet de tester le modèle de configuration de produit depuis la page **Détails du modèle de configuration de produits basée sur les contraintes** ou la page **Liste des modèles de configuration de produits**. Le fait de tester des modèles de configuration de produit simule le processus de configuration du modèle de produit qui se produit pendant le traitement des commandes.                                                                                                |
| Créer un modèle de modèle de configuration de produit.                | Permet de créer un modèle de configuration de produit sur la page **Modèles de configuration**. Un modèle de configuration inclut des valeurs pour les attributs du modèle de configuration de produit. Sélectionnez les valeurs d’attribut sur la page **Configurer la ligne**. Vous pouvez choisir de charger un modèle de modèle de configuration de produit pendant la configuration du modèle de produit.                                                   |
| Configurer un article.                                          | Les modèles de configuration de produit peuvent être configurés à partir d’une commande client, d’un devis de vente, d’une commande fournisseur, ou d’un ordre de fabrication.                                                                                                                                                                                                                                                                           |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]