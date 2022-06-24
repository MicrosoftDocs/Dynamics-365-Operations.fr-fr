---
title: Paramètres globaux des appareils mobiles
description: Cet article explique comment configurer les paramètres d’appareil mobile sur la page de paramètres de gestion des entrepôts.
author: Mirzaab
ms.date: 08/13/2021
ms.topic: article
ms.search.form: WHS
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e6e03414edd9243fcc4156195928455b30a7cee9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847757"
---
# <a name="global-mobile-device-parameters"></a>Paramètres globaux des appareils mobiles

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer les paramètres globaux de gestion des entrepôts qui affectent la façon dont le système interagit avec les appareils mobiles.

Pour plus d’informations sur la configuration des magasiniers, voir [Gestion des magasiniers](manage-warehouse-workers.md). Pour plus d’informations sur le traitement des contenants sur les appareils mobiles, voir [Réception du contenant via l’application mobile Warehouse Management](warehousing-mobile-device-app-license-plate-receiving.md). Pour plus d’informations sur les processus d’inventaire tournant, voir [Inventaire tournant](cycle-counting.md) et [Exemples de scénarios d’inventaire tournant](cycle-counting-scenarios.md).

## <a name="open-the-warehouse-management-parameters-page"></a>Ouvrir lapage des paramètres de gestion des entrepôts

Pour ouvrir la page **Paramètres de gestion des entrepôts**, accédez à **Gestion des entrepôts \> Paramétrage \> Paramètres de gestion des entrepôt**. Vous pouvez ensuite définir les champs liés au travail sur appareil mobile, comme décrit dans la section suivante de cet article.

## <a name="mobile-device-fasttab-on-the-general-tab"></a>Raccourci Appareil mobile dans l’onglet Général

Les paramètres globaux de l’appareil mobile sont disponibles sur le raccourci **Appareil mobile** sur l’onglet **Général** de la page **Paramètres de gestion des entrepôts**. Les champs disponibles sont les suivants.

| Champ | Description  |
|---|---|
| Type de note d’appareil mobile | Sélectionnez le type d’information affichée pour les collaborateurs pendant le prélèvement de la commande client. |
| Limite de quantité analysée | Saisissez la quantité maximale d’articles qu’un collaborateur peut numériser au cours de chaque session à l’aide d’un élément de menu d’appareil mobile doté d’une valeur **Processus de création de travail** définie sur *Ajustement en*. Ce champ n’affecte pas les analyses effectuées à l’aide d’un autre type d’élément de menu. |
| Utiliser la journalisation des sessions d’appareil mobile | Définissez cette option sur *Oui* pour conserver un journal de l’historique de connexion des collaborateurs. Pour afficher le journal, accédez à **Sessions des utilisateurs professionnels \> Recherche et états \> Journaux des appareils mobiles \> Sessions des utilisateurs professionnels**. |
| Nombre d’erreurs stockées | Entrez le nombre maximal d’enregistrements d’erreurs que le système doit stocker. Pour afficher le journal d’erreurs, accédez à **Sessions des utilisateurs professionnels \> Recherche et états \> Journaux des appareils mobiles \> Sessions des utilisateurs professionnels**. |
| Journal des transferts d’entrepôt par défaut | Sélectionnez le journal utilisé lorsque les collaborateurs utilisent un appareil mobile pour déplacer des produits d’un entrepôt à un autre. |
| Autoriser l’enregistrement de la ligne de commande fournisseur en mode révision externe | Définissez cette option sur *Oui* si les collaborateurs doivent pouvoir utiliser un appareil mobile pour enregistrer des lignes de commande pour les commandes fournisseur avec une valeur **Statut d’approbation** définie sur *En révision externe*. Définissez cette option sur *Non* pour empêcher les collaborateurs d’enregistrer des lignes pour les commandes fournisseur en révision externe. |
| Activer la prise en charge de RSAT | Le champ active le validateur de tâches de l’application mobile Warehouse Management, qui enregistre et valide chaque étape effectuée par l’application. Étant donné que ce processus peut considérablement ralentir les performances du système, vous ne devez activer le validateur que pendant les tests. Vous ne devez jamais l’activer dans un environnement de production. |
