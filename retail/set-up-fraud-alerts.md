---
title: "Paramétrer les alertes de fraude"
description: "Cette rubrique décrit le paramétrage des règles pour alerter les représentants du service client en cas d&quot;informations potentiellement frauduleuses lorsque des commandes sont traitées. Vous pouvez définir des codes spécifiques pour mettre en attente automatiquement ou manuellement des commandes suspectes."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: ddcf68b9d9d35d63cb092225d468dd4a6a3d4446
ms.contentlocale: fr-fr
ms.lasthandoff: 04/26/2017


---

# <a name="set-up-fraud-alerts"></a>Paramétrer les alertes de fraude

[!include[banner](includes/banner.md)]


Cette rubrique décrit le paramétrage des règles pour alerter les représentants du service client en cas d'informations potentiellement frauduleuses lorsque des commandes sont traitées. Vous pouvez définir des codes spécifiques pour mettre en attente automatiquement ou manuellement des commandes suspectes. 

Avant de paramétrer et d'utiliser des règles de contrôle de fraude, vous devez activer le contrôle de fraude et définir les valeurs de base du contrôle de fraude dans les paramètres du centre d'appels. Il existe deux types de règles de fraude :

-   Les **règles statiques** utilisent une valeur spécifique, telle qu'un numéro de téléphone qui a été mis sur la liste noire.
-   Les **règles dynamiques** peuvent comporter des variables et des conditions.

Avant de créer une règle dynamique, vous devez créer les variables et les conditions qui définissent ce à quoi la règle s'applique et quand elle doit être appliquée. Par exemple, vous pouvez créer une règle qui détermine qu'à chaque fois que le client 1202 passe une commande d'un montant de 1 000,00 ou plus, sa commande sera mise en attente jusqu'à ce que le paiement du client puisse être vérifié. Dans ce cas, les variables sont le client 1202 et un total de commande de 1 000,00. La condition spécifie que si le client 1202 passe une commande, et que le montant total de la commande est égal ou supérieur à 1 000.00, la commande client doit être mise en attente jusqu'à ce que le paiement client puisse être vérifié.




