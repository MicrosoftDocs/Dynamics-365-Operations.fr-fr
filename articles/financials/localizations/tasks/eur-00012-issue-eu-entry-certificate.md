--- 
title: "Émettre un certificat d'entrée de l'UE"
description: "Cette procédure indique comme autoriser un certificat d'entrée de l'UE, configurer un compte client pour utiliser les certificats d'entrée et pour émettre un certificat."
author: mrolecki
manager: AnnBe
ms.date: 02/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 1eca89c0588b3611cdd3ac5a62b5ac95c83c8e62
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="issue-an-eu-entry-certificate"></a>Émettre un certificat d'entrée de l'UE

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comme autoriser un certificat d'entrée de l'UE, configurer un compte client pour utiliser les certificats d'entrée et pour émettre un certificat. Cette procédure a été créée à l'aide des données fictives de la société DEMF.


## <a name="enable-entry-certificate-management"></a>Activer la gestion des certificats d'entrée
1. Accédez à Comptabilité client > Paramétrage > Paramètres de la comptabilité client.
2. Cliquez sur l'onglet Expéditions.
3. Développez la section Certificat d'entrée.
4. Sélectionnez Oui dans le champ Activer la gestion des certificats d'entrée.
5. Sélectionnez Oui dans le champ Activer l'émission des certificats d'entrée.
6. Cliquez sur l'onglet Souches de numéros.
7. Dans la liste, recherchez et sélectionnez la ligne Certificat d'entrée.
8. Dans le champ Code souche de numéros, entrez ou sélectionnez une valeur.

## <a name="set-up-a-customer"></a>Configurer un client
1. Accédez à Comptabilité client > Clients > Tous les clients.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, appliquez un filtre au champ Compte avec une valeur de « DE-015 ».
3. Ouvrez les détails du compte client.
4. Cliquez sur Modifier.
5. Développez la section Facturation et livraison.
6. Sélectionnez Oui dans le champ Certificat d'entrée requis.
7. Sélectionnez Oui dans le champ Émettre un certificat d'entrée.
8. Cliquez sur Enregistrer.

## <a name="create-an-eu-entry-certificate-automatically"></a>Créer automatiquement un certificat d'entrée de l'UE
1. Accédez à Comptabilité client > Commandes > Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Compte client.
4. Cliquez sur OK.
5. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
6. Cliquez sur Enregistrer.
7. Cliquez sur Prélever et emballer dans le volet Actions.
8. Cliquez sur Validation du bon de livraison.
9. Développez la section Paramètres.
10. Sélectionnez « Tout » dans le champ Quantité.
11. Désactivez la case à cocher Émettre un certificat d'entrée.
    * Un certificat d'entrée peut être émis lors de la validation du bon de livraison ou lors de la facturation de commande. Laissez la case à cocher Émettre un certificat d'entrée désactivée pour l'émettre ultérieurement.  
12. Cliquez sur OK.
13. Cliquez sur OK.
14. Dans le volet Actions, cliquez sur Facture.
15. Cliquez sur Facture.
    * Vérifiez que les cases à cocher Certificat d'entrée requis et Émettre un certificat d'entrée dans la section Vue d'ensemble sont activées.  Vous pouvez également activer la case à cocher Imprimer un certificat d'entrée pour autoriser l'impression du certificat.  
16. Cliquez sur OK.
17. Cliquez sur OK.
18. Dans le volet Actions, cliquez sur Facture.
19. Cliquez sur Facture.
20. Dans le volet Actions, cliquez sur Facture.
21. Cliquez sur Afficher les certificats d'entrée émis.
22. Cliquez sur Imprimer.
23. Fermez la page.
24. Cliquez sur Modifier le statut.
25. Dans le champ Nouveau statut, sélectionnez une option.
26. Cliquez sur OK.
27. Fermez la page.

## <a name="create-an-eu-entry-certificate-manually"></a>Créer manuellement un certificat d'entrée de l'UE
1. Dans le volet Actions, cliquez sur Facture.
2. Cliquez sur Créer un certificat d'entrée.
3. Cliquez sur OK.
4. Dans le volet Actions, cliquez sur Facture.
5. Cliquez sur Afficher les certificats d'entrée émis.

