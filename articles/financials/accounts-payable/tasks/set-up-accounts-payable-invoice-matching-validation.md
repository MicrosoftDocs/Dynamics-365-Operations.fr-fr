--- 
title: "Paramétrer la validation du rapprochement de factures de la compatibilité fournisseur."
description: "La société fictive USMF sert d'exemple dans cet enregistrement."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e9bf83269c34133509734691fd018ee703c40626
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Paramétrer la validation du rapprochement de factures de la compatibilité fournisseur.

[!include [task guide banner](../../includes/task-guide-banner.md)]

La société fictive USMF sert d'exemple dans cet enregistrement. Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable. Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée. Si l'entité juridique suit des dépenses, comme les frais de transport, à l'aide des frais, vérifiez que la clé de configuration Frais est sélectionnée.  Le rapprochement de factures du module Achats est le processus de rapprochement des informations de la facture fournisseur, de la commande fournisseur et de l'accusé de réception de marchandises. Les différences entre ces documents sont appelées des écarts de rapprochement. Ces derniers sont comparés aux tolérances spécifiées. Si un écart de rapprochement dépasse le pourcentage ou le montant de tolérance, des icônes d'écart de rapprochement sont affichées dans les écrans Facture fournisseur et Détails de rapprochement de factures.

1. Accédez à Comptabilité fournisseur > Paramétrage > Paramètres de la comptabilité fournisseur.
2. Cliquez sur l'onglet Contrôle de la facture.
3. Activez ou désactivez la case à cocher Activer le contrôle de rapprochement de factures.
    * Sélectionnez si l'approbation est requise avant de pouvoir valider une facture contenant des écarts pour le rapprochement de factures. Si cette option est définie sur Autoriser avec avertissement, l'indication visuelle s'affiche quand un écart pour le rapprochement de factures dépasse la tolérance. Vous pourrez toutefois valider la facture. Pour utiliser des workflows avec le contrôle de rapprochement de factures, vérifiez que le champ Valider la facture avec les non-correspondances est défini sur Autoriser avec avertissement pour ne pas avoir à l'approuver plusieurs fois.  
    * Dans le champ Mettre à jour automatiquement le statut d'en-tête des factures, sélectionnez si le rapprochement sera effectué automatiquement lors de la saisie de données des factures par le système. Le paramètre recommandé est Oui, sauf si vous rencontrez des soucis de performances de saisie de données. La désactivation des mises à jour automatiques peut accélérer les performances du système car le contrôle de rapprochement de factures est ignoré lors de la saisie de données. L'assistant chargé de saisir les données devra mettre à jour manuellement le statut des factures pour afficher les résultats du contrôle de rapprochement lorsque ce paramètre est défini sur Non.  
4. Activez ou désactivez l'extension de la section Rapprochement des totaux de facture.
5. Activez ou désactivez la case à cocher Mettre en correspondance les totaux de la facture pour rapprocher les totaux réels de la facture avec ceux prévus.
    * Sélectionnez si une icône doit être affichée quand un écart pour le rapprochement de factures dépasse la tolérance. Vous pouvez sélectionner d'afficher l'icône quand un écart positif dépasse la tolérance, ou quand un écart positif OU négatif dépasse la tolérance.  
    * Par exemple, la tolérance est de 5 % et le montant total de la facture sur la commande fournisseur est 100,00. Par conséquent, une icône de correspondance des prix s'affiche si le montant total de la facture dépasse 105,00. Si vous sélectionnez Si supérieur ou inférieur à la tolérance, l'icône s'affiche également si le montant de la facture est inférieur à 95,00.  
6. Entrez un nombre dans le champ Pourcentage de tolérance des totaux de facture.
7. Activez ou désactivez l'extension de la section Prix et correspondance de quantité.
    * Le champ Stratégie de rapprochement des lignes permet de sélectionner une valeur à utiliser comme stratégie par défaut pour l'entité juridique avec laquelle vous travaillez. « Non obligatoire » signifie qu'il n'y a pas de vérification entre les prix indiqués dans les lignes de facture pour le prix d'une commande fournisseur ou les quantités facturées et les quantités indiquées sur le bon de livraison. « Rapprochement à deux facteurs » signifie que la vérification des lignes de facture est requise mais que seule la commande fournisseur et les documents de facturation du fournisseur sont impliqués dans la vérification. L'accusé de réception de marchandises n'est pas factorisé dans les validations de rapprochement. « Rapprochement à trois facteurs » signifie que le prix unitaire net de la facture sera comparé au prix unitaire net de la commande fournisseur et la quantité de l'accusé de réception de marchandises rapprochée sera comparée à la quantité de la facture.  
    * Si vous utilisez une stratégie de rapprochement avec le rapprochement à deux ou à trois facteurs, vous pouvez paramétrer des pourcentages de tolérance de prix pour l'entité juridique, les articles et les fournisseurs dans la page Tolérance de prix d'article. Lors de la comparaison des factures fournisseur avec les informations des commandes fournisseur, le pourcentage de tolérance de prix applicable est recherché.  
8. Sélectionnez une option dans le champ Stratégie de rapprochement des lignes.
    * Pour autoriser l'application d'un autre niveau de correspondance sur un article, un fournisseur, une combinaison de fournisseur et d'article ou une ligne de commande fournisseur, sélectionnez une valeur dans le champ Autoriser le remplacement de la stratégie de rapprochement. La stratégie de rapprochement de ligne pour les fournisseurs peut être remplacée pour un fournisseur, un article ou une combinaison de fournisseurs et d'articles dans la page Stratégie de rapprochement.  
    * Pour faire correspondre les totaux de prix pour les lignes des factures, sélectionnez une valeur dans le champ Mettre en correspondance les prix totaux. Ce type de rapprochement est utile lorsque le fournisseur soumet plusieurs factures pour la même ligne de commande fournisseur. Vous pouvez comparer les informations de prix relatives au montant net de chaque ligne de la facture et de toutes les lignes de facture en attente et précédemment validées avec le montant net de la ligne de commande fournisseur correspondante.  
9. Sélectionnez une option dans le champ Mettre en correspondance les prix totaux.
10. Entrez un nombre dans le champ Tolérance du prix d'achat total.
11. Activez ou désactivez l'extension de la section Mise en correspondance des frais.
12. Pour faire correspondre les frais réels avec les frais prévus, selon les informations sur la commande fournisseur, activez la case à cocher Mettre en correspondance les frais.
13. Fermez la page.


