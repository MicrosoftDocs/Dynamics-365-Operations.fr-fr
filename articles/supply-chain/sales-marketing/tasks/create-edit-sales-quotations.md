---
title: Créer et modifier des devis de vente
description: Cette procédure illustre comment créer et mettre à jour un devis de vente.
author: omulvad
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable, CustQuotationConfirmationJournal, CustQuotationJournal, CustSalesLines, SalesQuotationCopying, SalesQuotationDeleteQuotations, SalesQuotationListPagePreviewPane, SalesQuotationTypeGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 73c15b41a4b0979ec79c8dbd8d88627bffcf6ed3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427694"
---
# <a name="create-and-edit-sales-quotations"></a>Créer et modifier des devis de vente

[!include [banner](../../includes/banner.md)]

Cette procédure illustre comment créer et mettre à jour un devis de vente. Vous pouvez exécuter cette procédure avec vos propres données ou avec la société fictive de démonstration USMF.


## <a name="create-a-sales-quotation"></a>Créer un devis de vente
1. Accédez à **Volet de navigation > Modules > Ventes et marketing > Devis de vente > Tous les devis**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Type de compte**, sélectionnez Prospect.
4. Dans le champ **Prospect**, tapez ou sélectionnez une valeur.
5. Développez la section **Général**. Étant donné que vous avez choisi de créer un devis à partir de la zone Ventes et marketing, le type est automatiquement défini sur Devis de vente. Pour créer un devis pour un projet, vous devez y accéder à partir du module **Gestion et comptabilité des projets**.
6. Cliquez sur **OK**. Les champs et les actions sur les lignes de devis sont très similaires à celles sur les lignes de commande client.   Comme les commandes client, les devis peuvent être créés pour un article spécifique ou, lorsque le numéro d'article n'est pas connu ou n'existe pas au moment de la création du devis, les devis peuvent être créés pour une catégorie de vente.     
7. Dans le champ **Article**, saisissez ou sélectionnez une valeur.
8. Tapez une valeur dans le champ **Site**.
9. Entrez un nombre dans le champ **Quantité**. S'il existe des accords commerciaux valides pour l'article sélectionné sur la ligne, le prix et les remises applicables sont automatiquement copiés sur la ligne de devis. Vérifiez que le champ Prix unitaire contient une valeur ; vous pouvez également entrer des valeurs de remise si vous le souhaitez. 
10. Cliquez sur **Enregistrer**.
11. Dans le **volet Actions**, cliquez sur **Devis de vente**.
12. Cliquez sur **Totaux**.
13. Cliquez sur **OK**.
14. Sélectionnez la ligne de devis de vente.
15. Dans le **volet Actions**, cliquez sur **Devis**.
16. Cliquez sur **Simulation de prix**.
    - Dans la page **Exécuter la simulation de prix**, vous pouvez expérimenter le réglage du produit espéré ou de la rentabilité de votre devis en fonction du prix unitaire, du montant de remise, du pourcentage de remise, du montant total, de la marge, ou du taux de contribution souhaités. Lorsque vous êtes satisfait des chiffres à atteindre, vous appliquez la suggestion à la ligne de devis, et ses champs associés au prix sont mis à jour en conséquence.  
    - Vous pouvez créer autant de simulations de prix que vous le souhaitez. Lorsque vous cliquez sur **Nouveau**, les conditions tarifaires issues de la ligne de devis actuelle sont copiées vers la page. Vous pouvez ensuite modifier les valeurs dans n'importe quel champ associé aux tarifs en valeurs cibles. La modification de l'un des champs déclenche le nouveau calcul dans tous les autres champs. Pour que le système calcule le taux de marge et de contribution, le coût unitaire du produit doit être connu. Utilisez l'onglet Prix simulés pour voir la vue détaillée des prix d'origine, des modifications proposées et de leurs effets sur les totaux du devis. En règle générale, lorsqu'une simulation qui définit un nouveau montant est appliquée à la ligne de devis, le système recalcule et entre une nouvelle valeur dans le champ Prix unitaire. Si la simulation est basée sur une nouvelle marge ou un nouveau taux de contribution, seul le montant HT du champ est mis à jour, et le prix unitaire est laissé vide. Dans les deux cas, les remises qui existaient sur la ligne de devis avant la simulation est supprimée.
17. Dans le **volet Actions**, cliquez sur **Devis**.
18. Cliquez sur **Envoyer le devis**.
19. Sélectionnez Oui dans le champ **Imprimer le devis**.
20. Cliquez sur **OK**. La génération de l'état peut prendre une minute. Ne pas fermez la page avant qu'elle soit terminée.

## <a name="update-a-sales-quotation"></a>Mettre à jour un devis de vente
1. Accédez à **Volet de navigation > Modules > Ventes et marketing > Devis de vente > Tous les devis**.
2. Sur le **volet Actions**, cliquez sur **Suivi**.
3. Cliquez sur **Convertir en client**.
4. Dans le champ **Compte client**, saisissez une valeur.
5. Cliquez sur **Vérifier**. Vérifiez qu'apparaît un message indiquant que le numéro de compte que vous avez tapé est disponible pour l'utilisation.  
6. Cliquez sur **OK**. Le système a maintenant créé un nouveau compte client pour le prospect du devis.  
7. Fermez la page.
8. Sur le **volet Actions**, cliquez sur **Suivi**.
9. Cliquez sur **Confirmer**.
10. Saisissez ou sélectionnez une valeur dans le champ **Motif**.
11. Cliquez sur **OK**.
12. Dans le volet **Actions**, cliquez sur **Général**.
13. Cliquez sur **Commandes client**.
14. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]