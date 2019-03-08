---
title: Importer ou créer manuellement des codes postaux
description: Cette rubrique décrit la procédure d'importation et de création manuelle de codes postaux au format approprié. Cette rubrique comprend des informations sur la fonction qui a été ajoutée ou modifiée dans Microsoft Dynamics 365 for Finance and Operations.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 29901
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: db7090e47301aad9ab56a62efd807140db62ab3b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "370734"
---
# <a name="import-or-manually-create-postal-codes"></a>Importer ou créer manuellement des codes postaux

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la procédure d'importation et de création manuelle de codes postaux au format approprié. Cette rubrique comprend des informations sur la fonction qui a été ajoutée ou modifiée dans Microsoft Dynamics 365 for Finance and Operations. 

Le processus d'importation permet de mettre à jour les codes postaux d'un pays ou d'une région spécifique. Vous pouvez également créer les codes postaux manuellement.

## <a name="import-zippostal-codes"></a>Importer des codes postaux
Vous pouvez utiliser la page **Importer des codes postaux** pour importer de nouveaux codes postaux dans Finance and Operations. Lorsque vous importez les codes, les codes postaux existants sont remplacés par le nouveau format, et les nouveaux codes sont ajoutés.

Pour certains pays, vous devez utiliser l'infrastructure de gestion des données pour importer des codes, tandis que pour d'autres pays, seul un fichier doit être téléchargé. Un fichier doit être téléchargé pour la Belgique, les Pays-Bas et la Suède.

> [!NOTE]
> -   Pour la Belgique, la page Web officielle de la poste belge fournit la liste officielle des codes postaux et les noms de ville correspondants. L'importation prend en charge le format de fichier HTML.
> -   Pour les Pays-Bas, une organisation tierce fournit le fichier contenant les codes postaux. Une fois l'importation terminée, tous les codes postaux s'affichent au format (NNNN AA.)
> -   Pour la Suède, Postnummerservice.se propose deux types de fichiers : les codes postaux suédois et les adresses suédoises. L'importation prend en charge le format de fichier texte pour les deux types.


## <a name="create-zippostal-codes-manually"></a>Création manuelle des codes postaux
Au lieu d'importer les codes, vous pouvez utiliser la page **Configuration de l'adresse** pour ajouter manuellement de nouveaux codes postaux.


