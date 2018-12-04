---
title: Amortissement de consommation
description: "Cet article donne une vue d'ensemble de la méthode de consommation de l'amortissement."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0c48877058edf8251ef6eb5dd63d7eecd1866f33
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="consumption-depreciation"></a>Amortissement de consommation

[!include [banner](../includes/banner.md)]

Cet article donne une vue d'ensemble de la méthode de consommation de l'amortissement.

Si vous paramétrez un profil d'amortissement pour des immobilisations et que vous sélectionnez **Consommation** dans le champ **Méthode** de la page **Profils d'amortissement**, les immobilisations affectées au profil d'amortissement sont basées sur leur utilisation. Vous n'êtes pas obligé de paramétrer des pourcentages et des intervalles sur la page **Profils d'amortissement**. Après avoir créé un profil d'amortissement qui utilise la méthode Consommation, vous pouvez paramétrer la méthode de plusieurs manières.

## <a name="set-up-and-use-consumption-depreciation"></a>Paramétrage et utilisation de l'amortissement par consommation
1.  Sur la page **Profils d'amortissement**, créez le profil d'amortissement. Pour les calculs de consommation, le profil d'amortissement doit être doté d'un ID et d'un nom, et vous devez sélectionner **Consommation** dans le champ **Méthode**.
2.  Sur la page **Facteurs de consommation**, paramétrez les facteurs de consommation. Chaque facteur de consommation doit être doté d'un ID et d'un nom, ainsi que d'un facteur de consommation spécifié en tant que quantité ou pourcentage.
3.  Sur la page **Unités de consommation**, paramétrez les unités de consommation. Chaque unité de consommation doit avoir un ID et un nom. Les unités d'amortissement permettent de calculer l'amortissement par consommation sur la page **Amortissement de consommation**. Exemples d'unités : un kilomètre (km), un kilogramme (kg) ou une heure.
4.  Sur la page **Immobilisations**, paramétrez les immobilisations individuelles. Pour chaque immobilisation, sélectionnez des modèles de valeurs et des registres des amortissements associés à des profils d'amortissement. Vous devez paramétrer des modèles de valeur ou des registres des amortissements pour l'amortissement par consommation, si une de vos immobilisations utilise des profils d'amortissement basés sur la méthode Consommation. Ce paramétrage est effectué soit sous l'onglet **Amortissement** de la page **Modèles de valeur**, soit dans l'organisateur **Général** de la page **Profil d'amortissement**. Vous pouvez utiliser le même modèle de valeur pour plusieurs immobilisations. Les profils d'amortissement font partie du modèle de valeur ou du registre des amortissements sélectionnés pour chaque immobilisation. Vous ne pouvez pas ajouter ni modifier de profils d'amortissement directement sur la page **Immobilisations**. Vous pouvez modifier les profils d'amortissement uniquement sur la page **Registres des amortissements**.
5.  Sur la page **Modèles de valeur** ou la page **Registres des amortissements**, dans le groupe de champs **Amortissement de consommation**, renseignez les champs suivants :
    -   Facteur de consommation
    -   Unité
    -   Amortissement à l'unité
    -   Consommation estimée

    Le champ**Consommation validée** indique l'amortissement par consommation, en unités, qui a déjà été validé soit pour la combinaison de l'immobilisation et du modèle de valeur, soit pour le registre des amortissements. Vous ne pouvez pas mettre à jour manuellement la valeur de ce champ.

## <a name="examples"></a>Exemples
### <a name="example-1"></a>Exemple 1

Le facteur de consommation suivant est paramétré pour le 31 janvier :

-   La quantité est de 1 000.
-   Le prix d'amortissement à l'unité spécifié est de 1,5.

La proposition d'amortissement du 31 janvier est la suivante : Quantité × Amortissement à l'unité 1 000 × 1,5 = 1 500 Si le facteur spécifié pour l'immobilisation est un facteur de pourcentage, la quantité qui est estimée dans le champ **Consommation estimée** pour le modèle de valeur de l'immobilisation est multiplié par le pourcentage paramétré pour la date de fin sélectionnée. La quantité qui en résulte est ensuite suggérée comme quantité d'amortissement pour la période.

### <a name="example-2"></a>Exemple 2

Le facteur suivant pour l'amortissement par consommation est paramétré pour le 31 janvier :

-   La pourcentage est de 10 pour cent.
-   Le prix d'amortissement à l'unité spécifié est de 1,5.
-   La quantité estimée de l'immobilisation est de 2 000.

La proposition d'amortissement du 31 janvier est la suivante : Quantité estimée × Pourcentage x Amortissement à l'unité 2 000 × 0,10 × 1,5 = 300




