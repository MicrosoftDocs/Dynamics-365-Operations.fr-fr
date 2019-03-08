---
title: Paramètres de langue et d'utilisateur de l'application Point of sale (POS)
description: Cette rubrique décrit la modification des paramètres de langue dans Retail Modern POS (MPOS) et Cloud POS.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: faf8cdcee70b55842072298b51789f6cd7a577af
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "336748"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a>Paramètres de langue et d'utilisateur de l'application Point of sale (POS)

[!include [banner](includes/banner.md)]

Cette rubrique décrit la modification des paramètres de langue dans Retail Modern POS (MPOS) et Cloud POS.

## <a name="overview"></a>Présentation

Retail Modern POS (MPOS) et Cloud POS prennent en charge les environnements dans lesquels les paramètres de langue et les traductions peuvent varier entre le magasin et les paramètres d'utilisateur. Par exemple, le magasin peut être situé dans une région où l'anglais est la langue la plus parlée par les clients, mais certains collaborateurs préfèrent utiliser l'application avec des traductions françaises.

## <a name="data-language"></a>Langue des données

Quels que soient les paramètres de l'utilisateur, MPOS et Cloud POS emploieront toujours les paramètres de langue des magasins pour déterminer les traductions utilisées pour les données. Cela permet d'assurer à tous les utilisateurs et les clients une expérience cohérente. Les exemples de données sont les suivants :

- Produits
- Attributs et valeurs
- Noms de catégorie
- Reçus de transaction imprimés ou envoyés par courrier électronique
- Noms de mode de paiement
- Messages d'affichage de ligne

La langue du magasin est également utilisée pour l'écran de connexion principal du PDV, puisque l'utilisateur n'est pas connu avant de se connecter. Si une traduction dans la langue du magasin n'est pas disponible, le PDV reviendra à la langue de la société.

### <a name="configuring-the-stores-language-setting"></a>Configuration du paramètre de langue du magasin

Le paramètre de langue du magasin est défini à partir de **Tous les magasins de vente au détail** sur la page **Magasin de vente au détail** sous **Général &gt; Paramètres régionaux &gt; Langue**. Utilisez le menu déroulant pour choisir la langue de chaque magasin.

## <a name="user-interface-language"></a>Langue de l'interface utilisateur

Le paramètre de langue de l'utilisateur du PDV détermine les traductions utilisées dans l'interface utilisateur de l'application. Cela inclut tous les noms, menus et listes qui ne sont pas considérés comme des données. Une exception est le texte affiché dans les groupes de boutons du PDV. Elles ne prennent pas en charge les traductions, donc elles affichent toujours le texte tel que défini sous le bouton. Afin de prendre en charge les boutons traduits, vous devez copier et conserver des grilles de bouton distinctes et les affecter aux utilisateurs concernés.

### <a name="configuring-the-users-language-setting"></a>Configuration du paramètre de langue de l'utilisateur

Le paramètre de langue de l'utilisateur du PDV est défini à partir de **Tous les collaborateurs** dans la page **Collaborateur** sous **Vente au détail &gt; Langue**. Il n'est pas défini dans l'onglet principal Profil. Ce paramètre n'est pas utilisé par le PDV. Si la langue de l'utilisateur n'est pas définie ou si elle est définie sur une langue dans laquelle les traductions ne sont pas disponibles, le PDV reviendra à la langue du magasin.

|             | Langue de l'interface utilisateur                | Langue des données (produits, formats d'accusé de réception, vue de ligne, etc.). |
|-------------|----------------------------|---------------------------------------------------------------|
| **Société** | Valeur par défaut                    | Valeur par défaut                                                       |
| **Magasin**   | Remplace la société          | Remplace la société                                             |
| **Utilisateur**    | Remplace le magasin ou la société | Jamais                                                         |
