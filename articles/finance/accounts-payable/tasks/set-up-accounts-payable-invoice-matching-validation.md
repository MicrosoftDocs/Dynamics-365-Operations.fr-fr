---
title: Paramétrer la validation du rapprochement de factures dans la comptabilité fournisseur
description: Cet article fournit des informations sur le paramétrage de la validation du rapprochement de factures de la comptabilité fournisseur.
author: abruer
ms.date: 02/14/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5c93ba4a13dee32427f33fe9f33fda5d783501a7
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775324"
---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Configurer la validation du rapprochement de factures de la comptabilité fournisseur

[!include [banner](../../includes/banner.md)]

Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée. Si l’entité juridique suit des dépenses, comme les frais de transport, à l’aide des frais, vérifiez que la clé de configuration Frais est sélectionnée. Le rapprochement de factures du module Achats est le processus de rapprochement des informations de la facture fournisseur, de la commande fournisseur et de l’accusé de réception de marchandises. Les différences entre ces documents sont appelées des écarts de rapprochement. Ces derniers sont comparés aux tolérances spécifiées. Si un écart de rapprochement dépasse le pourcentage ou le montant de tolérance, des icônes d’écart de rapprochement sont affichées dans les pages **Facture fournisseur** et **Détails de rapprochement de factures**.

## <a name="determine-which-invoice-matching-validation-to-use"></a>Déterminer la validation du rapprochement de factures à utiliser
Il existe quatre types de validation du rapprochement. 

- **Rapprochement au niveau ligne** – Le type le plus courant de rapprochement est le rapprochement au niveau ligne. Le rapprochement au niveau ligne peut être à deux ou trois facteurs. Le rapprochement au niveau ligne par défaut peut être spécifié pour une entité juridique sur la page **Paramètres de la comptabilité fournisseur**. Le rapprochement à deux facteurs compare le prix unitaire de la facture avec celui de la commande fournisseur. Le rapprochement à trois facteurs compare la quantité de la facture à la quantité de l’accusé de réception correspondant.
- **Rapprochement des totaux des factures** – Rapproche les montants totaux de la facture avec ceux de la commande fournisseur Ce type de rapprochement de factures inclut un minimum d’informations afin que vous puissiez utiliser cette option pour paramétrer des contrôles qui réduisent le temps de travail requis pour réviser les informations de rapprochement de factures. Six totaux sont comparés, notamment le sous-total, la remise totale, les frais, les taxes, l’arrondi et le montant de la facture. Le système valide si l’une de ces valeurs sur la facture s’écarte du montant prévu de plus que l’écart acceptable.
- **Rapprochement des frais** – Rapproche les informations de frais (montants) de la facture avec celles de la commande fournisseur.
- **Rapprochement des prix totaux par ligne article** – Ce type de rapprochement est utile pour les sociétés qui reçoivent généralement plusieurs factures pour une seule ligne de commande fournisseur. Si vous recevez généralement une seule facture par ligne de commande fournisseur, ce type de rapprochement n’est pas nécessaire. Ce rapprochement nécessite que le rapprochement à deux ou trois facteurs soit activé et sert de validation du montant net à ne pas dépasser, selon les pourcentages et les montants de tolérance. Ce type de rapprochement compare les informations de prix relatives au montant net de chaque ligne de la facture et de toutes les lignes de facture en attente et précédemment validées avec le montant net de la ligne de commande fournisseur correspondante. Le montant net est déterminé par la formule suivante : (Prix unitaire * Quantité de la ligne) + Frais de la ligne – Remises de la ligne. Lors du rapprochement des totaux des prix par pourcentage, les valeurs sont compensées à l’aide de la devise de transaction. Lors du rapprochement des totaux des prix par montant, le système compare les valeurs à l’aide de la devise comptable.

## <a name="set-up-parameters-to-enable-invoice-matching-validation"></a>Configurer les paramètres pour activer la validation du rapprochement de factures
1. Accédez à **Comptabilité fournisseur > Configuration > Paramètres de la comptabilité fournisseur**.
2. Sélectionnez l’onglet **Contrôle de la facture**.
3. Activez ou désactivez la case à cocher **Activer le contrôle de rapprochement de factures**.
    * Sélectionnez si l’approbation est requise avant de pouvoir valider une facture contenant des écarts pour le rapprochement de factures. Si cette option est définie sur **Autoriser avec avertissement**, une indication visuelle s’affiche quand un écart pour le rapprochement de factures dépasse la tolérance. Vous pourrez toutefois valider la facture. Pour utiliser des workflows avec le contrôle de rapprochement de factures, vérifiez que le champ **Valider la facture avec les non-correspondances** est défini sur **Autoriser avec avertissement** pour ne pas avoir à l’approuver plusieurs fois.  
    * Dans le champ **Mettre à jour automatiquement le statut d’en-tête des factures**, sélectionnez si le rapprochement sera effectué automatiquement lors de la saisie de données des factures. Le paramètre recommandé est **Oui**, sauf si vous rencontrez des soucis de performances de saisie de données. La désactivation des mises à jour automatiques peut accélérer les performances du système car le contrôle de rapprochement de factures est ignoré lors de la saisie de données. L’assistant chargé de entrer les données devra mettre à jour manuellement le statut des factures pour afficher les résultats du contrôle de rapprochement lorsque ce paramètre est défini sur **Non**.  
4. Définissez **Rapprochement des totaux de facture**.
5. Activez ou désactivez la case à cocher **Mettre en correspondance les totaux de la facture** pour rapprocher les totaux réels de la facture avec ceux prévus.
    * Sélectionnez si une icône doit être affichée quand un écart pour le rapprochement de factures dépasse la tolérance. Vous pouvez sélectionner d’afficher l’icône quand un écart positif dépasse la tolérance, ou quand un écart positif OU négatif dépasse la tolérance.  
    * Par exemple, la tolérance est de 5 % et le montant total de la facture sur la commande fournisseur est 100,00. Par conséquent, une icône de correspondance des prix s’affiche si le montant total de la facture dépasse 105,00. Si vous sélectionnez **Si supérieur ou inférieur à la tolérance**, l’icône s’affiche également si le montant de la facture est inférieur à 95,00.  
6. Dans le champ **Pourcentage de tolérance des totaux de facture**, entrez l’écart de pourcentage acceptable. Cette valeur est la valeur par défaut de la société. Cette valeur peut être remplacée pour des fournisseurs spécifiques, à l’aide de la page **Tolérances des totaux de facture**. Pour plus d’informations sur le remplacement du pourcentage de tolérance des totaux de facture pour un fournisseur donné, voir la section [Paramétrer la tolérance de rapprochement des totaux de facture pour les fournisseurs](set-up-accounts-payable-invoice-matching-validation.md#set-up-invoice-totals-matching-tolerance-for-vendors) plus loin dans cet article.
7. Définissez **Prix et correspondance de quantité**.
8. Le champ **Stratégie de rapprochement des lignes** permet de sélectionner une valeur à utiliser comme stratégie par défaut pour l’entité juridique avec laquelle vous travaillez. **Non obligatoire** signifie qu’il n’y a pas de vérification entre les prix indiqués dans les lignes de facture pour le prix d’une commande fournisseur ou les quantités facturées et les quantités indiquées sur le bon de livraison. **Rapprochement à deux facteurs** signifie que la vérification des lignes de facture est requise mais que seule la commande fournisseur et les documents de facturation du fournisseur sont impliqués dans la vérification. L’accusé de réception de marchandises n’est pas factorisé dans les validations de rapprochement. **Rapprochement à trois facteurs** signifie que le prix unitaire net de la facture sera comparé au prix unitaire net de la commande fournisseur et la quantité de l’accusé de réception de marchandises rapprochée sera comparée à la quantité de la facture.
9. Pour autoriser l’application d’un autre niveau de correspondance sur un article, un fournisseur, une combinaison de fournisseur et d’article ou une ligne de commande fournisseur, sélectionnez une valeur dans le champ **Autoriser le remplacement de la stratégie de rapprochement**. La stratégie de rapprochement de ligne pour les fournisseurs peut être remplacée pour un fournisseur, un article ou une combinaison de fournisseurs et d’articles dans la page **Stratégie de rapprochement**.
    * Si vous utilisez une stratégie de rapprochement avec le **rapprochement à deux facteurs** ou le **rapprochement à trois facteurs**, vous pouvez configurer des pourcentages de tolérance de prix pour l’entité juridique, les articles et les fournisseurs dans la page **Tolérance de prix d’article**. La tolérance de prix par défaut de l’entité juridique est définie au pourcentage zéro pour les rapprochements à deux et trois facteurs. Lors de la comparaison des factures fournisseur avec les informations des commandes fournisseur, le pourcentage de tolérance de prix applicable est recherché.   
10. Pour faire correspondre les totaux de prix pour les lignes des factures, sélectionnez une valeur dans le champ **Mettre en correspondance les prix totaux**. Ce type de rapprochement est utile lorsque le fournisseur soumet plusieurs factures pour la même ligne de commande fournisseur. Vous pouvez comparer les informations de prix relatives au montant net de chaque ligne de la facture et de toutes les lignes de facture en attente et précédemment validées avec le montant net de la ligne de commande fournisseur correspondante. Les options sont **Aucun**, **Pourcentage**, **Montant**, ou **Pourcentage et montant**.
11. Dans le champ **Pourcentage de tolérance du prix d’achat total**, entrez le pourcentage d’écart que vous acceptez. Ce champ est disponible quand **Mettre en correspondance les prix totaux** est défini sur **Pourcentage** ou **Pourcentage et montant**.
12. Dans le champ **Tolérance du prix d’achat total**, entrez un montant dans la devise comptable. Ce champ est disponible quand **Mettre en correspondance les prix totaux** est défini sur **Montant** ou **Pourcentage et montant**.
13. Le champ **Afficher l’icône de correspondance de prix total** permet de choisir si une icône s’affiche quand un écart dans le rapprochement de factures dépasse la tolérance. L’icône peut être affichée quand un écart positif dépasse la tolérance ou quand un écart positif OU négatif dépasse la tolérance.
Par exemple, la tolérance est de 5 % et la ligne du total des prix sur la commande fournisseur est 10,00. Par conséquent, une icône de correspondance des prix s’affiche si la ligne du total des prix de la facture dépasse 10,50. Si vous sélectionnez **Si supérieur ou inférieur à la tolérance**, l’icône s’affiche également si le total des lignes de prix de la facture est inférieur à 9,50.
13. Définissez la **mise en correspondance des frais**.
14. Pour faire correspondre les frais réels avec les frais prévus, selon les informations sur la commande fournisseur, activez la case à cocher **Mettre en correspondance les frais**.

## <a name="set-up-unit-price-tolerance-percentages"></a>Paramétrage des pourcentages de tolérance de prix unitaire
Accédez à **Comptabilité fournisseur > Paramétrage > Paramétrage du rapprochement de factures > Tolérances de prix** pour définir le pourcentage de tolérance sur les prix. Si vous utilisez une stratégie de rapprochement avec le **rapprochement à deux facteurs** ou le **rapprochement à trois facteurs**, vous pouvez configurer des pourcentages de tolérance de prix pour l’entité juridique, les articles et les fournisseurs. Lors de la comparaison des factures fournisseur avec les informations des commandes fournisseur, le pourcentage de tolérance de prix applicable est recherché. Ce qui suit est l’ordre de recherche par défaut :
* Table/table
* Table/Groupe
* Table/Tout
* Groupe/Table
* Groupe/Groupe
* Groupe/Tout
* Tout/Table
* Tout/Groupe
* Tout/tout

La tolérance de prix par défaut de l’entité juridique est 0 % et est appliquée à tous les articles et tous les comptes (Tout, Tout). Il est impossible de supprimer l’enregistrement de tolérance de prix par défaut de l’entité juridique.

Les différences de prix négatives sont autorisées par défaut. Toutefois, vous ne pouvez pas entrer un nombre négatif sous forme de pourcentage de tolérance de prix. Pour suivre les pourcentages de tolérance de prix négatifs, sélectionnez **Si supérieur à la tolérance ou inférieur à la tolérance** dans le champ **Afficher l’icône de correspondance des prix unitaires** de la page **Paramètres de la comptabilité fournisseur**. Entrez ensuite les pourcentages de tolérance de prix sur la page **Tolérances de prix**.

## <a name="set-up-matching-policy-override"></a>Configurer le remplacement de la stratégie de rapprochement

Accédez à **Comptabilité fournisseur > Paramétrage >Paramétrage du rapprochement de factures > Stratégie de rapprochement** pour définir l’entrée par défaut du champ **Stratégie de rapprochement** pour les lignes de la **commande fournisseur**. Cette configuration est facultative. Cette page permet de paramétrer le rapprochement à deux ou trois facteurs pour les articles, les fournisseurs ou les combinaisons article/fournisseur. Ces entrées permettent de définir des stratégies de rapprochement plus granulaires que la stratégie de rapprochement de l’entité juridique que vous avez définie dans la page **Paramètres de la comptabilité fournisseur**. La stratégie de rapprochement des lignes par défaut de l’entité juridique s’applique à tous les articles et les fournisseurs hormis ceux pour lesquels une autre stratégie de rapprochement des lignes est spécifiée dans cette page.

Dans cette page, sélectionnez **Niveau de la stratégie de rapprochement**. Sélectionnez le niveau dans la hiérarchie des stratégies de rapprochement pour lequel des stratégies de rapprochement des lignes doivent être définies.

- **Article et fournisseur** – Permet de définir une stratégie de rapprochement pour des article spécifiques achetés auprès de fournisseurs spécifiques.
- **Article** – Permet de spécifier une stratégie de rapprochement pour des articles spécifiques achetés auprès de n’importe quel fournisseur, hormis ceux spécifiés aux niveaux Article et Fournisseur.
- **Fournisseur** – Permet de spécifier une stratégie de rapprochement pour tous les articles achetés auprès de fournisseurs spécifiques, hormis ceux spécifiés aux niveaux Article et Fournisseur.
  
La hiérarchie suivante sert à déterminer la stratégie de rapprochement utilisée :
  *  Article et fournisseur
  *  Article
  *  Fournisseur
  *  Entité juridique
  
## <a name="set-up-invoice-totals-matching-tolerance-for-vendors"></a>Paramétrer les tolérances de rapprochement du factures pour les fournisseurs

Accédez à **Comptabilité fournisseur > Paramétrage > Paramétrage du rapprochement de factures > Tolérances de prix** pour spécifier les tolérances spécifiques aux fournisseurs pour le rapprochement des totaux de facture. Le calcul de mise en correspondance utilise le pourcentage de tolérance des totaux de facture à partir du compte fournisseur spécifié comme compte commande sur la facture fournisseur. Si le compte fournisseur ne dispose pas d’un pourcentage de tolérance spécifié pour les totaux de facture, celui qui est indiqué pour l’entité juridique dans la page **Paramètres de la comptabilité fournisseur** est utilisé.

1. Pour spécifier des tolérances pour des fournisseurs individuels qui remplacent la tolérance par défaut, sélectionnez un **Compte fournisseur**.
2. Entrez le pourcentage d’écart que vous accepterez pour ce fournisseur.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
