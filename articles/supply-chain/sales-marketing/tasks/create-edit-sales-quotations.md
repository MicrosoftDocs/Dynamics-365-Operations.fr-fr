--- 
title: "Créer et modifier des devis de vente"
description: "Cette procédure illustre comment créer et mettre à jour un devis de vente."
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8e7d2198b4976a6f60f05690d7b6f11f3da55e28
ms.openlocfilehash: 7ffa4fe8d87db5b3f8293ec9dbc042496d09d6e3
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-and-edit-sales-quotations"></a>Créer et modifier des devis de vente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure illustre comment créer et mettre à jour un devis de vente. Vous pouvez exécuter cette procédure avec vos propres données ou avec la société fictive de démonstration USMF.


## <a name="create-a-sales-quotation"></a>Créer un devis de vente
1. Accédez à Ventes et marketing > Devis de vente > Tous les devis.
2. Cliquez sur Nouveau.
3. Dans le champ Type de compte, sélectionnez « Prospect ».
4. Dans le champ Prospect, saisissez ou sélectionnez une valeur.
5. Développez la section Général.
    * Étant donné que vous avez choisi de créer un devis à partir de la zone Ventes et marketing, le type est automatiquement défini sur Devis de vente. Pour créer un devis pour un projet, vous devez y accéder à partir du module Gestion et comptabilité des projets.   
6. Cliquez sur OK.
    * Les champs et les actions sur les lignes de devis sont très similaires à celles sur les lignes de commande client.   Comme les commandes client, les devis peuvent être créés pour un article spécifique ou, lorsque le numéro d'article n'est pas connu ou n'existe pas au moment de la création du devis, les devis peuvent être créés pour une catégorie de vente.  
7. Dans le champ Article, saisissez ou sélectionnez une valeur.
8. Dans le champ Article, tapez une valeur.
9. Fermez la page.
10. Dans le champ Quantité, entrer un numéro.
    * S'il existe des accords commerciaux valides pour l'article sélectionné sur la ligne, le prix et les remises applicables sont automatiquement copiés sur la ligne de devis. Vérifiez que le champ Prix unitaire contient une valeur ; vous pouvez également entrer des valeurs de remise si vous le souhaitez.  
11. Cliquez sur Enregistrer.
12. Cliquez sur Devis de vente dans le volet Actions.
13. Cliquez sur Totaux.
14. Cliquez sur OK.
15. Cliquez sur Ligne du devis de vente.
16. Cliquez sur Prix.
    * Dans la page Exécuter la simulation de prix, vous pouvez expérimenter le réglage du produit espéré ou de la rentabilité de votre devis en fonction du prix unitaire, du montant de remise, du pourcentage de remise, du montant total, de la marge, ou du taux de contribution souhaités.   Lorsque vous êtes satisfait des chiffres à atteindre, vous appliquez la suggestion à la ligne de devis, et ses champs associés au prix sont mis à jour en conséquence.  
    * Vous pouvez créer autant de simulations de prix que vous le souhaitez. Lorsque vous cliquez sur Nouveau, les conditions tarifaires issues de la ligne de devis actuelle sont copiées vers la page. Vous pouvez ensuite modifier les valeurs dans n'importe quel champ associé aux tarifs en valeurs cibles. La modification de l'un des champs déclenche le nouveau calcul dans tous les autres champs. Pour que le système calcule le taux de marge et de contribution, le coût unitaire du produit doit être connu. Utilisez l'onglet Prix simulés pour voir la vue détaillée des prix d'origine, des modifications proposées et de leurs effets sur les totaux du devis.   En règle générale, lorsqu'une simulation qui définit un nouveau montant est appliquée à la ligne de devis, le système recalcule et entre une nouvelle valeur dans le champ Prix unitaire. Si la simulation est basée sur une nouvelle marge ou un nouveau taux de contribution, seul le montant HT du champ est mis à jour, et le prix unitaire est laissé vide. Dans les deux cas, les remises qui existaient sur la ligne de devis avant la simulation est supprimée.  
17. Fermez la page.
18. Cliquez sur Devis dans le volet Actions.
19. Cliquez sur Envoyer le devis.
20. Sélectionnez Oui dans le champ Imprimer le devis.
21. Cliquez sur OK.
    * La génération de l'état peut prendre une minute. Ne pas fermez la page avant qu'elle soit terminée.  
22. Fermez la page.

## <a name="update-a-sales-quotation"></a>Mettre à jour un devis de vente
1. Cliquez sur Suivi dans le volet Actions.
2. Cliquez sur Convertir en client.
3. Tapez une valeur dans le champ Compte client.
4. Cliquez sur Vérifier.
    * Vérifiez qu'apparaît un message indiquant que le numéro de compte que vous avez tapé est disponible pour l'utilisation.  
5. Cliquez sur OK.
    * Le système a maintenant créé un nouveau compte client pour le prospect du devis.  
6. Fermez la page.
7. Cliquez sur Suivi dans le volet Actions.
8. Cliquez sur Confirmer.
9. Dans le champ Motif, saisissez ou sélectionnez une valeur.
10. Cliquez sur OK.
11. Cliquez sur Général dans le volet Actions.
12. Cliquez sur Commandes client.
13. Fermez la page.


