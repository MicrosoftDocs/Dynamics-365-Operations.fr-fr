---
title: Copier des clients à l’aide de souches de numéros partagées
description: Cet article explique comment utiliser des souches de numéros partagées pour copier un client dans une autre entité juridique tout en conservant le même ID client.
author: abruer
ms.date: 08/31/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 54639356007198f256f0d80fce9bfa2013f7b2b7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899983"
---
# <a name="copy-customers-by-using-shared-number-sequences"></a>Copier des clients à l’aide de souches de numéros partagées

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser des souches de numéros partagées pour affecter des ID client. Les souches de numéros partagées vous permettent également de copier des clients d’une entité juridique à une autre tout en utilisant les mêmes ID client dans les deux entités juridiques.

## <a name="setup"></a>Configuration

La fonction est activée lorsque vous utilisez une souche de numéros partagée pour affecter des ID client. Vous devez utiliser la même souche de numéros dans chaque entité juridique dans laquelle vous souhaitez copier un client. Vous modifiez la souche de numéros client dans la page **Paramètres de la comptabilité client** pour chaque entité juridique. Sélectionnez **Comptabilité client** \> **Paramètres**, puis sélectionnez l’onglet **Souches de numéros**.

Vous pouvez également paramétrer des souches de numéros client pour chaque groupe de clients. Ces souches de numéros doivent également être partagées. La souche de numéros d’un groupe de clients est utilisée en premier. Si aucune souche de numéros n’est spécifiée pour un groupe de clients, la souche de numéros spécifiée dans la page **Paramètres de la comptabilité client** est utilisée.

Vous pouvez également copier des clients entre entités juridiques si vous utilisez des ID client manuels. Toutefois, si vous tentez de copier un client dans une entité juridique où l’ID client existe déjà, le processus de copie ne démarrera pas.

## <a name="copy-a-customer"></a>Copier un client

Pour copier un client, sélectionnez **Nouveau** dans la page de liste **Tous les clients** pour ouvrir la boîte de dialogue **Créer un client**. Notez que le nouvel ID client n’est pas affecté immédiatement. Ce comportement diffère de celui des versions précédentes. Comme vous n’avez pas encore sélectionné le groupe de clients, le système ne peut pas déterminer la souche de numéros appropriée à utiliser. En outre, il ne peut pas déterminer si vous essayez de créer un client ou de copier un client. Par conséquent, l’ID client n’est pas affecté tant que vous ne cliquez pas sur **Enregistrer** en bas de la boîte de dialogue.

Si vous créez un nouveau client, vous pouvez continuer à renseigner tous les champs comme vous le faites habituellement. Lorsque vous avez terminé et que vous cliquez sur **Enregistrer**, vous verrez que l’ID client a été affecté automatiquement. Sinon, pour les souches de numéros manuelles, vous verrez que votre ID client manuel a été utilisé.

Pour copier un client, dans le champ **Nom**, entrez un ou plusieurs caractères qui représentent le client que vous recherchez. Une boîte de dialogue de recherche affiche une liste de parties qui peuvent représenter le client que vous recherchez. Lorsque vous sélectionnez une des parties, des informations supplémentaires s’affichent à droite de la boîte de dialogue :

- L’onglet **Général** affiche le numéro de téléphone et l’adresse de la partie.
- L’onglet **Rôles** affiche les rôles disponibles pour la partie sélectionnée et l’entité juridique où se trouve chaque rôle.
- L’onglet **ID enregistrement de taxe** affiche les ID enregistrement de taxe affectés à la partie.

Vous pouvez copier une partie uniquement si un rôle client lui est affecté et si ce rôle se trouve dans une entité juridique qui n’est pas l’entité juridique actuelle. Lorsque vous trouvez une partie qui répond à ces critères, procédez comme suit.

1. L’option **Copier un client** s’affiche. Par défaut, cette option est définie sur **Non**. Pour copier le client dans l’entité juridique actuelle, définissez l’option sur **Oui**. 
2. Le champ **Entité juridique** s’affiche. Sélectionnez l’entité juridique à partir de laquelle copier le client. Si le client existe dans une seule entité juridique, le champ est défini sur cette entité juridique par défaut.
3. Cliquez sur **Sélectionner**. Le nouveau client est créé.

## <a name="validation"></a>Validation

Lorsque vous copiez un client, le système essaie d’enregistrer les nouvelles informations sur le client. Les validations sont exécutées pour vérifier que les données copiées sont correctes. Vous recevez un message d’erreur pour chaque validation qui échoue. Les messages d’erreur expliquent quelles informations doivent être mises à jour. La copie du client ne peut pas être enregistrée tant que vous ne résolvez pas toutes les erreurs de validation.

## <a name="copy-a-customer-by-using-tax-exempt-number-search-feature"></a>Copie d’un client à l’aide de la fonction de recherche du numéro identifiant TVA

Vous pouvez également copier des clients à l’aide de la fonction de recherche du numéro identifiant TVA qui est disponible dans le groupe **Enregistrement** sous l’onglet **Client** du volet Actions de la page **Tous les clients**. La boîte de dialogue **Recherche du numéro identifiant TVA** qui s’affiche répertorie les numéros identifiant TVA, l’ID client, le nom du client et l’entité juridique où l’ID identifiant TVA est utilisé. Vous pouvez copier un client uniquement s’il se trouve dans une entité juridique qui n’est pas l’entité juridique actuelle. Après avoir sélectionné un client qui répond à ce critère, procédez comme suit.

1. L’option **Copier un client** s’affiche. Par défaut, cette option est définie sur **Non**. Pour copier le client dans l’entité juridique actuelle, définissez l’option sur **Oui**. 
2. Cliquez sur **Sélectionner**. Le nouveau client est créé.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
