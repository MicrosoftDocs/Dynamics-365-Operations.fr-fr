---
title: Utilisation du programme périodique
description: Cette procédure vous guide dans la vente d'un programme périodique et le traitement des commandes client associées.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2baf0127a35cc62952fd78daaf8204d35ec8d2b3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412297"
---
# <a name="using-continuity-program"></a>Utilisation du programme périodique

[!include [banner](../includes/banner.md)]

Cette procédure vous guide dans la vente d'un programme périodique et le traitement des commandes client associées. Pour exécuter cette procédure, l'utilisateur doit être configuré comme utilisateur du centre d'appels. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Retail et Commerce > Clients > Service client.
2. Dans le champ SearchText, tapez « Karen », puis appuyez sur la touche Tab.
    * La boîte de dialogue de recherche avancée doit s'afficher. Si elle ne s'affiche pas, cliquez sur Rechercher à droite de ce champ.  
3. Dans la liste, marquez la ligne sélectionnée.
    * Il ne doit y avoir qu'une ligne portant la mention Karen Berg. Sélectionnez la ligne en cliquant sur la colonne à l'extrême gauche de la grille.  
4. Cliquez sur Sélectionner.
5. Cliquez sur Nouvelle commande client.
    * Il est conseillé de noter le numéro de la commande client. Vous en aurez besoin ultérieurement dans cette procédure.  
6. Dans le champ Numéro d'article, tapez « 88000 », puis appuyez sur la touche Tab.
    * Il s'agit d'un article périodique dans les données de démonstration USRT.  
7. Cliquez sur Terminé.
8. Dans le champ Mode de paiement, entrez « Visa ».
9. Cliquez sur Ajouter une carte de crédit.
    * Entrez les informations de carte de crédit requises dans cette page.  
10. Cliquez sur OK.
11. Développez la section Paiement.
    * Pour envoyer une commande du centre d'appels, les paiements doivent être entrés pour la commande.  
12. Cliquez sur OK.
13. Cliquez sur Soumettre.
    * Vous avez terminé de créer une commande périodique. Vous exécuterez ensuite deux processus de traitement par lots qui sont utilisés pour traiter les commandes périodiques.  
14. Fermez la page.
15. Accédez à Retail et Commerce > Périodicité > Traiter les paiements périodiques.
16. Dans le champ Article périodique, tapez « 88000 », puis appuyez sur la touche Tab.
17. Cliquez sur OK.
18. Accédez à Retail et Commerce > Périodicité > Créer des commandes enfants périodiques.
    * Ce processus créera des commandes client en fonction des paramètres de vos programmes périodiques.  
19. Dans le champ Article périodique, tapez « 88000 », puis appuyez sur la touche Tab.
    * L'article « 88000 »est un article périodique dans les données de démonstration USRT.  
20. Dans le champ Commande client, entrez ou sélectionnez une valeur.
    * Entrez le numéro de la commande client que vous avez noté précédemment dans la procédure. La durée de traitement sera maintenue à une valeur minimale pour cette procédure. Le champ Commande client est facultatif ; vous pouvez traiter toutes les commandes pour n'importe quel programme.  
21. Cliquez sur OK.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]