---
title: Démarrer un ordre de fabrication
description: Cette procédure indique comment démarrer un ordre de fabrication à l'atelier.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationStartJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47915a93151b1adc99ddb4e3facb29bf8db49dd6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427808"
---
# <a name="start-a-production-order"></a>Démarrer un ordre de fabrication

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment démarrer un ordre de fabrication à l'atelier. La consommation de matières et de temps est déclarée dans ce processus. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Il s'agit de la cinquième des sept procédures expliquant le cycle de vie de l'ordre de fabrication.


## <a name="start-a-production-order"></a>Démarrer un ordre de fabrication
1. Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.
    * Sélectionnez un ordre de fabrication ayant le statut Lancé.  
2. Cliquez sur Ordre de fabrication dans le volet Actions.
3. Cliquez sur Démarrer.
    * Dans cette page, vous pouvez confirmer le début de l'ordre de fabrication.  
4. Cliquez sur l'onglet Général.
5. Dans le champ Du n° opér., N° entrez 10.
6. Dans le champ Consommation de gamme automatique, sélectionnez « Toujours ».
7. Cochez la case Valider fiche production maintenant.
8. Dans le champ Consommation de nomenclature automatique, sélectionnez « Toujours ».
9. Cochez la case Valider les prélèvements maintenant.
10. Cochez la case Imprimer les prélèvements.
11. Cliquez sur OK.
    * Il s'agit de la liste de prélèvements imprimée qui indique les matières utilisées pour l'ordre de fabrication.  
12. Fermez la page.

## <a name="validate-the-picking-list"></a>Valider les prélèvements.
1. Cliquez sur Afficher dans le volet Actions.
2. Cliquez sur Prélèvements.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Cliquez sur Modifier.
6. Entrez un nombre dans le champ Consommation.
7. Cliquez sur Valider.
8. Cliquez sur OK.
    * Dans le journal des prélèvements, les matières consommées par l'ordre de fabrication sont validées. Avant de valider le journal, vous pouvez procéder à des ajustements s'il existe une différence entre la quantité estimée et la quantité réelle consommée.  
9. Cliquez sur l'onglet Volet de grille.
10. Fermez la page.

## <a name="verify-the-route-card-journal"></a>Vérifier le journal des fiches production
1. Cliquez sur Afficher dans le volet Actions.
2. Cliquez sur Fiche production.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Cliquez sur Modifier.
6. Dans le champ Heures, entrez un nombre.
7. Cliquez sur Valider.
8. Cliquez sur OK.
    * Dans le journal des fiches production, le temps passé sur les opérations individuelles est enregistré. Les quantités correctes et erronées peuvent également être déclarées.  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]