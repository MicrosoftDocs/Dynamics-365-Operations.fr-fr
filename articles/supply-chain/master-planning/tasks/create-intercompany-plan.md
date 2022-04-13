---
title: Créer un plan intersociétés
description: Cette procédure indique comment créer un plan intersociétés.
author: t-benebo
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2486ce6f03d03982a7ae9c43af447923aabfed2
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469559"
---
# <a name="create-an-intercompany-plan"></a>Créer un plan intersociétés

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment créer un plan intersociétés. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

## <a name="set-up-an-intercompany-planning-group"></a>Paramétrer un groupe de planification intersociétés

1. Dans le **Volet de navigation**, allez dans **Modules > Planification > Paramétrage > Groupes de planification intersociétés**.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Nom avec une valeur de « 10 ».
3. Dans la liste, marquer la ligne sélectionnée.
4. Sélectionnez **Supprimer**. Cette étape est nécessaire pour raccourcir l’exécution de la planification intersociétés.   La planification intersociétés exécute la planification dans toutes les sociétés d’un groupe de planification, en commençant par la séquence de planification la plus faible.  
5. Cliquez sur **Oui**.
6. Fermez la page.

## <a name="create-an-intercompany-master-plan"></a>Créer une planification générale intersociétés

1. Dans le **Volet de navigation**, allez dans **Modules > Planification > Espaces de travail > Planification**.
2. Sélectionnez **Planification générale intersociétés**.  
3. Dans le champ **Groupe de planification intersociétés**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, sélectionnez le lien dans la ligne sélectionnée. Sélectionnez le groupe de planification intersociétés 10.  
5. Entrez « 2 » dans le champ **Nombre d’itérations de planification intersociétés**. Le groupe de planification intersociétés 10 a deux membres. Afin de propager les retards de la société source (USMF) à la société cliente (DEMF), vous devez exécuter deux fois le module intersociétés dans les deux sociétés. La première itération propage la demande et identifie les retards dans la société source (USMF). La deuxième itération propage les retards d’USMF à DEMF.  
6. Sélectionnez « Régénération » dans le champ **Première itération**.
7. Sélectionnez « Régénération » dans le champ **Itérations suivantes**.
8. Entrez un nombre dans le champ **Nombre de threads**. Représente le nombre de threads parallèles utilisés pour la planification.  
9. Cliquez sur **OK**.

## <a name="view-the-result-of-the-plan"></a>Afficher le résultat du plan

1. Dans le champ **Régime**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
2. Dans la liste, sélectionnez le lien dans la ligne sélectionnée. Sélectionnez le lien de StaticPlan. Vous devez être dans la société USMF.  
3. Sélectionnez **Ordres prévisionnels**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]