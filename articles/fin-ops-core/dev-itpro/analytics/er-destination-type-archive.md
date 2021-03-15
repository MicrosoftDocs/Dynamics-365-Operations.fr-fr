---
title: Type de destination pour l’archivage d’états électronique
description: Cette rubrique fournit des informations sur la configuration d’une destination d’archive pour chaque composant DOSSIER ou FICHIER d’un format de gestion des états électroniques.
author: NickSelin
manager: AnnBe
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0067024d7a29e2a1db3b7fdba9ea3c6a63aad648
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094127"
---
# <a name="archive-er-destination-type"></a>Type de destination pour l’archivage d’états électronique

[!include [banner](../includes/banner.md)]

Vous pouvez configurer une destination d’archive pour chaque composant **Dossier** ou **Fichier** d’un format de rapport électronique (ER) configuré pour générer des documents sortants. En fonction du paramètre de destination, un document généré est stocké en tant que pièce jointe d’un enregistrement de la liste de tâches d’état électronique. Pour afficher les résultats, accédez à **Administration d’organisation** \> **Gestion des états électroniques** \> **Tâches de gestion des états électroniques**.

Vous pouvez utiliser cette option pour envoyer le document généré vers un dossier Microsoft SharePoint ou le stockage Microsoft Azure. Définissez **Activé** sur **Oui** pour envoyer la sortie vers une destination définie par le type de document sélectionné. Seuls les types de documents où le groupe est défini sur **Fichier** sont disponibles pour la sélection. Vous définissez les [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) de documents dans **Administration d’organisation** \> **Gestion de documents** \> **Types de documents**. La configuration des destinations d’états électroniques est identique à la configuration du système de gestion des documents.

[![Page Types de documents](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

L’emplacement détermine où le fichier est enregistré. Une fois la destination **Archive** activée, les résultats peuvent être enregistrés dans l’archive Tâche. Vous pouvez afficher les résultats sous **Administration d’organisation** \> **Gestion des états électroniques** \> **Tâches de gestion des états électroniques archivées**.

> [!NOTE]
> Sélectionnez un type de document pour l’archive Tâche en accédant à **Administration d’organisation** \> **Espaces de travail** \> **Gestion des états électroniques** \> **Paramètres de gestion des états électroniques**. Pour plus d’informations, voir [Configurer la structure de gestion des états électroniques (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

Vous pouvez enregistrer un fichier dans un dossier SharePoint désigné. Pour définir le serveur SharePoint par défaut, accédez à **Administration d’organisation** \> **Gestion des documents** \> **Paramètres de gestion des documents**. Sur l’onglet **SharePoint**, configurez le dossier SharePoint. Ensuite, vous pouvez le sélectionner comme dossier où la sortie ER sera enregistrée. L’emplacement **SharePoint** doit être sélectionné dans ce type de document.

[![Sélection d’un dossier SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Stockage Azure

Lorsque l’emplacement du type de document est défini sur **Stockage Azure**, vous pouvez enregistrer un fichier dans le stockage Azure.

> [!NOTE] 
> La structure de gestion des états électroniques stocke en permanence les fichiers dans le stockage Blob Azure contrairement à l’infrastructure de gestion des données qui applique la stratégie de rétention de sept jours pour les documents qui doivent être traités. Pour plus d’informations, voir [API pour obtenir le statut du message](../data-entities/recurring-integrations.md#api-for-getting-message-status) et [API de contrôle de statut](../data-entities/data-management-api.md#status-check-api). Les fichiers liés à ER seront stockés dans le stockage Blob Azure en tant que pièces jointes des enregistrements de table d’application aussi longtemps que nécessaire. Un seul fichier sera supprimé du stockage Blob Azure avec l’enregistrement de la table d’application auquel ce fichier était attaché.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des états électroniques](general-electronic-reporting.md)
- [Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)
- [Configurer la gestion des documents](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]