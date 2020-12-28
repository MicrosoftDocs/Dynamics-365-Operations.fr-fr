---
title: Analyse des problèmes d'actifs
description: Cette rubrique explique les analyses de défaillance d'actif dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectFaultCalculate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e911f7ca3b67acd9d5a1b170d8c99135da730847
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428003"
---
# <a name="asset-fault-analysis"></a>Analyse des problèmes d'actifs

[!include [banner](../../includes/banner.md)]

 

Dans le module Gestion des actifs, vous pouvez analyser les enregistrements de défaillance d'actif afin d'obtenir une vue d'ensemble du nombre total de défaillances consignées durant une période spécifique. Les enregistrements de défaillance peuvent être analysés à partir de perspectives différentes, par exemple en fonction des actifs, des types d'actifs, des postes techniques, des symptômes de défaillance, ou des types de défaillance.

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Défaillances des actifs** > **Analyses des défaillances des actifs**.

2. Dans la boîte de dialogue **Calcul d'analyse des défaillances des actifs**, vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de défaillance d'actif en fonction des postes techniques. 

    Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes de défaillance d'actif pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter des heures à partir des postes techniques situés à un niveau inférieur. 
        
    Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de défaillance d'actif sur tout le niveau du poste technique auquel elles sont liées.

3. Pour limiter la recherche, vous pouvez sélectionner des actifs, des dates de défaillance, des causes de défaillance et des solutions spécifiques sur l'organisateur **Enregistrements à inclure**.

4. Cliquez sur **OK** pour démarrer le calcul.

5. Dans l'onglet **Analyses des défaillances des actifs**, cliquez sur un ou plusieurs boutons **Grouper par** pour afficher le niveau de détail à afficher. Les boutons actionnés sont mis en surbrillance. Activez ou désactivez les boutons en cliquant dessus.

6. Cliquez sur **Mettre à jour les calculs** pour afficher vos sélections à l'écran. 

>[!NOTE]
>Chaque fois que vous activez ou de désactiver un bouton **Grouper par**, n'oubliez pas de cliquer sur le bouton **Mettre à jour les calculs**. Cela est nécessaire car un grand nombre de données sont traitées lorsque vous recalculez la probabilité de défaillance.

## <a name="examples"></a>Exemples

Il existe de nombreuses façons d'analyser les enregistrements de défaillance. Cette section contient cinq exemples de la manière dont différentes sélections fournissent peuvent fournir plus d'analyse et de détails lors de l'analyse des enregistrements de défaillance des actifs.

### <a name="group-by-symptoms"></a>Grouper par symptômes

Dans la capture d'écran ci-dessous, seul le bouton **Symptôme** est sélectionné.

- Les enregistrements de défaillance ont été effectués sur trois symptômes de défaillance : « Fuite d'air », « Fusible grillé » et « Équipement bloqué ».  
- Dans la colonne **% probabilité**, tous les pourcentages doivent totaliser 100 %. La probabilité est basée sur tous les enregistrements de **Symptôme** de cette analyse des défaillances.

![Figure 1](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a>Grouper par symptôme et période

Dans le capture d'écran ci-dessous, **Année** et **Mois** ont été ajoutés pour afficher la manière dont vous pouvez afficher des enregistrements de défaillance durant une période sélectionnée.

- Les symptômes de défaillance s'affichent comme des enregistrements par an/mois.  
- Dans la colonne **% probabilité**, si vous additionnez les pourcentages pour chaque mois, vous devez arriver à 100 %. La probabilité est basée sur tous les enregistrements de **Symptôme** de cette analyse des défaillances. Si vous avez un grand nombre de lignes sur un actif, mais qu'un pourcentage élevé figure sur une ligne, cela peut indiquer un symptôme de défaillance à examiner de près pour trouver une manière de limiter le nombre d'enregistrements pour ce symptôme de défaillance.

![Figure 2](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a>Grouper par plusieurs symptômes et actif

La combinaison des actifs et d'un type d'actif est utilisée comme base pour les calculs affichés dans les trois captures d'écran ci-dessous, ce qui va augmenter le niveau de détail.  

En général, les boutons des groupes du volet Actions **Grouper par date**, **Grouper par actif**, **Grouper par poste technique**, ainsi que le bouton **Problème** (ID de défaillance), contiennent des périodes ou des relations entre les actifs. Les boutons **Symptôme**, **Secteur**, **Type**, **Cause** et **Remède** sont des catégorisations utilisées dans la gestion de défaillance pour analyser les enregistrements de défaillance d'actif et les domaines problématiques ponctuels.  

**Grouper par symptôme, actif et type d'actif**

Dans la capture d'écran ci-dessous, **Actif** et **Type d'actif** ont été ajoutés pour fournir plus de détails concernant les enregistrements de défaillance.

- Les symptômes de défaillance sont désormais divisés dans des combinaisons **Actif** / **Type d'actif** / **Symptôme** .  
- Dans la colonne **% probabilité** si vous additionnez tous les pourcentages des combinaisons **Actif** / **Type d'actif** / **Symptôme** respectivement, vous devez arriver à 100 %. La probabilité est basée sur les enregistrements de **Symptôme** de cette analyse des défaillances. Si vous avez un grand nombre de lignes sur un actif, mais qu'un pourcentage élevé figure sur une ligne, cela peut indiquer un symptôme de défaillance à examiner de près pour trouver une manière de limiter le nombre d'enregistrements pour ce symptôme de défaillance.

![Figure 3](media/08-controlling-and-reporting.png)

**Grouper par deux symptômes, actif et type d'actif**

Dans la capture d'écran ci-dessous, **Secteur** a été ajouté à **Symptôme**, **Actif** et **Type d'actif** pour fournir plus de détails concernant les enregistrements de défaillance.

- Dans la colonne **% probabilité** si vous additionnez tous les pourcentages des combinaisons **Actif** / **Type d'actif** / **Symptôme** d'un actif, vous devez arriver à 100 %. La probabilité est basée sur la combinaison **Symptôme** et **Zone** dans cette analyse des défaillances. Si vous avez un grand nombre de lignes sur un actif, mais qu'un pourcentage élevé figure sur une ligne, cela peut indiquer une zone de défaillance à examiner de près pour trouver une manière de limiter le nombre d'enregistrements pour cette zone de défaillance.  

![Figure 4](media/09-controlling-and-reporting.png)

**Grouper par trois symptôme, actif et type d'actif**

Dans le capture d'écran ci-dessous, **Type** a été ajouté, et le calcul le plus détaillé dans cet exemple s'affiche.
 
- Dans la colonne **% probabilité** si vous additionnez tous les pourcentages des combinaisons **Actif** / **Type d'actif** / **Symptôme** d'un actif, vous devez arriver à 100 %. La probabilité est basée sur la combinaison **Symptôme**, **Secteur** et **Type** dans cette analyse des défaillances. Si vous avez un grand nombre de lignes sur un actif, mais qu'un pourcentage élevé figure sur une ligne, cela peut indiquer un type de défaillance à examiner de près pour trouver une manière de limiter le nombre d'enregistrements pour ce type de défaillance.

![Figure 5](media/10-controlling-and-reporting.png)


>[!NOTE]
>Pour obtenir une vue d'ensemble de tous les enregistrements de défaillance créés sur les ordres de travail et les demandes de maintenance, cliquez sur **Gestion des actifs** > **Recherches** > **Défaillance des actifs** > **Défaillance des actifs**. Dans la page **Défaillances des actifs**, sélectionnez un enregistrement de défaillance d'actif et développez le volet **Informations associées** pour afficher les informations concernant l'ordre de travail ou la demande de maintenance.

