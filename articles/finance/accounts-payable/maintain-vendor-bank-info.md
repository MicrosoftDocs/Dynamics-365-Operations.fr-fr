---
title: Tenir à jour les informations bancaires pour un compte fournisseur
description: Les fournisseurs peuvent utiliser la fonctionnalité Collaboration du fournisseur pour gérer leurs informations de compte bancaire. Cet article explique comment ajouter et gérer les informations bancaires des fournisseurs avec lesquels vous faites affaire.
author: v-kiarnd
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 26181
ms.assetid: 10f56dea-ea2d-48ea-9622-4ef715eb1179
ms.search.region: USA
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2011-01-14
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 83be2ac95d07ba494e08c07606cdbe36eba9f99b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890008"
---
# <a name="maintain-vendor-bank-account-information"></a>Tenir à jour les informations bancaires pour un compte fournisseur

[!include [banner](../includes/banner.md)]

Les fournisseurs peuvent utiliser la fonctionnalité Collaboration du fournisseur pour gérer leurs informations de compte bancaire. Cet article explique comment ajouter et gérer les informations bancaires des fournisseurs avec lesquels vous faites affaire.

Une fois que vous avez donné accès aux fournisseurs, ils peuvent ajouter des informations pour les nouveaux comptes bancaires. Vous pouvez ensuite consulter ces informations et terminer le processus de pré-note afin que les nouveaux comptes soient utilisés pour les paiements à ces fournisseurs.

Vous pouvez gérer votre compte fournisseur dans l’espace de travail **Informations fournisseur**. Les fournisseurs pourront ensuite sélectionner **Plus de détails** et **Comptes bancaires** dans la liste déroulante. Pour ajouter un nouveau compte bancaire, sélectionnez **Ajouter** au-dessus de la grille des comptes bancaires. Dans la boîte de dialogue **Nouveau** qui s’affiche, vous pouvez entrer les informations suivantes :

- Compte bancaire
- Nom de la banque
- Numéro de compte bancaire
- Numéro d’acheminement bancaire
- Date d’effet
- Date d’expiration
- Commentaires (facultatif)

Les codes SWIFT et IBAN (Numéro de compte bancaire international) sont requis pour toutes les entreprises non basées aux États-Unis. Vous pouvez mettre à jour le paramètre d’exigences SWIFT et IBAN sur la page **Paramètres de la Comptabilité fournisseur** une fois la fonctionnalité activée.

S’il existe des documents liés à la certification spécifique, vous pouvez les joindre en sélectionnant **Document**.

Les informations bancaires que les fournisseurs saisissent sur la page afficheront **Fournisseur** comme source. Vous pouvez également saisir des informations de compte bancaire à la place d’un fournisseur. Ces informations apparaîtront ici, et **Client** sera affiché comme source. Pour plus d’informations, voir [Créer un compte bancaire fournisseur](../../supply-chain/procurement/tasks/create-vendor-bank-account.md).

Une fois qu’un compte a été ajouté, les fournisseurs peuvent modifier les dates d’effet et d’expiration de leur banque au besoin.

## <a name="turn-on-the-vendor-bank-account-information-feature"></a>Activer la fonctionnalité d’informations de compte bancaire fournisseur

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser la page [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module** - *Comptabilité fournisseur*
- **Nom de la fonctionnalité** - *Tenir à jour les informations bancaires des fournisseurs à l’aide de l’espace de travail de collaboration avec les fournisseurs*

## <a name="vendor-collaboration-generated-bank-changes-page"></a>Page des modifications bancaires générées par la collaboration avec les fournisseurs

Une fois que les fournisseurs ont mis à jour leurs informations bancaires, ces informations seront visibles sur la nouvelle page **Modifications bancaires générées par la collaboration avec les fournisseurs** disponible sous **Comptabilité fournisseur \> Recherches \> États fournisseur**. Par défaut, tous les enregistrements bancaires nouvellement saisis ou modifiés sont affichés. L’adjoint chargé de la comptabilité fournisseur peut visualiser les modifications et exécuter les informations de compte via le processus de pré-note pour les valider. Quand ce processus est terminé et que le mode de paiement principal a été mis à jour manuellement, le compte bancaire indiqué sur la page **Modifications bancaires générées par la collaboration avec les fournisseurs** peut être sélectionnée et marquée comme révisée. Cette action supprime le compte de la liste par défaut.

Pour afficher toutes les modifications apportées aux informations bancaires d’un fournisseur, vous pouvez modifier les filtres pour afficher la page par compte fournisseur, par plage de dates de validité et si les modifications ont été vérifiées.
