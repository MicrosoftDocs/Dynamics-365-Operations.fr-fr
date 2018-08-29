--- 
title: "Créer et valider une facture client pour un client du secteur public (Danemark)"
description: "Cette procédure vous guide dans la création et la validation d'une facture de commande client pour un client à l'aide de la facturation électronique OIOUBL."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Denmark
ms.search.industry: Public Sector
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c689087f499330c8d662aed2632fd2e079145fde
ms.openlocfilehash: 846d7b67ca3287a5dbc0e3e18a22804fad847f1e
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="create-and-post-a-customer-invoice-for-a-public-sector-customer-denmark"></a>Créer et valider une facture client pour un client du secteur public (Danemark)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous guide dans la création et la validation d'une facture de commande client pour un client à l'aide de la facturation électronique OIOUBL. 



Elle a été créée avec les données de démonstration de la société fictive USMF, avec l'adresse principale de l'entité juridique au Danemark.



Il s'agit de la cinquième des six procédures illustrant le processus de bout en bout de génération de factures électroniques à l'aide des configurations de génération d'états électroniques. Elle est basée sur l'exemple de facture électronique OIOUBL, qui est commun au Danemark, à l'Autriche et à la Norvège. Afin d'identifier les différences mineures pour d'autres implémentations de facture électronique spécifiques au pays, comme l'espagnol ou l'italien, reportez-vous aux articles WIKI disponibles.



Avant d'exécuter cette procédure, vous devez effectuer les procédures suivantes : « Importer les configurations de génération d'état électronique de facturation électronique OIOUBL », « Paramétrer la facturation électronique OIOUBL » et « Paramétrer un compte client pour la facturation électronique OIOUBL ».


## <a name="create-a-sales-order"></a>Créer une commande client
1. Accédez à Comptabilité client > Commandes > Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Compte client.
    * Sélectionnez un client qui est activé pour la facturation électronique.  
4. Cliquez sur OK.
5. Sélectionnez une vue d'en-tête de commande client.
6. Dans le champ Contact, saisissez ou sélectionnez une valeur.
7. Tapez une valeur dans le champ Demande d'achat client.
8. Tapez une valeur dans le champ Référence client.
9. Développez la section Paramétrage.
10. Sélectionnez une vue de ligne de commande client.
11. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
    * Vous pouvez utiliser le numéro d'article « D0001 ».  
12. Cliquez sur Enregistrer.

## <a name="post-an-invoice-for-a-sales-order"></a>Valider une facture pour un commande client
1. Dans le volet Actions, cliquez sur Facture.
2. Cliquez sur Facture.
3. Développez la section Paramètres.
4. Sélectionnez « Tout » dans le champ Quantité.
5. Cliquez sur OK.
6. Cliquez sur OK.

## <a name="generate-oioubl-electronic-invoice"></a>Générer une facture électronique OIOUBL
1. Cliquez sur Facture.
2. Dans le volet Actions, cliquez sur Facture.
3. Cliquez sur Envoyer.
4. Cliquez sur Original.

## <a name="view-an-oioubl-electronic-invoice"></a>Afficher une facture électronique OIOUBL
1. Accédez à Administration d'organisation > Génération d'états électroniques > Tâches d'états électroniques.
2. Cliquez sur Afficher les fichiers.
3. Cliquez sur Ouvrir.


