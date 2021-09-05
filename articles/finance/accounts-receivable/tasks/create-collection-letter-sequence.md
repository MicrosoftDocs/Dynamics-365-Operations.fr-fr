---
title: Créer une série de lettres de relance
description: Utilisez cette procédure pour créer une série de lettres de relance.
author: mikefalkner
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b3062390da10f344c354cd2cc5cd7fb73623570
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/18/2021
ms.locfileid: "7394680"
---
# <a name="create-a-collection-letter-sequence"></a>Créer une série de lettres de relance

[!include [banner](../../includes/banner.md)]

Utilisez cette procédure pour créer une série de lettres de relance. La société fictive USMF est citée en exemple dans cette tâche.

1. Dans le volet de navigation, accédez à **Modules > Crédit et recouvrements > Paramétrage > Paramétrer la série de lettres de relance**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Série de lettres de relance**, entrez un ID souche qui représentera la séquence. Il sera utilisé pour paramétrer un profil de validation.
4. Tapez une valeur dans le champ **Description**.  Les conditions de paiement sont facultatives. Si vous entrez une valeur ici, la facture de frais de relance utilise ces conditions de paiement à la place de ceux enregistrés avec le client.  
5. Dans le champ **Code lettre de relance**, sélectionnez le code pour la première lettre de relance à envoyer. La première lettre de relance est créée en fonction de la date d’échéance figurant sur la facture, de la valeur que vous entrez pour la période de grâce dans le champ Jours de cette ligne, et des autres informations que vous entrez dans cette ligne.  
6. Tapez une valeur dans le champ **Description**. La devise des frais est définie par défaut sur la devise du client. Ce code devise peut être différent de la devise de facturation.  
7. Cliquez sur **Ajouter** pour ajouter la lettre de relance suivante qui sera envoyée dans la séquence. Dans de nombreux cas, la première lettre de relance est simplement un avertissement. Vous pouvez ajouter des frais si nécessaire.  
8. Dans le champ de code lettre de relance, sélectionnez la lettre de relance suivante qui sera envoyée dans la séquence.
9. Tapez une valeur dans le champ **Description**.
10. Dans le champ **Compte principal**, sélectionnez le compte de produit à utiliser pour les frais.
11. Entrez les frais qui seront facturés lorsque cette lettre de relance sera validée.
12. Dans le champ **Groupes de taxe d’article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. Sélectionnez un groupe de taxe d’article si des taxes doivent être calculées sur les frais.  
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
14. Dans le champ **Solde minimal en retard**, saisissez le solde minimal en retard requis avant qu’une lettre de relance ne soit envoyée.
15. Dans le champ **Jours**, entrez le nombre de jours de grâce que vous allez autoriser. Il s’agit du nombre de jours après la date d’échéance qu’une lettre de relance peut être générée. La date d’échéance utilisée pour le calcul dépend de la position de la lettre de relance dans la série de lettres de relance :
    - La période de grâce pour la lettre de relance 1 est relative à la date d’échéance de la facture.
    - La période de grâce pour les lettres de relance 2 et ultérieures est relative à la date à laquelle la lettre de relance précédente est validée ou imprimée, selon la sélection du champ Mettre à jour un code lettre de relance dans la page Paramètres de la comptabilité client.  
16. Cliquez sur **Ajouter** pour ajouter la dernière lettre de relance de la séquence. Vous pouvez ajouter jusqu’à cinq codes lettre de relance pour une série de lettres de relance.  
17. Dans le champ **Code lettre de relance**, sélectionnez la lettre de relance suivante qui sera envoyée dans la séquence.
18. Tapez une valeur dans le champ **Description**.
19. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
20. Entrez un nombre dans le champ **Frais en devise**.
21. Dans le champ **Groupes de taxe d’article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
22. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
23. Entrez un nombre dans le champ **Solde minimal en retard**.
24. Entrez un nombre dans le champ **Jours**.
25. Activez la case à cocher **Bloc** pour empêcher de nouvelles livraisons ou facturations avec le client. Pour débloquer le compte, sélectionnez **Non** dans le champ Facturation et livraison en attente dans la page Clients.  
26. Développez l’organisateur **Note**.
27. Entrez le texte tel que vous souhaitez qu’il apparaisse dans la lettre de relance pour le code lettre de relance sélectionné. Vous pouvez traduire ce texte dans plusieurs langues à l’aide du menu Traductions au-dessus de la zone de note.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
