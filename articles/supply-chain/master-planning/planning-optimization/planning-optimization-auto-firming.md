---
title: Confirmation automatique avec l’optimisation de la planification
description: Cette rubrique explique comment utiliser la confirmation automatique avec la fonction d'Optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: d014fcd542462e092f6e88232dff8fd5ee2253c1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963458"
---
# <a name="autofirming-with-planning-optimization"></a>Confirmation automatique avec l’optimisation de la planification

[!include [banner](../../includes/banner.md)]

La confirmation automatique vous permet de confirmer les ordres prévisionnels dans le cadre du processus de planification. Lorsque des ordres prévisionnels sont confirmés, ils deviennent des commandes fournisseur, ordres de transfert ou ordres de fabrication réels. Lorsque la fonction d'Optimisation de la planification est utilisée, les ordres prévisionnels sont confirmés pendant l'exécution d'une planification lorsque la date de commande (c'est-à-dire, la date de début) est comprise dans la plage de confirmation.

> [!NOTE]
> La confirmation automatique d'une commande fournisseur prévisionnelle n'est possible que si l'article est associé à un fournisseur.

## <a name="turn-on-autofirming"></a>Activer la confirmation automatique

Pour activer la confirmation automatique, procédez comme suit.

1. Dans l'espace de travail **Gestion des fonctionnalités**, sous l'onglet **Nouveau**, sélectionnez **Confirmation automatique de l'Optimisation de la planification** dans la liste. Si la fonctionnalité ne s'affiche pas sur l'onglet **Nouveau**, examinez les onglets **Non activé** et **Tous**.
1. Sélectionnez **Activer maintenant**. Sinon, sélectionnez **Programme**, puis sélectionnez l'heure à laquelle vous souhaitez activer la fonctionnalité.

## <a name="set-up-the-firming-time-fence"></a>Définissez la plage de gestion de la confirmation.

La plage de gestion de confirmation est calculée en avant à partir de la date d'exécution de la planification. Elle est définie par le nombre de jours que vous saisissez. Vous pouvez contrôler la plage de gestion de confirmation comme suit :

- Pour définir la plage de gestion de confirmation par défaut pour un groupe de couverture, accédez à **Planification** \> **Paramétrage** \> **Couverture** \> **Groupes de couverture**, puis sélectionnez un groupe de couverture. Puis, dans l'organisateur **Autre**, dans le champ **Plage de gestion de confirmation automatique (jours)**, entrez le nombre de jours.
- Pour remplacer la plage de gestion de confirmation définie pour le groupe de couverture pour un article spécifique, accédez à **Gestion des informations sur les produits** \> **Produits lancés**, puis dans le volet Actions, sélectionnez **Plan**, puis sélectionnez **Couverture de l'article**. Puis, dans l'onglet **Général**, sélectionnez **Remplacer les plages de gestion** et dans le champ **Plage de gestion de confirmation automatique (jours)**, entrez le nombre de jours.
- Pour remplacer la plage de confirmation définie pour le groupe de couverture et la couverture d'article pour un plan général spécifique, accédez à **Planification** \> **Paramétrage** \> **Plans généraux**, puis sélectionnez un plan général. Puis, dans l'organisateur **Plage de gestion en jours**, définissez **Confirmer** sur **Oui**, et saisissez le nombre de jours.

Si la confirmation automatique est activée pour l'exécution d'une planification avec l'option Optimisation de la planification, le processus de confirmation automatique a lieu selon la configuration de la confirmation automatique. Si la confirmation automatique n'est pas activée, ou si la planification a commencé depuis la page **Besoins nets**, le processus de confirmation automatique est ignoré.

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a>Optimisation de la planification vs moteur de planification intégré dans Supply Chain Management

L'option Optimisation de planification et le moteur de planification qui est intégré à Microsoft Dynamics 365 Supply Chain Management peuvent être utilisés pour confirmer automatiquement les ordres prévisionnels. Toutefois, il existe des différences importantes. Par exemple, tandis que l'Optimisation de la planification utilise la date de commande (à savoir la date de début) pour déterminer les ordres prévisionnels à confirmer, le moteur de planification intégré à Supply Chain Management utilise la date de besoin (à savoir la date de fin). Voici un résumé des différences.

**Service Optimisation de la planification**

- La confirmation automatique est basée sur la date de commande (date de début).
- Puisque la date de commande (date de début) déclenche la confirmation, vous n'avez pas à tenir compte du délai d'exécution dans le cadre de la plage de confirmation.
- Si vous souhaitez confirmer tous les ordres qui doivent commencer pendant la semaine en cours, la plage de confirmation doit être d'une semaine.

**Moteur de planification intégré à Supply Chain Management**

- La confirmation automatique est basée sur la date de besoin (date de fin).
- Pour assurer que les ordres sont confirmés en temps voulu, la plage de confirmation doit être plus longue que le délai d'exécution.
- Si vous souhaitez confirmer tous les ordres qui doivent commencer pendant la semaine en cours, la plage de confirmation doit être le délai d'exécution plus une semaine.
