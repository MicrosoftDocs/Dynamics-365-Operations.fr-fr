---
title: Gestion des modifications d’ingénierie - FAQ
description: Cet article fournit des réponses aux questions fréquemment posées sur la fonction de gestion des modifications d’ingénierie.
author: t-benebo
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-25
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 16d29fa6485bae866a5209a855dfb928e8bc4783
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870780"
---
# <a name="engineering-change-management-faq"></a>Gestion des modifications d’ingénierie - FAQ

[!include [banner](../includes/banner.md)]

Cet article fournit des réponses aux questions fréquemment posées sur la fonction de gestion des modifications d’ingénierie.

## <a name="should-i-track-the-version-in-transactions"></a>Dois-je suivre la version dans les transactions ?

Lorsque vous créez une catégorie de modification technique, les **Détails de la catégorie de produits d’ingénierie** page fournit une option nommée **Suivre la version dans les transactions**. Quel est ce paramètre et que fait-il ?

- Si vous définissez l’option **Suivre la version dans les transactions** sur *Oui*, le champ **Groupe de dimensions** sera filtré de manière à afficher uniquement les groupes de dimensions dont la version est une dimension active.
- Si vous définissez l’option **Suivre la version dans les transactions** sur *Non*, le champ **Groupe de dimensions** sera filtré de manière à afficher uniquement les groupes de dimensions dont la version n’est **pas** une dimension active.

### <a name="if-you-track-the-version-in-transactions"></a>Si vous suivez la version dans les transactions ?

Pour les catégories d’ingénierie dans lesquelles vous avez sélectionné un groupe de dimensions où la version est une dimension active, vous effectuerez le suivi des versions dans les transactions pour les produits de cette catégorie. Dans ce cas, le produit d’ingénierie sera le produit générique et chaque version du produit sera une variante qui utilise la dimension de la version. D’autres dimensions peuvent être utilisées avec la dimension de la version.

Dans ce cas, chaque version d’ingénierie sera traitée comme une variante dans tous les processus. Par conséquent, si vous avez une variante spécifique dans une transaction (afin de déterminer quelle variante a été vendue ou achetée), vous devez gérer le stock pour chaque version, et la planification générale planifiera l’approvisionnement pour chaque version, et ainsi de suite. Si vous retirez une version du marché, vous devez ajuster manuellement ses dates de début et de fin de validité afin qu’elles reflètent le changement. Vous devez également gérer votre stock pour vous assurer que vous n’avez pas de versions d’articles inutilisées dans vos entrepôts.

Bien que cette option nécessite plus d’efforts de gestion, nous la recommandons si vous avez besoin d’un niveau de traçabilité élevé des versions spécifiques utilisées dans chaque transaction.

### <a name="if-you-dont-track-the-version-in-transactions"></a>Vous ne suivez pas la version dans les transactions ?

Pour les catégories d’ingénierie dans lesquelles vous avez sélectionné un groupe de dimensions où la version n’est **pas** une dimension active, vous n’allez **pas** effectuer le suivi des versions dans les transactions pour les produits de cette catégorie. Dans ce cas, si vous n’utilisez aucune autre dimension, le produit d’ingénierie sera un produit distinct. Le produit sera toujours versionné et vous pourrez gérer les informations de versions spécifiques (par exemple, la nomenclature\[BOM] et la gamme), mais vous ne pourrez pas retracer quelle version spécifique a été utilisée dans chaque transaction. Les dates de début et de fin de validité indiquent la validité de chaque version.

Cette option est beaucoup plus facile à gérer, car si vous souhaitez passer d’une version à une autre, il vous suffit d’apporter les modifications requises selon un ordre de modification, puis de mettre à jour les dates de début et de fin de validité dans la version d’ingénierie. Les processus de production récupèrent ensuite la nomenclature et la gamme requises pour le produit (et sa version spécifique).

La plupart des organisations choisissent cette option car elle fournit une gestion des versions et des modifications, mais elle n’ajoute pas la surcharge supplémentaire de suivi de la version dans chaque transaction, dans l’inventaire et pendant la planification générale.

## <a name="which-fields-are-copied-from-the-released-item-template"></a>Quels champs sont copiés du modèle d’article lancé ?

Lorsqu’une société d’ingénierie crée un produit d’ingénierie, ce produit est créé en tant que produit lancé dans l’entreprise d’ingénierie. Le produit lancé qui est créé est basé sur le *modèle d’article publié*. (Le modèle d’article lancé est lui-même un produit lancé existant.) Le modèle d’article lancé est également utilisé lorsque le produit est lancé dans une société opérationnelle. Dans chaque cas, le modèle d’article lancé définit la plupart des valeurs de champ pour le produit lancé, et ces valeurs proviennent de la page **Détails du produit publié**.

Les tableaux suivants présentent les champs copiés au cours de ces processus.

| Organisateur | Champs copiés lors de la création du produit dans la société d’ingénierie | Champs copiés lors du lancement dans une société opérationnelle |
|---|---|---|
| **Général(e)** | Tous les champs de la section **Administration** | Les mêmes champs qui sont copiés pour la société d’ingénierie |
| **Achats** | Tous les champs | Tous les champs sauf **Unité** |
| **Vendre** | Tous les champs des sections suivantes : **Commande client**, **Administration**, **Imposition**, **Mise à jour des prix**, **Prix de vente de base**, **Frais**, **Remises**, et **Produit alternatif** | Les mêmes champs qui sont copiés pour la société d’ingénierie, sauf **Unité** |
| **Commerce extérieur** | Tous les champs | Tous les champs |
| **Gérer le stock** | Tous les champs et sections *sauf* **Dimensions physiques** et **Poids variable** | Les mêmes champs qui sont copiés pour la société d’ingénierie, sauf **Unité** |
| **Ingénieur**, **Plan**, **Gérer les coûts**, **Gérer des projets**, **Dimensions financières**, et **Entrepôt** | Tous les champs | Tous les champs sauf **Unité de nomenclature** |
| **Variantes de produit** | Tous les champs de la section **Variante de produit par défaut** | Les mêmes champs qui sont copiés pour la société d’ingénierie |

En plus des champs affichés dans le tableau précédent, tous les paramètres de commande par défaut sont copiés à partir du modèle d’article lancé, à la fois lorsque le produit est créé dans la société d’ingénierie et lorsqu’il est lancé dans une société opérationnelle. (Pour afficher les paramètres de commande par défaut pour un modèle d’article lancé, ouvrez a page **Détails des produits lancés**, puis, dans le volet Actions, sur l’onglet **Gérer le stock**, sélectionnez **Paramètres de commande par défaut** .)

> [!NOTE]
>
> - L’unité est définie par défaut à partir du modèle.
> - Pour les détaillants qui utilisent la fonctionnalité Dynamics 365 Commerce, lors de l’attribution d’une catégorie de vente au détail à un produit, la catégorie de vente au détail applique des valeurs par défaut à de nombreux champs au niveau du produit lancé. Ces valeurs par défaut remplacent les valeurs par défaut qui ont peut-être déjà été définies par le modèle ou copiées depuis l’étude technique.

## <a name="should-i-create-a-separate-legal-entity-for-engineering-products-or-use-an-existing-legal-entity"></a>Dois-je créer une entité juridique distincte pour les produits d’ingénierie ou utiliser une entité juridique existante ?

Les exigences de votre entreprise déterminent si vous devez créer une nouvelle entité juridique pour les produits d’ingénierie.

En créant une société d’ingénierie distincte, vous pouvez séparer les données d’ingénierie, puis ajouter les modifications nécessaires pour vos entreprises opérationnelles locales. De cette façon, vous pouvez atteindre les objectifs suivants :

- Garder une entité distincte où les produits d’ingénierie sont créés et gérés.
- Empêcher les produits d’ingénierie d’apparaître avec le reste de vos produits lancés jusqu’à ce qu’ils soient prêts et commercialisés.
- Distinguer clairement les données dictées par l’ingénierie et les données locales.

En revanche, vous devriez probablement utiliser une entité juridique existante en tant que société d’ingénierie si les conditions suivantes s’appliquent à vous :

- Vous n’avez qu’une seule entité juridique dans votre système et / ou vous n’avez pas besoin d’une séparation claire entre les produits en cours de conception.
- Vous ne souhaitez pas dupliquer certaines données, telles que les groupes de ressources, les ressources, les opérations et (peut-être) les sites.

## <a name="what-is-the-nomenclature-for-engineering-versions-and-variants"></a>Quelle est la nomenclature des versions d’ingénierie et des variantes ?

La nomenclature des produits d’ingénierie et des variantes de produits fonctionne de la manière suivante :

- Pour le produit d’ingénierie (c’est-à-dire le produit distinct si aucune dimension n’est utilisée, ou le produit générique si une dimension est utilisée), la nomenclature de la règle numérique est définie dans la catégorie de produit d’ingénierie. Là, vous avez la possibilité d’utiliser une séquence de nombres, des constantes de texte et des noms et valeurs d’attribut.
- Pour chaque variante d’un produit d’ingénierie (si votre produit d’ingénierie est un produit générique, les variantes sont configurées dans la catégorie de produit d’ingénierie où vous spécifiez le groupe de dimensions), la nomenclature de la règle numérique pour chaque variante est définie dans le groupe de dimensions. Dans ce cas, vous pouvez utiliser l’ID produit du maître, ainsi que les valeurs et noms de dimension.
