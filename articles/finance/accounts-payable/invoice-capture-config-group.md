---
title: Groupes de configuration de la solution Invoice capture
description: Cet article fournit des informations générales sur les groupes de configuration de la solution Invoice Capture.
author: sunfzam
ms.date: 09/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cfe5ae35b4f87a350d944b30a49251081766ad27
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691168"
---
# <a name="invoice-capture-solution-configuration-groups"></a>Groupes de configuration de la solution Invoice capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Les utilisateurs peuvent gérer la liste des champs de facture et le paramètre de révision manuelle pour les entités juridiques à l’aide de groupes de configuration. Les utilisateurs peuvent configurer des configurations de facture pour différentes entités juridiques dans des groupes. Toutes les entités juridiques du même groupe de configuration utilisent les mêmes champs de facture et le même paramètre de révision manuelle.

## <a name="manage-configuration-groups"></a>Gérer les groupes de configuration

Pour gérer les groupes de configuration à l’aide de l’application, accédez à **Configurer**, puis sélectionnez **Configuration du système \> Définir le composant des groupes de configuration**.

Sur la page **Définir des groupes de configuration**, l’onglet principal affiche la liste des groupes de configuration qui ont été définis. Il affiche également un groupe de configuration par défaut. Pour chaque groupe de configuration, les actions suivantes sont disponibles :

- **Copier un groupe de configuration** : vous pouvez créer un nouveau groupe de configuration en dupliquant un groupe existant. Le nouveau groupe a les mêmes valeurs que le groupe d’origine pour tous les champs sauf **Nom de groupe** et **Description du groupe**. Une fois le groupe de configuration dupliqué, sélectionnez **OK**.
- **Supprimer des groupes de configuration** : pour supprimer un groupe de configuration, sélectionnez-le, puis sélectionnez **Effacer**.

    > [!NOTE]
    > Impossible de supprimer le groupe de configuration par défaut.

- **Modifier l’ID d’un groupe de configuration** : pour modifier l’ID d’un groupe de configuration, sélectionnez le champ **ID de groupe** et mettez à jour la valeur. L’ID de groupe ne doit pas contenir d’espaces ni de caractères spéciaux et ne doit pas dépasser 20 caractères.

    > [!NOTE]
    > La valeur du champ **ID de groupe** ne peut être mise à jour qu’une seule fois.

- **Modifier une description d’un groupe de configuration** : pour modifier la description d’un groupe de configuration, sélectionnez le champ **Description** et mettez à jour la valeur.
- **Modifier le paramètre de révision manuelle** : les utilisateurs peuvent décider si une facture doit être révisée manuellement. Pour modifier le paramètre de révision manuelle, sélectionnez l’option **Révision manuelle requise**. Les options suivantes sont disponibles :

    - **Révision manuelle permanente** : sélectionnez cette option si les factures du groupe de configuration nécessitent toujours une révision manuelle.
    - **Pour les erreurs et les avertissements** : sélectionnez cette option si les factures qui contiennent des messages d’erreur ou des messages d’avertissement nécessitent une révision manuelle.
    - **Pour les erreurs** : sélectionnez cette option si les factures qui contiennent des messages d’erreur nécessitent une révision manuelle.

- **Modifier le paramètre de score de confiance** : le score de confiance est une métadonnée que la solution Invoice capture fournit pour signaler l’exactitude des données de facturation reconnues. Plus le score est élevé, plus les données reconnues peuvent être précises. La configuration permet aux utilisateurs de définir quand une révision manuelle est requise, en fonction du score de confiance. Les utilisateurs peuvent modifier le seuil du score de confiance pour les factures. Pour mettre à jour le paramètre de score de confiance, sélectionnez le champ **Note de confiance** et mettez à jour la valeur.

    Il existe deux types d’alertes pour les scores de confiance :

    - **Avertissement** : les champs de facture dont les scores de confiance dépassent le seuil d’avertissement sont considérés comme corrects. Le seuil d’avertissement doit être supérieur au seuil d’erreur et inférieur à 100.
    - **Erreur** : les champs de facture dont les scores de confiance se trouvent en dessous du seuil d’avertissement sont considérés comme erronés. Les messages d’erreur sont affichés à l’utilisateur. Le seuil d’erreur doit être supérieur à 0 (zéro) et inférieur au seuil d’avertissement. Des messages d’avertissement s’affichent pour les champs de facture dont les scores de confiance se situent entre le seuil d’avertissement et le seuil d’erreur.

- **Gérer les champs de facture** : les utilisateurs peuvent gérer la liste des champs de facture qui s’affiche dans la visionneuse côte à côte. Sur l’onglet **Gestion des champs de facturation**, sélectionnez le symbole d’engrenage, sélectionnez les champs de facture à ajouter, puis sélectionnez **Enregistrer**. Les champs sélectionnés sont ajoutés à la liste. Pour supprimer un champ de facture de la liste, sélectionnez **Retirer** sur le champ.

### <a name="manage-file-filters-optional"></a>Gérer les filtres de fichier (facultatif)

Gérer les filtres de fichiers permet aux utilisateurs de définir des filtres supplémentaires pour les fichiers de factures entrantes. Les fichiers qui ne répondent pas aux critères de filtrage sont reçus et apparaissent dans la liste **Fichiers reçus**, mais ils affichent des erreurs de validation de fichier. Ce comportement diffère du comportement des filtres définis dans le canal. Pour ces filtres, les fichiers qui ne répondent pas aux critères ne sont pas reçus du tout. Les utilisateurs peuvent examiner les fichiers entrants et décider si chaque fichier est une facture non valide, et ils peuvent rendre le fichier obsolète ou l’inclure manuellement pour la reconnaissance et l’inclusion dans les factures capturées.

Lorsque la solution Invoice capture est installée, un filtre de fichiers par défaut est défini. Ce filtre de fichiers est global. Si vous souhaitez des paramètres de filtre différents, vous pouvez mettre à jour le filtre par défaut. Si un champ est obligatoire, sélectionnez **Obligatoire**. 

### <a name="accepted-file-size"></a>Taille de fichier acceptée

Vous pouvez choisir la taille de fichier acceptée.

> [!NOTE]
> Les fichiers dont la taille est supérieure à 20 480 kilo-octets (Ko) ne sont pas pris en charge.

### <a name="supported-file-types"></a>Types de fichiers pris en charge

Les types de fichier suivants sont actuellement pris en charge :

- PDF
- PNG
- JPG
- JPEG
- TIF
- TIFF
