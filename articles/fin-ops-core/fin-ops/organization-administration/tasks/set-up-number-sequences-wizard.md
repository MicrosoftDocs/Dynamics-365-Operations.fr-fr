---
title: Configurer les souches de numéros à l’aide d’un assistant
description: Cet article explique comment définir toutes les souches de numéros requises en même temps à l’aide d’un Assistant.
author: SunilGarg
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cae739aad1166eee1abebe3c0adc7939bca55bc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847061"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>Configurer les souches de numéros à l’aide d’un assistant

[!include [banner](../../includes/banner.md)]

Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transaction qui en ont besoin. Un enregistrement de données principales ou de transaction nécessitant un identificateur est également appelé référence. Avant de pouvoir créer des enregistrements pour une référence, vous devez paramétrer une souche de numéros et l’associer à la référence. Cet article explique comment définir toutes les souches de numéros requises en même temps à l’aide d’un Assistant. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Accédez à **Navigation > Modules > Administration d’organisation > Souches de numéros > Souches de numéros**.
2. Sélectionnez **Générer**.
3. Sélectionnez **Suivant**.

   - Dans cette page, vous pouvez modifier le code d’identification, la valeur la plus faible et la valeur la plus élevée. De plus, vous pouvez indiquer si la souche de numéros doit être continue.   
   - Ne sélectionnez pas l’option **Continue** si vous devez préalablement affecter des numéros pour la souche de numéros. Pour ajouter un segment de portée au format d’une souche de numéros, sélectionnez le format dans la liste, puis sélectionnez **Inclure la portée dans le format**. Pour supprimer un segment de portée du format d’une souche de numéros, sélectionnez le format dans la liste, puis sélectionnez **Supprimer la portée du format**. Pour exclure une souche de numéros du processus de génération automatique, sélectionnez la souche de numéros dans la liste, puis sélectionnez **Supprimer**.  

4. Sélectionnez **Suivant**.
5. Sélectionnez **Terminer**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
