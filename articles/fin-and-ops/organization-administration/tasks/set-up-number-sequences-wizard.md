--- 
title: "Configurer les souches de numéros à l'aide d'un assistant"
description: "Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transaction qui en ont besoin."
author: sericks007
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5fe6e54b4ebcf6cd611af54e7066a3e39d0e677d
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a>Configurer les souches de numéros à l'aide d'un assistant

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transaction qui en ont besoin. Un enregistrement de données principales ou de transaction nécessitant un identificateur est également appelé référence. Avant de pouvoir créer des enregistrements pour une référence, vous devez paramétrer une souche de numéros et l'associer à la référence. Cette procédure explique comment définir toutes les souches de numéros requises en même temps à l'aide d'un Assistant. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Accédez à Administration d'organisation > Séquences de nombres > Séquences de nombres.
2. Cliquez sur Générer.
3. Cliquez sur Suivant.
    * Dans cette page, vous pouvez modifier le code d'identification, la valeur la plus faible et la valeur la plus élevée. De plus, vous pouvez indiquer si la souche de numéros doit être continue.   
    * Ne sélectionnez pas l'option Continue si vous devez préalablement affecter des numéros pour la souche de numéros.     Pour ajouter un segment de portée au format d'une souche de numéros, sélectionnez le format dans la liste, puis cliquez sur Inclure la portée dans le format.     Pour supprimer un segment de portée du format d'une souche de numéros, sélectionnez le format dans la liste, puis cliquez sur Supprimer la portée du format.     Pour exclure une souche de numéros du processus de génération automatique, sélectionnez la souche de numéros dans la liste, puis cliquez sur Supprimer.  
4. Cliquez sur Suivant.
5. Cliquez sur Terminer.


