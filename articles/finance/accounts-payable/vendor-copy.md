---
title: Copier des fournisseurs à l’aide de souches de numéros partagées
description: Cette rubrique explique comment utiliser des souches de numéros partagées pour copier un fournisseur dans une autre entité juridique tout en conservant le même ID fournisseur.
author: sunfzam
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: e29932ca34576d15b7350ab6c711563682d8ddf8
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753541"
---
# <a name="copy-vendors-by-using-shared-number-sequences"></a>Copier des fournisseurs à l’aide de souches de numéros partagées

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser des souches de numéros partagées pour affecter des ID fournisseur. Les souches de numéros partagées vous permettent également de copier des fournisseurs d’une entité juridique à une autre tout en utilisant les mêmes ID fournisseur dans les deux entités juridiques.

## <a name="setup"></a>Configuration

La fonction est activée lorsque vous utilisez une souche de numéros partagée pour affecter des ID fournisseur. Vous devez utiliser la même souche de numéros dans chaque entité juridique dans laquelle vous souhaitez copier un fournisseur. Vous modifiez la souche de numéros fournisseur dans la page **Paramètres de la comptabilité fournisseur** pour chaque entité juridique. Sélectionnez **Comptabilité fournisseur** \> **Paramétrage** \> **Paramètres de la comptabilité fournisseur**, puis sélectionnez l’onglet **Souches de numéros**.

Vous pouvez également paramétrer des souches de numéros fournisseur pour chaque groupe de fournisseurs. Ces souches de numéros doivent également être partagées. La souche de numéros d’un groupe de fournisseurs est utilisée en premier. Si aucune souche de numéros n’est spécifiée pour un groupe de fournisseurs, la souche de numéros spécifiée dans la page **Paramètres de la comptabilité fournisseur** est utilisée.

Vous pouvez également copier des fournisseurs entre entités juridiques si vous utilisez des ID fournisseur manuels. Toutefois, si vous tentez de copier un fournisseur dans une entité juridique où l’ID fournisseur existe déjà, le processus de copie ne démarrera pas.

## <a name="copy-a-vendor"></a>Copier un fournisseur

Pour copier un fournisseur, sélectionnez **Nouveau** dans la page de liste **Tous les fournisseurs** pour ouvrir la page **Tous les fournisseurs, nouvel enregistrement**. Notez que le nouvel ID fournisseur n’est pas affecté immédiatement. Ce comportement diffère de celui des versions précédentes. Comme vous n’avez pas encore sélectionné le groupe de fournisseurs, le système ne peut pas déterminer la souche de numéros appropriée à utiliser. En outre, il ne peut pas déterminer si vous essayez de créer un fournisseur ou de copier un fournisseur. Par conséquent, l’ID fournisseur n’est pas affecté tant que vous ne cliquez pas sur **Enregistrer** en bas de la page.

Si vous créez un nouveau fournisseur, vous pouvez continuer à renseigner tous les champs comme vous le faites habituellement. Lorsque vous avez terminé et que vous cliquez sur **Enregistrer**, vous verrez que l’ID fournisseur a été affecté automatiquement. Sinon, pour les souches de numéros manuelles, vous verrez que votre ID fournisseur manuel a été utilisé.

Pour copier un fournisseur, dans le champ **Nom**, entrez un ou plusieurs caractères qui représentent le fournisseur que vous recherchez. Une boîte de dialogue de recherche affiche une liste de parties qui peuvent représenter le fournisseur que vous recherchez. Lorsque vous sélectionnez une des parties, des informations supplémentaires s’affichent à droite de la boîte de dialogue :

- L’onglet **Général** affiche le numéro de téléphone et l’adresse de la partie.
- L’onglet **Rôles** affiche les rôles disponibles pour la partie sélectionnée et l’entité juridique où se trouve chaque rôle.
- L’onglet **ID enregistrement de taxe** affiche les ID enregistrement de taxe affectés à la partie.

Vous pouvez copier une partie uniquement si un rôle fournisseur lui est affecté et si ce rôle se trouve dans une entité juridique qui n’est pas l’entité juridique actuelle. Lorsque vous trouvez une partie qui répond à ces critères, procédez comme suit.

1. L’option **Copier un fournisseur** s’affiche. Par défaut, cette option est définie sur **Non**. Pour copier le fournisseur dans l’entité juridique actuelle, définissez l’option sur **Oui**. 
2. Le champ **Entité juridique** s’affiche. Sélectionnez l’entité juridique à partir de laquelle copier le fournisseur. Si le fournisseur existe dans une seule entité juridique, le champ est défini sur cette entité juridique par défaut.
3. Cliquez sur **Sélectionner**. Le nouveau fournisseur est créé.

## <a name="validation"></a>Validation

Lorsque vous copiez un fournisseur, le système essaie d’enregistrer les nouvelles informations sur le fournisseur. Les validations sont exécutées pour vérifier que les données copiées sont correctes. Vous recevez un message d’erreur pour chaque validation qui échoue. Les messages d’erreur expliquent quelles informations doivent être mises à jour. La copie du fournisseur ne peut pas être enregistrée tant que vous ne résolvez pas toutes les erreurs de validation.

## <a name="copy-a-vendor-by-using-the-tax-exempt-number-search-feature"></a>Copie d’un fournisseur à l’aide de la fonction de recherche du numéro identifiant TVA

Vous pouvez également copier des fournisseurs à l’aide de la fonction de recherche du numéro identifiant TVA qui est disponible dans le groupe **Enregistrement** sous l’onglet **Fournisseurs** du volet Actions de la page **Tous les fournisseurs**. La boîte de dialogue **Recherche du numéro identifiant TVA** qui s’affiche répertorie les numéros identifiant TVA, l’ID fournisseur, le nom du fournisseur et l’entité juridique où l’ID identifiant TVA est utilisé. Vous pouvez copier un fournisseur uniquement s’il se trouve dans une entité juridique qui n’est pas l’entité juridique actuelle. Après avoir sélectionné un fournisseur qui répond à ce critère, procédez comme suit.

1. L’option **Copier un fournisseur** s’affiche. Par défaut, cette option est définie sur **Non**. Pour copier le fournisseur dans l’entité juridique actuelle, définissez l’option sur **Oui**.
2. Cliquez sur **Sélectionner**. Le nouveau fournisseur est créé.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
