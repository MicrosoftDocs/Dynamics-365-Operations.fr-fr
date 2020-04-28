---
title: Désactiver les règles dans le vérificateur de cohérence des transactions de vente au détail
description: Cette rubrique décrit la fonctionnalité de désactivation des règles du vérificateur de cohérence des transactions dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 37209f1c1de19335f5f9fa6636ab55dd8b2fccc1
ms.sourcegitcommit: 02640a0f63daa9e509146641824ed623c4d69c7f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2020
ms.locfileid: "3265524"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Désactiver les règles dans le vérificateur de cohérence des transactions de vente au détail 

[!include [banner](../includes/banner.md)]

Les détaillants peuvent avoir des scénarios et des processus métier qui leur sont propres. Par conséquent, toutes les règles disponibles par défaut dans le vérificateur de cohérence des transactions commerciales ne s'appliquent pas à tous les détaillants. Pour tenir compte des différences, Microsoft Dynamics 365 Commerce fournit une fonctionnalité permettant de désactiver les règles qui ne s'appliquent pas.

Pour afficher la liste des règles disponibles dans le vérificateur de cohérence des transactions dans votre environnement, et pour afficher le statut de chaque règle, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux**, puis sélectionnez l'onglet **Validation de transaction**.

Par défaut, le statut de chaque règle est défini sur **Activé**. Par conséquent, toutes les règles sont utilisées pour valider les transactions avant qu'elles soient extraites dans les relevés commerciaux. Pour désactiver une règle, modifiez son statut en **Désactivé**. Les règles désactivées ne sont pas prises en compte lorsque les transactions sont validées au cours du processus de calcul des relevés.

Pour contourner l'ensemble du processus de validation, indépendamment des règles activées, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux**, puis, dans l'onglet **Validation de transaction**, définissez l'option **Désactiver le vérificateur de cohérence pour les transactions commerciales** sur **Oui**. Une fois cette option définie sur **Non**, elle ne peut pas être redéfinie sur **Oui** à partir de l'interface utilisateur.
