--- 
title: "Créer et valider une facture financière pour un client du secteur public (Danemark)"
description: "Cette procédure vous guide dans la création et la validation d'une facture financière pour un client à l'aide de la facturation électronique OIOUBL."
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
ms.openlocfilehash: 3b23be85ec0ec60f62a30348ea72c633e8d515c9
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="create-and-post-a-free-text-invoice-for-a-public-sector-customer-denmark"></a>Créer et valider une facture financière pour un client du secteur public (Danemark)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous guide dans la création et la validation d'une facture financière pour un client à l'aide de la facturation électronique OIOUBL. 



Elle a été créée avec les données de démonstration de la société fictive USMF, avec l'adresse principale de l'entité juridique au Danemark.



Il s'agit de la quatrième des six procédures illustrant le processus de bout en bout de génération de factures électroniques à l'aide des configurations de génération d'états électroniques. Elle est basée sur l'exemple de facture électronique OIOUBL, qui est commun au Danemark, à l'Autriche et à la Norvège. Afin d'identifier les différences mineures pour d'autres implémentations de facture électronique spécifiques au pays, comme l'espagnol ou l'italien, reportez-vous aux articles WIKI disponibles.



Avant d'exécuter cette procédure, vous devez effectuer les procédures suivantes : « Importer les configurations de génération d'état électronique de facturation électronique OIOUBL », « Paramétrer la facturation électronique OIOUBL » et « Paramétrer un compte client pour la facturation électronique OIOUBL ».

1. Accédez à Comptabilité client > Factures > Toutes factures financières.
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Compte client.
    * Un client sélectionné pour la facture financière doit être activé pour la facturation électronique.  
4. Sélectionnez une vue d'en-tête de facture financière.
5. Développez la section Client.
6. Tapez une valeur dans le champ Demande d'achat client.
7. Tapez une valeur dans le champ Référence client.
8. Dans le champ Contact, saisissez ou sélectionnez une valeur.
9. Sélectionnez une vue de lignes de facture financière.
10. Dans la liste, marquer la ligne sélectionnée.
11. Tapez une valeur dans le champ Description.
12. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
13. Entrez un nombre dans le champ Prix unitaire.
14. Cliquez sur Valider.
15. Cliquez sur OK.

## <a name="generate-an-oioubl-electronic-invoice"></a>Générer une facture électronique OIOUBL
1. Cliquez sur Envoyer.
2. Cliquez sur Original.
    * Vous pouvez vérifier le statut de la tâche et télécharger le fichier en cours dans la page des tâches de génération d'états électroniques.  


