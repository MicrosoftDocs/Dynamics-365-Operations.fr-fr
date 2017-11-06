--- 
title: Fournir des contrats de vente
description: "Cette procédure montre comment honorer un contrat de vente en y associant des commandes client."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f0894bf962c139c2e9e4c9f8d1589fd933afcedb
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="fulfill-sales-agreements"></a>Fournir des contrats de vente

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment honorer un contrat de vente en y associant des commandes client. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Avant de lancer ce guide, vérifiez que vous avez un contrat de vente en vigueur du type « Engagement à la valeur du produit ». Dans le cas contraire, vous pouvez exécuter le guide de tâche appelé « Créer des contrats de vente ».  




## <a name="release-a-sales-order-from-the-agreement"></a>Lancer une commande client à partir du contrat
1. Accédez à Ventes et marketing > Contrats de vente > Contrats de vente.
2. Dans la liste, ouvrez l'accord avec lequel vous souhaitez lancer la commande.
3. Dans le volet Actions, cliquez sur Contrats de vente.
4. Cliquez sur Lancer la commande.
    * Comme l'indique le texte en haut de la page Créer un ordre de lancement, les détails requis pour les lignes de commande client seront différents selon que l'accord est fondé sur la quantité ou sur la valeur.  
    * Dans ce guide, l'accord est du type « Engagement à la valeur du produit ». C'est pourquoi la section Lignes de cette page est vide. Si l'engagement était fondé sur la quantité, les informations de ligne seraient copiées à partir de l'accord.  
5. Cliquez sur Créer.
    * Le message vous indique qu'une commande fournisseur a été créée. Étant donné que la commande ne contient aucune ligne, vous devez ajouter des détails de ligne de commande pour compléter le processus de lancement.   
6. Fermez la page.
7. Fermez la page.
8. Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.
9. Dans la liste, cherchez et ouvrez la commande qui a été créée suite au lancement de commande de la tâche précédente.
10. Cliquez sur Ajouter une ligne.
11. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
12. Dans le champ Numéro d'article, tapez ou sélectionnez l'article spécifié dans le contrat de vente associé.
13. Dans le champ Quantité, entrer un numéro.
    * Assurez-vous d'entrer une quantité qui porte le montant HT sous la valeur du contrat de vente associé.  
    * Notez que, comme la commande client est liée à l'accord, le pourcentage de remise négocié est appliqué à la ligne de commande.  
14. Cliquez sur Mettre à jour la ligne.
15. Cliquez sur Joint.
    * La page Accord joint affiche l'ID et les conditions de l'accord à partir duquel la ligne est lancée.  
16. Fermez la page.
17. Cliquez sur Général dans le volet Actions.
18. Cliquez sur Contrat de vente joint.
19. Développez la section Détails de ligne.
20. Cliquez sur l'onglet Exécution.
    * L'onglet Exécution indique un récapitulatif de toutes les lignes de commande client associées à cet engagement et leur état d'exécution, ainsi que le montant ou la quantité qui n'ont pas encore été lancés.   
21. Fermez la page.
22. Fermez la page.
23. Fermez la page.

## <a name="apply-sales-agreement-in-the-order-process"></a>Appliquer un contrat de vente dans le processus de commande
1. Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cherchez et sélectionnez le client spécifié dans le contrat de vente.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Développez la section Général.
7. Dans le champ ID Contrat de vente, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Cliquez sur Oui.
10. Cliquez sur OK.
11. Dans la liste, marquez la ligne sélectionnée.
12. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
13. Dans le champ Numéro d'article, tapez ou sélectionnez l'article spécifié dans le contrat de vente associé.
14. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
15. Cliquez sur Enregistrer.
16. Cliquez sur Prélever et emballer dans le volet Actions.
17. Cliquez sur Validation du bon de livraison.
18. Développez la section Paramètres.
19. Sélectionnez Oui dans le champ Validation.
20. Cliquez sur OK.
21. Cliquez sur OK.
22. Cliquez sur Général dans le volet Actions.
23. Cliquez sur Contrat de vente joint.
24. Cliquez sur l'onglet Exécution.


