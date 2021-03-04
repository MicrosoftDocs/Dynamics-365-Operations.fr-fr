---
title: Mesures d'actifs
description: La rubrique explique comment créer des types de mesures d'actifs dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCounterPart, EntAssetObjectCounterLookup, EntAssetCounterType, EntAssetObjectCounterTotals
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: adadb1df7b41488fad496f937ecbc24e0761e42d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427996"
---
# <a name="counters"></a>Compteurs

[!include [banner](../../includes/banner.md)]

La rubrique explique comment créer des types de compteurs dans le module Gestion des actifs. Les types de compteurs permettent de faire des enregistrements de compteurs sur les actifs, par exemple en ce qui concerne le nombre d'heures de production ou la quantité produite sur l'actif. Les types d'actifs sont liés aux types de compteurs. Cela signifie qu'un compteur ne peut être utilisé sur un actif que si le compteur est configuré sur le type d'actif utilisé sur l'actif.

Avant de pouvoir effectuer des enregistrements de compteurs, commencez par créer les types de compteurs à utiliser dans **Compteurs**. Ensuite, vous pouvez créer des enregistrements de compteurs sur les actifs dans **Compteurs**. 

Les compteurs peuvent être utilisés sur les plans de maintenance. Une ligne de plan de maintenance peut être de type « compteur », par exemple, en relation avec le nombre d'heures ou la quantité de production produite. 

Un enregistrement de compteur peut être mis à jour manuellement ou automatiquement en fonction des heures ou de la quantité de production produite. Un compteur peut être paramétré pour utiliser une des trois méthodes de mise à jour (que vous sélectionnez dans le champ **Mettre à jour** dans **Compteurs**) :
  
- Manuel - Vous devez enregistrer manuellement des valeurs de compteurs.  
- Heures de production - le compteur est automatiquement mis à jour en fonction du nombre d'heures de production.  
- Quantité de production - le compteur est automatiquement mis à jour en fonction des quantités produites.  

>[!NOTE]
>Si la quantité produite est utilisée, *tous* les articles enregistrés sont inclus dans l'enregistrement de compteurs, bonne quantité, ainsi que quantité d'erreur. Il reste possible d'effectuer des enregistrements de compteurs manuels, le cas échéant.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Créez les contre-types pour les enregistrements de compteurs d'actifs

1. Sélectionnez **Gestion des actifs** > **Paramétrage** > **Types d'actifs** > **Compteurs**.
2. Sélectionnez **Nouveau** pour créer un type de compteur.
3. Insérez un ID dans le champ **Compteur**, et un nom de compteur dans le champ **Nom**.
4. Dans l'organisateur **Général**, sélectionnez un compteur dans le champ **Unité**.
5. Dans le champ **Mettre à jour**, sélectionnez la méthode de mise à jour à utiliser pour le compteur.
6. Sélectionnez « Oui » sur le bouton de basculement **Hériter des contre-valeurs** si les actifs enfants d'une structure d'actif doivent hériter automatiquement des enregistrements de compteurs effectués sur l'actif parent.
7. Dans le champ **Agrégat total**, sélectionnez la méthode de synthèse à utiliser pour un compteur à l'aide de ce type de compteur. La « somme » est la sélection standard utilisée pour ajouter en continu des valeurs enregistrées à la valeur totale. La « moyenne » peut être utilisée si un compteur est configuré pour surveiller un seuil, par exemple en ce qui concerne la température, les vibrations ou l'usure d'un actif. 
8. Dans le champ **Écart supérieur à**, insérez le niveau supérieur en pourcentage pour vérifier si les enregistrements du compteur manuel se situent dans une plage prévue. La validation est basée sur une augmentation linéaire du nombre d'enregistrements existants de compteurs.
9. Dans le champ **Écart inférieur à**, insérez le niveau inférieur en pourcentage pour vérifier si les enregistrements du compteur manuel se situent dans une plage prévue. La validation est basée sur une diminution linéaire du nombre d'enregistrements existants de compteurs.
10. Dans le champ **Type**, sélectionnez le type de message (informations, avertissement, erreur) à afficher si des écarts en dehors de la plage définie se produisent lorsque vous enregistrez manuellement les compteurs.
11. Dans l'organisateur **Types d'actifs**, ajoutez des types d'actifs qui doivent pouvoir utiliser le compteur.
12. Dans l'organisateur **Compteurs d'actifs associés**, ajoutez le compteur que vous souhaitez mettre à jour automatiquement lorsque ce compteur est mis à jour.


>[!NOTE]
>Un compteur associé est automatiquement mis à jour uniquement si le compteur associé a le type d'actif auquel elle est liée dans la configuration du compteur. Par exemple : Vous paramétrez un compteur pour les « heures de production » et ajoutez le type « Moteur de camion ». Lorsque ce compteur est mis à jour, un compteur associé à « Huile » est également mis à jour avec les mêmes valeurs de compteurs. Le paramétrage dans **Compteurs** inclut le paramétrage des « Heures ». En outre, pour le compteur « Pétrole », le type d'actif « Moteur de camion » doit être ajouté dans l'organisateur **Types d'actifs** pour garantir la relation de compteur. Voir les captures d'écran ci-dessous pour obtenir un exemple du paramétrage des compteurs Heures et Pétrole.

Lorsque des types d'actifs sont ajoutés à un type de compteur dans **Compteurs**, ce compteur est automatiquement ajouté aux types d'actifs dans l'organisateur **Compteurs** dans [Types d'actifs](../setup-for-objects/object-types.md).

![Figure 1](media/071-setup-for-objects.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]