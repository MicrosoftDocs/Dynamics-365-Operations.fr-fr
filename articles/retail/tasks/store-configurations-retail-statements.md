--- 
title: " Enregistrer les configurations pour les relevés de vente au détail"
description: "Cette procédure illustre les configurations du magasin de vente au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cac676c9c6ebb6769fe7e30ac08a2c8334befc24
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="store-configurations-for-retail-statements"></a> Enregistrer les configurations pour les relevés de vente au détail

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure illustre les configurations du magasin de vente au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés. Les dimensions financières pour les magasins de vente au détail sont traitées dans une autre procédure. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Commerce et vente au détail > Canaux > Magasins de vente au détail > Tous les magasins de vente au détail.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Les paramètres de la section Relevé/clôture affectent la création, le contrôle et, la validation de relevés pour le magasin.  Ouvrez la section Relevé/clôture  
    * Sélectionnez la méthode à utiliser sur pour regrouper les lignes de relevé.  
    * Sélectionnez « Oui » si un seul relevé doit être créé par jour lors de la création de relevés à partir du traitement par lots de la création de relevés.  
    * Le champ Calcul de comptage de caisse définit si les comptages de caisse doivent être ajoutés ensemble ou si c'est le dernier qui doit être utilisé.  
    * Sélectionnez le compte général dans lequel valider les différences d'arrondi.  
    * Dans le champ Différence d'arrondi maximale, vous pouvez spécifier la différence d'arrondi maximale autorisée.  
    * Dans le champ Validation, vous pouvez spécifier la différence de validation totale maximale autorisée pour un relevé.  
    * Dans le champ Équipe, vous pouvez spécifier la différence totale maximale au sein d'une équipe dans un relevé.  
    * Dans le champ Transaction, vous pouvez spécifier la différence totale maximale dans une ligne de relevé.  
    * Dans le champ Méthode de clôture, vous pouvez définir si les transactions à inclure dans un relevé doivent faire partie d'une équipe de travail clôturée ou s'il peut s'agir de toute transaction comprise dans la période définie.  
    * Dans le champ Fin du jour ouvrable, vous pouvez spécifier une heure si les transactions qui surviennent après minuit doivent être validées dans le cadre du jour précédent.  
    * Sélectionnez « Oui » si les transactions qui surviennent après minuit doivent être validées dans le cadre du jour précédent.  
    * Sélectionnez « Oui » pour que des relevés soient créés pour chaque méthode de relevé définie. Cela peut s'avérer utile si les performances de la validation doit être améliorée pour les magasins affichant des volumes élevé de transactions, car cela créera de nombreux relevés plus petits qui peuvent être traités en parallèle.  
    * Dans le champ Client par défaut, vous pouvez sélectionner le compte client à utiliser pour les ventes aux clients qui se rendent dans le magasin.  


