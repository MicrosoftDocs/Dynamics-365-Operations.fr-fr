---
title: Valider les transactions du magasin pour le calcul du relevé
description: Cet article décrit la fonctionnalité de validation des transactions en magasin dans Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: analpert
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4be40189777a37495f185467050b61af47b684d7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890511"
---
# <a name="validate-store-transactions-for-statement-calculation"></a>Valider les transactions du magasin pour le calcul du relevé

[!include [banner](includes/banner.md)]

Cet article décrit la fonctionnalité de validation des transactions en magasin dans Microsoft Dynamics 365 Commerce. Le processus de validation identifie et marque les transactions qui provoqueront des erreurs de comptabilisation, avant qu’elles ne soient récupérées par le processus de validation des relevés.

Lorsque vous essayez de publier un relevé, le processus de validation peut échouer en raison de données incohérentes dans les tables de transactions commerciales. Voici quelques exemples de facteurs pouvant entraîner ces incohérences :

- Le total des transactions dans la table des en-têtes ne correspond pas au total des transactions sur les lignes.
- Le nombre d’éléments spécifié dans la table d’en-tête ne correspond pas au nombre d’éléments dans la table des transactions.
- Les taxes dans la table des en-têtes ne correspondent pas au montant des taxes sur les lignes. 

Si des transactions incohérentes sont prélevées par le processus de validation des relevés, les factures client et les journaux de paiement incohérents qui sont créés peuvent provoquer l’échec de l’ensemble du processus de validation des relevés. Le processus **Valider les transactions en magasin** empêche ces problèmes en garantissant que seules les transactions qui passent les règles de validation de transaction sont transmises au processus de calcul du relevé de transactions.

L’illustration suivante montre les processus de jour récurrents pour le téléchargement des transactions, la validation des transactions, ainsi que le calcul et la validation des relevés de transaction et les processus de fin de journée pour le calcul et la validation du tableau d’analyse.

![L’illustration montre les processus de jour récurrents pour le téléchargement des transactions, la validation des transactions, ainsi que le calcul et la validation des relevés de transaction et les processus de fin de journée pour le calcul et la validation du tableau d’analyse](./media/valid-checker-statement-posting-flow.png)

## <a name="store-transaction-validation-rules"></a>Règles de validation des transactions en magasin

Le processus de traitement par lots **Valider les transactions en magasin** vérifie la cohérence des tables de transactions commerciales en fonction des règles de validation suivantes.

> [!NOTE]
> Des règles de validation continueront d’être ajoutées dans les versions ultérieures.

### <a name="transaction-header-validation-rules"></a>Règles de validation des en-têtes de transaction

Le tableau suivant répertorie les règles de validation des en-têtes de transaction qui sont vérifiées par rapport à l’en-tête des transactions de vente au détail avant que ces transactions ne soient transmises à la validation des relevés.

| Règle | Description |
|-------|-------------|
| Date commerciale | Cette règle valide que la date commerciale de la transaction est associée à une période fiscale en cours dans la comptabilité. |
| Arrondi des devises | Cette règle valide que les montants des transactions sont arrondis selon la règle d’arrondi des devises. |
| Compte client | Cette règle valide que le client utilisé dans la transaction existe dans la base de données. |
| Montant de la remise | Cette règle valide que le montant de la remise dans l’en-tête est égal à la somme des montants des remises sur les lignes. |
| Statut de comptabilisation des documents fiscaux (Brésil) | Cette règle valide que le document fiscal peut être validé avec succès. |
| Montant brut | Cette règle valide que le montant brut de l’en-tête de transaction correspond au montant net, taxes comprises, des lignes de transactions plus les frais. |
| Net | Cette règle valide que le montant net de l’en-tête de transaction correspond au montant net, hors taxes, des lignes de transactions plus les frais. |
| Net + taxes | Cette règle valide que le montant brut de l’en-tête de transaction correspond au montant net, hors taxes, des lignes de transactions plus les taxes et les frais. |
| Nombre d’articles | Cette règle valide que le nombre d’articles spécifié sur l’en-tête de transaction correspond à la somme des quantités sur les lignes de transaction. |
| Montant du paiement | Cette règle valide que le montant du paiement sur l’en-tête de la transaction correspond à la somme de toutes les transactions de paiement. |
| Calcul de l’exonération fiscale | Cette règle valide que la somme du montant calculé et du montant de taxe exonérée des lignes de frais est égale au montant calculé d’origine. |
| Prix TTC | Cette règle valide que l’indicateur **La taxe est incluse dans le prix** est cohérent dans l’en-tête de transaction et les transactions de taxe. |
| La transaction n’est pas vide | Cette règle valide que la transaction contient des lignes et qu’au moins une ligne n’est pas annulée. |
| Moins-perçu/Trop-perçu | Cette règle valide que la différence entre le montant brut dans l’en-tête et le montant du paiement ne dépasse pas la configuration maximale du moins-perçu/trop-perçu. |

### <a name="transaction-line-validation-rules"></a>Règles de validation des lignes de transaction

Le tableau suivant répertorie les règles de validation des lignes de transaction qui sont vérifiées par état aux détails des lignes des transactions de vente au détail avant que ces transactions ne soient transmises à la validation des relevés.

| Règle | Description |
|-------|-------------|
| Code-barres | Cette règle valide que tous les codes-barres d’articles utilisés sur les lignes de transaction existent dans la base de données. |
| Lignes de frais | Cette règle valide que la somme du montant calculé et du montant de taxe exonérée des lignes de frais est égale au montant calculé d’origine. |
| Retours de cartes cadeaux | Cette règle valide qu’il n’y a pas de retours de cartes cadeaux dans la transaction. |
| Variante d’article | Cette règle valide que tous les articles et toutes les variantes utilisés sur les lignes de transaction existent dans la base de données. |
| Remise ligne | Cette règle valide que le montant de la remise de ligne correspond à la somme des transactions de remise. |
| Taxe de ligne | Cette règle valide que le montant de la taxe de ligne correspond à la somme des transactions de taxes. |
| Prix négatif | Cette règle valide qu’il n’existe aucun prix négatif n’est utilisé sur les lignes de transactions. |
| Numéro de série contrôlé | Cette règle valide que le numéro de série est présent sur la ligne de transaction pour les articles contrôlés par numéro de série. |
| Dimension numéro de série | Cette règle valide qu’aucun numéro de série n’est fourni si la dimension du numéro de série de l’article est inactive. |
| Contradiction de signe | Cette règle valide que le signe de la quantité et celui du montant net sont identiques sur toutes les lignes de transaction. |
| Exonération de taxe | Cette règle valide que la somme du prix de l’article de ligne et du montant de taxe exonérée est égale au prix d’origine. |
| Affectation du groupe de taxe | Cette règle valide que la combinaison du groupe de taxe et du groupe de taxe d’article produit une intersection de taxe valide. |
| Conversions de l’unité de mesure | Cette règle valide que l’unité de mesure de toutes les lignes a une conversion valide en unité de mesure d’inventaire. |

## <a name="enable-the-store-transaction-validation-process"></a>Activer le processus de validation des transactions en magasin

Configurez le processus de traitement par lots **Valider les transactions en magasin** pour des exécutions périodiques dans Commerce headquarters (**Retail et Commerce \> IT Retail et Commerce \> Validation du PDV**). Le traitement par lots est planifié en fonction de la hiérarchie d’organisation du magasin. Nous vous recommandons de configurer ce processus de traitement par lots pour qu’il s’exécute à la même fréquence que vos traitements par lots **Tâche -P** et **Calcul du relevé transactionnel**.

## <a name="results-of-the-validation-process"></a>Résultats du processus de validation

Les résultats du processus de traitement par lots **Valider les transactions en magasin** peuvent être consultés sur chaque transaction de magasin de détail. Le champ **Statut de validation** de l’enregistrement de la transaction est défini sur **Réussite**, **Erreur** ou **Aucune**. Le champ **Heure de la dernière validation** affiche la date de la dernière exécution de validation.

Le tableau suivant décrit chaque état de validation.

| Statut de validation | Description |
|-------------------|-------------|
| Réussite | Toutes les règles de validation activées ont réussi. |
| Erreur | Une règle de validation activée a identifié une erreur. Vous pouvez afficher plus de détails sur l’erreur en sélectionnant **Erreurs de validation** dans le volet Actions. |
| Aucune | Le type de transaction ne nécessite pas l’application de règles de validation. |

![Page des transactions en magasin affichant le champ Statut de validation et le bouton Erreurs de validation.](./media/valid-checker-validation-status-errors.png)

Seules les transactions qui ont un statut de validation **Réussite** seront extraites des relevés transactionnels. Pour afficher les transactions dont le statut est **Erreur**, passez en revue la vignette **Échecs de validation au comptant sans livraison** dans l’espace de travail **Finances du magasin**.

![Vignettes de l’espace de travail Finances du magasin.](./media/valid-checker-cash-carry-validation-failures.png)

Pour plus d’informations sur la façon de corriger les échecs des transactions au comptant sans livraison, consultez [Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison](edit-cash-trans.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison](edit-cash-trans.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
