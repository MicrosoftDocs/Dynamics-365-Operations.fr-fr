---
title: Numérotation chronologique des documents et des justificatifs
description: Cet article explique comment paramétrer et utiliser des numéros chronologiques pour les documents applicables et les justificatifs associés.
author: ikond
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.custom: 401195
ms.search.form: NumberSequenceGroup
ms.openlocfilehash: 1a1b8887eff625d9e4095380fbb7c8963682ef3c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272426"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a>Numérotation chronologique des documents et des justificatifs

[!include [banner](../includes/banner.md)]


Dans certains pays, il est obligatoire de numéroter les documents et les justificatifs associés dans l’ordre chronologique. La chronologie doit être prise en charge par périodes. Tous les numéros qui appartiennent à des périodes antérieures doivent être inférieurs aux numéros qui appartiennent aux périodes ultérieures. Pour répondre à cette exigence, une fonctionnalité de numérotation chronologique a été implémentée. Cet article explique comment configurer et utiliser des numéros chronologiques pour les documents applicables et les justificatifs associés.

## <a name="prerequisites"></a>Conditions préalables

Dans l’espace de travail Gestion des fonctionnalités, activez la fonctionnalité **Numérotation chronologique**. Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-chronological-numbering"></a>Configurer la numérotation chronologique

La numérotation chronologique affecte les documents suivants.

**Comptabilité client**
- Facture client
- N° document de facture client
- Avoir sur vente
- N° document d’avoir sur vente
- Facture financière
- N° document de facture financière
- Avoir financier
- N° document d’avoir financier
- Bon de livraison
- N° document de bon de livraison
- Document de correction du bon de livraison
- N° document de note d’intérêt
- N° document de lettre de relance

**Comptabilité fournisseur**
- N° document de facture
- N° document d’avoir
- N° document d’accusé de réception de marchandises

**Gestion de projets**
- Facture
- N° document de facture
- Avoir
- N° document d’avoir 

### <a name="define-number-sequences"></a>Définir des souches de numéros

Pour définir des souches de numéros, accédez à **Administration d’organisation** > **Souches de numéros** > **Souches de numéros**. Vous pouvez définir autant de souches de numéros que nécessaire pour couvrir les périodes concernées pour les documents requis. 

Spécifiez une société pour chaque souche de numéros. Les segments des souches de numéros doivent être définis de manière à fournir l’ordre chronologique des périodes. Par exemple, les noms de segment peuvent contenir un préfixe spécial qui identifie une période spécifique.

![Paramètres des séquences de numéros.](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a>Configurer des groupes de souches de numéros

Pour configurer des groupes de souches de numéros, accédez à **Comptabilité client** > **Paramétrage** > **Paramètres de la comptabilité client**. Dans l’onglet **Souches de numéros**, définissez autant de groupes de souches de numéros qu’il est nécessaire pour couvrir les périodes affectées. 

Pour chaque groupe, dans la section **Référence**, sélectionnez l’une des références de document prises en charge et dans le champ **Code souche de numéros**, référez-vous à une souche de numéros qui a été précédemment créée pour la période concernée.

![Paramétrage du groupe souche de numéros.](media/chrono-num-sequence-group.jpg)

De même, configurez les groupes de souches de numéros dans les modules **Comptabilité fournisseur** et **Gestion et comptabilité du projet**.

### <a name="configure-number-sequence-groups-chronology"></a>Configurer la chronologie des groupes de souches de numéros

Pour configurer la chronologie des groupes de souches de numéros, accédez à **Administration d’organisation** > **Souches de numéros** > **Groupes de souches de numéros chronologiques**. Définissez les conditions d’applicabilité des groupes de souches de numéros.

![Paramétrage des numéros chronologiques.](media/chrono-num-sequence-group-period.jpg)

| Champ            | Description                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Date d’effet  | La date de début de l’applicabilité du groupe de souches de numéros. |
| Expiration      | La date de fin de l’applicabilité du groupe de souches de numéros. Si aucune date de fin n’est appliquée, sélectionnez **Jamais**. |
| Groupe souche de numéros | Groupe de souches de numéros qui sera utilisé pour générer des numéros de document pendant la période. |
| Groupe de souches de numéros d’origine | Ce code de groupe de souches de numéros est utilisé pour un filtrage supplémentaire si les documents ont déjà un groupe de souches de numéros *permanent* attribué. Une valeur vide est considérée comme une valeur spécifique. Si vous devez ignorer un groupe attribué au préalable, utilisez l’option **Par défaut** pour ce paramétrage. |
| Par défaut | Si cette option est activée, le système ignore le groupe de souches de numéros attribué au préalable et utilise uniquement les dates de début et de fin des périodes pour l’analyse d’applicabilité. Si elle est désactivée, le système utilise la combinaison complète **Date d’effet** + **Expiration** + **Groupe de souches de numéros d’origine** pour la sélection. |

## <a name="document-posting"></a>Validation de document
Lorsque vous validez un document, le groupe de souches de numéros d’origine approprié lui est affecté, en fonction de la date de validation du document, puis utilisé pour générer un numéro de document en fonction de la souche de numéros détectée. Le système fournit un message concernant l’affectation des groupes de souches de numéros.

![Numéro de référence.](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> Pour certains pays, il existe déjà une logique spécifique pour la numérotation des documents. Dans ce cas, la logique propre au pays remplacera la fonctionnalité **Numérotation chronologique**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
