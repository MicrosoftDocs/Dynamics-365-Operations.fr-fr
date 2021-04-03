---
title: Créer un plan intersociétés
description: Cette procédure indique comment créer un plan intersociétés.
author: ShylaThompson
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b64ababa618d58feb6095704e5978295060c96f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261115"
---
# <a name="create-an-intercompany-plan"></a>Créer un plan intersociétés

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment créer un plan intersociétés. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="set-up-an-intercompany-planning-group"></a>Paramétrer un groupe de planification intersociétés 
1. Dans le **Volet de navigation**, allez dans **Modules > Planification > Paramétrage > Groupes de planification intersociétés**. 
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Nom avec une valeur de « 10 ».
3. Dans la liste, marquez la ligne sélectionnée.
4. Cliquez sur **Supprimer**. Cette étape est nécessaire pour raccourcir l’exécution de la planification intersociétés.   La planification intersociétés exécute la planification dans toutes les sociétés d’un groupe de planification, en commençant par la séquence de planification la plus faible.  
5. Cliquez sur **Oui**.
6. Fermez la page.

## <a name="create-an-intercompany-plan"></a>Créer un plan intersociétés
1. Dans le **Volet de navigation**, allez dans **Modules > Planification > Espaces de travail > Planification**.
2. Cliquez sur **Planification intersociétés**.  
3. Dans le champ **Groupe de planification intersociétés**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée. Sélectionnez le groupe de planification intersociétés 10.  
5. Entrez « 2 » dans le champ **Nombre d’itérations de planification intersociétés**. Le groupe de planification intersociétés 10 a deux membres. Afin de propager les retards de la société source (USMF) à la société cliente (DEMF), vous devez exécuter deux fois le module intersociétés dans les deux sociétés. La première itération propage la demande et identifie les retards dans la société source (USMF). La deuxième itération propage les retards d’USMF à DEMF.  
6. Sélectionnez « Régénération » dans le champ **Première itération**.
7. Sélectionnez « Régénération » dans le champ **Itérations suivantes**.
8. Entrez un nombre dans le champ **Nombre de threads**. Représente le nombre de threads parallèles utilisés pour la planification.  
9. Cliquez sur **OK**.

## <a name="view-the-result-of-the-plan"></a>Afficher le résultat du plan
1. Dans le champ **Régime**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée. Cliquez sur le lien de StaticPlan. Vous devez être dans la société USMF.  
3. Cliquez sur **Ordres prévisionnels**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]