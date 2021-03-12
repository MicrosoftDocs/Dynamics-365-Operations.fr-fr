---
title: Résoudre les problèmes d'optimisation de la planification
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation de l'optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2020
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
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 8e67a6faf52b51264555b06f56b289d19ca580d6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992493"
---
# <a name="troubleshoot-planning-optimization"></a>Résoudre les problèmes d'optimisation de la planification 

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de l'utilisation de l'optimisation de la planification.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>L'installation du complément Optimisation de la planification n'a pas aboutie

L'Optimisation de la planification nécessite que Lifecycle Services (LCS) soit activé, un environnement à haute disponibilité, niveau 2 ou supérieur (pas un environnement OneBox), avec Dynamics 365 Supply Chain Management version 10.0.7 ou les versions ultérieures. Si vous essayez d'installer le complément dans un environnement OneBox, l'installation ne va pas aboutir.

**Correction** : Annulez l'installation et utilisez un environnement à haute disponibilité, de niveau 2 ou supérieur (pas un environnement OneBox).

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>La planification des travaux par lots échoue lorsque l'optimisation de la planification est activée.

Lorsque vous activez l'optimisation de la planification, le moteur de planification principal intégré est automatiquement désactivé. Les traitements par lots de planification créés pour le moteur de planification intégré de Supply Chain Management vont échouer s'ils sont déclenchés tandis que l'optimisation de la planification est activée. Vous risquez de recevoir un message d'erreur tel que *Cette opération a déclenché la planification principale qui n'est pas prise en charge lorsque l'optimisation de la planification est activée*.

**Correction** : Annulez tous les travaux par lots de planification principale créés pour le moteur de planification intégré de Supply Chain Management.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>Les résultats de l'optimisation de la planification sont différents des résultats précédents

L'optimisation de la planification diffère de la conception de planification principale intégrée dans certains domaines. Cela peut également être dû à des fonctionnalités en attente.

**Correction** : Exécutez l'analyse d'ajustement de l'optimisation de la planification, puis analysez les résultats tout en vous référant à la documentation associée pour comprendre l'impact. Pour plus d'informations, voir [Analyse de concordance d'Optimisation de la planification](planning-optimization-fit-analysis.md).

## <a name="master-planning-doesnt-respect-the-coverage-time-fence"></a>La planification ne respecte pas la plage de gestion de la couverture

Cela est dû à une fonctionnalité en attente pour l'optimisation de la planification.

**Correction** : Jusqu'à ce que la fonction en attente soit disponible, filtrez ou supprimez les ordres planifiés pour supprimer les suggestions d'approvisionnement en dehors de la période de couverture.

## <a name="cant-enable-planning-optimization"></a>Impossible d'activer l'optimisation de la planification

Le **Statut de connexion** doit être **Connecté** avant de pouvoir définir **Utiliser l'optimisation de la planification** sur **Oui**. Pour plus d'informations, voir [Prise en main d'Optimisation de la planification](get-started.md).

**Correction** : Assurez-vous que le complément Optimisation de la planification a été installé avec succès.

## <a name="error-message-is-shown-during-ctp"></a>Un message d'erreur s'affiche pendant le CTP

Si vous essayez d'exécuter capable to promise (CTP) à partir d'une commande client lorsque l'optimisation de la planification est activée, vous recevrez le message d'erreur suivant : *Cette opération a déclenché la planification principale qui n'est pas prise en charge lorsque l'optimisation de la planification est activée*.

Ceci est lié à une fonctionnalité en attente qui est prévue dans le cadre de la prise en charge des ordres de fabrication.

**Correction :** Évitez les calculs de CTP lorsque l'optimisation de la planification est activée jusqu'à ce que la prise en charge de CTP soit disponible.

## <a name="additional-resources"></a>Ressources supplémentaires

[Mise en route de l'optimisation de la planification](get-started.md)

[Analyse de concordance pour l’optimisation de la planification](planning-optimization-fit-analysis.md)
