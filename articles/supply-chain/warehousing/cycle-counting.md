---
title: Inventaire tournant
description: Cet article décrit la manière dont vous pouvez utiliser l'inventaire tournant associé à la solution de stockage disponible dans le module Gestion des entrepôts. Cet article ne s'applique pas à la solution de stockage disponible dans la Gestion des stocks.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 50671
ms.assetid: 49f5c431-b043-4170-aa24-b7d5d1ee063e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aef99a7e8964dba0e3c3a507bb214b79ae723357
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251521"
---
# <a name="cycle-counting"></a>Inventaire tournant

[!include [banner](../includes/banner.md)]

Cet article décrit la manière dont vous pouvez utiliser l'inventaire tournant associé à la solution de stockage disponible dans le module Gestion des entrepôts. Cet article ne s'applique pas à la solution de stockage disponible dans la Gestion des stocks.

L'inventaire tournant est un processus d'entrepôt qui permet d'auditer les articles en stock disponibles. Le processus d'inventaire tournant peut être décrit en trois étapes :

1.  **Créer un travail d'inventaire tournant** – Un travail d'inventaire tournant peut être créé automatiquement en fonction des paramètres de seuil pour des articles ou à l'aide d'un plan d'inventaire tournant. Vous pouvez également créer manuellement un travail d'inventaire tournant en utilisant les paramètres de l'article ou de l'entrepôt dans la page **Travail d'inventaire tournant par article** ou la page **Travail d'inventaire tournant par emplacement**.
2.  **Traiter l'inventaire tournant** – Après avoir créé le travail d'inventaire tournant, vous effectuez le travail d'inventaire tournant en comptant les articles dans un emplacement d'entrepôt puis vous utilisez un appareil mobile pour entrer le résultat dans Dynamics 365 Supply Chain Management. Sinon, vous pouvez compter les articles dans un emplacement d'entrepôt sans créer de travail d'inventaire tournant. Ce processus est également appelé *inventaire tournant ponctuel*.
3.  **Corriger des différences dans la valeur comptabilisée** – Après la réalisation d'un inventaire tournant, les articles présentant des différences au niveau de la valeur comptabilisée ont un statut de travail de **Révision en attente** dans la page **Tout le travail**. Vous pouvez résoudre ces différences dans la page **Révision en attente de travail d'inventaire tournant**.

L'illustration suivante indique comment effectuer le processus d'inventaire tournant. ![Flux de processus pour l'inventaire tournant](./media/performcyclecountinginawarehouselocation.jpg)

## <a name="cycle-counting-prerequisites"></a>Conditions requises pour l'inventaire tournant
Le tableau suivant indique les conditions requises devant être mises en place avant d'utiliser l'inventaire tournant.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Logiciel requis</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Article</td>
<td>L'article doit être activé pour les processus de gestion des entrepôts.</td>
</tr>
<tr class="even">
<td>Entrepôt</td>
<td>L'entrepôt doit être activé pour les processus de gestion des entrepôts. Pour activer l'entrepôt pour les processus de gestion des entrepôts, dans la page <strong>Entrepôts</strong>, sélectionnez l'entrepôt, puis activez l'option <strong>Utiliser les processus de gestion des entrepôts</strong>. Pour autoriser des collaborateurs à déplacer des palettes pendant un inventaire tournant, dans l'organisateur <strong>Gestion des entrepôts</strong>, sélectionnez l'option <strong>Autoriser les déplacements de palettes pendant l'inventaire tournant</strong>.</td>
</tr>
<tr class="odd">
<td>Pools de travail</td>
<td>Facultatif : Créez un pool de travail pour isoler le travail d'entrepôt selon le type de travail (dans ce cas, un travail d'inventaire tournant).</td>
</tr>
<tr class="even">
<td>Lieux</td>
<td>Activez l'inventaire tournant pour les emplacements. Pour autoriser un inventaire tournant pour un emplacement d'entrepôt, dans la page <strong>Profils d'emplacement</strong>, sélectionnez l'option <strong>Autoriser l'inventaire tournant</strong>.</td>
</tr>
<tr class="odd">
<td>Paramètres de gestion des entrepôts</td>
<td>Définissez les paramètres de l'inventaire tournant. Dans la page <strong>Paramètres de gestion des entrepôts</strong>, spécifiez le code type d'ajustement par défaut, l'ID de la classe de travail et la priorité du travail pour l'inventaire tournant.</td>
</tr>
<tr class="even">
<td>Appareil mobile</td>
<td><ul>
<li>Créez une option de menu pour l'une des méthodes suivantes dans la page <strong>Options de menu d'appareil mobile</strong> :
<ul>
<li>Inventaire tournant dirigé par utilisateur</li>
<li>Inventaire tournant dirigé par le système</li>
<li>Regroupement d'inventaires tournants</li>
<li>Inventaire tournant ponctuel</li>
</ul>
</li>
<li>Paramétrez un menu pour l'appareil mobile.</li>
<li>Créez un compte d'utilisateur de travail et affectez un menu d'appareil mobile à l'ID utilisateur de travail.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tâche associée de paramétrage</td>
<td>Paramétrez un plan d'inventaire tournant pour un emplacement d'entrepôt.</td>
</tr>
</tbody>
</table>

## <a name="automatically-create-cycle-counting-work"></a>Créer automatiquement un travail d'inventaire tournant
Il existe deux manières de planifier la création récurrente du travail d'inventaire tournant : le paramétrage des seuils d'inventaire tournant ou celui des plans d'inventaire tournant.

-   Un seuil d'inventaire tournant indique la limite de quantité ou de pourcentage des articles en stock. Le travail d'inventaire tournant est automatiquement créé lorsque la limite de seuil est atteinte.
-   Un plan d'inventaire tournant crée un travail d'inventaire tournant immédiatement ou périodiquement par le biais d'un traitement par lots. Lorsqu'un travail d'inventaire tournant est créé, la ligne de travail d'inventaire comprend des informations sur l'emplacement d'inventaire. Le stock disponible associé à cet emplacement n'est pas bloqué et il est donc disponible pour la réservation et le traitement sortant, même si un travail d'inventaire en cours existe.

### <a name="create-cycle-counting-work-based-on-threshold-parameters-for-items"></a>Créer un inventaire tournant basé sur des paramètres de seuil pour les articles

Le travail d'inventaire tournant peut être créé lorsque le nombre d'articles passe en dessous d'une valeur de seuil spécifique dans un emplacement. Par exemple, supposons que vous ayez 60 articles dans un emplacement dont le seuil d'inventaire tournant est de 40. Lors d'une transaction de commande client, 25 articles sont prélevés de l'emplacement et placés dans un emplacement temporaire. Étant donné que le nombre d'articles restants, 35, est inférieur à la quantité de seuil, un travail d'inventaire tournant est automatiquement créé pour l'emplacement.

### <a name="schedule-cycle-counting-work"></a>Planification d'un travail d'inventaire tournant

Vous pouvez programmer des plans d'inventaire tournant pour créer le travail d'inventaire tournant immédiatement ou périodiquement. En paramétrant des plans de cycle d'inventaire, vous pouvez contrôler le pool de travail pour lequel le travail d'inventaire tournant est créé, le nombre maximal d'inventaires tournants créés pour des articles dans différents emplacements et le nombre de jours avant le prochain inventaire de l'entrepôt. Par exemple, un article est disponible dans trois emplacements de l'entrepôt et le nombre maximal d'inventaires tournants est défini sur **2**. Dans ce cas, lorsque vous exécutez le plan d'inventaire tournant, deux inventaires tournants sont créés pour les deux emplacements dans lesquels l'article est présent. Autre exemple, vous définissez le nombre de jours entre les inventaires tournants sur **5**. Dans ce cas, le travail d'inventaire tournant est créé tous les cinq jours. Toutefois, si le travail d'inventaire tournant est traité le jour 3, le travail d'inventaire tournant suivant sera créé cinq jours après le traitement du dernier inventaire tournant, le jour 8.

## <a name="create-cycle-counting-work-manually"></a>Création manuelle d'un travail d'inventaire tournant
Pour créer manuellement un cycle d'inventaire tournant, utilisez les pages **Inventaire tournant par article** ou **Travail d'inventaire tournant par emplacement**. Vous pouvez spécifier le nombre maximal d'inventaires tournants à créer. Par exemple, si le responsable d'entrepôt spécifie une valeur de **5**, alors le travail d'inventaire tournant est créé pour cinq emplacements, même si l'article est présent dans 10 emplacements. Vous pouvez également choisir un ID de pool de travail auquel attribuer les ID de travail d'inventaire tournant créés. Lorsqu'un ID de pool de travail est traité pour l'inventaire tournant, les ID de travail d'inventaire tournant qui sont affectés au pool de travail sont traités comme un groupe.

## <a name="perform-a-cycle-count-by-using-a-mobile-device"></a>Effectuer un inventaire tournant en utilisant un appareil mobile
Il existe plusieurs méthodes pour traiter un travail d'inventaire tournant à l'aide de Supply Chain Management sur un appareil mobile :

-   **Dirigé par l'utilisateur** – Le collaborateur peut préciser un ID de travail d'inventaire tournant qui a le statut **Ouvert**.
-   **Dirigé par le système** – Supply Chain Management attribue un ID de travail d'inventaire au collaborateur.
-   **Regroupement d'inventaires tournants** – Le collaborateur peut regrouper plusieurs ID de travail d'inventaire tournant qui sont spécifiques à un emplacement, à une zone ou à un pool de travail.
-   **Inventaire tournant ponctuel** – Le collaborateur peut compter les articles dans un emplacement d'entrepôt à tout moment, sans créer de travail d'inventaire tournant. Pour effectuer l'inventaire tournant ponctuel dans un emplacement, le travailleur entre l'ID de l'emplacement.

L'exemple suivant montre comment vous pouvez effectuer un inventaire tournant ponctuel à l'aide d'un appareil mobile. Les instructions que le travailleur voit sur le périphérique varient selon le paramétrage de l'élément de menu pour l'inventaire tournant ponctuel.

1.  Sur l'appareil mobile, sélectionnez l'option de menu pour traiter le travail d'inventaire tournant ponctuel.
2.  Enregistrez l'emplacement pour lequel vous voulez effectuer l'inventaire tournant.
3.  Enregistrez et confirmez le numéro d'article et la quantité de l'article compté. **Remarque :** Le statut du travail d'inventaire tournant est mis à jour sur **Révision en attente** ou **Clôturé** dans la page **Tout le travail**, selon les paramètres définis dans la page **Collaborateur**.
4.  Facultatif : Répétez l'étape 3 pour les articles restants de l'emplacement et confirmez qu'il n'existe aucun article supplémentaire disponible pour le comptage.

## <a name="resolve-cycle-counting-differences"></a>Résoudre les différences de l'inventaire tournant
Une différence au niveau de l'inventaire tournant se produit dans les scénarios suivants si l'option **Superviseur d'inventaire tournant** est réglée sur **Non** pour un ID utilisateur de travail :

-   La valeur d'inventaire tournant n'est pas comprise dans les limites d'écart spécifiées dans les champs **Limite maximale du pourcentage** ou **Limite maximale de la quantité** dans la page **Utilisateurs du travail**. Par exemple, la quantité de stock disponible dans un emplacement est de 50 et la limite d'écart pour l'utilisateur de travail est de 10. Si l'utilisateur de travail entre une valeur qui n'est pas comprise entre 40 et 60, une différence se produit.
-   La valeur d'inventaire tournant diffère de la quantité de stock disponible et aucune limite d'écart n'est définie.

Ajustez les différences dans la valeur d'inventaire puis acceptez la valeur d'inventaire dans la page **Inventaire tournant en attente de révision**. Vous pouvez vérifier le compte modifié de la quantité d'articles dans la page **Disponible par emplacement**. La valeur d'inventaire est rejetée si la différence ne peut pas être approuvée.

## <a name="additional-resources"></a>Ressources supplémentaires
[Configurer des appareils mobiles pour un travail d'entrepôt](configure-mobile-devices-warehouse.md)



