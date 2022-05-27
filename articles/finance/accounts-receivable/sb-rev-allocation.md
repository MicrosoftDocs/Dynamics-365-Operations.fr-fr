---
title: Allocation des revenus
description: Cette rubrique explique comment utiliser la répartition de produits dans la facturation des abonnements.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 09d3e9295f1fb753156aa603b00372316173721e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695244"
---
# <a name="revenue-allocation"></a>Allocation des revenus

Cette rubrique explique comment configurer les paramètres de répartition de produits dans l’échéancier de facturation. Vous pouvez configurer ou modifier la répartition des produits quand vous créez l’échéancier de facturation. Quand vous ouvrez la page **Répartition des revenus** pour un échéancier de facturation actif ou terminé, les champs sont en lecture seule.

## <a name="specify-the-revenue-allocation-for-a-billing-schedule"></a>Spécifier la répartition des revenus pour un échéancier de facturation

Pour spécifier la répartition de revenus sur un échéancier de facturation, procédez comme suit.

1. Sur la page de liste **Tous les échéancier de facturation ou les échéancier de facturation actifs**, sélectionnez un échéancier de facturation ou une ligne d’échéancier de facturation.
2. Sur l’onglet **Répartition des revenus** en haut de la page, sélectionnez **Répartition des revenus**.
3. Dans le champ **Type d’arrangement à articles multiples**, sélectionnez le type d’organisation à plusieurs éléments (MEA).
4. Dans le champ **Nombre d’arrangements à plusieurs éléments**, indiquez le numéro MEA. Puis, dans le champ **Compte de revenus de contrats différés**, indiquez le compte de produits différés du contrat.

    Si vous réglez le champ **Type d’arrangement à plusieurs éléments** sur **Seul**, les mêmes valeurs **Numéro d’arrangement de plusieurs éléments** et **Compte de revenus de contrats différés** s’appliquent à chaque ligne. Si vous réglez le champ **Type d’arrangement à plusieurs éléments** sur **Plusieurs**, vous pouvez spécifier différentes valeurs **Numéro d’arrangement de plusieurs éléments** et **Compte de revenus de contrats différés** pour chaque ligne.
    
    Un numéro MEA ne peut être attribué qu’à deux articles ou plus. Une seule ligne ne peut pas avoir son propre numéro MEA.

5. Cliquez sur **Enregistrer**.

### <a name="fields"></a>Champs

La page **Organisation à plusieurs éléments** contient les champs suivants.

| Champ | Description |
|---|---| 
| Type d’accord à plusieurs éléments | <p>Sélectionner le type de MEA pour la transaction :</p><ul><li>**Plusieurs** – Les articles de ligne de la transaction font partie du MEA, ou il existe plus d’une organisation.</li><li>**Aucun** – La transaction est une transaction standard qui n’a aucune répartition de revenus.</li><li>**Seul** – Tous les éléments de la transaction font partie d’un seul MEA.</li></ul> |
| Numéro d’organisation à plusieurs éléments | <p>Numéro MEA de la ligne. Ce champ est disponible si le champ **Type d’organisation à plusieurs éléments** est défini sur **Plusieurs**.</p><p>Si ce champ est vide et que vous attribuez un numéro MEA, les champs **Origine du prix de vente autonome** et **Prix de vente autonome** sont automatiquement mis à jour en fonction des valeurs de la page **Prix de vente autonome de l’article**. Seuls les numéros MEA affectés à d’autres lignes de la commande client sont disponibles.</p> |
| Compte de produit du contrat différé | Spécifiez le compte à utiliser pour les entrées de journal à la création d’une facture de contrat MEA. Ce champ est disponible uniquement quand la facturation récurrente des contrats est utilisée. |
| **Lignes** | |
| Numéro de variante | Numéro de variante provenant de la commande client. |
| Numéro d’article | Numéro d’article provenant de la commande client. |
| Fréquence de facturation | Fréquence de la répartition de produit : **Quotidienne**, **Mensuelle**, **Trimestrielle**, **Semestrielle** ou **Annuelle**. |
| Quantity | La valeur provient de la commande client. |
| Valeur du contrat | Valeur du contrat. |
| Numéro d’organisation à plusieurs éléments | <p>Numéro MEA de la ligne. Ce champ est disponible si le champ **Type d’organisation à plusieurs éléments** est défini sur **Plusieurs**.</p><p>Si ce champ est vide et que vous attribuez un numéro MEA, les champs **Origine du prix de vente autonome** et **Prix de vente autonome** sont automatiquement mis à jour en fonction des valeurs de la page **Prix de vente autonome de l’article**. Seuls les numéros MEA affectés à d’autres lignes de la commande client sont disponibles. Si ces valeurs ne sont pas configurées pour l’article, les valeurs de la page **Paramètres de répartition des produits à plusieurs éléments** sont utilisées.</p> | 
| Origine du prix de vente autonome | <p>Origine du prix de vente autonome :</p><ul><li>**Montant** : le prix de vente autonome est un montant que vous spécifiez qui est supérieur à 0 (zéro). Le montant est converti entre la devise fonctionnelle et la devise d’origine selon les besoins.</li><li>**Prix de vente de base** : le prix de vente autonome correspond au prix de vente de base de l’article.</li><li>**Prix facturé** : le prix de vente autonome correspond au prix facturé de l’article.</li><li>**Pourcentage de l’article** : le prix de vente autonome est spécifié sous forme de pourcentage et est calculé en fonction du prix de l’article. Si cette option est sélectionnée, indiquez le pourcentage par défaut.</li><li>**Répartir le montant résiduel** : l’origine du prix de vente autonome est calculée comme *Valeur totale contractuelle de l’article parent* – *Prix de vente autonome total des articles enfants* :</p><ul><li>*Valeur totale contractuelle de l’article parent* est le montant net ou facturé.</li><li>Le *Prix de vente autonome total des articles enfants* est la somme des prix de vente autonomes étendus ou contractuels de tous les articles enfants, à l’exception de l’article enfant qui utilise cette origine de prix de vente autonome.</li></ul><p>Si le montant calculé est une valeur négative, le montant est défini sur 0 (zéro).</p><p>**Remarque :** cette option peut être sélectionnée pour un seul article enfant dans la répartition des revenus.</p></li><li>**Aucun** : l’origine du prix de vente autonome est basée sur les articles enfants. Cette option s’applique aux articles définis comme articles parents dans un modèle de répartition des revenus. Si la case **Répartition des revenus** est cochée, cette option est automatiquement sélectionnée et le paramètre ne peut pas être modifié.</li><li>**Pourcentage du prix de la facture parente** : l’origine du prix de vente autonome est un pourcentage du prix facturé de l’article parent. Cette option n’est disponible que pour les articles enfants dans un modèle de répartition des revenus.</li><li>**Pourcentage du prix standard parent** : l’origine du prix de vente autonome est un pourcentage du prix standard de l’article parent. Cette option n’est disponible que pour les articles enfants dans un modèle de répartition des revenus. Quand l’option d’un article enfant passe de **Pourcentage du prix standard parent** à **Pourcentage du prix de la facture parent**, ou de **Pourcentage du prix de la facture parent** à **Pourcentage du prix standard parent**, les valeurs calculées sont également mises à jour.</li></ul> |
| Prix de vente autonome | <p>Prix de vente autonome de la ligne, dans la devise de la transaction.</p><p>La valeur dans le champ **Montant** est soit saisie, soit calculée.</p> |
| Prix de vente autonome du contrat | Prix de vente autonome du contrat. |
| Reste des revenus du contrat | Montant de produit restant pour le contrat. Ce montant est la somme de toutes les lignes pour lesquelles des factures n’ont pas encore été créées. |
| Produit total du contrat | Montant total de produit du contrat pour la ligne. Ce montant est la somme de toutes les lignes, que les factures aient été créées pour elles ou non. |
| Compte de produit du contrat différé | <p>Spécifiez le compte à utiliser pour les entrées de journal à la création d’une facture de contrat MEA.</p><p>Ce champ est disponible uniquement quand la facturation récurrente des contrats est utilisée.</p> |
| Erreur | Toutes les erreurs qui se sont produites pour la répartition du produit. |

## <a name="use-revenue-allocation-on-a-sales-order"></a>Utilisation de la répartition de produit sur une commande client

Pour utiliser la fonctionnalité de répartition des produits sur une commande client, procédez comme suit.

1. Dans la page **Toutes les commandes client**, créez une commande client avec des articles.
2. Sur l’onglet **Facture**, sous **Répartition des revenus**, sélectionnez **Répartition des revenus**.
3. Dans le champ **Type d’arrangements à plusieurs éléments**, sélectionnez le type MEA.
4. Dans le champ **Nombre d’arrangements à plusieurs éléments**, indiquez le numéro MEA.
5. Si le champ **Type d’arrangement à plusieurs éléments** est défini sur **Plusieurs**, sélectionnez les lignes souhaitées, puis **Appliquer à la sélection**.
6. Cliquez sur **Enregistrer**.

Si vous utilisez des reports de revenus et de dépenses, l’échéancier de report est automatiquement créé. Vous pouvez l’afficher sur la page **Tous les échéanciers de report**.
