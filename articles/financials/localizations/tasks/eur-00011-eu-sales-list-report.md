---
title: EUR-00011 Générer l'état Liste des ventes intracommunautaires
description: Cette procédure vous guide dans la génération de l'état de la liste des ventes intracommunautaires.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  EUSalesList, EUSalesListSelection, SysQueryForm, SysLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1c8a58c36b20935c26d8f0d13a6719c7c8877cf
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1537920"
---
# <a name="eur-00011-generate-the-eu-sales-list-report"></a>EUR-00011 Générer l'état Liste des ventes intracommunautaires

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous guide dans la génération de l'état de la liste des ventes intracommunautaires. Cela inclut le transfert des transactions d'échanges intracommunautaires dans la liste des ventes intracommunautaires et l'exécution de l'état. Cette procédure inclut également la création d'une transaction d'échanges intracommunautaires à des fins de démonstration. Pour plus d'informations sur la déclaration de la liste des ventes intracommunautaires, notamment les conditions préalables requises, reportez-vous à l'aide de Dynamics 365 for Finance and Operations.

Cette procédure s'applique à tous les pays/régions européens. La procédure a été créée à l'aide de la société DEMF fictive, avec l'Allemagne comme exemple de pays/région locaux. La procédure utilise également le Portugal comme exemple de pays/région européen. Avant d'exécuter cette procédure, vous devez configurer la génération d'états de liste des ventes intracommunautaires.

Cette procédure est destinée aux comptables.


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a>Créer une transaction de vente intracommunautaire à des fins de démonstration
1. Accédez à Comptabilité client > Commandes > Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Tapez PRT-001 dans le champ Compte client.
4. Cliquez sur OK.
5. Entrez « D0001 » dans le champ Numéro d'article.
6. Développez la section Détails de ligne.
7. Cliquez sur l'onglet Paramétrage.
8. Dans le champ Groupe de taxe d'article, tapez la valeur « FULL ».
9. Cliquez sur Ajouter une ligne.
10. Entrez « D0003 » dans le champ Numéro d'article.
11. Dans le champ Groupe de taxe d'article, tapez la valeur « RED ».
12. Cliquez sur Enregistrer.
13. Dans le volet Actions, cliquez sur Facture.
14. Cliquez sur Facture.
15. Développez la section Paramètres.
16. Sélectionnez « Tout » dans le champ Quantité.
17. Développez la section Paramétrage.
18. Dans le champ Date de facture, définissez la date à « 01/11/2016 ».
19. Cliquez sur OK.
20. Cliquez sur OK.

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a>Transférer des transactions d'échanges intracommunautaires vers la liste des ventes intracommunautaires.
1. Accédez à Taxe > Déclarations > Commerce extérieur > Liste des ventes intracommunautaires.
2. Cliquez sur Transférer.
3. Sélectionnez Oui dans le champ Article pour transférer les transactions d'article.
4. Sélectionnez Oui dans le champ Service pour transférer les transactions de service.
    * Vous pouvez également spécifier des filtres supplémentaires sur les transactions d'échanges intracommunautaires à transférer.  
5. Cliquez sur Transférer.
    * Vérifiez que la transaction de vente intracommunautaire est correctement transférée vers la liste des ventes intracommunautaires.  

## <a name="generate-the-eu-sales-list-report"></a>Générer l'état Liste des ventes intracommunautaires
1. Cliquez sur Génération d'états.
2. Dans le champ Génération d'états, sélectionnez « Mensuel ».
3. Dans le champ Date de début, définissez la date à « 01/01/2016 ».
4. Sélectionnez Oui dans le champ Générer un fichier.
5. Sélectionnez Oui dans le champ Générer un état.
6. Dans le champ Nom de fichier, tapez « EUSalesList ».
7. Dans le champ Nom du fichier d'état, tapez « EUSalesList ».
8. Dans le champ ID de la liste des ventes intracommunautaires, tapez « 123 ».
    * Ce champ est uniquement disponible pour l'Allemagne.  
    * Vous pouvez également spécifier des filtres supplémentaires sur les transactions d'échanges intracommunautaires à inclure au rapport.  
9. Cliquez sur OK.
    * Vérifiez que les fenêtres contextuelles confirment que le fichier et l'état de contrôle sont en cours de téléchargement.  

## <a name="mark-eu-sales-list-lines-as-reported"></a>Marquer les lignes de la liste des ventes intracommunautaires comme déclarées
1. Cliquez sur Marquer.
2. Cliquez sur Marquer comme déclarée.
3. Dans la liste, sélectionnez la ligne pour le champ Date de facture.
4. Dans le champ Critères, tapez « 01/01/2016..01/31/2016 ».
5. Dans la liste, sélectionnez la ligne pour le champ Statut de génération d'états.
6. Dans le champ Critères, sélectionnez « Inclus ».
    * Vous pouvez également spécifier des filtres supplémentaires sur les transactions d'échanges intracommunautaires à marquer comme Déclarées.  
7. Cliquez sur OK.
8. Dans le champ Sélection, sélectionnez « Déclarée ».

## <a name="mark-eu-sales-list-lines-as-closed"></a>Marquer les lignes de la liste des ventes intracommunautaires comme clôturées
1. Cliquez sur Marquer.
2. Cliquez sur Marquer comme clôturé.
3. Dans la liste, marquez la ligne pour le champ Date de facture.
4. Dans le champ Critères, tapez « 01/01/2016..01/31/2016 ».
5. Dans la liste, marquez la ligne pour le champ Statut de génération d'états.
6. Dans le champ Critères, sélectionnez « Déclaré ».
    * Vous pouvez également spécifier des filtres supplémentaires sur les transactions d'échanges intracommunautaires à marquer comme Clôturées.  
7. Cliquez sur OK.
8. Dans le champ Sélection, sélectionnez « Clôturé ».

