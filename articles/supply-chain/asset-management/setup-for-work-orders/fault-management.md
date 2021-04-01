---
title: Gestion des erreurs
description: Cette rubrique explique la gestion des erreurs dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 43f996921ccac0b3c85ecea2460cb9e4614f8c04
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226807"
---
# <a name="fault-management"></a>Gestion des erreurs

[!include [banner](../../includes/banner.md)]

 

Dans le module Gestion des actifs, vous pouvez utiliser le concepteur de défaillance pour paramétrer les symptômes de défaillance, les zones de défaillance, et les types de défaillance sur les types d’actifs. De cette manière, vous pouvez gérer les défaillances qui sont détectées sur les actifs. Il est en outre possible d’enregistrer les causes de défaillance, ainsi que des suggestions pour les résoudre sur un ordre de travail.

Le processus d’enregistrement et de gestion de défaillance se déroule comme suit :

1. Créez une liste des symptômes de défaillance, des zones de défaillance, et des types de défaillance qui peuvent se produire sur vos types d’actifs.
2. Dans le concepteur de défaillance, paramétrez les symptômes de défaillance, les zones de défaillance, et les types de défaillance.

Voici quelques exemples pour vous aider à comprendre la différence entre les symptômes de défaillance, les zones de défaillance, et les types de défaillance.

**Symptômes de défaillance :**

- Tensions non équilibrées
- Court circuit
- Bruit
- Fuite
- Vibrations

**Zones de défaillance :**

- Électrique
- Mécanique
- Hydraulique
- Pneumatique

**Types de défaillance :**

- Bobinage du stator principal défectueux
- Diode défectueuse
- Enroulements encrassés
- Générateur défectueux
- Capteur défectueux

## <a name="create-fault-symptoms"></a>Créer les symptômes de défaillance

Procédez comme suit pour créer une liste des symptômes qui peuvent être utilisés dans le concepteur de défaillance.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Symptômes de défaillance**.
2. Sélectionnez **Nouveau** pour créer un enregistrement.
3. Entrez un nom pour le symptôme de défaillance dans le champ **Symptômes de défaillance**.
4. Entrez une description dans le champ **Description**.
5. Sélectionnez **Enregistrer**.

## <a name="create-fault-areas"></a>Créer des zones de défaillance

Procédez comme suit pour créer une liste des zones ou des emplacements qui peuvent être utilisés dans le concepteur de défaillance.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Zones de défaillance**.
2. Sélectionnez **Nouveau** pour créer un enregistrement.
3. Entrez un nom pour la zone de défaillance dans le champ **Zone de défaillance**.
4. Entrez une description dans le champ **Description**.
5. Sélectionnez **Enregistrer**.

## <a name="create-fault-types"></a>Créer des types de défaillance

Procédez comme suit pour créer une liste des types de défaillance qui peuvent être utilisés dans le concepteur de défaillance.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Types de défaillance**.
2. Sélectionnez **Nouveau** pour créer un enregistrement.
3. Dans le champ **Type de défaillance**, entrez un nom pour le type de défaillance.
4. Entrez une description dans le champ **Description**.
5. Sélectionnez **Enregistrer**.

## <a name="set-up-the-fault-designer"></a>Paramétrer le concepteur de défaillance

Dans le concepteur de défaillance, vous devez paramétrer des données de défaillance sur les types d’actifs.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Concepteur de défaillance**.
2. Dans le volet gauche, sélectionnez le type d’actif pour lequel paramétrer un enregistrement de défaillance.
3. Dans le raccourci **Symptôme de défaillance**, sélectionnez **Ajouter une ligne**, puis, dans le champ **Symptôme de défaillance**, sélectionnez un symptôme de défaillance.
4. Dans le raccourci **Zone de défaillance**, sélectionnez **Ajouter une ligne**, puis, dans le champ **Zone de défaillance**, sélectionnez une zone de défaillance.
5. Dans le raccourci **Type de défaillance**, sélectionnez **Ajouter une ligne**, puis, dans le champ **Type de défaillance**, sélectionnez un type de défaillance.
6. Pour créer rapidement des combinaisons de tous les symptômes, de toutes les zones, et de tous les types de défaillance existants pour le type d’actif sélectionné, sélectionnez **Créer des combinaisons de défaillance**. Cette fonction est utile si vous avez ajouté beaucoup de symptômes, de zones, et de types de défaillance. Il est plus facile de supprimer les lignes des combinaisons qui ne conviennent pas pour le type d’actif que de créer de nouvelles lignes manuellement.

    > [!NOTE]
    > Copiez le paramétrage des symptômes, des zones et des types de défaillance d’un type d’actif sur le type d’actif sélectionné, sélectionnez **Copier à partir du type d’actif**.

7. Sélectionnez **Enregistrer** pour enregistrer les modifications.

![Page Concepteur de défaillance](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a>Créer des causes de défaillance

Procédez comme suit pour créer une liste des causes connues de défaillance pouvant être ajoutées à un ordre de travail ou à une demande de maintenance.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Causes de défaillance**.
2. Sélectionnez **Nouveau** pour créer un enregistrement.
3. Dans le champ **Cause de défaillance**, entrez un nom pour la cause de défaillance.
4. Entrez une description dans le champ **Description**.
5. Sélectionnez **Enregistrer**.

## <a name="create-fault-remedies"></a>Créer des solutions aux défaillances

Procédez comme suit pour créer une liste de suggestions de résolution et de réparation pouvant être ajoutées à un ordre de travail ou à une demande de maintenance.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Solutions aux défaillances**.
2. Sélectionnez **Nouveau** pour créer un enregistrement.
3. Entrez un nom pour la solution à la défaillance dans le champ **Solutions aux défaillances**.
4. Entrez une description dans le champ **Description**.
5. Sélectionnez **Enregistrer**.

> [!NOTE]
> Vous pouvez modifier les noms des symptômes, zones, types, causes, et recours pour les défaillances dont vous disposez comme vous le souhaitez. Les modifications apportées au nom sont répercutées automatiquement dans les enregistrements de défaillance liés.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]