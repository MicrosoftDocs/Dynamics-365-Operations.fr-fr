---
title: Auditer la synchronisation des opérations client dans Commerce headquarters
description: Cet article explique comment auditer la synchronisation des opérations client dans Microsoft Dynamics 365 Commerce headquarters pour aider à résoudre les problèmes des utilisateurs du site.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-28
ms.openlocfilehash: c615b0b436e01a1423b5611a72f0056b5b14f8e8
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691094"
---
# <a name="audit-synchronization-of-customer-operations-in-headquarters"></a>Auditer la synchronisation des opérations client dans Commerce headquarters

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cet article explique comment auditer la synchronisation des opérations client dans Microsoft Dynamics 365 Commerce headquarters pour aider à résoudre les problèmes des utilisateurs du site.

Alors que les organisations commencent à adopter la possibilité de créer et de modifier des clients de manière asynchrone, les administrateurs de site ont besoin d’un moyen de visualiser et de dépanner les opérations, en fonction des demandes des utilisateurs du site ou des échecs de processus. Dans ces scénarios, les administrateurs de site doivent être en mesure d’auditer les opérations de création et de modification des clients, et de résoudre les éventuels échecs à l’aide d’un modèle en libre-service.

## <a name="customer-synchronization-status"></a>Statut de synchronisation des clients

Lorsque vous sélectionnez le mode asynchrone de la gestion client et ses fonctionnalités correspondantes, les administrateurs de Commerce headquarters doivent créer et planifier un traitement par lots récurrent pour la **tâche P**, la tâche **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone** et la tâche **1010**, afin que tous les clients asynchrones soient convertis en clients synchrones dans Commerce headquarters. La synchronisation des opérations de gestion des clients se produit chaque fois que ces tâches sont exécutées. Pour plus d’informations, voir [Mode de création de client asynchrone](async-customer-mode.md).

En tant que propriétaire d’entreprise, vous pouvez effectuer les opérations suivantes :

- Affichez toutes les opérations de création/modification des utilisateurs du site. Les détails incluent le statut et un horodatage.
- Filtrez les opérations en utilisant n’importe lequel des champs et valeurs de la table client pour affiner le journal d’audit.
- Affichez de brèves descriptions des modifications ainsi que les détails de l’état pour comprendre les opérations à un niveau élevé.
- En cas d’échec, modifiez et corrigez les champs problématiques, puis enregistrez et synchronisez les opérations client spécifiques.

### <a name="elements-on-the-customer-synchronization-status-page"></a>Éléments de la page Statut de synchronisation client

Pour afficher une liste de toutes les opérations de synchronisation, dans Commerce headquarters, accédez à **Commerce et vente au détail \> Clients \> Statut de synchronisation client**. L’illustration suivante montre un exemple de page **Statut de synchronisation client**.

![Page d’état de la synchronisation des clients dans Commerce headquarters.](media/D365-Commerce-Customer-Mgmt-Audi-Async-Operations.png)

Par défaut, la liste des opérations de synchronisation client sur le côté gauche de la page **Statut de synchronisation client** comprend les colonnes suivantes :

- Nom de canal
- Compte client
- Compte client asynchrone
- Horodatage d’opération
- Statut de synchronisation des clients

L’angle supérieur droit de la page affiche les détails du compte client, tels que **Compte client**, **Opération asynchrone de vente au détail**, **État de synchronisation des clients** et **Dernière erreur connue**.

La section **Changer la description** contient une description du type d’opération de gestion des clients qui s’est exécutée (par exemple, création de client, mise à jour de compte ou échec de synchronisation avec les détails).

La section **Attributs client** contient une grille qui affiche tous les attributs du client, ainsi que les anciennes et les nouvelles valeurs. Vous pouvez modifier cette section si vous souhaitez modifier les valeurs de vos attributs client pour corriger des bogues, puis synchroniser à nouveau.
