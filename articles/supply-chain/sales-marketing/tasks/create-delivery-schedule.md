---
title: Créer un calendrier de livraison
description: Cette procédure illustre comment créer un calendrier de livraison pour une commande client.
author: omulvad
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 79fa41df07bc09f24e31900a52f4905db6d1c63e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836420"
---
# <a name="create-delivery-schedule"></a>Créer un calendrier de livraison

[!include [banner](../../includes/banner.md)]

Cette procédure illustre comment créer un calendrier de livraison pour une commande client. Un plan de livraison est utilisé lorsqu’une quantité sur une commande ou un devis doit être livrée dans le cadre de plusieurs expéditions. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.


## <a name="create-delivery-schedule"></a>Créer un calendrier de livraison
1. Allez dans Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Compte client.
4. Cliquez sur OK.
5. Entrez ou sélectionnez une valeur dans le champ Numéro d’article.
6. Entrez une valeur supérieure à 1 dans le champ Quantité.
7. Cliquez sur Ligne de commandes client.
8. Cliquez sur Plan de livraison.
    * La page Plan de livraison est l’emplacement dans lequel vous pouvez spécifier le nombre d’expéditions pour lesquelles la quantité totale de la ligne de commande sera livrée au client.    
    * Par défaut, le système copie la quantité totale et d’autres détails de livraison de la ligne de vente d’origine dans la première ligne du calendrier de livraison. Dans cet exemple, nous allons créer un programme pour deux expéditions. La date de la deuxième expédition sera décalée d’une semaine par rapport à la première.  
9. Dans le champ Quantité, entrez un nombre qui fait partie de la quantité totale.
10. Cliquez sur Nouveau.
11. Entrez la quantité restante dans le champ Quantité.
12. Dans le champ Date d’expédition demandée, entrez une date ayant une semaine d’avance sur la date de la première ligne de livraison.
    * Les deux options de l’organisateur Conversion de frais contrôlent la manière dont vous souhaitez répartir les frais entre les lignes du plan de livraison, une fois qu’ils ont été affectés à la ligne de commande d’origine. Si vous sélectionnez Copier les montants bruts, le même montant des frais est copié dans chaque ligne. L’option Allouer aux lignes de livraison divise les frais de manière égale entre les lignes de livraison.  
    * Seuls les frais fixes peuvent être divisés alors que les frais variables sont toujours copiés dans les lignes.  
13. Déplacez le curseur de la deuxième ligne de livraison pour mettre la page à jour.
    * Vous pouvez suivre la quantité totale répartie sur les lignes du plan de livraison en regardant les champs Total et Restant. Lorsque la quantité restante est nulle cela signifie que la quantité totale de la ligne d’origine a été affectée au plan.   
14. Cliquez sur OK.
    * Le plan de livraison vient d’être copié dans les lignes de commande.   
    * La ligne de commande d’origine (appelée Ligne commerciale) a été convertie en une ligne de commande contenant plusieurs livraisons. Elle est identifiée par une icône distincte et fait office d’en-tête pour les lignes de livraison.  
    * Les deux nouvelles lignes (appelées lignes de livraison) constituent un plan de livraison. La commande sera traitée par rapport à ces lignes et non la ligne d’origine. Si des documents tels que les bordereaux de confirmation, les prélèvements, les bons de livraison ou les factures sont imprimés, seules les lignes de livraison sont affichées.   
    * Les lignes de livraison peuvent avoir des dates de livraison, des quantités, des modes de livraison et des dimensions de stockage différents (telles qu’un site ou un entrepôt). Toutefois, les dimensions de produit doivent toujours correspondre à celles de la ligne commerciale et ne peuvent pas être changées.  
15. Entrez une valeur supérieure à celle actuelle dans le champ Quantité.
16. Sélectionnez la ligne commerciale pour voir l’effet du nouveau calcul de quantité.
17. Cliquez sur Prélever et emballer dans le volet Actions.
18. Cliquez sur Validation du bon de livraison.
19. Développez la section Paramètres.
20. Sélectionnez « Tout » dans le champ Quantité.
    * Notez que le bon de livraison sera créé pour les deux lignes du plan de livraison et non pour la ligne de commande d’origine.  
21. Sélectionnez Oui dans le champ Imprimer le bon de livraison.
22. Cliquez sur OK.
23. Cliquez sur Oui.
24. Fermez la page.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]