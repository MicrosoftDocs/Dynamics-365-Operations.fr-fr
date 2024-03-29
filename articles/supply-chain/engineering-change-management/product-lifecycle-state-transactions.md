---
title: États et transactions du cycle de vie du produit
description: Cet article explique comment contrôler les transactions autorisées pour chaque état du cycle de vie au fur et à mesure qu’un produit d’ingénierie parcourt son cycle de vie.
author: t-benebo
ms.date: 02/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcoResProductLifecycleStateChange
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dd9155f799c66e8297b93d8ffbeeced1acd14220
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867954"
---
# <a name="product-lifecycle-states-and-transactions"></a>États et transactions du cycle de vie du produit

[!include [banner](../includes/banner.md)]

Au fur et à mesure qu’un produit d’ingénierie parcourt son cycle de vie, il est important de pouvoir contrôler les transactions autorisées pour chaque état du cycle de vie. Par exemple, les produits qui ne sont pas encore dans un état mature ne doivent pas être mis sur une commande client. Sinon, si un produit atteint son état de fin de vie, vous pouvez vouloir contrôler l’afflux de ce produit.

Pour un produit d’ingénierie, les modifications apportées à l’état du cycle de vie sont liées aux versions d’ingénierie du produit. Par conséquent, l’état du cycle de vie du produit peut également être connecté à ses versions d’ingénierie. Lorsque l’état du cycle de vie du produit est connecté à une version d’ingénierie, vous pouvez utiliser l’état du cycle de vie pour contrôler les transactions autorisées pour la version d’ingénierie.

## <a name="create-and-manage-product-lifecycle-states"></a>Créer et gérer des états de cycle de vie des produits

Pour utiliser les états de cycle de vie des produits, accédez à **Gestion du changement d’ingénierie \> Configurer \> État du cycle de vie du produit**. Suivez ensuite l’une des procédures suivantes.

- Pour créer un état du cycle de vie, sélectionnez **Nouveau** dans le volet Actions, puis définissez les champs comme décrit dans les sous-sections suivantes.
- Pour modifier un état du cycle de vie existant, sélectionnez-la dans le volet de liste, sélectionnez **Modifier** dans le volet Actions, puis définissez les champs comme décrit dans les sous-sections suivantes.
- Pour supprimer un état du cycle de vie existante, sélectionnez-le dans le volet de liste, puis sélectionnez **Supprimer** sur le volet Actions.

> [!NOTE]
> Les produits d’ingénierie utilisent les mêmes états de cycle de vie que les produits standard (non d’ingénierie). Vous pouvez également ouvrir la page **État du cycle de vie du produit** décrite dans cet article en accédant à **Gestion des informations produit \> Configurer \> État du cycle de vie du produit**. Pour plus d’informations sur les états du cycle de vie des produits, pour les produits d’ingénierie et les produits standard, voir [Présentation de l’état du cycle de vie du produit](../pim/product-lifecycle.md).

### <a name="header"></a>En-tête

Définissez les champs suivants sur l’en-tête d’un état du cycle de vie de produit.

| Champ | Description |
|---|---|
| État | Permet d’entrer un nom pour l’état du cycle de vie d’un produit. |
| Description | Permet d’entrer une description de l’état du cycle de vie d’un produit. |

### <a name="general-fasttab"></a>Organisateur Général

Définissez les champs suivants dans l’organisateur **Général**.

| Champ | Description |
|---|---|
| Valeur par défaut lors du lancement dans une entité juridique | Pour les produits standard, définissez cette option sur *Oui* si cet état du cycle de vie doit être appliqué par défaut à tous les produits lors de leur première sortie. Définissez-le sur *Non* si cet état du cycle de vie sera appliqué manuellement ultérieurement.<p>Ce paramètre ne s’applique pas aux produits d’ingénierie. L’état du cycle de vie d’une version de produit d’ingénierie après sa création dans la société d’ingénierie est spécifié dans sa catégorie de modification technique. Lorsque le produit est remis à une société opérationnelle, l’état du cycle de vie du produit est copié. En d’autres termes, lorsqu’un produit d’ingénierie est mis à la disposition d’une entreprise opérationnelle, il a le même état de cycle de vie que celui de l’entreprise d’ingénierie. L’état du cycle de vie peut être écrasé dans l’entreprise opérationnelle.</p> |
| Est actif pour la planification | Définissez cette option sur *Oui* pour inclure les produits qui se trouvent dans cet état du cycle de vie dans les calculs aux niveaux de la planification principale et de la nomenclature. Définissez-le sur *Non* pour exclure les produits qui sont dans cet état de cycle de vie des calculs. |

### <a name="enabled-business-processes-fasttab"></a>Raccourci Processus d’entreprise activés

Utilisez le raccourci **Processus d’entreprise activés** pour contrôler quels processus d’entreprise disponibles peuvent être utilisés avec des produits dans l’état actuel du cycle de vie. Les processus répertoriés sur ce raccourci sont automatiquement trouvés de la manière suivante :

- La première fois que vous enregistrez un nouvel état de cycle de vie, la page charge les processus d’entreprise actuellement disponibles.
- Si vous ajoutez de nouveaux processus d’entreprise à votre système, vous pouvez mettre à jour la liste sur le raccourci **Processus d’entreprise activés** pour un état de cycle de vie existant en sélectionnant **Rechercher des mises à jour** sur le volet Actions.

Les champs suivants sont disponibles pour chaque processus répertorié sur le raccourci **Processus d’entreprise activés**.

| Champ | Description |
|---|---|
| Processus | Ce champ en lecture seule affiche le nom d’un processus d’entreprise existant. |
| Zone de traitement | Ce champ en lecture seule affiche le nom d’une zone de processus existant. |
| Police | Sélectionnez l’une des valeurs suivantes pour contrôler si et comment le processus actuel sera autorisé pour les produits qui se trouvent dans cet état de cycle de vie :<ul><li>**Activé** – Le processus d’entreprise est autorisé.</li><li>**Bloqué** – Le processus n’est pas autorisé. Si un utilisateur tente d’utiliser le processus sur un produit qui est dans cet état de cycle de vie, le système bloquera la tentative et affichera une erreur à la place. Par exemple, vous pouvez bloquer l’achat de produits en fin de vie.</li><li>**Activé avec avertissement** – Le processus est autorisé, mais un avertissement sera affiché. Par exemple, vous souhaiterez peut-être qu’un produit prototype soit placé sur un ordre de fabrication créé par le service Recherche et développement. Cependant, les autres services doivent savoir qu’ils ne doivent pas encore fabriquer le produit.</li></ul> |

Si vous ajoutez d’autres règles d’état du cycle de vie en tant que personnalisation, vous pouvez afficher ces règles dans l’interface utilisateur (IU) en sélectionnant **Actualiser les processus** dans le volet supérieur. Le bouton **Actualiser les processus** est disponible uniquement pour les administrateurs.

## <a name="lifecycle-states-for-released-products-and-product-variants"></a>États du cycle de vie des produits lancés et des variantes de produit

Pour un produit qui a des variantes (principal et variantes), le produit (principal) aura un état de cycle de vie et chacune des variantes peut également avoir un état de cycle de vie différent.

Pour des processus spécifiques, si la variante ou le produit est bloqué, le processus sera également bloqué. Plus précisément, pour déterminer si un processus est bloqué, le système effectuera les vérifications suivantes :

- Pour les produits contrôlés par l'ingénierie :
  - Si la version d'ingénierie actuelle est bloquée, bloquez le processus.
  - Si la variante actuelle est bloquée, bloquez le processus.
  - Si le produit lancé est bloqué, bloquez le processus.
- Pour les produits standards :
  - Si la variante actuelle est bloquée, bloquez le processus.
  - Si le produit lancé est bloqué, bloquez le processus.

Par exemple, supposons que vous ne souhaitiez vendre qu'une seule variante (rouge) d'un produit donné (t-shirt) et bloquer les ventes de toutes les autres variantes pour le moment. Vous pouvez l'implémenter en utilisant la configuration suivante :

- Attribuez au produit un état de cycle de vie qui autorise le processus. Par exemple, attribuez au produit t-shirt un état de cycle de vie *Vendable*, ce qui permet le processus d'affaires *Commande client*.
- Attribuez à la variante vendable un état de cycle de vie qui autorise le processus. Par exemple, attribuez également à la variante rouge un état de cycle de vie *Vendable*.
- Toutes les autres variantes se voient attribuer un autre état de cycle de vie où le processus est bloqué. Par exemple, attribuez à la variante blanche (et à toutes les autres variantes) un état de cycle de vie *Non vendable*, qui bloque le processus d'affaires *Commande client*.

## <a name="default-product-lifecycle-states"></a>États du cycle de vie du produit

L’état du cycle de vie par défaut d’une version d’ingénierie est spécifié par sa catégorie d’ingénierie. L’état sera défini par défaut lorsque vous créerez une nouvelle version d’ingénierie, y compris la première version d’un nouveau produit.

Lorsque vous créez un nouveau produit ou produit d’ingénierie, vous pouvez également définir l’état du cycle de vie par défaut en le spécifiant sur le modèle de produit lancé de la politique de lancement attribuée au produit.

Dans ce cas, il est possible que le produit ait un état de cycle de vie différent de celui de la version lorsque vous créez un nouveau produit d’ingénierie.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
