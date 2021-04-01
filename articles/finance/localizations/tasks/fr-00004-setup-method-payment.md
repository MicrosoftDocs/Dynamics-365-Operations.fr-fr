---
title: FR-00004 Paramétrer le mode de paiement
description: La procédure vous guide dans la configuration des modes de paiement d’établissement afin de vous aider à créer et valider la lettre de change après l’avoir approuvée dans le journal de création de lettres de change.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, CustVendPaymFormat
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 533bb8b63c310b0ca0ed52614a6199113f09e54f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227865"
---
# <a name="fr-00004-setup-method-of-payment"></a>FR-00004 Paramétrer le mode de paiement

[!include [banner](../../includes/banner.md)]

La procédure vous guide dans la configuration des modes de paiement d’établissement afin de vous aider à créer et valider la lettre de change après l’avoir approuvée dans le journal de création de lettres de change.

Cette procédure a été créée à l’aide des données fictives de la société FRSI. 

Cette fonctionnalité est disponible pour les entités juridiques dont l’adresse principale est en France.

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
12. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Recherchez et sélectionnez « Lettre de change française » et utilisez la flèche pour la déplacer vers la liste sélectionnée.  
13. Cliquez sur Enregistrer.
14. Fermez la page.
15. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez « EnmmEAR »  
17. Dans le champ Format d’exportation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
18. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Par exemple : Sélectionnez « Lettre de change française »  
19. Cochez ou décochez la case Créer et valider automatiquement le journal de création lors de la validation des factures.
20. Cochez ou décochez la case à cocher Exécuter le script d’exportation.
21. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]