---
title: Générer et traiter les remises client
description: Cette procédure illustre comment traiter les remises client de la génération de la réclamation à l’étape pendant laquelle elles passent en régularisations à la comptabilité client.
author: Henrikan
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PdsRebateAgreement, SalesTableListPage, SalesCreateOrder, SalesTable, MCRPriceHistory, SalesEditLines,  PdsRebateTableListPage, MCRBrokerWriteOffReason, MRCHierarchyAddCust, PdsItemRebateGroup, PdsRebate, PdsRebateProgramTMATable, PdsRebateTable, PdsRebateTableListPagePreviewPane, PdsRebateTrans, PdsRebateType_CustLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a85c027571a6d77ed61cd874bb9d97221b099967
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7969085"
---
# <a name="generate-and-process-customer-rebates"></a>Générer et traiter les remises client

[!include [banner](../../includes/banner.md)]

Cette procédure illustre comment traiter les remises client de la génération de la réclamation à l’étape pendant laquelle elles passent en régularisations à la comptabilité client. Elle présente un exemple spécifique pour expliquer la manière dont les différentes conditions sur les lignes de remise affectent les montants finaux qui sont crédités sur le client. Vous devez utiliser la société de données de démonstration USMF, puis effectuer les tâches suivantes avant de commencer le guide : (1) Accédez à la page Paramètres comptabilité et développez l’onglet Prix, puis l’onglet Détails de prix, et vérifier que l’option Activer les détails de prix est définie sur Oui. (2) Accédez à la page Accords de remise et sélectionnez l’accord de remise du client : USMF-000001. Si le champ Statut de l’approbation du workflow n’est pas défini sur Approuvé, vous devez cliquer sur Validation sur le volet Actions pour l’approuver.


## <a name="review-a-customer-rebate-agreement"></a>Consulter un accord de remise client
1. Accédez à **volet Navigation > Modules > Ventes et marketing > Remises client > Accords de remise**.
    - Les quelques étapes suivantes concernent les conditions de l’accord USMF-000001. Ceci facilite la compréhension du calcul des valeurs de crédit client plus loin dans la procédure.  
    - L’accord concerne un client individuel, dans cet exemple, il s’agit du client US-009.  
    - Les remises sont données au client lorsqu’il achète un produit spécifique. Dans ce cas, le produit a le numéro d’article T0020.   
    - Les performances de ventes du client, qui sert à estimer les montants des remises, doivent être accumulées sur une base hebdomadaire.  
    - Le paramètre pour « Prix extrait de » est Brut, ce qui signifie que le montant de vente de cette ligne sur la base de laquelle la réclamation est estimée n’est pas réduit par la remise de ligne.  
    - Le champ de type Saut de ligne de remise indique le mode de calcul des remises. Dans ce cas, l’objectif de vente avec lequel les remises doivent être estimées est défini sur la quantité.   
    - Les lignes de l’accord indiquent le type de montant de remise, la valeur réelle de remise et les seuils. Dans cet exemple, le client bénéficiera d’une remise de 20 EUR par unité vendue, si les achats hebdomadaires du produit varient entre 1 et 50 unités, et d’une remise de 40 EUR par unité, s’il achète plus de 50 unités.  
2. Fermez la page.

## <a name="generate-rebate-claims"></a>Générer des réclamations de remise
1. Accédez à **Volet de navigation > Modules > Ventes et marketing > Commandes client > Toutes les commandes client**.
2. Cliquez sur **Nouveau**. Pour simuler la manière dont les réclamations de remise seraient générées, la tâche suivante consiste à créer une commande client, dans laquelle le produit et la quantité permettront au client en question de bénéficier d’une remise.    
3. Entrez ou sélectionnez une valeur dans le champ **Compte client**.
4. Cliquez sur **OK**.
5. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.
6. Définissez le champ **Quantité** sur « 40 ».
7. Sous la section **Lignes de commande client**, cliquez sur **Ligne de commande client**.
8. Cliquez sur **Détails du prix.** Si vous ne voyez pas cette option, cela est dû au fait que vous n’avez pas défini l’option **Activer les détails des prix** sur Oui avant de commencer le guide.     
9. Développer la section **Remises**. L’onglet **Remise** répertorie tous les accords de remise qui s’appliquent à la ligne de commande actuelle et affiche le montant estimé de remise. Notez que les montants affichés ne sont que des indications de ce que pourraient être les futures réclamations de remise. Les montants réels de remise peuvent être différents selon : le volume de ventes total atteint par le client dans le cadre d’un accord périodique de remise ; que le client avait retourné tout ou partie ou des quantités ; et que la commande client applicable a été facturée.
10. Fermez la page.
11. Cliquez sur **Ajouter une ligne**.
12. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.
13. Définissez le champ **Quantité** sur « 60 ».
14. Cliquez sur **Enregistrer**.
15. Cliquez sur **Facture** dans le volet **Actions**.
16. Cliquez sur **Facture**.
17. Développez la section **Paramètres**.
18. Dans le champ **Quantité**, sélectionnez ’Tout’.
19. Cliquez sur **OK**.
20. Cliquez sur **OK**.

## <a name="process-rebate-claims"></a>Traiter les réclamations de remise
1. Accédez à **volet Navigation > Modules > Ventes et marketing > Remises client > Remises**.
    - La page Remises agit comme une console dans laquelle vous pouvez réviser, approuver et traiter des réclamations de remise. Vous allez maintenant traiter les réclamations créées suite à la facturation d’une commande client pour le client US-009, qui fait l’objet de l’accord de remise USMF-000001.   
    - La première ligne représente une réclamation de remise de 800 EUR, basée sur les ventes de 40 unités du produit T0020, calculée à 20 EUR par unité. Ceci satisfait les conditions de la première pause de quantité dans l’accord de remise.  
    - La deuxième réclamation est de 2 400 EUR, basée sur les ventes de 60 unités du produit T0020, calculée à 40 EUR par unité, conformément à la deuxième pause de quantité dans l’accord.  
    - Les deux réclamations sont à l’état « À calculer ». Cela signifie qu’elles sont associées à un accord qui suit les performances de ventes du client sur la base périodique et qu’elles doivent être recalculées pour prendre en compte le volume total des ventes sur la période respective.   
2. Cliquez sur **Cumuler**.
3. Dans le champ **Client**, saisissez ou sélectionnez une valeur.
4. Dans le champ **Date de début**, sélectionnez la date d’aujourd’hui.
5. Cliquez sur **OK**. Conséquemment à l’exécution de la fonction **Cumuler**, le montant estimé de réclamation est désormais ajusté pour prendre en compte le fait que le volume total des ventes du client sur la période de référence est plus élevé que lorsque la première remise a été générée. Plus particulièrement et puisque la quantité totale achetée a atteint 100 unités, le client bénéficie à présent d’une remise de 40 EUR par unité (conformément à la deuxième pause de quantité de l’accord), soit 4,000 EUR de montant total de remise. La différence est enregistrée comme nouvel « ajustement » de réclamation pour les 800 EUR supplémentaires. Le statut des réclamations de remise incluses dans la mise à jour Cumuler est désormais défini sur Calculé. 
6. Dans la liste, marquez toutes les lignes.
7. Cliquez sur **Approuver**.
8. Cliquez sur **Traiter**.
9. Dans le champ **Client**, saisissez ou sélectionnez une valeur.
10. Cliquez sur **OK**. Un message indique que la remise a été traitée correctement et que le statut des réclamations a été modifié sur Marquer. Cela signifie que, suite à la validation d’un journal de régularisation de remise :
    - Les réclamations ont maintenant été transférées vers le solde client temporaire en tant que déductions.
    - Le compte de régularisation Remise a été crédité pour représenter le futur passif du client.
    - Le compte de frais de remise a été débité pour représenter les coûts engagés dans le cadre de la vente.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
