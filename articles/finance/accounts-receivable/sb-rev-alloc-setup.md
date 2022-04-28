---
title: Configurer la répartition des revenus à plusieurs éléments
description: Cette rubrique décrit comment configurer les paramètres pour la répartition des revenus à plusieurs éléments dans la facturation des abonnements.
author: JodiChristiansen
ms.date: 11/04/2021
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
ms.openlocfilehash: e422b16d1c4505b2837bb282918ecada902b806e
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8566359"
---
# <a name="set-up-multiple-element-revenue-allocation"></a>Configurer la répartition des revenus à plusieurs éléments

La répartition des revenus à plusieurs éléments vous permet de configurer différents modèles utilisés pour calculer et répartir les revenus entre plusieurs éléments. Cette fonctionnalité peut vous aider à vous conformer à l'article 606 de la codification des normes comptables (ASC 606) et/ou à la Norme internationale d'information financière 15 (IFRS 15).

## <a name="multiple-element-revenue-allocation-parameters"></a>Paramètres de répartition des revenus à plusieurs éléments

Utilisez la page **Paramètres de répartition des revenus à éléments multiples** pour configurer les paramètres de la répartition de revenus à éléments multiples.

### <a name="standalone-selling-price-origin"></a>Origine du prix de vente autonome

Le champ **Origine du prix de vente autonome** détermine d'où vient le prix de vente autonome. Vous pouvez mettre à jour la valeur sur la page **Prix de vente autonome de l'article** et sur la transaction. Les options suivantes sont disponibles :

| Option | Description |
|--------|-------------|
| Montant | Le prix de vente autonome est un montant que vous spécifiez qui est supérieur à 0 (zéro). Le montant est converti entre la devise fonctionnelle et la devise d'origine selon les besoins. |
| Prix de vente de base | Le prix de vente autonome correspond au prix de vente de base de l'article. |
| Prix de facturation | Le prix de vente autonome correspond au prix facturé de l'article. |
| Pourcentage d’article | Le prix de vente autonome est spécifié sous forme de pourcentage et est calculé en fonction du prix de l'article. Si vous sélectionnez cette option, indiquez le pourcentage par défaut. |
| Répartir le montant d’affectation | <p>L'origine du prix de vente autonome est calculée comme *Valeur totale contractuelle de l'article parent* – *Prix de vente autonome total des articles enfants* :</p><ul><li>*Valeur totale contractuelle de l'article parent* est le montant net ou facturé.</li><li>Le *Prix de vente autonome total des articles enfants* est la somme des prix de vente autonomes étendus ou contractuels de tous les articles enfants, à l'exception de l'article enfant qui utilise cette origine de prix de vente autonome.</li></ul><p>Si le montant calculé est une valeur négative, le montant est défini sur 0 (zéro).</p><p>**Remarque :** cette option peut être sélectionnée pour un seul article enfant dans la répartition des revenus.</p> |
| Aucune | L'origine du prix de vente autonome est basée sur les articles enfants. Cette option s'applique aux articles définis comme articles parents dans un modèle de répartition des revenus. Si la case **Répartition des revenus** est cochée, cette option est automatiquement sélectionnée et le paramètre ne peut pas être modifié. |
| Pourcentage du prix de la facture parente | L'origine du prix de vente autonome est un pourcentage du prix facturé de l'article parent. Vous pouvez modifier la valeur par défaut. Cette option n’est disponible que pour les articles enfants dans un modèle de répartition des revenus. |
| Pourcentage du prix standard parent | L'origine du prix de vente autonome est un pourcentage du prix standard de l'article parent. Vous pouvez modifier la valeur par défaut. Cette option n’est disponible que pour les articles enfants dans un modèle de répartition des revenus. C'est l'option par défaut pour les articles enfants. Lorsque l'option d'un article enfant passe de **Pourcentage du prix standard parent** à **Pourcentage du prix de la facture parent**, ou de **Pourcentage du prix de la facture parent** à **Pourcentage du prix standard parent**, les valeurs calculées sont également mises à jour. |

### <a name="account-for-revenue-allocation-rounding-differences"></a>Compte pour les différences d’arrondi dans la répartition des revenus

Le champ **Compte pour les différences d’arrondi dans la répartition des revenus** spécifie le compte utilisé pour enregistrer les ajustements d'arrondi d'un montant de revenu d'un contrat. Il est disponible lorsque la facturation récurrente des contrats est utilisée.

## <a name="item-standalone-selling-price"></a>Prix de vente autonome de l’article

Utilisez la page **Prix de vente autonome de l'article** pour spécifier l'origine et le prix de vente autonome d'un article. Les valeurs spécifiées sur cette page sont utilisées comme valeurs par défaut sur la page **Répartition des revenus** dans la répartition des revenus à éléments multiples et la facturation récurrente des contrats.

### <a name="specify-item-standalone-selling-price"></a>Indiquer le prix de vente autonome de l’article

Pour spécifier le prix autonome d'un article, procédez comme suit.

1. Sur la page **Prix de vente autonome de l'article**, dans le champ **Origine du prix de vente autonome**, sélectionnez l'origine du prix de vente autonome.
2. Suivez l’une des procédures suivantes, selon la valeur que vous avez sélectionnée dans le champ **Origine du prix de vente autonome** :

    * Si vous avez sélectionné **Pourcentage de l'article**, spécifiez le pourcentage dans le champ **Pour cent**.
    * Si vous avez sélectionné **Montant**, indiquez le montant dans le champ **Prix de vente autonome**.

2. Pour chaque article que vous souhaitez ajouter à la liste, sélectionnez **Ajouter**.
3. Dans le champ **Code article**, sélectionnez le code article. Dans le champ **Relation d’article**, sélectionnez la relation d’article. Pour les articles où la case **Répartition des revenus** est décochée, la combinaison sélectionnée d'un code d'article et d'une relation d'article doit être unique.
4. Modifiez la valeur par défaut des champs **Origine du prix de vente autonome**, **Prix de vente autonome**, ou **Pour cent** selon vos besoins.
5. Pour chaque article parent que vous souhaitez ajouter à la liste, sélectionnez **Ajouter**.
6. Dans le champ **Code article**, sélectionnez le code article. Dans le champ **Relation d’article**, sélectionnez la relation d’article.
7. Activez la case à cocher **Répartition des revenus**.
8. Dans le champ **Relation d’article**, sélectionnez la relation d’article. La liste est mise à jour avec l'article parent et tous les articles enfants.
9. Pour l'article enfant, modifiez la valeur par défaut du champ **Origine du prix de vente autonome**, **Pourcentage du prix standard parent**, **Pourcentage du prix de la facture parent**, ou **Répartir le montant résiduel** selon vos besoins.
10. Pour ajouter plusieurs éléments à la fois, sélectionnez **Ajouter des articles**.
11. Mettez à jour la requête pour sélectionner la plage d'articles que vous souhaitez ajouter.
12. Sélectionnez **OK**, passez en revue la liste des articles que vous avez ajoutés, puis sélectionnez **OK**.

### <a name="fields"></a>Champs

La page **Prix de vente autonome de l'article** contient les champs suivants.

| Champ | Description |
|-------|-------------|
| Origine du prix de vente autonome | <p>Sélectionnez l’origine du prix de vente autonome :</p><ul><li>**Montant** : le prix de vente autonome est un montant que vous spécifiez qui est supérieur à 0 (zéro). Le montant est converti entre la devise fonctionnelle et la devise d'origine selon les besoins.</li><li>**Prix de vente de base** : le prix de vente autonome correspond au prix de vente de base de l'article.</li><li>**Prix facturé** : le prix de vente autonome correspond au prix facturé de l'article.</li><li>**Pourcentage de l'article** : le prix de vente autonome est spécifié sous forme de pourcentage et est calculé en fonction du prix de l'article. Si vous sélectionnez cette option, indiquez le pourcentage par défaut.</li></ul>**Répartir le montant résiduel** : l'origine du prix de vente autonome est calculée comme *Valeur totale contractuelle de l'article parent* – *Prix de vente autonome total des articles enfants* :</p><ul><li>*Valeur totale contractuelle de l'article parent* est le montant net ou facturé.</li><li>Le *Prix de vente autonome total des articles enfants* est la somme des prix de vente autonomes étendus ou contractuels de tous les articles enfants, à l'exception de l'article enfant qui utilise cette origine de prix de vente autonome.</li></ul><p>Si le montant calculé est une valeur négative, le montant est défini sur 0 (zéro).</p><p>**Remarque :** cette option peut être sélectionnée pour un seul article enfant dans la répartition des revenus.</p></li><li>**Aucun** : l'origine du prix de vente autonome est basée sur les articles enfants. Cette option s'applique aux articles définis comme articles parents dans un modèle de répartition des revenus. Si la case **Répartition des revenus** est cochée, cette option est automatiquement sélectionnée et le paramètre ne peut pas être modifié.</li><li>**Pourcentage du prix de la facture parente** : l'origine du prix de vente autonome est un pourcentage du prix facturé de l'article parent. Vous pouvez modifier la valeur par défaut. Cette option n’est disponible que pour les articles enfants dans un modèle de répartition des revenus.</li><li>**Pourcentage du prix standard parent** : l'origine du prix de vente autonome est un pourcentage du prix standard de l'article parent. Vous pouvez modifier la valeur par défaut. Cette option n’est disponible que pour les articles enfants dans un modèle de répartition des revenus. C'est l'option par défaut pour les articles enfants. Lorsque l'option d'un article enfant passe de **Pourcentage du prix standard parent** à **Pourcentage du prix de la facture parent**, ou de **Pourcentage du prix de la facture parent** à **Pourcentage du prix standard parent**, les valeurs calculées sont également mises à jour.</li></ul> |
| Prix de vente autonome | Indiquez le prix de vente autonome de l'article. Ce champ est disponible lorsque le champ **Origine du prix de vente autonome** est défini sur **Montant**. |
| Pourcentage | Indiquez le pourcentage du prix de vente autonome. Ce champ est disponible lorsque le champ **Origine du prix de vente autonome** est défini sur **Pourcentage de l'article**, **Pourcentage du prix de la facture parente** ou **Pourcentage du prix standard parent**. |
| Répartition des revenus | <p>Spécifiez si une ligne utilise la répartition des revenus :</p><ul><li>**Sélectionné** : seuls les articles pour lesquels un modèle de répartition des revenus est configuré peuvent être sélectionnés dans le champ **Relation d'article**. Vous ne pouvez cocher cette case que pour les articles parents d'un modèle de répartition des revenus.</li><li>**Décoché** : l'article est un article standard qui n'utilise pas la répartition des revenus.</li></ul> |
| Relation | Un symbole indique si l'article est un article parent ou enfant dans une répartition des revenus. |
| Article - valide pour | <p>Sélectionnez le code article: **Table** ou **Groupe**.</p><p>Si la case **Répartition des revenus** est cochée, ce champ est défini sur **Table** et cette valeur ne peut pas être modifiée.</p> |
| Relation d’article | <p>Sélectionnez un numéro d’article.</p><p>Si la case **Répartition des revenus** est cochée, seuls les articles qui sont des articles parents pour lesquels un modèle de répartition des revenus est configuré peuvent être sélectionnés. Lorsque l'article parent est sélectionné, la liste est automatiquement mise à jour avec les articles enfants de cet article parent.</p> |
| Article parent | Pour l'article parent, ce champ affiche le numéro de l'article. Pour les articles enfants dans une répartition des revenus, il affiche le numéro d'article de l'article parent. |

## <a name="mea-templates"></a>Modèles MEA

Utilisez la page **Modèles MEA** pour créer et modifier des ID de modèle d'arrangement d'éléments multiples (MEA). Ces ID sont utilisés sur la page **Répartition des revenus** pour regrouper les éléments.

### <a name="create-a-template"></a>Créer un modèle

Pour paramétrer un modèle MEA, procédez comme suit.

1. Sur la page **Modèles MEA**, sélectionnez **Nouveau**.
1. Dans le champ **ID modèle MEA**, entrez un ID unique.
1. Entrez une description dans le champ **Description**.
1. Dans le champ **Compte de produit du contrat différé**, sélectionnez le compte que vous souhaitez utiliser pour les écritures de journal lors de la création d'une facture de contrat MEA. Ce champ est disponible lorsque la facturation récurrente des contrats est activée et utilisée.
1. Cliquez sur **Enregistrer**.
