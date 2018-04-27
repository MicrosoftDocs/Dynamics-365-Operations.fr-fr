--- 
title: "Paramétrer un mode de paiement (France)"
description: "La procédure vous guide dans la configuration des modes de paiement d'établissement afin de vous aider à créer et valider la lettre de change après l'avoir approuvée dans le journal de création de lettres de change."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 123767806836bb9d4a98e5f729ade8d0d7909b59
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-method-of-payment-france"></a>Paramétrer un mode de paiement (France)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

La procédure vous guide dans la configuration des modes de paiement d'établissement afin de vous aider à créer et valider la lettre de change après l'avoir approuvée dans le journal de création de lettres de change.

Cette procédure a été créée à l'aide des données fictives de la société FRSI. 

Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en France.

Pour effectuer cette procédure, vous devez avoir le rôle de responsable de la comptabilité client.





1. Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Mode de paiement.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Statut de paiement, sélectionnez « Approuvé ».
6. Dans le champ Type de paiement, sélectionnez « Lettre de change ».
7. Développez ou réduisez la section Général.
8. Sélectionnez Banque dans le champ Type de compte.
9. Dans le champ Compte de paiement, indiquez les valeurs souhaitées.
    * Par exemple : « FRSI OPER »  
10. Développez ou réduisez la section Formats de fichier.
11. Cliquez sur Paramétrage.
12. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Recherchez et sélectionnez « Lettre de change française » et utilisez la flèche pour la déplacer vers la liste sélectionnée.  
13. Cliquez sur Enregistrer.
14. Fermez la page.
15. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez « EnmmEAR »  
17. Dans le champ Format d'exportation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
18. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Par exemple : Sélectionnez « Lettre de change française »  
19. Cochez ou décochez la case Créer et valider automatiquement le journal de création lors de la validation des factures.
20. Cochez ou décochez la case à cocher Exécuter le script d'exportation.
21. Cliquez sur Enregistrer.


