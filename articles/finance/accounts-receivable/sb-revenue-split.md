---
title: Modèles de répartition des produits dans Facturation de l’abonnement
description: Cette rubrique explique comment configurer des modèles de répartition des produits pour les articles vendus sous forme d’offres groupées.
author: JodiChristiansen
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 5c2eb6c8e18770eb149c445f662ab7a90aad81a7
ms.sourcegitcommit: 367e323bfcfe41976e5d8aa5f5e24a279909d8ac
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2022
ms.locfileid: "8660453"
---
# <a name="revenue-split-templates-in-subscription-billing"></a>Modèles de répartition des produits dans Facturation de l’abonnement

Utilisez la page **Modèle de répartition des produits** pour configurer des modèles de répartition des produits. La répartition des produits se compose d’un article parent qui a des articles enfants. Ce type d’article est souvent vendu aux clients sous la forme d’un seul article ou d’une offre groupée.

Par exemple, un article informatique peut être créé de la manière suivante :

- **Article parent :** Abonnement Argent
- **Articles (enfants) de Ligne :**

    - Support
    - Maintenance
    - Licence

Quand vous créez un article parent, gardez à l’esprit les restrictions suivantes :

- Un article ne peut être spécifié comme article parent qu’une seule fois.
- L’article parent peut être sélectionné comme article enfant dans le même modèle.
- Un modèle valide nécessite au moins un article enfant.
- Un article peut être spécifié comme article enfant pour plusieurs articles d’offres groupées.
- Chaque relation parent-enfant doit être unique.

## <a name="create-a-parent-item-that-has-child-items"></a>Créer un article parent qui a des articles enfants

Pour créer un article parent contenant des articles enfants, procédez comme suit.

1. Sur la page **Modèle de répartition des produits**, sélectionnez **Nouveau**.
1. Dans le champ **Article parent**, sélectionnez un article parent. Le champ **Numéro de variante** est mis à jour automatiquement. Vous pouvez modifier la valeur comme vous le voulez.
1. Dans le champ **Méthode de répartition**, sélectionnez une méthode de répartition.
1. Dans la liste **Articles de composant**, sélectionnez **Ajouter** pour ajouter des articles enfants.
1. Si vous avez sélectionné **Pourcentage** dans le champ **Méthode de répartition**, spécifiez un pourcentage dns le champ **Pourcentage**.

    - Si vous avez sélectionné **Montant égal** dans le champ **Méthode d’attribution**, le champ **Pourcentage** est automatiquement mis à jour afin que chaque article ait un pourcentage égal.
    - Si vous avez sélectionné **Montant de la variable**, **Zéro montant parent**, ou **Montant nul** dans le champ **Méthode d’attribution**, la valeur du champ **Pourcentage** reste **0** (zéro) et ne peut pas être modifié.

1. Cliquez sur **Enregistrer**.

## <a name="fields"></a>Champs

La page **Modèle de fractionnement de produit** contient les champs suivants.

| Champ | Description |
|-------|-------------|
| Article parent | Sélectionnez un numéro d’article. Cet article devient l’article parent de l’article d’offre groupée que vous créez. |
| Nom produit | Le nom du produit. |
| Mode de répartition | <p>Sélectionnez la méthode de répartition :</p><ul><li>**Montant égal** – Les pourcentages de répartition sont calculés automatiquement et répartis équitablement entre tous les articles du modèle.</li><li>**Pourcentage** – Vous pouvez spécifier un pourcentage pour la répartition. La somme de tous les pourcentages doit être égale à 100.</li><li>**Montant variable** – Les articles enfants qui sont ajoutés ont un montant net de 0 (zéro). Le prix des articles enfants doit être spécifié au niveau de la transaction.</li><li>**Montant nul** – L’article parent conserve son prix unitaire et son montant net. Tous les articles enfants ont un montant net de 0 (zéro).</li><li>**Zéro montant parent** – L’article parent a un montant net fixe de 0 (zéro). Tous les articles enfants sont traités comme des articles standard. Aucune validation n’est effectuée pour vérifier que la somme des montants de l’article enfant est égale au montant de l’article parent.</li></ul> |
| **Éléments constitutifs** | |
| Article composant | Sélectionnez un numéro d’article. Cet article est un article enfant. |
| Numéro de variante | Sélectionnez le Numéro variante de l’article. |
| Nom produit | Le nom du produit. |
| Pourcentage | <p>Le pourcentage de répartition pour le jalon :</p><ul><li>Si le champ **Méthode de répartition** est défini sur **Pourcentage**, vous pouvez spécifier le pourcentage.</li><li>Si le champ **Méthode de répartition** est défini sur **Même montant**, le pourcentage est automatiquement calculé afin que chaque article du modèle ait un pourcentages égal.</li><li>Si le champ **Méthode d’attribution** est défini sur **Montant variable**, **Zéro montant parent**, ou **Montant nul**, le pourcentage est 0 (zéro) et ne peut pas être modifié.</li></ul><p>La valeur de ce champ peut être n’importe quel nombre positif entre 0 (zéro) et 100. La somme de tous les pourcentages doit être égale à 100.</p> |
| Pourcentage total | <p>Somme des valeurs dans la colonne **Pourcentage**.</p><ul><li>Si le champ **Méthode de répartition** est défini sur **Montant égal** ou **Pourcentage**, la somme de tous les pourcentages doit être égal à 100.</li><li>Si le champ **Méthode d’attribution** est défini sur **Montant variable**, **Zéro montant parent**, ou **Montant nul**, le pourcentage total est 0 (zéro).</li></ul> |

## <a name="revenue-split-on-a-sales-order"></a>Répartition des produits sur une commande client

Pour créer une commande client comportant un article configuré pour le fractionnement des produits, procédez comme suit.

1. Dans la page **Commandes client**, créez une commande client.
2. Sur la ligne de chaque article configuré pour le fractionnement des produits, cochez la case **Fractionnement du produit**. Cet article devient l’article parent. Si le modèle est déjà configuré, les articles enfants apparaissent automatiquement dans la liste.
3. Pour ajouter d’autres articles enfants, sélectionnez **Ajouter un enfant de fractionnement des produits**, puis l’article enfant que vous souhaitez ajouter.
4. Enregistrez la commande.

## <a name="revenue-split-with-billing-schedules"></a>Fractionnement du produit avec les échéanciers de facturation

Pour créer un échéancier de facturation comportant un article configuré pour le fractionnement des produits, procédez comme suit.

1. Sur la page **Tous ou les échéanciers de facturation actifs**, créez un échéancier de facturation.
2. Sur la ligne de chaque article configuré pour le fractionnement des produits, cochez la case **Fractionnement du produit**. Cet article devient l’article parent. Si le modèle est déjà configuré, les articles enfants apparaissent automatiquement dans la liste.
3. Pour ajouter d’autres articles enfants, sélectionnez **Ajouter un enfant de fractionnement des produits**, puis l’article enfant que vous souhaitez ajouter.
4. Continuez avec les étapes pour utiliser l’échéancier de facturation.

> [!NOTE]
> Si l’option **Créer automatiquement un fractionnement de revenu** est définie sur **Oui** sur la page **Paramètres de facturation des contrats récurrents**, les actions suivantes se produisent :
>
> - Si l’article de la ligne est configuré en tant qu’article parent dans un modèle de fractionnement de produit, la case **Fractionnement de produit** est automatiquement cochée.
> - Les articles enfants sont automatiquement renseignés sur la ligne de commande client ou d’échéancier de facturation.
>
> Si l’option **Créer automatiquement un fractionnement de produit** est définie sur **Non**, le comportement est comme expliqué précédemment.
