---
title: États du cycle de vie de la demande de maintenance
description: Cette rubrique décrit comment paramétrer les états du cycle de vie de la demande de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d1e4412af0619b57467b5bcba75ea7259604d1d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209005"
---
# <a name="maintenance-request-lifecycle-states"></a>États du cycle de vie de la demande de maintenance

[!include [banner](../../includes/banner.md)]

 


Les états du cycle de vie de la demande de maintenance définissent les différentes étapes d'une demande. **Créé**, **Actif** et **Terminé** sont des exemples. Lorsqu'une demande de maintenance est convertie en bon de travail, l'état du cycle de vie de la demande de maintenance doit être mis jour sur **Terminé** ou **Clôturé** pour indiquer que la demande de maintenance n'est plus active. Dans la page de liste **Toutes les demandes de maintenance**, vous pouvez afficher toutes les demandes de maintenance, quel que soit leur état du cycle de vie.

## <a name="set-up-maintenance-request-lifecycle-states"></a>Définir les états du cycle de vie de la demande de maintenance

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Demandes de maintenance** \> **États du cycle de vie**.
2. Sélectionnez **Nouveau** pour créer un état du cycle de vie de la demande de maintenance.
3. Dans le champ **État du cycle de vie**, entrez un ID pour l'état du cycle de vie.
4. Dans le champ **Nom**, entrez un nom.

    Dans le raccourci **Détails**, le champ **Modèles de cycle de vie** affiche le nombre de modèles de cycle de vie de la demande de maintenance qui utilisent cet état du cycle de vie.

5. Dans le raccourci **Général**, définissez l'option **Actif** sur **Oui** si une demande de maintenance doit être active lorsqu'elle est dans cet état du cycle de vie.
6. Définissez l'option **Définir la fin réelle** sur **Oui** si une date et une heure de fin réelles doivent être automatiquement entrées dans une demande de maintenance qui est dans cet état du cycle de vie.
7. Définissez l'option **Créer un ordre de travail** sur **Oui** si un ordre de travail peut être créé à partir d'une demande de maintenance qui est dans cet état du cycle de vie.
8. Définissez l'option **Supprimer** sur **Oui** si une demande de maintenance peut être supprimée lorsqu'elle est dans cet état du cycle de vie.
9. Dans le raccourci **Mettre à jour**, les options **Entrant** et **Sortant** dans la section **Actif** sont utiles si vous utilisez la réparation au dépôt. Définissez l'option appropriée sur **Oui** si l'état du cycle de vie des actifs sélectionnés dans une demande de maintenance doit être automatiquement mis à jour sur **Entrant** ou **Sortant** lorsque l'état du cycle de vie de cette demande de maintenance est défini sur **Entrant** ou **Sortant**.

L'illustration suivante présente un exemple de la page **États du cycle de vie de la demande de maintenance**.

![Page États du cycle de vie de la demande de maintenance](media/02-setup-for-requests.png)

> [!NOTE]
> Les états du cycle de vie de la demande de maintenance, les groupes d'états du cycle de vie et les types sont liés et utilisés de la même manière que les états du cycle de vie de l'ordre de travail, les groupes d'états du cycle de vie et les types. 

## <a name="set-up-maintenance-request-lifecycle-models"></a>Définir les modèles de cycle de vie de la demande de maintenance

Après avoir créé les états du cycle de vie requis pour vos demandes de maintenance, ils peuvent être divisés en groupes d'états du cycle de vie ou en modèles de cycle de vie. Les modèles de cycle de vie de la demande de maintenance permettent de créer le flux qui peut être utilisé pour différents types de demandes de maintenance. Au minimum, un modèle de cycle de vie de la demande de maintenance standard doit être créé.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Demandes de maintenance** \> **Modèles de cycle de vie**.
2. Sélectionnez **Nouveau** pour créer un modèle de cycle de vie de la demande de maintenance.
3. Dans le champ **Modèle de cycle de vie**, entrez un ID pour le modèle de cycle de vie.
4. Dans le champ **Nom**, entrez un nom.

    Dans le raccourci **Détails**, le champ **États du cycle de vie** affiche le nombre d'états du cycle de vie qui sont sélectionnés dans ce modèle de cycle de vie. Le champ **Types de demandes de maintenance** affiche le nombre de types de demandes de maintenance qui utilisent ce modèle de cycle de vie.

5. Dans le raccourci **États du cycle de vie**, sélectionnez les états du cycle de vie qui doivent être inclus dans le modèle de cycle de vie :

    - Pour inclure un état du cycle de vie dans le modèle de cycle de vie, sélectionnez-le dans la section **États du cycle de vie restants**, puis utilisez le bouton Flèche droite ![Flèche droite](media/03-setup-for-requests.png) pour le déplacer vers la section **États du cycle de vie sélectionnés**.
    - Pour inclure tous les états du cycle de vie disponibles dans le modèle de cycle de vie, sélectionnez le bouton **Sélectionner tous les états disponibles** ![Sélectionner tous les états disponibles](media/04-setup-for-requests.png). Tous les états du cycle de vie sont déplacés vers la section **États du cycle de vie sélectionnés**.
    - Pour supprimer un état du cycle de vie du modèle de cycle de vie, sélectionnez-le dans la section **États du cycle de vie sélectionnés**, puis utilisez le bouton Flèche gauche ![Flèche gauche](media/05-setup-for-requests.png) pour le déplacer vers la section **États du cycle de vie restants**.

6. Dans le raccourci **Général**, les champs de la section **Mises à jour** sont utiles si vous utilisez la réparation au dépôt.

    - Dans le champ **État du cycle de vie pour l'actif reçu**, sélectionnez l'état du cycle de vie vers lequel les actifs sélectionnés dans une demande de maintenance doivent être automatiquement mis à jour lorsqu'ils sont reçus pour réparation au dépôt.
    - Dans le champ **État du cycle de vie pour l'actif livré**, sélectionnez l'état du cycle de vie vers lequel les actifs sélectionnés dans une demande de maintenance doivent être automatiquement mis à jour lorsqu'ils sont retournés après réparation.

L'illustration suivante présente un exemple de la page **Modèles de cycle de vie de la demande de maintenance**.

![Page Modèles de cycle de vie de la demande de maintenance](media/06-setup-for-requests.png)
