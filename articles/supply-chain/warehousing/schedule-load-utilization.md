---
title: Programmer l’utilisation de l’espace de chargement
description: Cette rubrique explique comment configurer et planifier la charge d’un entrepôt.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f88dc44b036f6d5535f7e83693a387149f94f37d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239252"
---
# <a name="schedule-load-utilization"></a>Programmer l’utilisation de l’espace de chargement

[!include[banner](../includes/banner.md)]

Vous pouvez programmer l’utilisation de l’espace de chargement pour les types d’emplacements sélectionnés, et vous pouvez également prévoir l’utilisation actuelle et future de l’espace de chargement. Vous pouvez prévoir la charge pour un ou plusieurs sites, pour les unités de charge (zone ou entrepôt), ou pour une combinaison d’une zone et d’un entrepôt.

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a>Planification et affichage de la charge d’un entrepôt ou un site

Pour planifier la charge des sites, entrepôts ou zones, vous créez un paramétrage de l’utilisation de l’espace et vous l’associez à un plan général.

Dans le paramétrage de l’utilisation de l’espace, vous utilisez des types d’emplacement, tels que **Emplacement de stockage en gros** et **Emplacement de prélèvement**, pour indiquer comment l’utilisation de l’espace doit être projetée. Vous spécifiez également un mode de charge de stockage, tel que **Zone**.

La projection de l’utilisation de l’espace future est basée sur les informations calculées dans le plan général associé. Les plans généraux prévoient la planification des ressources pour les commandes entrantes et sortantes pour la production et les opérations. La projection de l’espace disponible est basée sur la relation entre le paramétrage de l’utilisation de l’espace et le plan général sélectionné.

À l’aide du mode de charge de stockage sélectionné dans le paramétrage de l’utilisation de l’espace, vous pouvez spécifier si la charge doit être prévue pour chaque entrepôt ou zone, ou si les projections doivent inclure des informations sur les entrepôts et les zones à la fois. Indiquez également si les emplacements bloqués doivent être exclus du calcul de l’utilisation de l’espace de chargement.

Vous pouvez prévoir l’utilisation de l’espace en générant l’état **Utilisation de l’espace de chargement d’entrepôt**. Lorsque vous générez cet état, vous pouvez spécifier si l’utilisation de l’espace de chargement doit être prévue pour chaque site, par site ou pour l’unité de charge sélectionnée, telle qu’une zone ou un entrepôt.

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a>Création d’un paramétrage d’utilisation de l’espace pour un entrepôt

1. Sélectionnez **Gestion des stocks** \> **Paramétrage** \> **Surveillance de l’entrepôt** \> **Utilisation de l’espace**.
2. Sélectionnez **Nouveau** pour créer un paramétrage de l’utilisation de l’espace. Spécifiez un ID et un nom pour le nouveau paramétrage.
3. Dans le champ **Mode de charge de stockage**, indiquez si la vue d’ensemble de l’utilisation de l’espace doit afficher des informations par entrepôt, zone ou entrepôt et zone à la fois.
4. Définissez l’option **Exclure les emplacements bloqués** sur **Oui** pour exclure les emplacements de stockage bloqués du calcul de l’espace disponible. Vous pouvez bloquer un emplacement de stockage pour l’entrée et la sortie en spécifiant une cause de blocage pour l’emplacement dans le champ **Cause du blocage des entrées** ou **Cause du blocage des sorties** de l’organisateur **Autre** de la page **Emplacements de stockage**.
5. Dans l’organisateur **Type d’emplacement**, sélectionnez les types d’emplacements à inclure dans le calcul de l’utilisation de l’espace. Vous devez sélectionner au moins un type d’emplacement pour la projection.

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a>Association d’un paramétrage de l’utilisation de l’espace à un plan général

1. Sélectionnez **Gestion des stocks** \> **Tâches périodiques** \> **Programmer l’utilisation de l’espace de chargement**.
2. Dans le champ **Plan général**, sélectionnez un plan général.
3. Dans le champ **Nombre de jours**, spécifiez le nombre de jours à inclure dans la projection des charges de travail actuelles et futures.
4. Dans le champ **Utilisation de l’espace**, sélectionnez le paramétrage de l’utilisation de l’espace à utiliser pour la projection des charges de travail actuelles et futures.

### <a name="specify-the-load-utilization-projection-and-view-information"></a>Spécification de la projection de l’utilisation de l’espace de chargement et affichage des informations

1. Sélectionnez **Gestion des stocks** \> **Recherches et états** \> **États sur le stock physique** \> **Utilisation de l’espace de chargement d’entrepôt**.
2. Dans le champ **Afficher par**, sélectionnez le niveau de la projection de l’utilisation de l’espace :

    - **Site** – Prévoyez l’utilisation de l’espace pour chaque site. Cette projection est utile si vous souhaitez par exemple afficher tous les entrepôts pour un site afin de pouvoir équilibrer l’utilisation de l’espace entre les entrepôts.
    - **Unité de charge** – Prévoyez l’utilisation de l’espace pour des zones ou des entrepôts. L’espace disponible est ensuite prévu en fonction de la valeur que vous avez sélectionnée dans le champ **Mode de charge de stockage** de la page **Utilisation de l’espace** lorsque vous avez créé le paramétrage de l’utilisation de l’espace.

3. Suivez l’une des procédures suivantes, selon la valeur que vous avez sélectionnée à l’étape précédente :

    - Si vous avez sélectionné **Site** dans le champ **Afficher par**, le champ **Site** est disponible. Sélectionnez un ou plusieurs sites à inclure dans la projection.
    - Si vous avez sélectionné **Unité de charge** dans le champ **Afficher par**, le champ **Unité de charge** est disponible. Sélectionnez l’unité de charge.

4. Dans le champ **Type de charge**, sélectionnez **Volume** ou **Poids** pour spécifier l’unité opérationnelle d’entrepôt pour laquelle prévoir l’espace.
5. Dans le champ **Paramétrage de l’utilisation de l’espace**, sélectionnez le paramétrage de l’utilisation de l’espace sur lequel la projection doit être basée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]