--- 
title: "Paramétrer les règles de commission sur les ventes"
description: "Cette procédure vous montre comment paramétrer et activer le calcul et le suivi des commissions sur les ventes."
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
ms.openlocfilehash: 3d5c38b1f07803242350fe016b45c45d49c0b59b
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-sales-commission-rules"></a>Paramétrer les règles de commission sur les ventes

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous montre comment paramétrer et activer le calcul et le suivi des commissions sur les ventes. La procédure montre comment créer des groupes de commissions client et article, puis lier un client et un produit sélectionnés aux groupes respectifs. Ces groupes sont alors utilisés dans le paramétrage du calcul de la commission pour créer une combinaison client, article et commercial qui doit être mise en correspondance avec la commande client pour que le commercial ait droit à la commission. La création des groupes de commissions client et articles est facultative, comme le calcul de la commission peut également être effectué pour un client et/ou un article individuels. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.


## <a name="set-up-commission-groups-and-commission-rates"></a>Paramétrer les groupes de commissions et les taux de commission
1. Accédez à Ventes et marketing > Commissions > Groupes de clients pour la commission.
2. Cliquez sur Nouveau.
3. Dans le champ Groupe, tapez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Cliquez sur Enregistrer.
6. Fermez la page.
7. Accédez à Ventes et marketing > Commissions > Groupes d'articles.
8. Cliquez sur Nouveau.
9. Dans le champ Groupe, tapez une valeur.
10. Tapez une valeur dans le champ Nom.
11. Fermez la page.
12. Accédez à Ventes et marketing > Commissions > Groupes de ventes.
    * Un groupe de ventes de commission spécifie les employés dans les rôles de commercial qui sont éligibles à recevoir une commission lorsqu'un client associé au groupe de ventes approprié achète certains articles.  
    * Dans les données de démonstration de la société fictive USMF, il existe un groupe de ventes appelé « Commerciaux US ».  
13. Cliquez sur Général dans le volet Actions.
14. Cliquez sur Commercial.
    * La page Commercial affiche la liste des commerciaux de la société qui sont associés à un groupe de commission spécifique. Vous pouvez affecter plusieurs commerciaux au même groupe et définir leur part respective de la commission totale sous la forme d'un pourcentage. Le total des parts de la commission partagée entre les employés ne doit pas dépasser 100.  
15. Dans la liste, marquez la ligne sélectionnée.
16. Cliquez sur Modifier.
17. Définissez la part de commission sur 50.
18. Cliquez sur Nouveau.
19. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
20. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Nom avec une valeur « Susan Burk ».
21. Cliquez sur Sélectionner.
22. Définissez la part de commission sur 50.
23. Cliquez sur Enregistrer.
24. Accédez à Ventes et marketing > Commissions > Calcul de la commission.
    * Dans la page Calcul de la commission, vous définissez le taux de commission que l'employé doit recevoir pour une transaction de vente lorsqu'elle contient la combinaison pré-établie du client et du produit. Dans le cadre du paramétrage du taux de commission, vous devez spécifier la base du calcul de la commission et si elle doit inclure ou exclure les remises. Vous pouvez également entrer une période de validité du taux de commission.  
25. Cliquez sur Nouveau.
26. Sélectionnez Groupe dans le champ Article - valide pour.
27. Dans le champ Relation d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
28. Dans la liste, localisez et sélectionnez le groupe que vous avez créé précédemment.
29. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
30. Sélectionnez « Groupe » dans le champ Code client.
31. Dans le champ Relation client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
32. Dans la liste, localisez et sélectionnez le groupe que vous avez configuré précédemment.
33. Dans le champ Relation de commercial, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
34. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Conservez l'option « Avant remise ligne. »  
    * Conservez l'option « Produit » comme base du calcul de la valeur de la commission.    
35. Entrez un nombre dans le champ Pourcentage de commission.
36. Cliquez sur Enregistrer.

## <a name="setting-up-commission-posting"></a>Paramétrage de la validation de commission
1. Accédez à Ventes et marketing > Commissions > Validation de la commission.
    * Les taxes de commissions sont payables aux employés et doivent donc être paramétrées pour assurer la validation financière correcte dans les comptes correspondants dans la comptabilité. Cela est effectué dans la page Validation de commission. Examinez le paramétrage disponible pour la société actuelle. Généralement, les montants de commission sont validés dans un compte de dépenses dédié et sont compensés un compte payable dédié. Si vous n'avez pas de règles de validation de commission paramétrées, le système ne parviendra pas à facturer une commande client dont les commissions sont éligibles.  
2. Fermez la page.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Affecter un groupe de commissions à un client et à un produit
1. Accédez à Ventes et marketing > Clients > Tous les clients.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Modifier.
5. Développez la section des valeurs par défaut des commandes clients.
6. Dans le champ Groupe de commissions, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, localisez et sélectionnez le groupe que vous avez créé précédemment.
8. Dans le champ Groupe de ventes, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
10. Cliquez sur Enregistrer.
11. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
12. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Numéro d'article avec une valeur de « T0020 ».
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
14. Cliquez sur Modifier.
15. Développez la section Vendre.
16. Dans le champ Groupe de commissions, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
17. Dans la liste, localisez et sélectionnez le groupe de commissions que vous avez créé précédemment.


