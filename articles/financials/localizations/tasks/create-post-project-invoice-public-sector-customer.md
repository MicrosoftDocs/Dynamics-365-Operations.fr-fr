--- 
title: "Créer et valider une facture de projet pour un client du secteur public (Danemark)"
description: "Cette tâche vous guide dans la création et la validation d'une facture de projet pour un client à l'aide de la facturation électronique OIOUBL."
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
ms.openlocfilehash: a781ba3368a41d704d92560d27bbc39435490e90
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="create-and-post-a-project-invoice-for-a-public-sector-customer-denmark"></a>Créer et valider une facture de projet pour un client du secteur public (Danemark)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette tâche vous guide dans la création et la validation d'une facture de projet pour un client à l'aide de la facturation électronique OIOUBL. 



Cette tâche a été créée avec les données de démonstration de la société fictive USMF, le pays/région de l'adresse principale de l'entité juridique étant actualisé en Danemark.



Il s'agit de la sixième des six procédures illustrant le processus de bout en bout de génération de factures électroniques à l'aide des configurations de génération d'états électroniques. Elle est basée sur l'exemple de facture électronique OIOUBL, qui est commun au Danemark, à l'Autriche et à la Norvège. Afin d'identifier les différences mineures pour d'autres implémentations de facture électronique spécifiques au pays, comme l'espagnol ou l'italien, reportez-vous aux articles WIKI disponibles.



Avant d'exécuter cette procédure, vous devez effectuer les procédures suivantes : « Importer les configurations de génération d'état électronique de facturation électronique OIOUBL », « Paramétrer la facturation électronique OIOUBL » et « Paramétrer un compte client pour la facturation électronique OIOUBL ».


## <a name="update-a-project-contract"></a>Mettre à jour un contrat de projet
1. Accédez à Gestion et comptabilité des projets > Projets > Contrats de projets.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, appliquez un filtre au champ ID contrat de projet avec une valeur de « 000057 ».
    * Sélectionnez un contrat de projet ayant une source de financement client qui est activée pour la facturation électronique.  
3. Ouvrir les détails d'un contrat de projet.
4. Développez la section Sources de financement.
5. Cliquez sur Détails.
6. Développer la section Autre.
7. Tapez une valeur dans le champ Demande d'achat client.
8. Tapez une valeur dans le champ Référence client.
9. Dans le champ ID contact, saisissez ou sélectionnez une valeur.
10. Cliquez sur Enregistrer.

## <a name="create-a-project-transaction"></a>Créer une transaction de projet
1. Accédez à Gestion de projets et comptabilité > Tâches d'article > Demandes d'articles.
2. Cliquez sur Nouveau.
3. Saisissez ou sélectionnez une valeur dans le champ ID projet.
    * Par exemple, vous pouvez utiliser l'ID projet « 000057 ».  
4. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
    * Par exemple, vous pouvez utiliser le numéro d'article « D0001 ».  
5. Dans le volet Actions, cliquez sur Gérer.
6. Cliquez sur Validation.
7. Cliquez sur Bon de livraison.
8. Développez la section Paramètres.
9. Sélectionnez « Tout » dans le champ Quantité.
10. Cliquez sur OK.
11. Cliquez sur OK.

## <a name="create-a-proposal-and-post-an-invoice"></a>Créer une proposition et valider une facture 
1. Accédez à Gestion et comptabilité des projets > Factures de projets > Propositions de facture du projet.
2. Cliquez sur Nouveau.
3. Cliquez sur Proposition de facture.
4. Dans le champ Projet, saisissez ou sélectionnez une valeur.
5. Cliquez sur OK.
6. Cliquez sur Valider.
7. Cliquez sur OK.
8. Cliquez sur OK.

## <a name="generate-an-oioubl-project-invoice"></a>Générer une facture de projet OIOUBL
1. Accédez à Gestion et comptabilité des projets > Factures de projets > Factures de projet.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, appliquez un filtre au champ ID contrat de projet avec une valeur de « 000057 ».
3. Dans le volet Actions, cliquez sur Facture de projet.
4. Cliquez sur Envoyer.
5. Cliquez sur Original.

## <a name="view-an-oioubl-electronic-invoice"></a>Afficher une facture électronique OIOUBL
1. Accédez à Administration d'organisation > Génération d'états électroniques > Tâches d'états électroniques.
2. Cliquez sur Afficher les fichiers.
3. Cliquez sur Ouvrir.


