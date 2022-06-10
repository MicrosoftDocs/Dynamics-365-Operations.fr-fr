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
ms.openlocfilehash: 73dbc2242639a54d687506e7c325fec4b9a95d12
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770152"
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

## <a name="additional-revenue-split-information"></a>Informations supplémentaires sur la répartition des revenus

Lorsque vous ajoutez un article faisant partie d’une répartition des revenus, notez les informations suivantes : 

- Le montant parental ne peut pas être reporté.
- La date de début, la date de fin, la quantité, l’unité, le site et les valeurs d’entrepôt des articles enfants sont basées sur l’article parent. Ces valeurs ne peuvent pas être modifiées pour les articles enfants. Toutes les modifications doivent être apportées à l’article parent. 
- La méthode de tarification est **Forfaitaire** et ne peut pas être modifiée.
- Les articles enfants peuvent être ajoutés ou supprimés.
- Les articles parent et enfant doivent utiliser le même groupe d’articles. 
- Les articles enfants peuvent avoir l’une des configurations suivantes :

    - Les champs **Fréquence de facturation** et **Intervalles de facturation** sont définis sur la même valeur que l’article parent. 
    - Le champ **Fréquence de facturation** est défini sur **Une fois**. Dans ce cas, le champ **Intervalles de facturation** est automatiquement défini sur **1**. 

- La somme des montants nets des articles enfants est égale au montant parent. Si la méthode d’attribution est **Montants nuls**, la somme des montants de l’article enfant et du montant parent est égale à 0 (zéro). 

    > [!NOTE]
    > Si la méthode d’attribution est **Zéro montant parental**, la somme (non nulle) des articles enfants n’est pas égale au montant parent, qui est 0 (zéro). Cette méthode de répartition est utilisée à des fins internes, afin que les employés puissent voir les articles enfants. Cependant, les clients ne peuvent voir que l’article parent.

- Si le type de disposition à articles multiples (MEA) de la commande client est **Seul**, la ligne de transaction de répartition des revenus à articles multiples correspondante est créée lorsque les articles parent et enfant sont ajoutés. 
- Si la méthode de répartition pour une répartition des revenus est **Montants égaux**, et que le montant parent est modifié, les montants sont recalculés pour toutes les lignes enfants. 
- Pour une répartition des revenus où la méthode de répartition est **Montant variable**, le comportement suivant se produit :

    - Le montant net de l’article parent apparaît dans la colonne **Montant parental**. Cette valeur peut être modifiée. Cependant, le prix unitaire, le montant net et la remise sont 0 (zéro) et ne peuvent pas être modifiés.
    - Le prix unitaire des articles enfants est 0 (zéro). Vous pouvez modifier le prix unitaire ou le montant net. Lorsque vous modifiez une valeur, l’autre valeur est automatiquement mise à jour.

- Pour une répartition des revenus où la méthode de répartition est **Pourcentage**, le comportement suivant se produit :

    - Le montant net de l’article parent apparaît dans la colonne **Montant parental**. Cette valeur peut être modifiée. Cependant, le prix unitaire, le montant net et la remise sont 0 (zéro) et ne peuvent pas être modifiés. 
    - Le montant net des articles enfants est calculé comme suit : *Pourcentage* &times; *Montant parental*.

- Pour une répartition des revenus où la méthode de répartition est **Montant égal**, le comportement suivant se produit :

    - Le montant net de l’article parent apparaît dans la colonne **Montant parental**. Cette valeur peut être modifiée. Cependant, le prix unitaire, le montant net et la remise sont 0 (zéro) et ne peuvent pas être modifiés. 
    - Le montant net des articles enfants est calculé en divisant le montant parent de manière égale entre tous les articles enfants. 
    - Si des articles enfants sont supprimés ou ajoutés, le montant net et les prix unitaires sont recalculés afin que toutes les lignes enfants aient des montants égaux. 
    - Si le montant parent ne peut pas être divisé en parts égales, le montant net et le prix unitaire du dernier article enfant peuvent être légèrement supérieurs ou inférieurs au montant net et au prix unitaire des autres articles enfants. 

- Pour une répartition des revenus où la méthode de répartition est **Montant nul**, le comportement suivant se produit :

    - Le prix unitaire, le montant net et la remise peuvent être modifiés. Le montant parent est 0 (zéro) et ne peut pas être modifié. 
    - La quantité, l’unité, le site et les valeurs d’entrepôt des articles enfants sont basés sur l’article parent. Vous ne pouvez pas modifier ces valeurs pour les articles enfants. Toutes les modifications doivent être apportées à l’article parent. 
    - Le prix unitaire et le prix net des articles enfants sont 0 (zéro) et ne peuvent pas être modifiés. 

- Pour une répartition des revenus où la méthode de répartition est **Montant parent nul**, le comportement suivant se produit :

    - Le prix unitaire, le montant parent et le montant net de l’article parent sont 0 (zéro).
    - Dans un échéancier de facturation, les lignes enfants apparaissent comme si elles avaient été ajoutées manuellement et toutes les valeurs sont mises à jour en fonction du groupe d’échéanciers de facturation sélectionné. Ces valeurs ne peuvent pas être modifiées. Pour les articles enfants, vous pouvez accéder à l’option **Escalade et remise** et **Tarification avancée** en utilisant les champs **Quantité saisie**, **Prix unitaire**, **Remise** et **Montant net** dans **Afficher les détails de facturation**. 
    - Sur une commande client, les lignes enfants ont une remise et un pourcentage de remise de 0 (zéro). 
    - La fréquence de facturation des articles parent et enfant peut être modifiée, et chaque ligne peut avoir une fréquence différente. Cependant, l’article parent est automatiquement mis à jour afin qu’il utilise la fréquence la plus courte parmi ses lignes enfants. Par exemple, une répartition des revenus comporte deux articles enfants, dont l’un utilise la fréquence de facturation **Mensuelle** et dont l’autre utilise la fréquence de facturation **Annuelle**. Dans ce cas, la fréquence de facturation de l’article parent est mise à jour sur **Mensuelle**.
