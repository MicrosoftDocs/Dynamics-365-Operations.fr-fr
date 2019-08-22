---
title: Mesures d'actifs
description: La rubrique explique comment créer des types de mesures d'actifs dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c445832a649c4f6a6642036ecab325e8aa2079
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783273"
---
# <a name="asset-measures"></a>Mesures d'actifs

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

La rubrique explique comment créer des types de mesures d'actifs dans le module Gestion des actifs. Les types de mesures d’actifs permettent d’enregistrer des mesures, par exemple en ce qui concerne le nombre d’heures de production ou la quantité produite sur l’actif. Les types d'actifs sont liés aux types de mesures d'actifs. Cela signifie qu'une mesure de l'actif ne peut être utilisée sur un actif que si la mesure de l'actif est configurée sur le type d'actif utilisé sur l'actif.

Avant de pouvoir créer des enregistrements de mesure sur les actifs, commencez par la mesure des types d'actifs à utiliser dans **Compteurs**. Ensuite, vous pouvez créer des enregistrements de mesure sur les actifs dans **Mesures d'actifs**. 

Les mesures d'actifs peuvent être utilisées sur les plans de maintenance. Une ligne de plan de maintenance peut être de type « compteur », par exemple, en relation avec le nombre d'heures ou la quantité de production produite. 

Un enregistrement de mesure d'actif peut être mis à jour manuellement ou automatiquement en fonction des heures ou de la quantité de production produite. Une mesure d'actif peut être paramétrée pour utiliser une des trois méthodes de mise à jour (que vous sélectionnez dans le champ **Mettre à jour** dans **Compteurs**) :
  
- Manuel - Vous devez enregistrer manuellement des valeurs de mesure d'actifs.  
- Heures de production - le compteur est automatiquement mis à jour en fonction du nombre d'heures de production.  
- Quantité de production - le compteur est automatiquement mis à jour en fonction des quantités produites.  

>[!NOTE]
>Si la quantité produite est utilisée, *tous* les articles enregistrés sont inclus dans l'enregistrement de mesure, bonne quantité, ainsi que quantité d'erreur. Il reste possible d'effectuer des enregistrements de mesure d'actifs manuels, le cas échéant.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Créez les contre-types pour les enregistrements de compteurs d'actifs

1. Sélectionnez **Gestion des actifs** > **Paramétrage** > **Types d'actifs** > **Compteurs**.
2. Sélectionnez **Nouveau** pour créer un type de mesure d'actif.
3. Insérez un ID dans le champ **Compteur**, et un nom de compteur dans le champ **Nom**.
4. Dans l'organisateur **Général**, sélectionnez l'unité de mesure dans le champ **Unité**.
5. Dans le champ **Mettre à jour**, sélectionnez la méthode de mise à jour à utiliser pour la mesure d'actif.
6. Sélectionnez « Oui » sur le bouton bascule **Hériter des contre-valeurs** si les actifs enfants d'une structure d'actif doivent hériter automatiquement des enregistrements de mesures d'actifs effectués sur l'actif parent.
7. Dans le champ **Agrégat total**, sélectionnez la méthode de synthèse à utiliser pour une mesure d'actif à l'aide de cette mesure de type d'actif. La « somme » est la sélection standard utilisée pour ajouter en continu des valeurs enregistrées à la valeur totale. La « moyenne » peut être utilisée si une mesure d'actif est configurée pour surveiller un seuil, par exemple en ce qui concerne la température, les vibrations ou l'usure d'un actif. 
8. Dans le champ **Écart supérieur à**, insérez le niveau supérieur en pourcentage pour vérifier si la mesure manuelle des enregistrements d'actifs dans une plage prévue. La validation est basée sur une augmentation linéaire du nombre d’enregistrements existants de mesures d'actifs.
9. Dans le champ **Écart inférieur à**, insérez le niveau inférieur en pourcentage pour vérifier si la mesure manuelle des enregistrements d'actifs dans une plage prévue. La validation est basée sur une diminution linéaire du nombre d’enregistrements existants de mesures d'actifs.
10. Dans le champ **Type**, sélectionnez le type de message (informations, avertissement, erreur) à afficher si des écarts en dehors de la plage définie se produisent lorsque vous enregistrez manuellement les mesures des actifs.
11. Dans l'organisateur **Types d'actifs**, ajoutez des types d'actifs qui doivent pouvoir utiliser la mesure des actifs.
12. Dans l'organisateur **Mesures d'actifs connexes**, ajoutez les mesures d'actifs que vous souhaitez mettre à jour automatiquement lorsque cette mesure d'actif est mise à jour.


>[!NOTE]
>Une mesure d'actif liée est automatiquement mise à jour uniquement si la mesure d'actif associée a le type d'actif auquel elle est liée dans la configuration de la mesure d'actif. Par exemple : Vous paramétrez une mesure d'actif pour les « heures de production » et ajoutez le type « Moteur de camion ». Lorsque cette mesure de l'actif est mise à jour, un compteur associé à « Huile » est également mis à jour avec les mêmes valeurs de mesure des actifs. Le paramétrage dans **Compteurs** inclut le paramétrage des « Heures ». En outre, pour la mesure de l’actif « Pétrole », le type d’actif « Moteur de camion » doit être ajouté dans l'organisateur **Types d'actifs** pour garantir la relation de mesures d'actifs. Voir les captures d'écran ci-dessous pour obtenir un exemple du paramétrage des mesures Heures et Huile.

Lorsque des types d’actifs sont ajoutés à un type de mesure d’actifs dans **Compteurs**, cette mesure d'actif est automatiquement ajoutée aux types d'actifs dans l'organisateur **Compteurs** dans [Types d'actifs](../setup-for-objects/object-types.md).

![Figure 1](media/071-setup-for-objects.png)


