---
title: Désactiver les règles utilisées dans le processus de validation des transactions
description: Cet article décrit la fonctionnalité de désactivation des règles de validation des transactions dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 7d566aa3b829dad281528925a341382f9637fdba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884874"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>Désactiver les règles utilisées dans le processus de validation des transactions

[!include [banner](../includes/banner.md)]

Les détaillants peuvent avoir des scénarios et des processus métier qui leur sont propres. Par conséquent, toutes les règles incluses dans le processus de validation des transactions commerciales ne s’appliquent pas à tous les détaillants. Pour tenir compte des différences, Microsoft Dynamics 365 Commerce fournit une fonctionnalité permettant de désactiver les règles qui ne s’appliquent pas.

Pour afficher la liste des règles disponibles dans le processus de validation des transactions dans votre environnement et pour voir l’état de chaque règle, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux** et sélectionnez l’onglet **Validation des transactions**. Toutes les règles activées sont utilisées pour valider les transactions pendant le processus **Valider les transactions en magasin** et doivent être respectées pour que les transactions soient collectées et affichées sur un relevé de transaction.

Par défaut, le statut de chaque règle est défini sur **Activé**. Par conséquent, toutes les règles sont utilisées pour valider les transactions avant qu’elles soient extraites dans les relevés transactionnels commerciaux. Pour désactiver une règle, modifiez son statut en **Désactivé**. Les règles désactivées ne sont pas prises en compte lorsque les transactions sont validées au cours du processus **Valider les transactions en magasin**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
