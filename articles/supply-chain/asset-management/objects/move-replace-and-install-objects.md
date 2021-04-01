---
title: Déplacer, remplacer et installer des actifs
description: Cette rubrique explique comment déplacer, remplacer et installer des actifs dans Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectReplace, EntAssetObjectInstallLookup, EntAssetObjectMove, EntAssetObjectTableEditSubObjects
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f5eff3cc1bcf85e1541917edf525d83c124edb7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253228"
---
# <a name="move-replace-and-install-assets"></a>Déplacer, remplacer et installer des actifs

[!include [banner](../../includes/banner.md)]

 

Cette rubrique explique comment déplacer, remplacer et installer des actifs dans Gestion des actifs. Vous pouvez créer les actifs individuels sans aucun lien avec d’autres actifs, ou créer une structure d’actif incluant un actif parent (actif supérieur) et des actifs enfants associés (sous-actifs). Dans Gestion des actifs, il existe trois approches pour déplacer et modifier l’emplacement d’un actif :

- **Déplacer** - Déplacement d’un actif vers une autre structure d’actif, ou vers un autre emplacement dans la même structure d’actif.
- **Remplacer** - Suppression temporaire d’un actif d’une structure d’actif afin de pouvoir réparer ou rénover un actif, puis rajout de l’actif rénové à la structure d’actif ultérieurement. Sinon, remplacement définitif d’un actif usagé par un nouvel actif.
- **Installer** - Installation d’un actif parent et de tous les actifs enfants associés à un poste technique.

> [!NOTE]
> L’actif que vous déplacez, remplacez ou installez peut être associé à un autre poste technique. Dans ce cas, l’actif peut utiliser des dimensions financières du poste technique. Sur la page **Types de postes techniques**, vous paramétrez le traitement des dimensions financières aux postes techniques.

## <a name="move-asset"></a>Déplacer l’actif

Utilisez la fonctionnalité **Déplacer l’actif** pour déplacer l’actif vers une autre structure d’actif, ou vers un autre emplacement dans la même structure d’actif. Vous pouvez également déplacer un actif en dehors d’une structure d’actif afin qu’il devienne autonome sans aucune relation de structure.

> [!NOTE]
> N’utilisez pas cette fonctionnalité si des actifs sont en cours de réparation ou remplacés temporairement. Au lieu de cela, utilisez la fonctionnalité **Remplacer l’actif** décrite plus loin dans cette rubrique.

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les Actifs** ou **Actifs actifs**.
2. Dans la liste, sélectionnez l’actif à déplacer. Si l’actif comporte des actifs enfants, vous déplacez également ces actifs.
3. Sélectionnez **Déplacer l’actif**.
4. Pour déplacer l’actif afin qu’il puisse faire une partie d’une structure d’actif, sélectionnez le nouvel actif parent dans le champ **Actif parent**. Si vous déplacez un actif enfant, et que vous souhaitez en faire un actif autonome qui n’a aucune relation de structure, laissez le champ **Actif parent** vide.
5. Par défaut, le champ **Date d’effet** est défini sur la date et l’heure actuelles. Toutefois, vous pouvez sélectionner d’autres date et heure à partir desquelles le déplacement de l’actif sera valide.
6. Cliquez sur **OK**.

## <a name="replace-asset"></a>Remplacer l’actif

Utilisez la fonctionnalité **Remplacer l’actif** en relation avec des réparations, une rénovation ou un remplacement permanent d’un actif usagé par un nouvel actif. Cette fonctionnalité permet de remplacer les actifs enfants dans une structure d’actif. Pour les actifs parents (c’est-à-dire les actifs qui n’ont pas d’actif parent actuellement), ce remplacement est effectué à un poste technique. Pour plus d’informations sur le remplacement des actifs parents à un poste technique, voir [Installer des actifs et des postes techniques](../functional-locations/install-objects-on-functional-locations.md).

> [!NOTE]
> Si un atelier de réparation est lié à votre service de production, vous pouvez créer des postes techniques, tels que **Réparation**, **Rebut** et **Stockage** pour gérer la réparation et le remplacement des actifs.

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les Actifs** ou **Actifs actifs**.
2. Dans la liste, sélectionnez l’actif enfant à remplacer. Si l’actif comporte des actifs enfants, vous remplacez également ces actifs.
3. Sélectionnez **Remplacer l’actif**.

    Le champ **Modification de la structure** affiche les dernières date et heure auxquelles l’actif et les actifs enfants associés sélectionnés ont été déplacés dans la structure de l’actif.

4. Dans la section **Actif sélectionné**, dans le champ **Poste technique cible**, sélectionnez le poste technique vers lequel déplacer l’actif. Par exemple, sélectionnez l’emplacement **Réparation** ou **Rebut**.

    Dans la section **Actif parent**, le champ **Date d’effet** affiche les dernières date et heure auxquelles l’actif parent et les actifs enfants associés ont été installés ou déplacés au poste technique actuel.

5. Dans la section **Nouvel actif**, dans le champ **Actif**, sélectionnez l’actif à insérer comme remplacement temporaire ou permanent pour l’actif sélectionné. Cet actif peut se trouver actuellement à un autre poste technique, tel que **Stockage**.
7. Dans la section **Début d’effet**, le champ **Date d’effet** est défini sur la date et l’heure actuelles par défaut. Toutefois, vous pouvez sélectionner d’autres date et heure à partir desquelles le remplacement de l’actif sera valide.
8. Cliquez sur **OK**.

## <a name="install-asset"></a>Installer l’actif

Utilisez la fonctionnalité **Installer l’actif** pour installer une structure d’actif à un poste technique.

> [!NOTE]
> Sélectionnez toujours un actif parent. L’actif parent et les actifs enfants associés sont déplacés vers le poste technique sélectionné.

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les Actifs** ou **Actifs actifs**.
2. Dans la liste, sélectionnez l’actif parent à installer à un autre poste technique.
3. Sélectionnez **Installer l’actif**.

    La section **Attributs** affiche les attributs de l’actif qui sont paramétrés sur l’actif parent.

4. Dans le champ **Poste technique**, sélectionner le nouvel emplacement.
5. Par défaut, le champ **Date d’effet** est défini sur la date et l’heure actuelles. Toutefois, vous pouvez sélectionner d’autres date et heure à partir desquelles l’installation sur la structure d’actif sera valide.
6. Cliquez sur **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]