---
title: Résoudre les problèmes d’optimisation de la planification
description: Cet article décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation de l’optimisation de la planification.
author: t-benebo
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 37c38ab9cec8ae3c9d4decf8043b43ea2251083e
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739727"
---
# <a name="troubleshoot-planning-optimization"></a>Résoudre les problèmes d’optimisation de la planification 

[!include [banner](../../includes/banner.md)]

Cet article décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de l’utilisation de l’optimisation de la planification.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>L’installation du complément Optimisation de la planification n’a pas aboutie

L’Optimisation de la planification nécessite que Lifecycle Services (LCS) soit activé, un environnement à haute disponibilité, niveau 2 ou supérieur (pas un environnement OneBox), avec Dynamics 365 Supply Chain Management version 10.0.7 ou les versions ultérieures. Si vous essayez d’installer le complément dans un environnement OneBox, l’installation ne va pas aboutir.

**Correction** : Annulez l’installation et utilisez un environnement à haute disponibilité, de niveau 2 ou supérieur (pas un environnement OneBox).

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>La planification des travaux par lots échoue lorsque l’optimisation de la planification est activée.

Lorsque vous activez l’optimisation de la planification, le moteur de planification générale déprécié est automatiquement désactivé. Les traitements par lots de planification générale créés pour le moteur de planification générale déprécié vont échouer s’ils sont déclenchés tandis que l’optimisation de la planification est activée. Vous risquez de recevoir un message d’erreur tel que *Cette opération a déclenché la planification principale qui n’est pas prise en charge lorsque l’optimisation de la planification est activée*.

**Correction** : annulez tous les traitements par lots de planification générale créés pour le moteur de planification générale déprécié.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>Les résultats de l’optimisation de la planification sont différents des résultats précédents

L’optimisation de la planification diffère de la conception du moteur de planification générale déprécié dans certains domaines. Cela peut également être dû à des fonctionnalités en attente.

**Correction** : Exécutez l’analyse d’ajustement de l’optimisation de la planification, puis analysez les résultats tout en vous référant à la documentation associée pour comprendre l’impact. Pour plus d’informations, voir [Analyse de concordance d’Optimisation de la planification](planning-optimization-fit-analysis.md).

## <a name="cant-enable-planning-optimization"></a>Impossible d’activer l’optimisation de la planification

Le **Statut de connexion** doit être **Connecté** avant de pouvoir définir **Utiliser l’optimisation de la planification** sur **Oui**. Pour plus d’informations, voir [Prise en main d’Optimisation de la planification](get-started.md).

**Correction** : Assurez-vous que le complément Optimisation de la planification a été installé avec succès.

## <a name="error-message-is-shown-during-ctp"></a>Un message d’erreur s’affiche pendant le CTP

Si vous essayez d’exécuter capable to promise (CTP) à partir d’une commande client lorsque l’optimisation de la planification est activée, vous recevrez le message d’erreur suivant : *Cette opération a déclenché la planification principale qui n’est pas prise en charge lorsque l’optimisation de la planification est activée*.

Ceci est lié à une fonctionnalité en attente qui est prévue dans le cadre de la prise en charge des ordres de fabrication.

**Correction :** Évitez les calculs de CTP lorsque l’optimisation de la planification est activée jusqu’à ce que la prise en charge de CTP soit disponible.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Démarrer avec la planification générale](get-started.md)
- [Analyse de concordance pour l'optimisation de la planification](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]