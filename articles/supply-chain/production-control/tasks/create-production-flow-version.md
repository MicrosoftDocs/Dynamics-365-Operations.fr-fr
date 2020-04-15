---
title: Créer une version de flux de production
description: Cette procédure est orientée vers la création d'une nouvelle version de flux de production.
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5512c30be586c75d2571d60588a1179c0d47570b
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146995"
---
# <a name="create-a-production-flow-version"></a>Créer une version de flux de production

[!include [banner](../../includes/banner.md)]

Cette procédure est orientée vers la création d'une nouvelle version de flux de production. Pour cette procédure, les paramètres de production pour la lean manufacturing et les unités de mesure du temps des classes doivent être définis. Vous devez également définir une chaîne de valeur et un groupe de production. Pour plus d'informations sur les flux de production et des activités en lean manufacturing, consultez les livres blancs sur la Lean manufacturing pour Microsoft Dynamics AX. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-a-production-flow"></a>Création d'un flux de production
1. Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez une unité opérationnelle du type chaîne de valeur. Une chaîne de valeur est une unité opérationnelle qui couvre tous les activités et flux de la chaîne de valeur. À ce stade, les unités opérationnelles sont limitées à une entité juridique et n'ont aucune fonctionnalité supplémentaire.  
7. Dans le champ Groupe de production, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez un groupe de production pour le flux de production. Les groupes de production permettent de définir les matières, le travail, et les comptes de travaux en cours pour un processus de production. Pour associer le contexte de comptabilité à un flux de production, il convient de créer un groupe de production.  
9. Cliquez sur Enregistrer.

## <a name="create-a-production-flow-version"></a>Créer une version de flux de production
1. Cliquez sur Ajouter.
2. Entrez une date et une heure dans le champ Date d'expiration.
    * Si nécessaire, définissez une date d'expiration de la version. Vous pouvez la mettre à jour à tout moment, même pour les versions actives. Vous pouvez l'utiliser pour planifier l'élimination d'une version.  
3. Cliquez sur OK.
4. Dans la liste, marquez la ligne sélectionnée.
5. Dans le champ Unité, tapez une valeur.
6. Résolvez les modifications de l'unité de Takt.
7. Dans le champ Takt time moyen, entrez un nombre.
    * Définissez le takt time moyen de la version. Pour le contrôle takt de la version du flux de production, définissez un takt time moyen cible. Le takt est défini comme une quantité par période. Dans l'exemple, le takt time est de 0,2 heures par 10 pièces. Pour une durée de travail de 8 heures, cela correspond à une capacité de production journalière de 400 pièces.  
8. Entrez un numéro dans le champ Quantité par cycle.
    * Définissez la quantité par cycle liée au takt time moyen.  
9. Activez ou désactivez l'extension de la section Détails de la version.
10. Dans le champ Takt time minimal, entrez un nombre.
    * Définissez le takt time minimal. Le takt time minimal doit être inférieur ou égal au takt time moyen.  
11. Dans le champ Takt time maximal, entrez un nombre.
    * Le takt time maximal doit être supérieur ou égal au takt time moyen.  
12. Entrez un nombre dans le champ Période pour la durée de cycle réelle (jours).
    * Entrez le nombre de jours dans la période pour la durée de cycle réelle. La période pour la durée de cycle réelle est le nombre de jours pendant lesquels les tâches sont regroupées à rebours à partir de la minute actuelle pour calculer la durée de cycle réelle. Cette valeur peut être modifiée à tout moment et n'est utilisée que pour le calcul des durées de cycle réelles.  
13. Cliquez sur Enregistrer.

