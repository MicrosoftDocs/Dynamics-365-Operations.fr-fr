---
title: Créer, calculer et valider des relevés pour un magasin de vente au détail
description: Cette rubrique décrit les étapes manuelles pour créer, calculer et valider un relevé pour un magasin.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21f1b0a34205e192957405bc9d298c45c8bb4d25
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141012"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a>Créer, calculer et valider des relevés pour un magasin de vente au détail

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les étapes manuelles pour créer, calculer et valider un relevé pour un magasin. Des traitements par lots peuvent également être configurés pour les mêmes tâches. Les étapes de configuration et d'exécution des traitements par lots sont disponibles dans d'autres rubriques. Pour effectuer cette procédure, vous devez disposer des transactions effectuées dans le PDV et extraites dans Dynamics 365 Commerce. Cet enregistrement utilise la société USRT dans les données de démonstration.

1. Sélectionnez **Finances du magasin** sur la page d'accueil.
2. Sélectionnez **Nouveau relevé**.
3. Dans le champ **Numéro de magasin**, sélectionnez une option dans le menu déroulant.
4. Cliquez sur **OK**.
5. Le groupe **Paramétrage** contient les paramètres qui contrôlent les transactions incluses dans le relevé et leur regroupement en lignes de relevé. Vous pouvez ouvrir le groupe **Paramétrage** et modifier ces paramètres, ou vous pouvez utiliser les valeurs par défaut.  
    - Le champ **Méthode de relevé** définit la manière dont les lignes de relevé sont regroupées.  
    - Sélectionnez un membre du personnel ou une caisse enregistreuse dans le champ **Personnel/caisse enregistreuse** si vous souhaitez calculer un relevé uniquement pour ce membre du personnel ou cette caisse enregistreuse spécifique.  
6. Dans le champ **Méthode de clôture**, sélectionnez une option.
7. Sélectionnez **Calcul du relevé** du volet Actions.
8. Cliquez sur **Oui**.
    - Après le calcul du relevé, des lignes doivent être créées avec les montants totaux pour chaque mode de paiement et chaque méthode de relevé utilisé.  
    - Saisissez un montant compté dans chaque ligne s'il doit être saisi ou mis à jour. Le champ Compté est renseigné avec les montants des comptages de caisse effectués dans le PDV.  
9. Sélectionnez **Validation du relevé** du volet Actions.
10. Sélectionnez **Fermer**.
11. Fermez le volet.
12. Sur la page d'accueil, sélectionnez **Finances du magasin**.
13. Sélectionnez l'onglet **Relevés validés**.

