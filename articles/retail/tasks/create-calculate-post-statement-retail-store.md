--- 
title: " Créer, calculer et valider un relevé pour un magasin de vente au détail"
description: "Cette procédure décrit les étapes manuelles pour créer, calculer et valider un relevé pour un magasin."
author: jashanno
manager: AnnBe
ms.date: 11/15/2016
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
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 60bcafffc922e6d57e52a5dff104a0fbb252f6ce
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a> Créer, calculer et valider un relevé pour un magasin de vente au détail

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure décrit les étapes manuelles pour créer, calculer et valider un relevé pour un magasin. Des traitements par lots peuvent également être configurés pour les mêmes tâches. Les étapes de configuration et d'exécution des traitements par lots sont disponibles dans d'autres rubriques. Pour effectuer cette procédure, vous devez disposer des transactions effectuées dans le PDV et extraites dans Dynamics AX. Cet enregistrement utilise la société USRT dans les données de démonstration. Cette procédure peut faire référence à Microsoft Dynamics AX. Notez que Dynamics AX est maintenant appelé Microsoft Dynamics 365 for Operations.

1. Accédez à Tous les espaces de travail > .. > Finances du magasin de vente au détail.
2. Cliquez sur Nouveau relevé.
3. Dans le champ Numéro de magasin, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Cliquez sur OK.
    * Le groupe Paramétrage contient les paramètres qui contrôlent les transactions incluses dans le relevé et leur regroupement en lignes de relevé. Vous pouvez ouvrir le groupe Paramétrage et modifier ces paramètres, ou vous pouvez utiliser les valeurs par défaut.  
    * Le champ Méthode de relevé définit la manière dont les lignes de relevé sont regroupées.  
    * Sélectionnez un membre du personnel ou une caisse enregistreuse si vous souhaitez calculer un relevé uniquement pour ce membre du personnel ou cette caisse enregistreuse spécifique.  
6. Dans le champ Méthode de clôture, sélectionnez une option.
7. Cliquez sur Calcul du relevé.
8. Cliquez sur Oui.
    * Après le calcul du relevé, des lignes doivent être créées avec les montants totaux pour chaque mode de paiement et chaque méthode de relevé utilisé.  
    * Saisissez un montant compté dans chaque ligne s'il doit être saisi ou mis à jour. Le champ Compté est renseigné avec les montants des comptages de caisse effectués dans le PDV.  
9. Cliquez sur Validation du relevé.
10. Cliquez sur Fermer.
11. Accédez à Commerce et vente au détail > Canaux > Finances du magasin de vente au détail.
12. Cliquez sur l'onglet Relevés validés.

