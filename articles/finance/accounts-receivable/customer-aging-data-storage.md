---
title: Stockage des données âgées du client
description: Cette rubrique décrit le processus d’utilisation du stockage externe pour les données d’ancienneté du client. Vous pouvez exécuter le processus de stockage des données d’ancienneté du client pour rendre la sortie disponible pour l’exportation vers un système externe.
author: JodiChristiansen
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1af4b4cbf503369565ee64ad8889ee9e59a92b3f
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735519"
---
# <a name="customer-aging-data-storage"></a>Stockage des données âgées du client

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le processus d’utilisation du stockage externe pour les données d’ancienneté du client. Dans Microsoft Dynamics 365 Finance, vous pouvez exécuter le processus de **stockage des données d’ancienneté du client** pour rendre la sortie disponible pour l’exportation vers un système externe. Lorsque vous exécutez le processus, les options de rapport d’ancienneté disponibles dans le système sont aussi disponibles pour les systèmes externes. Les détails sont toujours inclus dans les données exportées.

Il peut être utile de mettre les données d’ancienneté du client à la disposition d’un système externe à des fins de stockage dans les cas où la sortie contient de nombreux clients et/ou de nombreuses transactions. En cas d’expiration de la **Balance âgée des clients** en raison d’un trop grand nombre de données à imprimer, cette fonctionnalité offre un autre moyen d’obtenir les mêmes données.

## <a name="enable-the-customer-aging-data-storage-feature"></a>Activer la fonctionnalité de stockage des données d’ancienneté du client

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer dans votre système. Les administrateurs peuvent utiliser les paramètres de gestion des fonctionnalités pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** Crédit et relances
- **Nom de la fonctionnalité :** Stockage des données d’ancienneté du client

## <a name="run-the-customer-aging-data-storage-process"></a>Activer le processus de stockage des données d’ancienneté du client

1. Accédez à **Crédit et relances \> Recherches et états \> Client \> Stockage des données d’ancienneté du client**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Nom**, entrez un nom pour le processus.
4. Définissez les paramètres restants selon vos besoins.

    > [!NOTE]
    > Les détails de la transaction sont toujours inclus et le traitement est toujours effectué par lots.

5. Cliquez sur **OK**.
6. Actualisez la page **Stockage des données d’ancienneté du client** pour voir les valeurs **Nom du traitement par lots** et **Temps d’exécution du traitement par lots** qui sont affichées ensemble avec la valeur **Statut de traitement**. Une fois le traitement par lots terminé, le champ **Statut de traitement** est défini sur **Terminé** et le champ **Nombre de lignes d’ancienneté** est défini. Si le traitement par lots est récurrent, le champ **Statut de traitement** est défini sur **En attente**.
7. Cliquez sur le bouton **Filtre** à côté du champ **Nombre de lignes d’ancienneté** pour passer en revue les filtres qui ont été ajoutés pour le traitement par lots.

La page **Stockage des données d’ancienneté du client** n’inclut pas les résultats. Cependant, l’entité de données **Stockage des données d’ancienneté du client** vous permet d’exporter la sortie dans n’importe quel format pris en charge par Gestion des données.

> [!NOTE]
> Avant d’effectuer une exportation, ajoutez un filtre pour limiter les résultats exportés aux dernières données d’ancienneté. Par exemple, ajoutez les critères suivants pour renvoyer l’exécution du traitement par lots la plus récente :
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchName())
>
> Vous pouvez aussi ajouter les critères suivants pour renvoyer l’exécution du traitement par lots la plus récente de l’utilisateur actuel :
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchNameForCurrentUser())
