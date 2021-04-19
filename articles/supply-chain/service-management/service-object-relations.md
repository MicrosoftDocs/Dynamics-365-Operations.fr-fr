---
title: Relations d’objets de service
description: Vous pouvez créer des relations d’objets de service entre un objet de service et un accord de service ou une commande de service.
author: ShylaThompson
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1984e4c2d57a03ad27c1f6d417209b806f7d6be6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835844"
---
# <a name="service-object-relations"></a>Relations d’objets de service 

[!include [banner](../includes/banner.md)]

Vous pouvez créer des relations d’objets de service entre un objet de service et un accord de service ou une commande de service. Lorsque vous créez une relation, vous associez l’objet de service à l’accord de service ou la commande de service.

Une fois la relation créée, vous pouvez associer l’objet de service à n’importe quelle ligne de l’accord de service ou de la commande de service.

## <a name="template-boms"></a>Nomenclatures des modèles

Vous pouvez également spécifier une nomenclature des modèles pour une relation d’objets. La nomenclature des modèles est une nomenclature pour l’objet associé au service. Si vous remplacez un composant de l’objet de service au cours d’une visite de service, vous pouvez enregistrer cette modification dans la nomenclature des services à l’aide de l’écran Objets du service.

## <a name="example"></a>Exemple

Vous créez un accord de service pour la prise en charge de deux ascenseurs sur le site d’un client.
L’accord de service est doté de l’ID d’identification SAL-001.

Les ascenseurs sont paramétrés comme objets du service EL-S/1000 et EL-L/1000 dans l’écran .

Vous associez les objets de service EL-S/1000 et EL-L/1000 à l’accord de service.

Vous souhaitez enregistrer des modifications dans la nomenclature pour l’objet de service en raison du remplacement de composants de l’objet. Vous associez donc une nomenclature des services à la relation d’objets de service, comme indiqué dans le tableau ci-dessous.

| Objet de service | Relation – Accord de service | Nomenclature des services   |
|----------------|------------------------------|---------------|
| EL-S/1000      | ID SAL-001                   | BOM-EL-S/1000 |
| EL-L/1000      | ID SAL-001                   | BOM-EL-L/1000 |

Comme l’accord inclut des relations d’objets de service, vous pouvez créer des lignes d’accord de service avec ces objets, comme indiqué dans le tableau ci-dessous.

| Type de transaction | catégorie ;           | Objet de service |
|------------------|--------------------|----------------|
| Heure             | Inspection         | EL-S/1000      |
| Heure             | Nettoyage du système d’engrenages  | EL-S/1000      |
| Article             | Matériaux de nettoyage | EL-S/1000      |
| Heure             | Inspection         | EL-L/1000      |
| Heure             | Nettoyage du système d’engrenages   | EL-L/1000      |
| Article             | Matériaux de nettoyage | EL-L/1000      |

Au cours d’une visite de service, vous devez remplacer le système d’engrenages de l’ascenseur EL-S/1000. Pour remplacer le composant de l’objet, vous pouvez accéder au Concepteur de nomenclatures à l’aide de la relation d’objets de service paramétrée pour l’accord de service en cours.

Accès au Concepteur de nomenclatures à l’aide de la relation d’objets de service

1. Accords de service
2. Double-cliquez sur un accord de service, ou cliquez sur Accord de service pour créer un accord de service.
3. Cliquez sur l’onglet Paramétrage.
4. Cliquez sur Objets du service pour lier une nomenclature des modèles à l’accord de service.
5. Dans l’écran d’objets du service, cliquez sur Concepteur pour ouvrir l’écran Concepteur et modifier la nomenclature des modèles.

## <a name="automatically-created-service-orders"></a>Commandes de service créées automatiquement

Si vous créez automatiquement des commandes de service pour un accord de service, les relations d’objets de service dans l’accord sont également créées dans les commandes de service.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]