---
title: Transférer des transactions dans la déclaration d’échanges de biens
description: Cette procédure vous guide dans le paramétrage des paramètres de déclaration d’échanges de biens et le transfert des transactions dans la déclaration d’échanges de biens.
author: Anasyash
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm, DeliveryReason, DeliveryTerms, DestinationCode
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c9a5037f9e5381c61b72947d85bf07d571fe094d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982095"
---
# <a name="transfer-transactions-to-the-intrastat"></a>Transférer des transactions dans la déclaration d’échanges de biens

[!include [banner](../../includes/banner.md)]

Cette procédure vous guide dans le paramétrage des paramètres de déclaration d’échanges de biens et le transfert des transactions dans la déclaration d’échanges de biens. Cette procédure a été créée à l’aide des données fictives de la société DEMF.


## <a name="create-new-and-update-existing-commodity-code"></a>Crée et mettre à jour un code marchandise existant
1. Dans le volet de navigation, allez dans **Modules > Gestion des informations sur les produits > Configuration > Catégories et attributs > Hiérarchies de catégories**.
2. Dans la liste, recherchez ou sélectionnez l’enregistrement **Codes marchandise de la déclaration d’échanges de biens**.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Sélectionnez un enregistrement dans l’arborescence. Sélectionnez **Déclaration d’échanges de biens\Haut-parleur**, par exemple.  
5. Cliquez sur **Modifier**.
6. Développez le raccourci **Commerce extérieur**.
7. Entrez ou sélectionnez une valeur dans le champ **Unités additionnelles**. Sélectionnez **pcs**, par exemple.  
8. Sélectionnez **Oui** dans le champ **Poids non applicable**.
9. Sélectionnez **Déclaration d’échanges de biens** dans l’arborescence.
10. Cliquez sur **Nouveau nœud de catégorie**.
11. Entrez le nom de la marchandise dans le champ **Nom**. Entrez **Autre marchandise**, par exemple.  
12. Entrez le code marchandise dans le champ **Code**. Entrez **995 00 00**, par exemple.  
13. Dans le champ Nom convivial, saisissez une valeur. Entrez **Autre**, par exemple.  
14. Cliquez sur **Enregistrer**.
15. Fermez la page.

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a>Affecter un code marchandise à la hiérarchie des produits et au produit lancé
1. Utilisez le filtre rapide pour rechercher des enregistrements. Par exemple, filtrez le champ **Nom** avec la valeur **ventes**.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
3. Dans l’arborescence, développez un **nœud de catégorie**. Développez **Hiérarchie de vente\Audio d’accueil**, par exemple.  
4. Dans l’arborescence, sélectionnez la **catégorie à affecter au code marchandise**. Sélectionnez **Hiérarchie de vente\Audio d’accueil\Haut-parleurs, par exemple.  
5. Développez le raccourci **Codes marchandise**.
6. Cliquez sur **Ajouter**.
7. Sélectionnez **Déclaration d’échanges de biens** dans le champ **Sélectionner une hiérarchie**.
8. Dans la liste, recherchez et sélectionnez le code marchandise. Sélectionnez **Haut-parleur 920 20 34**, par exemple.  
9. Cliquez sur la flèche droite pour sélectionner le code.
10. Cliquez sur **OK**.
11. Dans le volet de navigation, allez dans **Modules > Gestion d’informations sur les produits > Produits > Produits lancés**.
12. Dans la liste, choisissez le produit lancé à affecter au code marchandise. Sélectionnez **D0001**, par exemple.  
13. Cliquez sur **Modifier**.
14. Développez le raccourci **Commerce extérieur**.
15. Entrez le code marchandise dans le champ **Marchandise**. Sélectionnez la valeur **Haut-parleur 920 20 34**, par exemple.    
16. Entrez un nombre dans le champ **Pourcentage de frais**. Par exemple, entrez **3**.  
17. Dans le champ **Pays/Région**, entrez ou sélectionnez un pays ou une région d’origine. Par exemple, sélectionnez **AUT**.  
18. Développez le raccourci **Gérer le stock**.
19. Entrez un poids en kg dans le champ **Poids net**. Par exemple, entrez **2,5**.  
20. Cliquez sur **Enregistrer**.

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a>Paramétrer des codes de transaction de déclaration d’échanges de biens et des paramètres de commerce extérieur
1. Dans le volet de navigation, allez dans **Modules > Taxe > Paramétrage > Commerce extérieur > Codes transaction**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Code transaction**. Entrez **21**, par exemple pour le code de transaction utilisé comme retour.  
4. Tapez le nom du code de transaction dans le champ **Nom**. Entrez **Retour**, par exemple.  
5. Sélectionnez une option dans le champ **Montant statistique**. Sélectionnez **Vide**, par exemple, ce qui indique que la valeur statistique à déclarer pour les transactions avec le code transaction **21** est toujours zéro.  
6. Dans le volet de navigation, allez dans **Modules > Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur**.
7. Entrez ou sélectionnez une valeur dans le champ **Code transaction**. Par exemple, sélectionnez **11**.  
8. Entrez ou sélectionnez une valeur dans le champ **Avoir**. Cette valeur identifie également le retour physique. L’avoir pour le retour physique est transféré dans le journal de déclaration d’échanges de biens dans le sens opposé. Par exemple, le retour de l’arrivée est transféré en tant qu’expédition.   Sinon, l’avoir est considéré comme une correction et il est transféré avec le même sens et le signe contraire. Par exemple, la correction de l’arrivée est transférée sous la forme d’une arrivée avec un montant négatif et la balise active est définie sur **Correction**.  
9. Développez le raccourci **Transférer**.
10. Sélectionnez **Oui** dans le champ **Articles avec code marchandise**. Sélectionnez cette option pour transférer uniquement les transactions ayant un code marchandise affecté. Les transactions sans code marchandise ne sont pas **transférées à la déclaration d’échanges de biens.  
11. Sélectionnez une option dans le champ **Transférer en cas de réalisation du critère**. Sélectionnez **Un des critères**, par exemple.  
12. Développez la section **Hiérarchie des nomenclatures douanières**.
13. Cliquez sur l’onglet **Propriétés de pays/régions**.
14. Cliquez sur **Nouveau**.
15. Dans le champ **Pays/Région**, sélectionnez ou entrez une valeur. Sélectionnez la valeur **FRA**, par exemple.  
16. Entrez le code pays ISO pour le pays dans le champ **Code de déclaration d’échanges de biens**.  Entrez **FR**, par exemple.  
17. Dans le champ **Type de pays/région**, sélectionnez **UE**.
18. Cliquez sur l’onglet Souches de numéros.

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a>Paramétrer des modes de livraison et des règles pour inclure les frais de déclaration d’échanges de biens
1. Dans le volet de navigation, allez dans **Modules > Ventes et marketing > Paramétrage > Distribution > Modes de livraison**.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. Sélectionnez **20 Air**, par exemple.  
3. Développez le raccourci **Commerce extérieur**.
4. Cliquez sur **Modifier**.
5. Entrez ou sélectionnez une valeur dans le champ **Transport**. Par exemple, sélectionnez **02**.  
6. Dans le volet de navigation, accédez à **Modules > Comptabilité client > Paramétrage des frais > Code frais**.
7. Utilisez le filtre rapide pour rechercher des enregistrements. Par exemple, filtrez le champ Code frais avec la valeur **transport**.
8. Développez le raccourci **Commerce extérieur**.
9. Cliquez sur **Modifier**.
10. Sélectionnez **Oui** dans le champ **Valeur de la facture de la déclaration d’échanges de biens**. Le montant est transféré dans le champ **Frais de la facture** et il est résumé avec le montant transféré dans le champ Montant de la facture. Sélectionnez **Oui** dans le champ **Valeur statistique de la déclaration d’échanges de biens** si la quantité de modifications doit être transférée vers le champ **Frais statistiques** et être récapitulée avec le champ **Montant statistique**.  

## <a name="sell-products-for-eu-customers"></a>Vendre des produits pour les clients de l’UE
1. Dans le volet de navigation, allez dans **Modules > Comptabilité client > Commandes > Toutes les commandes client**.
2. Cliquez sur **Nouveau**.
3. Sélectionnez un client de l’UE dans le champ **Compte client**. Sélectionnez **DE-012 Litware Retail**, par exemple.  
4. Développez le raccourci **Livraison**.
5. Entrez ou sélectionnez une valeur dans le champ **Mode de livraison**. Sélectionnez **20 Air**, par exemple.  
6. Cliquez sur **OK**.
7. Sélectionnez la première ligne des lignes de commande client.
8. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**. Par exemple, sélectionnez **D001**.  
9. Développez le raccourci **Détails de ligne**.
10. Cliquez sur l’onglet **Commerce extérieur**. Le transport est renseigné automatiquement à partir du mode de livraison sélectionné.  
11. Entrez ou sélectionnez une valeur dans le champ **Port**.
12. Cliquez sur **Finances**. Conformément aux paramètres, ce montant sera inclus dans la **valeur de la facture de la déclaration d’échanges de biens**.  
13. Cliquez sur **Tenir les frais à jour**.
14. Entrez ou sélectionnez une valeur dans le champ **Code frais**. Sélectionnez **FREIGHT**, par exemple.  
15. Activez la case à cocher **Conserver**.
16. Dans le champ **Valeur des frais**, entrez un nombre. Par exemple, entrez **10**.  
17. Cliquez sur **Enregistrer**.
18. Fermez la page.
19. Cliquez sur **Facture** dans le volet Actions.
20. Cliquez sur **Facture**.
21. Développez la section **Paramètres**.
22. Sélectionnez **Tout** dans le champ **Quantité**.
23. Développez le raccourci **Paramétrage**.
24. Entrez une date dans le champ **Date de facture**. Par exemple, entrez **31-01-2015**.  
25. Cliquez sur **OK**.
26. Cliquez sur **OK**.
27. Fermez la page.
28. Cliquez sur **Nouveau**.
29. Sélectionnez un client de l’UE dans le champ **Compte client**. Sélectionnez **DE-013 Trey Wholesales**, par exemple.
30. Cliquez sur **OK**.
31. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**. Par exemple, sélectionnez **D0001**.  
32. Cliquez sur **Enregistrer**.
33. Cliquez sur **Facture**.
34. Entrez une date dans le champ **Date de facture**. Entrez la date **31-01-2015**, par exemple.  
35. Cliquez sur **OK**.
36. Cliquez sur **OK**.

## <a name="transfer-transactions-to-the-intrastat"></a>Transférer des transactions dans la déclaration d’échanges de biens
1. Dans le volet de navigation, allez dans **Modules > Taxe > Déclarations > Commerce extérieur > Déclaration d’échange de biens**.
2. Cliquez sur **Transférer**.
3. Sélectionnez **Oui** dans le champ **Facture client**.
4. Cliquez sur **Filtre**.
5. Dans la liste, marquez la ligne avec la **date**.
6. Tapez une valeur dans le champ **Critères**. Par exemple, entrez le filtre pour janvier 2015 (la valeur exacte dépend du format de date) : 1/1/2015..31/1/2015  
7. Cliquez sur **OK**.
8. Cliquez sur **OK**.
9. Dans la liste, recherchez et sélectionnez l’enregistrement transféré.
10. Cliquez sur l’onglet **Général**.
    
Examinez les données transférées, notamment pays\la région de destination/d’expédition, pays d’origine, poids, quantité, quantité en unités supplémentaires, marchandise, code de transaction, montants facturés et montants statistiques. Vous pouvez modifier les données, le cas échéant.  

