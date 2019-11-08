---
title: Créer des demandes de maintenance
description: Cette rubrique explique comment créer une demande de maintenance dans Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7fc9ec2f6a9a8a11d824e4b5c13d5aa173541454
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571919"
---
# <a name="create-maintenance-requests"></a>Créer des demandes de maintenance

[!include [banner](../../includes/banner.md)]

 

Les demandes de maintenance peuvent être utilisées si les agents de maintenance ou de production découvrent que l'équipement doit être réparé, mais que la réparation ne peut pas être effectuée immédiatement.

**Exemple :** Pendant qu'un agent de maintenance effectue une réparation, il découvre qu'un autre actif situé au même endroit doit être réparé. Cependant, l'agent de maintenance n'a pas le temps ni les pièces de rechange nécessaires pour effectuer le travail de réparation. Par conséquent, il crée une demande de maintenance pour l'actif et entre une brève description du problème.

La section **Demandes de maintenance actives** du volet **Informations associées** à droite de la page **Tous les actifs** ou **Actifs actifs** (**Gestion d'actifs** \> **Commun** \> **Actifs** \> **Tous les actifs** ou **Actifs actifs**) affiche les demandes de maintenance actives attachées à l'actif sélectionné.

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**.
2. Sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une demande**, dans le champ **Type de demande de maintenance**, sélectionnez le type de demande de maintenance. Un type par défaut est proposé.
4. Dans le champ **Description**, entrez un nom ou un titre décrivant brièvement la demande de maintenance.
5. Dans les champs **Poste technique** et **Actif**, sélectionnez un poste technique ou un actif, ou la combinaison d'un poste technique et d'un actif, comme vous le souhaitez. Vous pouvez créer une demande de maintenance sans activer d'actif, et l'actif pourra être ajouté à la demande de maintenance ultérieurement. Si l'agent de maintenance qui est connecté est lié à une ressource associée à un actif, le champ **Actif** est automatiquement défini.

    Si une demande de maintenance est déjà jointe à l’actif sélectionné, une barre de message apparaît en haut de la boîte de dialogue **Créer une demande** pour vous indiquer l'ID de la demande de maintenance. Une barre de message vous informe également si l'actif est couvert par un accord de garantie.

6. Dans le champ **Niveau de service**, sélectionnez un niveau de service qui indique l'urgence de la demande.
7. Si vous avez sélectionné un actif à l'étape 5, vous pouvez utiliser les champs **Symptôme de défaut**, **Zone de défaut** et **Type de défaut** pour créer un enregistrement de défaut.
8. Si la demande de maintenance a entraîné un temps d'arrêt pour maintenance, entrez la date et l'heure de début du temps d'arrêt.

    Le champ **Lancé par** est automatiquement défini pour votre nom.

10. Le champ **Début réel** est automatiquement défini sur la date et l'heure actuelles. Vous pouvez néanmoins modifier la valeur comme vous le voulez.
11. Dans le champ **Détails**, entrez des notes supplémentaires requises.
12. Cliquez sur **OK**.

![Créer une demande de maintenance](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a>Traitement ultérieur des demandes de maintenance

Une fois une demande de maintenance créée, mais avant qu’elle ne soit convertie en ordre de travail, vous devez mettre à jour diverses informations. Généralement, un gestionnaire ou un autre employé administratif effectue cette tâche.

- Dans la page **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**, sélectionnez la demande à utiliser, puis sélectionnez **Modifier**.

Dans la vue Détails, vous pouvez mettre à jour diverses informations. Voici quelques exemples :

- Sélectionnez et vérifiez l'actif. Si vous devez sélectionner un autre actif ultérieurement, vous pouvez définir l'option **Actif vérifié** sur **Non**.
- Sélectionnez un groupe d'agents de maintenance responsable et/ou un agent de maintenance responsable. Pour plus d'informations sur le paramétrage requis, voir [Agents de maintenance responsables](../setup-for-maintenance-requests/responsible-workers.md).
- Sélectionnez un type de tâche de maintenance et, si ces informations sont pertinentes, une variante de la tâche de maintenance associée et un commerce de tâche.
- Dans les champs **Latitude** et **Longitude**, entrez les coordonnées géographiques. Toutes les coordonnées ajoutées à une demande de maintenance sont automatiquement transférées vers un ordre de travail associé. 

![Mettre à jour la demande de maintenance](media/04-manage-maintenance-requests.png)

> [!NOTE]
> Si vous sélectionnez un actif lorsque vous créez une demande de maintenance, vous pouvez ajouter un défaut à l'actif. Une fois la demande de maintenance créée, vous pouvez ajouter des défauts, comme vous le souhaitez. Pour ajouter des défauts, sélectionnez **Défaut d'actif** sur la page **Toutes les demandes de maintenance**.
