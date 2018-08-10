--- 
title: "Créer une série de lettres de relance"
description: "Utilisez ce guide de tâche pour créer une série de lettres de relance."
author: mikefalkner
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6331c3680169b305c4bfbfada4ba106b619be092
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-collection-letter-sequence"></a>Créer une série de lettres de relance

[!include [task guide banner](../../includes/task-guide-banner.md)]

Utilisez ce guide de tâche pour créer une série de lettres de relance. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à Crédit et relances > Paramétrage > Paramétrer la série de lettres de relance.
2. Cliquez sur Nouveau.
3. Dans le champ Série de lettres de relance, entrez un ID souche qui représentera la séquence. Il sera utilisé pour paramétrer un profil de validation.
4. Dans le champ Description, entrez une valeur.
    * Les conditions de paiement sont facultatives. Si vous entrez une valeur ici, la facture de frais de relance utilise ces conditions de paiement à la place de ceux enregistrés avec le client.  
5. Dans le champ de code lettre de relance, sélectionnez le code pour la première lettre de relance à envoyer.
    * La première lettre de relance est créée en fonction de la date d'échéance figurant sur la facture, de la valeur que vous entrez pour la période de grâce dans le champ Jours de cette ligne, et des autres informations que vous entrez dans cette ligne.  
6. Dans le champ Description, entrez une valeur.
    * La devise des frais est définie par défaut sur la devise du client. Ce code devise peut être différent de la devise de facturation.  
7. Cliquez sur Ajouter pour ajouter la lettre de relance suivante qui sera envoyée dans la séquence
    * Dans de nombreux cas, la première lettre de relance est simplement un avertissement. Vous pouvez ajouter des frais si nécessaire.  
8. Dans le champ de code lettre de relance, sélectionnez la lettre de relance suivante qui sera envoyée dans la séquence.
9. Tapez une valeur dans le champ Description.
10. Dans le champ de compte principal, sélectionnez le compte de produit à utiliser pour les frais.
11. Entrez les frais qui seront facturés lorsque cette lettre de relance sera validée.
12. Dans le champ Groupes de taxe d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez un groupe de taxe d'article si des taxes doivent être calculées sur les frais.  
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
14. Entrez le solde minimal en retard nécessaire avant qu'une lettre de relance soit envoyée.
15. Entrez le nombre de jours de grâce que vous allez autoriser.
    * Il s'agit du nombre de jours après la date d'échéance qu'une lettre de relance peut être générée. La date d'échéance utilisée pour le calcul dépend de la position de la lettre de relance dans la série :   ⦁    La période de grâce pour la lettre de relance 1 est relative à la date d'échéance de la facture.  ⦁ La période de grâce pour les lettres de relance 2 et ultérieures est relative à la date à laquelle la lettre de relance précédente est validée ou imprimée, selon la sélection du champ Mettre à jour un code lettre de relance dans la page Paramètres de la comptabilité client.  
16. Cliquez sur Ajouter pour ajouter la dernière lettre de relance de la séquence.
    * Vous pouvez ajouter jusqu'à cinq codes lettre de relance pour une série de lettres de relance.  
17. Dans le champ de code lettre de relance, sélectionnez la lettre de relance suivante qui sera envoyée dans la séquence.
18. Tapez une valeur dans le champ Description.
19. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
20. Entrez un nombre dans le champ Frais en devise.
21. Dans le champ Groupes de taxe d'article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
22. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
23. Entrez un nombre dans le champ Solde minimal en retard.
24. Entrez un nombre dans le champ Jour.
25. Activez cette case à cocher pour empêcher de nouvelles livraisons ou facturations avec le client.
    * Pour débloquer le compte, sélectionnez Non dans le champ Facturation et livraison en attente dans la page Clients.  
26. Développer l'organisateur Note.
27. Entrez le texte tel que vous souhaitez qu'il apparaisse dans la lettre de relance pour le code lettre de relance sélectionné.
    * Vous pouvez traduire ce texte dans plusieurs langues à l'aide du menu Traductions au-dessus de la zone de note.  


