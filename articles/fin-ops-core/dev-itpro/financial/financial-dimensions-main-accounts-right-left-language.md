---
title: Dimensions financières et comptes principaux dans des langues qui se lisent de droite à gauche
description: Cette rubrique décrit certaines des décisions que vous devez prendre en compte lorsque vous utilisez une langue qui se lit de droite à gauche, et vous devez paramétrer des dimensions financières et des comptes principaux.
author: RyanCCarlson2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: rcarlson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5de2e0e6e56651487ebd36e3594eb378ce6154ea
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734951"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a>Dimensions financières et comptes principaux dans des langues s’écrivant de droite à gauche

[!include [banner](../includes/banner.md)]

Cette rubrique décrit certaines des décisions d’implémentation que vous devez prendre en compte lorsque vous utilisez une langue qui se lit de droite à gauche, et vous devez paramétrer des dimensions financières et des comptes principaux.

Les dimensions financières et les comptes principaux sont des composants clés de la phase de planification pour une implémentation. Une fois les dimensions financières et les comptes principaux créés dans le système, ils sont utilisés sur les pages **Configurer des structures de compte**, **Structures de règle avancées** et **Configuration de dimension financière pour l’intégration d’applications**. L’ordre qui est défini sur ces pages est utilisé dans le système pour la saisie de données et la consommation. À certains endroits du système, les dimensions financières et les comptes principaux apparaissent dans des champs distincts. À d’autres endroits, tels que les journaux, les dimensions financières et les comptes principaux apparaissent sous forme de chaîne simple.

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Recommandations concernant le paramétrage des dimensions financières et des comptes principaux dans un système qui se lit de droite à gauche

- Lorsque vous sélectionnez le séparateur pour les plans de comptes, sélectionnez l’une des options de séparateur double : trait d’union double (`--`), double barre (`||`) ou double point (`..`) ou double trait de soulignement (`\\`).
- Lorsque vous créez des valeurs de dimension financière et de compte principal, utilisez uniquement des nombres et des caractères de langue qui se lisent de droite à gauche.
- Évitez d’utiliser le séparateur de plan de comptes sélectionné dans les valeurs de dimension financière et de compte principal.

Si vous suivez ces recommandations, vous vous assurez d’une représentation cohérente de l’ordre défini par l’utilisateur dans tout le système.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
