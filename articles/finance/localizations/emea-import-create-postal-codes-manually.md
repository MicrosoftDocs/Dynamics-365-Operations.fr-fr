---
title: Importer ou créer manuellement des codes postaux
description: Cette rubrique décrit la procédure d’importation et de création manuelle de codes postaux au format approprié.
author: EvgenyPopovMBS
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 29901
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d547b6cb199279b6e40e6d6cf005086d62386421945cbeb04a9cfc395a55f0fc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768248"
---
# <a name="import-or-manually-create-postal-codes"></a>Importer ou créer manuellement des codes postaux

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la procédure d’importation et de création manuelle de codes postaux au format approprié. 

Le processus d’importation permet de mettre à jour les codes postaux d’un pays ou d’une région spécifique. Vous pouvez également créer les codes postaux manuellement.

## <a name="import-zippostal-codes"></a>Importer des codes postaux
Vous pouvez utiliser la page **Importer des codes postaux** pour importer de nouveaux codes postaux dans Dynamics 365 Finance. Lorsque vous importez les codes, les codes postaux existants sont remplacés par le nouveau format, et les nouveaux codes sont ajoutés.

Pour certains pays, vous devez utiliser l’infrastructure de gestion des données pour importer des codes, tandis que pour d’autres pays, seul un fichier doit être téléchargé. Un fichier doit être téléchargé pour la Belgique, les Pays-Bas et la Suède.

> [!NOTE]
> -   Pour la Belgique, la page Web officielle de la poste belge fournit la liste officielle des codes postaux et les noms de ville correspondants. L’importation prend en charge le format de fichier HTML.
> -   Pour les Pays-Bas, une organisation tierce fournit le fichier contenant les codes postaux. Une fois l’importation terminée, tous les codes postaux s’affichent au format (NNNN AA.)
> -   Pour la Suède, Postnummerservice.se propose deux types de fichiers : les codes postaux suédois et les adresses suédoises. L’importation prend en charge le format de fichier texte pour les deux types.


## <a name="create-zippostal-codes-manually"></a>Création manuelle des codes postaux
Au lieu d’importer les codes, vous pouvez utiliser la page **Configuration de l’adresse** pour ajouter manuellement de nouveaux codes postaux.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]