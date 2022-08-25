---
title: Configurer un environnement de développement d’e-commerce pour déboguer sur une machine virtuelle Retail Server Niveau 1
description: Cet article explique comment configurer un environnement de développement d’e-commerce pour déboguer sur une machine virtuelle (VM) Retail Server Niveau 1.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 64e03c742f7095e2e485f32ad534f2a755ddd062
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277877"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a>Configurer un environnement de développement d’e-commerce pour déboguer sur une machine virtuelle Retail Server Niveau 1

[!include [banner](../../includes/banner.md)]

Cet article explique comment configurer un environnement de développement d’e-commerce pour déboguer sur une machine virtuelle (VM) Retail Server Niveau 1.

## <a name="description"></a>Description

Les environnements Microsoft Dynamics 365 Commerce de niveau 1 sont généralement déployés pour Commerce Runtime (CRT) et le développement de l’extension de point de vente (PDV). Ce sont des environnements autonomes. En raison de la nature logiciel en tant que service (SaaS) de l’architecture, ils n’incluent pas de composants e-commerce.

Dans certains scénarios, vous souhaiterez peut-être tester les appels aux extensions dans un environnement de niveau 1, afin de pouvoir déboguer des extensions à partir de composants e-commerce. Pour des instructions générales, voir [Déboguer dans un environnement de développement Commerce de niveau 1](../e-commerce-extensibility/debug-tier-1.md).

Lorsque vous déboguez dans un environnement de niveau 1, étant donné que le site appelle maintenant un autre serveur Retail Server, les appels entre serveurs peuvent provoquer diverses erreurs liées à la stratégie de sécurité du contenu.

L’illustration suivante montre un exemple d’erreur qui peut se produire lorsqu’une variante est sélectionnée sur une page de détails de produit.

![Erreur lorsqu’une variante est sélectionnée sur une page de détails du produit.](media/unhandled-rejection-error.jpg)

L’illustration suivante montre un exemple d’erreur similaire dans les outils de débogage d’un navigateur (outils de développement F12). Le message d’erreur mentionne la violation de la directive de stratégie de sécurité du contenu.

![Erreur des outils de débogage.](media/debugger-tools-error.JPG)

## <a name="resolution"></a>Résolution

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a>Désactiver la stratégie de sécurité du contenu pour le site dans le générateur de site Commerce

1. Sélectionnez le site sur lequel vous travaillez.
1. Sélectionnez **Paramètres**, puis **Extensions**.
1. Sur l’onglet **Stratégie de sécurité du contenu**, sélectionnez **Désactiver la stratégie de sécurité du contenu**.
1. Sélectionnez **Enregistrer et publier**.

> [!NOTE]
> La connexion B2C ne fonctionnera pas dans un environnement de développement local. Cependant, vous pouvez utiliser des caisses invité ou créer des simulations de page pour simuler la connexion d’un utilisateur si nécessaire.

## <a name="additional-resources"></a>Ressources supplémentaires

[Démarrer avec le développement d’extensibilité en ligne de l’e-commerce](../e-commerce-extensibility/sdk-getting-started.md)

[Gérer la stratégie de sécurité du contenu (CSP) sur le site d’e-commerce](../manage-csp.md)
