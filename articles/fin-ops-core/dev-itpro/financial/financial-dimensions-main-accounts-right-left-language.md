---
title: Dimensions financières et comptes principaux dans des langues qui se lisent de droite à gauche
description: Cette rubrique décrit certaines des décisions que vous devez prendre en compte lorsque vous utilisez une langue qui se lit de droite à gauche, et vous devez paramétrer des dimensions financières et des comptes principaux.
author: RyanCCarlson2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: rcarlson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 26fd186415db0adf01b8c53b188171fcf86fbc88
ms.sourcegitcommit: eff3da7ea98758f100d44ff7feec17157afc2e80
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111660"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a><span data-ttu-id="b05e0-103">Dimensions financières et comptes principaux dans des langues s’écrivant de droite à gauche</span><span class="sxs-lookup"><span data-stu-id="b05e0-103">Financial dimensions and main accounts in right-to-left languages</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b05e0-104">Cette rubrique décrit certaines des décisions d’implémentation que vous devez prendre en compte lorsque vous utilisez une langue qui se lit de droite à gauche, et vous devez paramétrer des dimensions financières et des comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="b05e0-104">This topic describes some of the implementation decisions that you should consider when you use a right-to-left language, and you must set up financial dimensions and main accounts.</span></span>

<span data-ttu-id="b05e0-105">Les dimensions financières et les comptes principaux sont des composants clés de la phase de planification pour une implémentation.</span><span class="sxs-lookup"><span data-stu-id="b05e0-105">Financial dimensions and main accounts are key components of the planning phase for an implementation.</span></span> <span data-ttu-id="b05e0-106">Une fois les dimensions financières et les comptes principaux créés dans le système, ils sont utilisés sur les pages **Configurer des structures de compte**, **Structures de règle avancées** et **Configuration de dimension financière pour l’intégration d’applications**.</span><span class="sxs-lookup"><span data-stu-id="b05e0-106">After financial dimensions and main accounts are created in the system, they are used on the **Configure account structures**, **Advanced rule structures**, and **Financial dimension configuration for integrating applications** pages.</span></span> <span data-ttu-id="b05e0-107">L’ordre qui est défini sur ces pages est utilisé dans le système pour la saisie de données et la consommation.</span><span class="sxs-lookup"><span data-stu-id="b05e0-107">The order that is defined on those pages is used in the system for data entry and consumption.</span></span> <span data-ttu-id="b05e0-108">À certains endroits du système, les dimensions financières et les comptes principaux apparaissent dans des champs distincts.</span><span class="sxs-lookup"><span data-stu-id="b05e0-108">In some places in the system, the financial dimensions and main accounts appear in separate fields.</span></span> <span data-ttu-id="b05e0-109">À d’autres endroits, tels que les journaux, les dimensions financières et les comptes principaux apparaissent sous forme de chaîne simple.</span><span class="sxs-lookup"><span data-stu-id="b05e0-109">In other places, such as journals, the financial dimensions and main accounts appear as a single string.</span></span>

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a><span data-ttu-id="b05e0-110">Recommandations concernant le paramétrage des dimensions financières et des comptes principaux dans un système qui se lit de droite à gauche</span><span class="sxs-lookup"><span data-stu-id="b05e0-110">Best practices for setting up financial dimensions and main accounts in a right-to-left system</span></span>

- <span data-ttu-id="b05e0-111">Lorsque vous sélectionnez le séparateur pour les plans de comptes, sélectionnez l’une des options de séparateur double : trait d’union double (`--`), double barre (`||`) ou double point (`..`) ou double trait de soulignement (`\\`).</span><span class="sxs-lookup"><span data-stu-id="b05e0-111">When you select the delimiter for charts of accounts, select one of the double delimiter options: double hyphen (`--`), double bar (`||`), double period (`..`), or double underscore (`\\`).</span></span>
- <span data-ttu-id="b05e0-112">Lorsque vous créez des valeurs de dimension financière et de compte principal, utilisez uniquement des nombres et des caractères de langue qui se lisent de droite à gauche.</span><span class="sxs-lookup"><span data-stu-id="b05e0-112">When you create financial dimension and main account values, use only numbers and right-to-left language characters.</span></span>
- <span data-ttu-id="b05e0-113">Évitez d’utiliser le séparateur de plan de comptes sélectionné dans les valeurs de dimension financière et de compte principal.</span><span class="sxs-lookup"><span data-stu-id="b05e0-113">Avoid using the selected chart of accounts delimiter in financial dimension and main account values.</span></span>

<span data-ttu-id="b05e0-114">Si vous suivez ces recommandations, vous vous assurez d’une représentation cohérente de l’ordre défini par l’utilisateur dans tout le système.</span><span class="sxs-lookup"><span data-stu-id="b05e0-114">By following these best practices, you help guarantee consistent representation of the user defined-order throughout the system.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]