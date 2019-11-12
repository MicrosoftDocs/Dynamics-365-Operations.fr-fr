---
title: Désactiver les règles dans le vérificateur de cohérence des transactions de vente au détail
description: Cette rubrique décrit la fonctionnalité de désactivation des règles du vérificateur de cohérence des transactions de vente au détail dans Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4bf8df2fb9f8f5c33ceb13eb012fb6879f81ec66
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2019
ms.locfileid: "2586295"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Désactiver les règles dans le vérificateur de cohérence des transactions de vente au détail 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Les détaillants peuvent avoir des scénarios et des processus métier qui leur sont propres. Par conséquent, toutes les règles disponibles par défaut dans le vérificateur de cohérence des transactions de vente au détail ne s'appliquent pas à tous les détaillants. Pour tenir compte des différences, Microsoft Dynamics 365 Retail fournit une fonctionnalité permettant de désactiver les règles qui ne s'appliquent pas.

Pour afficher la liste des règles disponibles dans le vérificateur de cohérence des transactions de vente au détail dans votre environnement, et pour afficher le statut de chaque règle, accédez à **Vente au détail \> Configuration du siège \> Paramètres \> Paramètres des ventes au détail**, puis sélectionnez l'onglet **Validation de transaction**.

Par défaut, le statut de chaque règle est défini sur **Activé**. Par conséquent, toutes les règles sont utilisées pour valider les transactions de vente au détail avant qu'elles soient extraites dans les relevés de vente au détail. Pour désactiver une règle, modifiez son statut en **Désactivé**. Les règles désactivées ne sont pas prises en compte lorsque les transactions de vente au détail sont validées au cours du processus de calcul des relevés.

Pour contourner l'ensemble du processus de validation, indépendamment des règles activées, accédez à **Vente au détail \> Configuration du siège \> Paramètres \> Paramètres des ventes au détail**, puis, dans l'onglet **Validation de transaction**, définissez l'option **Désactiver le vérificateur de cohérence pour les transactions de vente au détail** sur **Oui**. Une fois cette option définie sur **Non**, elle ne peut pas être redéfinie sur **Oui** à partir de l'interface utilisateur.
