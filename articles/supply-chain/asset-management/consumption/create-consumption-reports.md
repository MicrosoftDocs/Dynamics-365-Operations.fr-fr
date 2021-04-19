---
title: Créer des états de consommation
description: Cette rubrique explique comment créer des états de consommation dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8add0602e0ebe7a5c0cf2c76de6fa2f4f21a2f72
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837919"
---
# <a name="create-consumption-reports"></a>Créer des états de consommation

[!include [banner](../../includes/banner.md)]

 

Lorsque vous avez créé et validé les enregistrements de consommation sur les ordres de travail dans le module Gestion des actifs, deux états sont disponibles pour afficher les détails de la consommation.


## <a name="asset-consumption-report"></a>État relatif à la consommation des actifs

Lorsque vous avez validé la consommation sur les ordres de travail, vous pouvez imprimer un état relatif à la consommation des actifs. L’état affiche les heures, le coût des heures, le coût des articles, et les dépenses validées sur des actifs.

1. Cliquez sur **Gestion des actifs** > **États** > **Actifs** > **Consommation d’actifs**.

2. Dans la boîte de dialogue **Consommation d’actifs**, sélectionnez les paramètres et le niveau de détail que vous souhaitez afficher en sélectionnant **Oui** sur les boutons bascule appropriés, puis en entrant le niveau du poste technique dans la section **Afficher**.
    - Vous pouvez utiliser le champ **Niveaux** pour indiquer quel niveau de détail vous souhaitez dans les lignes d’actif en fonction des postes techniques. 
    
        Par exemple, si vous entrez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, tous les actifs pour un poste technique s’affichent dans le niveau supérieur et il est donc possible d’ajouter une ligne à partir des postes techniques situés à un niveau inférieur. 
        
        Par exemple, si vous entrez le chiffre « 0 » dans le champ **Niveaux**, un résultat détaillé s’affiche et indique tous les actifs sur tous les niveaux du poste technique auxquels ils sont liés. 
        
    - Sélectionnez **Oui** sur le bouton bascule **Somme de tous les sous-actifs** pour afficher les sommes des chaque sous-actif de l’état.

3. Sélectionnez un intervalle de dates dans la section **Dates**.

4. Dans l’organisateur **Destination**, indiquez si vous souhaitez afficher l’état à l’écran, l’imprimer ou l’enregistrer en tant que fichier ou e-mail.

5. Si nécessaire, vous pouvez sélectionner des actifs spécifiques à afficher dans l’état. Dans l’organisateur **Enregistrements à inclure**, cliquez sur **Filtre**, puis ajoutez des actifs à inclure dans l’état.

6. Cliquez sur **OK** pour générer l’état.


## <a name="work-order-consumption-report"></a>État de consommation de l’ordre de travail

Lorsque vous avez validé la consommation sur les ordres de travail, vous pouvez imprimer un état relatif à cette consommation. L’état affiche les heures, le coût des heures, le coût des articles, et les dépenses validées sur des ordres de travail.

1. Cliquez sur **Gestion des actifs** > **États** > **Ordres de travail** > **Consommation de l’ordre de travail**.

2. Dans la boîte de dialogue **Consommation de l’ordre de travail**, sélectionnez les paramètres que vous souhaitez inclure dans l’état en sélectionnant **Oui** sur les boutons à bascule dans la section **Afficher**.

3. Sélectionnez un intervalle de dates dans la section **Dates**.

4. Dans l’organisateur **Destination**, indiquez si vous souhaitez afficher l’état à l’écran, l’imprimer ou l’enregistrer en tant que fichier ou e-mail.

5. Si nécessaire, vous pouvez sélectionner des ordres de travail spécifiques à afficher dans l’état. Dans l’organisateur **Enregistrements à inclure**, cliquez sur **Filtre**, puis ajoutez des ordres de travail à inclure dans l’état.

6. Cliquez sur **OK** pour générer l’état.


>[!NOTE]
>Vous pouvez également générer un [état d’ordre de travail](../work-orders/work-order-report.md), qui contient plus de détails sur les ordres de travail.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]