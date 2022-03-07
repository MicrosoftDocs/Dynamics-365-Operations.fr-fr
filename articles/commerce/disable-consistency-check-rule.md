---
title: Désactiver les règles utilisées dans le processus de validation des transactions
description: Cette rubrique décrit la fonctionnalité de désactivation des règles de validation des transactions dans Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 12/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: cdaea51b4c84e6a62f0eb9412315ae77b4c11503
ms.sourcegitcommit: 9c2bc045eafc05b39ed1a6b601ccef48bd62ec55
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7919523"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>Désactiver les règles utilisées dans le processus de validation des transactions

[!include [banner](../includes/banner.md)]

Les détaillants peuvent avoir des scénarios et des processus métier qui leur sont propres. Par conséquent, toutes les règles incluses dans le processus de validation des transactions commerciales ne s’appliquent pas à tous les détaillants. Pour tenir compte des différences, Microsoft Dynamics 365 Commerce fournit une fonctionnalité permettant de désactiver les règles qui ne s’appliquent pas.

Pour afficher la liste des règles disponibles dans le processus de validation des transactions dans votre environnement et pour voir l’état de chaque règle, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux** et sélectionnez l’onglet **Validation des transactions**. Toutes les règles activées sont utilisées pour valider les transactions pendant le processus **Valider les transactions en magasin** et doivent être respectées pour que les transactions soient collectées et affichées sur un relevé de transaction.

Par défaut, le statut de chaque règle est défini sur **Activé**. Par conséquent, toutes les règles sont utilisées pour valider les transactions avant qu’elles soient extraites dans les relevés transactionnels commerciaux. Pour désactiver une règle, modifiez son statut en **Désactivé**. Les règles désactivées ne sont pas prises en compte lorsque les transactions sont validées au cours du processus **Valider les transactions en magasin**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
