---
title: Créer un actif
description: Cette rubrique décrit comment créer un actif dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTableCopyStructure, EntAssetObjectTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28c4685c3b6f543324953cd03646d5b15fdb8c59
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019427"
---
# <a name="create-an-asset"></a>Créer un actif

[!include [banner](../../includes/banner.md)]

 

Cette rubrique décrit comment créer un actif dans le module Gestion des actifs.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs** ou **Actifs actifs**.
2. Cliquez sur le bouton **Nouveau**.
3. Dans la boîte de dialogue **Créer des actifs**, insérez des données relatives à l'**Actif** (l'ID d'actif) et le nom de l'actif. Sélectionnez la date et l'heure d'effectivité de l'actif dans le champ **Date d'effet**. À partir de cette date, vous pouvez installer l'actif dans un poste technique, ainsi qu'un déplacement et remplacement de l'actif dans une structure d'actif.
4. Dans le champ **Type d'actif**, sélectionnez le type d'actif pour l'actif (champ obligatoire). Si nécessaire, sélectionnez **Fabricant d'actif** et **Modèle d'actif** pour l'actif. Si un seul produit a été paramétré, ce produit est automatiquement sélectionné dans le champ **Fabricant d'actif**. Les sélections disponibles dans les champs **Fabricant d'actif** et **Modèle d'actif** dépendent du paramétrage dans [Fabricants et modèles d'actifs](../setup-for-objects/product-and-model.md).
5. Dans le groupe **Actif des parents**, le champ **Actif** est vide par défaut. Si nécessaire, vous pouvez sélectionner un actif parent, puis tous les champs du groupe **Actif des parents** sont automatiquement complétés.
    >[!NOTE]  
    >Lorsque vous sélectionnez un actif parent, deux ou trois onglets sont disponibles : L'onglet **Mes actifs** contient des actifs associés à des postes techniques dans lesquels vous (l'agent de maintenance connecté au système) pouvez être affecté(e). Si aucun poste technique n'est paramétré sur un agent de maintenance dans l'écran [Agents de maintenance et groupes d'employés](../setup-for-objects/workers-and-worker-groups.md), l'onglet **Mes actifs** ne sera pas visible. L'onglet **Actifs actifs** contient la liste de tous les actifs avec l'état de cycle de vie de l'actif « Actif ». L'onglet **Vue des actifs** affiche une arborescence des postes techniques et des actifs installés sur ces emplacements.

6. Le poste technique par défaut que vous avez paramétré est proposé pour l'actif dans le groupe **Actif** > champ **Poste technique**. Sélectionnez un autre poste technique, si nécessaire.

    >[!NOTE]
    >Après avoir créé un actif, vous pouvez l'installer sur un autre poste technique, si nécessaire. Seuls les actifs supérieurs (actifs sans actif des parents actuel) peuvent être installés sur un poste technique. Cela signifie que vous installez le niveau supérieur ainsi que tous les actifs enfants sous le poste technique sélectionné. Découvrez-en plus sur l'installation des actifs dans des postes techniques dans [Vue d'ensemble des postes techniques](../functional-locations/introduction-to-functional-locations.md).

7. Cliquez sur **OK**.
8. Sélectionnez l'actif dans la liste **Tous les actifs**, puis cliquez sur le bouton **Modifier** pour ajouter des informations à l'actif.

## <a name="general-information"></a>Informations générales

Le poste technique dans lequel l'actif est regroupé est affiché dans le champ **Poste technique**. Si l'actif est un actif parent, le nombre d'enfants lié à l'actif est affiché dans le champ **Enfants**. Si l'actif est un sous-actif d'un actif existant, l'ID de l'actif des parents est affiché dans le champ **Parent**.

Vous pouvez modifier les informations relatives à **Fabricant d'actif** et **Modèle d'actif** sur l'actif, qui permet de gérer des pièces détachées, des pièces détachées de remplacement, des valeurs par défaut du type de tâche. Voir [Fabricants et modèles d'actifs](../setup-for-objects/product-and-model.md) pour plus d'informations. Vous pouvez également ajouter des informations sur **Année du modèle** et **Numéro de série**, si nécessaire.

Le paramètre **État du cycle de vie actuel** permet de définir si l'actif est actif ou inactif. En créant un actif, le stade est toujours défini sur le premier stade du groupe de stades d'actifs. Lorsque vous êtes prêt(e) à activer un actif, cliquez sur **Mettre à jour l'état d'actif**, puis sélectionnez l'état de cycle de vie que vous avez défini comme « actif actif », puis cliquez sur **OK**.

**Remarque :** Lorsqu'un actif est défini sur « inactif », il n'est plus possible de créer des ordres de travail pour l'actif. En outre, vous ne pouvez pas planifier des tâches de maintenance préventive pour un actif inactif.

Les champs **Niveau de service** et **Criticalité** se rapportent aux ordres de travail créés pour l'actif Les champs affichent les nombres **Niveau de service** et **Criticalité** calculés pour le paramètre actuel de l'actif. Voir [Niveaux de service des actifs](../setup-for-objects/object-priorities.md) et [Types d'élément critique des actifs](../setup-for-objects/object-criticalities.md) en considérant le paramétrage de ces valeurs.

## <a name="asset"></a>Actif

Vous pouvez sélectionner **Ressource** pour l'actif. La sélection de ressources détermine le calendrier à utiliser pour la planification des ordres de travail. La sélection de ressources est souvent utilisée pour les actifs. Les ressources et les groupes de ressources sont paramétrés dans **Administration d'organisation** > **Ressources** > **Groupes de ressources** ou **Ressources**.

Dans le champ **Nombre d'actifs**, vous pouvez sélectionner un actif à associer à l'actif. Cela est pertinent si votre actif est lié à un projet d'investissement.

- Si l'actif est associé à un actif, vous pouvez créer un type d'ordre de travail à utiliser pour les ordres de travail associés à un projet d'investissement. 
- Les informations sur les actifs pour un actif sont liées au module **Actifs** dans Dynamics 365 Supply Chain Management. Cela signifie que dans **Actifs** > **Actifs** > **Actifs**, vous pouvez obtenir une vue d'ensemble des projets de gestion d'actifs qui peuvent être associés à un actif en sélectionnant l'actif dans la liste et en affichant le contenu dans le volet **Informations associées** > section **Projets associés**.


## <a name="details"></a>Détails

Dans le champ **Actif à partir du**, la date à laquelle vous avez mis à jour l'état du cycle de vie de l'actif à un état actif (voir [États du cycle de vie de l'actif](../setup-for-objects/object-stages.md) concernant le paramétrage des états du cycle de vie de l'actif), s'affiche. Si l'actif n'est plus actif, et que vous avez mis à jour l'état du cycle de vie de l'actif à un état de cycle de vie inactif, la date à partir de laquelle l'actif est inactif est affichée dans le champ **Actif jusqu'à**. Au besoin, vous pouvez changer manuellement ces dates.

Si nécessaire, vous pouvez insérer une date prévue pour le remplacement de l'actif dans le champ **Date de remplacement**. La valeur estimée pour remplacer l'actif peut être insérée dans le champ **Valeur de remplacement**. Exemple : Vous pouvez utiliser les informations de remplacement pour les comparer aux coûts de maintenance d'un actif, puis prendre la décision d'acheter un nouvel actif si les coûts de maintenance de l'actif existant augmentent rapidement.

## <a name="notes"></a>Notes

Vous pouvez ajouter des notes relatives à l'actif sur l'organisateur **Détails**. Cliquez sur le bouton **Ajouter l'horodatage** avant que vous écriviez la note, si vous souhaitez ajouter les informations utilisateur et une date/un horodatage à la note.

## <a name="attributes"></a>Attributs

Sous cet organisateur, vous pouvez définir les valeurs définies pour les attributs d'actifs. Ces attributs peuvent être utilisés pour décrire des propriétés ou des caractéristiques pertinentes pour l'actif, telles que la taille, le poids ou la configuration de la machine.

Cliquez sur **Ajouter la ligne**, puis sélectionnez le type d'attribut. Ensuite, insérez la **Valeur** associée au type d'attribut et sauvegardez l'enregistrement.

>[!NOTE] 
>Vous pouvez obtenir une vue d'ensemble des types d'attribut d'actif et leurs relations aux actifs dans **Attribut d'actif** et **Vue d'ensemble des attributs des actifs**. Voir [Vue d'ensemble des attributs des actifs](../objects/object-specification-overview.md) pour plus d'informations.

## <a name="vendor"></a>Fournisseur

Dans l'organisateur **Fournisseur**, sélectionnez un compte fournisseur pour l'actif. De même, si une garantie de fournisseur a été octroyée, vous pouvez insérer des informations de garantie ici.

## <a name="address"></a>Adresse

Dans l'organisateur **Adresse**, vous pouvez insérer l'adresse de l'équipement. Si aucune adresse n'est insérée dans l'actif, l'actif utilise l'adresse d'un actif parent, si l'actif parent contient une adresse. Si aucune adresse n'est associée à l'actif ou à un parent dans la hiérarchie d'actifs, l'adresse du poste technique dans lequel l'actif est installé peut être utilisée. Si ce poste technique n'a aucune adresse associée à celui-ci, l'adresse du poste technique parent est utilisée dans l'actif.

## <a name="asset-management-plans"></a>Plans de gestion des actifs

Des plans de maintenance sont utilisés pour planifier des tâches de maintenance préventive à intervalles réguliers sur l'actif. Sous cet organisateur, vous pouvez paramétrer des lignes de plan de mise à jour de l'actif sélectionné. Les visites de maintenance peuvent être configurées pour divers actifs sur lesquels vous devez effectuer une tâche similaire à intervalles réguliers. Dans l'onglet **Plans de maintenance des postes techniques**, les plans de maintenance liés au poste technique dans lequel l'actif est installé.

>[!NOTE]
>Si vous supprimez une ligne de plan de maintenance ou une visite de maintenance à un actif dans **Tous les actifs**, vous supprimez également automatiquement tous les plans de mise à jour avec le statut « Créé » ayant été créés en fonction de ce plan de maintenance ou de cette visite de maintenance.

## <a name="functional-location-maintenance-plans"></a>Plans de maintenance des postes techniques

Dans cet organisateur, vous pouvez obtenir une vue d'ensemble des plans de maintenance des postes techniques, les plans de maintenance liés au poste technique dans lequel l'actif est installé.

## <a name="maintenance-rounds"></a>Visites de maintenance

Sous cet organisateur, vous pouvez ajouter ou supprimer les visites de maintenance étant associées à l'actif.

## <a name="financial-dimensions"></a>Dimensions financières

Vous pouvez sélectionner des dimensions financières pour l'actif.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]