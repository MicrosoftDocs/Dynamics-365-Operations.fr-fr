---
title: Calcul PDP/MRP intersociétés
description: Cette rubrique explique la planification principale intersociétés
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 02d1a3675cfe30f2e72237f69509398122d17f05
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671868"
---
# <a name="intercompany-master-scheduling"></a>Calcul PDP/MRP intersociétés

[!include [banner](../../includes/banner.md)]

Le calcul PDP/MRP intersociétés permet de calculer les demandes et de générer les ordres prévisionnels intersociétés de plusieurs sociétés internes. Le calcul PDP/MRP intersociétés s'effectue sur le nombre spécifié d'itérations. Pour permettre à Microsoft Dynamics 365 Supply Chain Management d'effectuer le calcul PDP/MRP intersociétés, vous devez paramétrer le calcul PDP/MRP dans chacune des sociétés intersociétés. Cela requiert plusieurs itérations dans lesquelles Microsoft Dynamics 365 Supply Chain Management crée automatiquement une commande fournisseur intersociétés et entraîne, à son tour, la création automatique d'une commande client intersociétés, engendrant alors de nouvelles demandes.

Vous paramétrez le plan général intersociétés et l'ordre de planification intersociétés dans les paramètres **Planification générale** de chacune des sociétés intersociétés.

Afin de propager la demande dans la chaîne intersociétés, vous devez définir des paramètres assurant que les commandes fournisseur prévisionnelles sont automatiquement confirmées, c'est-à-dire que les commandes ne peuvent pas être modifiées en termes de délai ou de quantité. Configurez le groupe **Plage de gestion de la confirmation** ou **Plage de gestion de la confirmation** dans le plan général. Si aucune **Plage de gestion de la confirmation** n'est paramétrée, aucune commande fournisseur intersociétés n'est créée automatiquement. Seule la première exécution de l'ordonnancement directeur donne lieu à des ordres planifiés. Cependant, étant donné qu'aucune commande fournisseur intersociétés n'est créée, aucune commande client intersociétés n'est créée et, par conséquent, aucune autre commande fournisseur intersociétés n'est créée, et ainsi de suite.

Lorsque vous démarrez le calcul PDP/MRP intersociétés, Microsoft Dynamics 365 Supply Chain Management effectue un calcul PDP/MRP dans chaque société intersociétés, puis effectue un second calcul PDP/MRP dans chaque société intersociétés, etc., jusqu'à ce que le nombre d'itérations spécifié soit atteint. Un maximum de 30 itérations est possible, cependant, plus vous sélectionnez d'itérations, plus le calcul prend du temps.

Vous pouvez démarrer le calcul PDP/MRP intersociétés depuis n'importe quelle société intersociétés car le calcul PDP/MRP dans les sociétés est contrôlé par la séquence de planification intersociétés, c'est-à-dire l'ordre de priorité des calculs PDP/MRP programmé entre chaque société intersociétés. Puisque la séquence de planification intersociétés détermine l'ordre dans lequel le calcul PDP/MRP est effectué dans les sociétés, l'emplacement de début du calcul PDP/MRP intersociétés importe peu. À chaque itération, la société actuelle exécute le dernier.

> [!NOTE]
> La meilleure solution consiste à permettre le lancement du calcul PDP/MRP intersociétés depuis une société Microsoft Dynamics 365 Supply Chain Management unique.

Sur la page **Calcul PDP/MRP intersociétés**, vous pouvez démarrer une suite de calculs PDP/MRP, qui exécute un calcul PDP/MRP la première fois, en suivant le principe de mise à jour du calcul des besoins sélectionné pour la première itération pour toutes les sociétés intersociétés. Les itérations suivantes appliquent le second principe que vous sélectionnez pour l'itération suivante, et ce principe est appliqué jusqu'à ce que le nombre d'itérations spécifié soit atteint.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
