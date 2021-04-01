---
title: Paramétrer les règles de commission sur les ventes
description: Cette procédure vous montre comment paramétrer et activer le calcul et le suivi des commissions sur les ventes.
author: omulvad
manager: tfehr
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionCustomerGroup, CommissionItemGroup, CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, CommissionCalc, InventPosting, CustTable, EcoResProductDetailsExtended, CommissionEmplSalesGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab352e1174dbee65f676c5b9bae45f2947dbcd6f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232252"
---
# <a name="set-up-sales-commission-rules"></a>Paramétrer les règles de commission sur les ventes

[!include [banner](../../includes/banner.md)]

Cette procédure vous montre comment paramétrer et activer le calcul et le suivi des commissions sur les ventes. La procédure montre comment créer des groupes de commissions client et article, puis lier un client et un produit sélectionnés aux groupes respectifs. Ces groupes sont alors utilisés dans le paramétrage du calcul de la commission pour créer une combinaison client, article et commercial qui doit être mise en correspondance avec la commande client pour que le commercial ait droit à la commission. La création des groupes de commissions client et articles est facultative, comme le calcul de la commission peut également être effectué pour un client et/ou un article individuels. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.


## <a name="set-up-commission-groups-and-commission-rates"></a>Paramétrer les groupes de commissions et les taux de commission
1. Accédez à **volet Navigation > Modules > Ventes et marketing > Commissions > Groupes de clients pour la commission**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Groupe**, tapez une valeur.
4. Tapez une valeur dans le champ **Nom**.
5. Sélectionnez **Enregistrer**.
6. Fermez la page.
7. Accédez à **volet Navigation > Modules > Ventes et marketing > Commissions > Groupes d’articles**.
8. Sélectionnez **Nouveau**.
9. Dans le champ **Groupe**, tapez une valeur.
10. Tapez une valeur dans le champ **Nom**.
11. Sélectionnez **Enregistrer**.
12. Fermez la page.
13. Accédez à **Ventes et marketing > Commissions > Groupes de ventes**.
    - Un groupe de ventes de commission spécifie les employés dans les rôles de commercial qui sont éligibles à recevoir une commission lorsqu’un client associé au groupe de ventes approprié achète certains articles.  
    - Dans les données de démonstration de la société fictive USMF, il existe un groupe de ventes appelé « Commerciaux US ».  
14. Dans le **volet Actions**, sélectionnez **Général**.
15. Cliquez sur **Commercial**. La page Commercial affiche la liste des commerciaux de la société qui sont associés à un groupe de commission spécifique. Vous pouvez affecter plusieurs commerciaux au même groupe et définir leur part respective de la commission totale sous la forme d’un pourcentage. Le total des parts de la commission partagée entre les employés ne doit pas dépasser 100. 
16. Dans la liste, marquer la ligne sélectionnée.
17. Sélectionnez **Modifier**.
18. Définissez la **part de commission** sur 50.
19. Cliquez sur **Nouveau**.
20. Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
21. Utilisez le **Filtre rapide** pour rechercher les enregistrements. Par exemple, filtrez sur le champ Nom avec une valeur « Susan Burk ».
22. Cliquez sur **Sélectionner**.
23. Définissez la **part de commission** sur 50.
24. Cliquez sur **Enregistrer**.
25. Accédez à **Ventes et marketing > Commissions > Calcul de la commission**. Sur la page **Calcul de la commission**, vous définissez le taux de commission que l’employé doit recevoir pour une transaction de vente lorsqu’elle contient la combinaison pré-établie du client et du produit. Dans le cadre du paramétrage du taux de commission, vous devez spécifier la base du calcul de la commission et si elle doit inclure ou exclure les remises. Vous pouvez également entrer une période de validité du taux de commission.  
26. Cliquez sur **Nouveau**.
27. Sélectionnez « Groupe » dans le champ **Code article**.
28. Dans le champ **Relation d’article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
29. Dans la liste, localisez et sélectionnez le groupe que vous avez créé précédemment.
30. Dans le champ **Code client**, sélectionnez ’Groupe’.
31. Dans le champ **Relation client**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
32. Dans la liste, localisez et sélectionnez le groupe que vous avez configuré précédemment.
33. Dans le champ **Relation de commercial**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
34. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    - Conservez l’option « Avant remise ligne. »  
    - Conservez l’option « Produit » comme base du calcul de la valeur de la commission.    
35. Entrez un nombre dans le champ Pourcentage de commission.
36. Cliquez sur **Enregistrer**.

## <a name="setting-up-commission-posting"></a>Paramétrage de la validation de commission
1. Accédez à **volet Navigation > Ventes et marketing > Commissions > Validation de la commission**. Les taxes de commissions sont payables aux employés et doivent donc être paramétrées pour assurer la validation financière correcte dans les comptes correspondants dans la **comptabilité**. Cela est effectué dans la page **Validation de commission**. Examinez le paramétrage disponible pour la société actuelle. Généralement, les montants de commission sont validés dans un compte de dépenses dédié et sont compensés un compte payable dédié. Si vous n’avez pas de règles de validation de commission paramétrées, le système ne parviendra pas à facturer une commande client dont les commissions sont éligibles.  
2. Fermez la page.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Affecter un groupe de commissions à un client et à un produit
1. Accédez à **volet Navigation > Modules > Ventes et marketing > Clients > Tous les clients**.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur **Modifier**.
5. Développez la section des **valeurs par défaut des commandes clients**.
6. Dans le champ **Groupe de commissions**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, localisez et sélectionnez le groupe que vous avez créé précédemment.
8. Dans le champ **Groupe de ventes**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
10. Cliquez sur **Enregistrer**.
11. Accédez à **Volet de navigation > Modules > Gestion d’informations sur les produits > Produits > Produits lancés**.
12. Utilisez le **Filtre** pour rechercher les enregistrements. Par exemple, filtrez sur le champ Numéro d’article avec une valeur de « T0020 ».
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
14. Cliquez sur **Modifier**.
15. Développez la section **Vendre**.
16. Dans le champ **Groupe de commissions**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
17. Dans la liste, localisez et sélectionnez le groupe de commissions que vous avez créé précédemment.
18. Sélectionnez **Enregistrer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]