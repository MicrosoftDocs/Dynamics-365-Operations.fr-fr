---
title: "Tâches de service"
description: "Les tâches de service permettent de décrire la tâche à accomplir lors d'une commande de service. Les techniciens comme les clients ont accès à ces informations."
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 221b9dae7e83e7f4a535ac60f2a2011533d7861c
ms.openlocfilehash: de180a1258bbfb95acbfd0985cb91c88efc320f2
ms.contentlocale: fr-fr
ms.lasthandoff: 02/21/2018

---

# <a name="service-tasks"></a>Tâches de service  

[!INCLUDE [banner](../includes/banner.md)]

Les tâches de service permettent de décrire la tâche à accomplir lors d'une commande de service.
Les techniciens comme les clients ont accès à ces informations.

Créez des tâches de service dans la page **Tâches de service**, puis associez-les à un accord de service ou une commande de service spécifique en créant des relations de tâches de service. Chaque fois que vous créez une relation de tâches de service, vous pouvez créer ce qui suit :

-  des notes internes relatives à la tâche, telles que des requêtes techniques détaillées que le technicien doit connaître ;

-  des notes externes que le client peut consulter. Celles-ci peuvent fournir des informations moins techniques sur la tâche en cours d'exécution, conformément à l'accord conclu entre le client et la société de service.

Dès que vous avez paramétré une relation de tâches de service entre une tâche de service et une commande ou un accord de service, vous pouvez spécifier cette tâche de service lors de la création de lignes de commande de service ou de lignes d'accord de service pour la commande de service active ou l'accord de service actif.

Lorsque vous générez des commandes de service à partir d'un accord de service, vous pouvez utiliser les tâches de service affectées à chaque ligne d'accord de service afin de regrouper les lignes de commande de service dans des commandes de service.

## <a name="create-a-service-task"></a>Créer une tâche de service

1. Cliquez sur **Gestion des services** \> **Paramétrage** \> **Tâches de service**.
2. Créez une ligne.
3. Entrez l'ID et la description du service.

## <a name="example"></a>Exemple

Un technicien doit accomplir deux tâches au niveau d'un système d'engrenages (objet de service GB-1234) sur le site du client. Un accord de service est créé pour le client, et plusieurs transactions sont associées aux tâches. L'accord de service et les lignes de l'accord de service pour les deux tâches se présentent comme suit :

### <a name="service-agreement"></a>Accord de service

| Projet | Accord de service | Description                                   | Regrouper   |
|---------|-------------------|----------------------------------------------|---------|
| 9012    | 000008\_001       | Inspection et remplacement de routine – GB-1234 | Prime |

### <a name="service-agreement-lines"></a>Lignes d'accord de service

| Description              | Type de transaction | Objet du service | Tâche de service |
|-------------------------|------------------|----------------|--------------|
| Inspection et nettoyage | Heure             | GB-1234        | I/C - GB1234 |
| Déplacements                  | Dépense          | GB-1234        | I/C - GB1234 |
| Matériaux               | Article             | GB-1234        | I/C - GB1234 |
| Remplacement de routine     | Heure             | GB-1234        | RR - GB1234  |
| GR-1                    | Article             | GB-1234        | RR - GB1234  |
| GR-5                    | Article             | GB-1234        | RR - GB1234  |

Deux tâches de service sont associées aux lignes d'accord de service des deux tâches. Ces tâches de service permettent de déterminer les transactions propres à chaque tâche. Dans le premier cas, la tâche de service I/C - GB1234 caractérise toutes les lignes d'accord de service impliquées dans l'inspection et le nettoyage de l'objet GB-1234. Dans le deuxième cas, la tâche de service RR - GB1234 caractérise toutes les lignes d'accord de service impliquées dans l'exécution d'une tâche de remplacement de routine.

Les relations de tâches de service qui lient les tâches de service à l'accord spécifique se présentent comme suit :

### <a name="service-tasks"></a>Tâches de service

| Tâche de service | Description                              | Note interne                                                                                                                 | Note externe                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| I/C - GB1234 | Inspection du système d'engrenages GB-1234           | Inspection visuelle et mécanique et nettoyage du système d'engrenages GB-1234.                                                              | Inspection de routine du système d'engrenages |
| RR - GB1234  | Remplacement de routine de pièces du système d'engrenages GB-1234 | Remplacement de service de routine des composants GR-1 et GR-5 (pour les systèmes d'engrenages fabriqués avant 2002, remplacer également le composant GR-2) | Remplacement de routine des pièces  |

## <a name="group-service-orders"></a>Regrouper les commandes de service

Lors de la création automatique de commandes de service, vous pouvez utiliser les tâches de service comme critères de regroupement. Pour regrouper des commandes de service par tâches de service, vous devez spécifier dans l'accord de service que les commandes de service basées sur cet accord de service doivent être regroupées par ID de tâche de service comme critères de regroupement initial.

**Regroupement par tâche de service**

1. Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.
2. Dans l'onglet **Paramétrage**, sélectionnez **Par tâche de service** dans le champ **Combiner les commandes de service**.



