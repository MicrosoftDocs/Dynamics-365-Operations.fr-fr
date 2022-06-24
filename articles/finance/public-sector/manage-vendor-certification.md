---
title: Mettre à jour la certification des fournisseurs
description: Cet article décrit les étapes que les fournisseurs peuvent suivre pour maintenir leurs certifications à jour à l’aide de l’espace de travail Collaboration du fournisseur.
author: v-kiarnd
ms.date: 04/27/2021
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 37990292748c363f44d306bda0263dd117808eb1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891435"
---
# <a name="maintain-vendor-certification"></a>Mettre à jour la certification des fournisseurs

[!include [banner](../includes/banner.md)]

Cet article décrit les étapes que vos fournisseurs peuvent suivre pour maintenir leurs certifications à jour à l’aide de l’espace de travail **Collaboration du fournisseur**. Parmi les exemples de certifications on trouve une entreprise Woman Business Enterprise (WBE) ou une entreprise de leadership dans la conception énergétique et environnementale (LEED). Les fournisseurs devront saisir les informations de certification dans l’espace de travail **Informations fournisseur**. Ils devront ensuite sélectionner **Plus de détails**, puis **Certifications**.

## <a name="turn-on-the-vendor-certification-feature"></a>Activer la fonctionnalité de certification des fournisseurs

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser la page [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module** - *Comptabilité fournisseur*
- **Nom de la fonctionnalité** - *Activer la gestion de la certification pour la collaboration avec les fournisseurs*

## <a name="add-a-new-certification"></a>Ajouter une nouvelle certification

Pour ajouter une nouvelle certification, cliquez sur le bouton **Ajouter** situé au-dessus de la grille **Certification** dans l’espace de travail **Informations fournisseur**. Entrez les informations suivantes :

- Numéro de certification
- Type de certification
- Organisme de certification
- Date de la certification
- Montant de la responsabilité, le cas échéant
- Date d’effet
- Date d’expiration
- Commentaires (facultatifs)

S’il existe des documents liés à la certification spécifique, vous pouvez les joindre en cliquant sur le bouton **Document**.

Les certifications entrées par vos fournisseurs sur cette page se verront attribuer « Fournisseur » comme source. Vous pouvez saisir les informations de certificat au nom de votre fournisseur sous les comptes bancaires du fournisseur. Ces informations apparaîtront à cet emplacement et **Client** sera indiqué comme source.

Les fournisseurs peuvent modifier ou supprimer leurs certifications au besoin.

## <a name="vendor-collaboration-generated-certification-records"></a>La collaboration des fournisseurs a généré des enregistrements de certification

Une fois les informations de certification ajoutées par un fournisseur, les informations seront visibles sur la page **La collaboration des fournisseurs a généré des certifications**. Pour ouvrir la page, accédez à **Comptes fournisseurs > Demandes de renseignements > Rapports des fournisseurs > Certifications générées par la collaboration avec les fournisseurs**. Par défaut, tous les enregistrements de certification nouveaux ou modifiés sont visibles. L’adjoint chargé de la comptabilité fournisseur peut visualiser les modifications et valider les informations via leur processus de confirmation pour valider. Une fois les informations confirmées, l’enregistrement de certification répertorié sur la page peut être sélectionné et marqué comme révisé. Marquer l’enregistrement comme révisé le supprimera de la liste par défaut.

Tous les changements de certification sont visibles sur la page **La collaboration des fournisseurs a généré des certifications**. Si une modification n’est pas affichée sur la page, vous pouvez l’afficher en ajustant les filtres pour le compte fournisseur, la plage de dates d’effet ou en choisissant d’inclure des informations sur les modifications de certification qui ont été examinées.

