---
title: Nomenclatures des modèles
description: Une nomenclature des modèles permet d’avoir une liste normalisée des composants d’objets de service traités régulièrement.
author: ShylaThompson
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70b514aeed48180bb1b14be8b3d95d55d44d2ca8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824321"
---
# <a name="template-boms"></a>Nomenclatures des modèles    

[!include [banner](../includes/banner.md)]


Une nomenclature des modèles permet d’avoir une liste normalisée des composants d’objets de service traités régulièrement. Les composants figurant dans la nomenclature des modèles représentent les sous-composants individuels de l’objet de service. En appliquant la nomenclature des modèles à un objet de service, vous pouvez conserver un enregistrement des sous-composants remplacés sur l’objet de service.

Pour appliquer une nomenclature des modèles à un accord de service ou une commande de service, vous associez celle-ci à une relation d’objets de service.


> [!NOTE]
> <P>Vous ne pouvez appliquer qu’une seule nomenclature des modèles à un objet de service.</P>

## <a name="create-a-template-bom"></a>Création d’un modèle de nomenclature

Le tableau suivant contient des informations sur les différentes méthodes qui permettent de créer une nomenclature des modèles.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Méthode</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Production</p></td>
<td><p>La nomenclature des modèles est basée sur un ordre de fabrication. Cette option s’applique uniquement si vous opérez dans un environnement de production. Cette méthode permet d’avoir une liste détaillée et actualisée des composants d’un article.</p></td>
</tr>
<tr class="even">
<td><p>Article BOM</p></td>
<td><p>La nomenclature des modèles est basée sur un article de nomenclature. La nomenclature des articles, à la différence de la nomenclature de production, est une liste statique des composants qui constituent un article.</p></td>
</tr>
<tr class="odd">
<td><p>Modèle existant</p></td>
<td><p>Le modèle est basé sur une nomenclature des modèles existante.</p></td>
</tr>
<tr class="even">
<td><p>Manuel</p></td>
<td><p>Si vous connaissez les pièces généralement remplacées dans un objet de service, vous pouvez créer votre nomenclature des modèles manuellement. Si vous utilisez cette approche, assurez-vous que les composants inclus dans le modèle reflètent les besoins réels de votre lieu de travail.</p></td>
</tr>
</tbody>
</table>


## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a>Appliquer la nomenclature des modèles à un accord de service ou une commande de service

Vous pouvez appliquer la nomenclature des modèles à un accord de service et/ou à une commande de service. L’accord de service couvre généralement une relation de long terme avec un client. L’historique des remplacements enregistré dans la nomenclature des services constitue des données utiles pour l’accord de service.

Vous pouvez également appliquer une nomenclature des modèles à une commande de service pour enregistrer l’historique du service qui a été réalisé sur un objet de service.

## <a name="copy-the-history-of-a-service-bom"></a>Copier l’historique d’une nomenclature des services

Vous pouvez copier l’historique d’une ligne de nomenclature des services d’un accord de service vers un autre accord de service. En copiant l’historique des services entre des accords de service, vous pouvez conserver l’enregistrement des remplacements effectués sur un article.

**Exemple**

Vous avez défini un accord de service de trois ans pour le véhicule d’un client. Pendant cette période, le client s’habitue à l’excellence du service offert par la société. Par conséquent, une fois l’accord expiré, le client souhaite en paramétrer un nouveau. Vous êtes désormais en mesure de négocier un accord plus avantageux pour la société. Comme l’enregistrement des composants remplacés peut s’avérer utile à l’avenir, vous copiez l’historique de la nomenclature des services vers le nouvel accord.

## <a name="modify-the-template-bom"></a>Modifier la nomenclature des modèles

Si une nomenclature des modèles n’a pas été associée à un objet de service, vous pouvez modifier ou supprimer les lignes associées. Une fois la nomenclature des modèles associée à un objet de service, vous pouvez seulement modifier la version locale de la nomenclature. Si vous voulez copier le paramétrage de la version locale d’une nomenclature des modèles, vous pouvez créer une nomenclature des modèles basée sur la version locale. Pour plus d’informations, voir [Modifier une nomenclature des services](modify-service-bom.md).

Si vous remplacez un article dans la nomenclature, vous pouvez enregistrer le remplacement dans la ligne de nomenclature dans le concepteur de nomenclatures. Facultatif : vous pouvez créer une ligne de commande de service pour l’objet de remplacement. Si vous créez une ligne de commande de service, vous pouvez facturer l’article de remplacement. Si vous ne créez pas de ligne de commande de service pour un remplacement, l’enregistrement du remplacement est conservé à des fins de suivi de l’historique de l’objet de service.

## <a name="change-how-information-on-the-bom-line-is-displayed"></a>Modifier l’affichage des informations de la ligne de nomenclature

Vous pouvez modifier le mode d’affichage des informations de ligne de nomenclature pour toutes les nomenclatures des modèles et des services. Les modifications sont appliquées à l’ensemble des nomenclatures des modèles et des services. Y compris celles associées aux objets de service.

## <a name="set-up-number-sequences-for-template-boms"></a>Paramétrer des souches de numéros pour les nomenclatures des modèles

Pour utiliser les nomenclatures des modèles, vous devez paramétrer deux souches de numéros. Paramétrez une souche de numéros pour la nomenclature des modèles et une souche de numéros pour le numéro de ligne d’historique de nomenclature.


> [!NOTE]
> <P>Les souches de numéros sont utilisées pour attribuer des identificateurs aux enregistrements qui en ont besoin. Avant de pouvoir affecter une souche de numéros à une nomenclature des modèles ou une ligne d’historique de nomenclature, vous devez paramétrer des codes souche de numéros.</P>


## <a name="set-up-number-sequences"></a>Définir des souches de numéros

1.  Dans la page de liste **Souches de numéros**, créez des souches de numéros pour les nomenclatures des modèles et le numéro de ligne d’historique de nomenclature. 

2.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Paramètres de gestion des services**.

3.  Cliquez sur **Souches de numéros**, puis sélectionnez un code souche de numéros pour les références de souches de numéros créées dans l’écran **Souches de numéros**.

4.  Fermez l’écran pour enregistrer vos modifications.


> [!NOTE]
> <P>Le numéro de ligne d’historique de nomenclature est utilisé par le système pour associer les transactions dans l’historique de nomenclature avec un accord ou une commande de service. Le numéro n’est pas affiché dans l’interface utilisateur.</P>



## <a name="see-also"></a>Voir également :

[Création d’un modèle de nomenclature](create-template-bom.md)

[Gestion des modèles de nomenclatures sur des relations d’objets](manage-template-boms-on-object-relations.md)

[Modifier une nomenclature des services](modify-service-bom.md)

 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]