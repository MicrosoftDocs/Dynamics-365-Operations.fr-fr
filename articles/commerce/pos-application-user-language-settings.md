---
title: Paramètres de la langue de l’utilisateur et de l'application Point de vente (PDV)
description: Cet article décrit la modification des paramètres de langue dans Modern POS (MPOS) et Cloud POS.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.industry: Retail
ms.search.form: HcmWorker, RetailStoreTable
ms.openlocfilehash: 663e9a3558bd4d0556644fe5ad6f7f832a18ded5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288377"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a>Paramètres de la langue de l’utilisateur et de l'application Point de vente (PDV)

[!include [banner](includes/banner.md)]

Cet article décrit la modification des paramètres de langue dans Modern POS (MPOS) et Cloud POS.

## <a name="overview"></a>Vue d’ensemble
Modern POS (MPOS) et Cloud POS prennent en charge les environnements dans lesquels les paramètres de langue et les traductions peuvent varier entre le magasin et les paramètres utilisateur. Par exemple, le magasin peut être situé dans une région où l’anglais est la langue la plus parlée par les clients, mais certains collaborateurs préfèrent utiliser l’application avec des traductions françaises.

## <a name="data-language"></a>Langue des données

Quels que soient les paramètres de l’utilisateur, MPOS et Cloud POS emploieront toujours les paramètres de langue des magasins pour déterminer les traductions utilisées pour les données. Cela permet d’assurer à tous les utilisateurs et les clients une expérience cohérente. Les exemples de données sont les suivants :

- Produits
- Attributs et valeurs
- Noms de catégorie
- Reçus de transaction imprimés ou envoyés par courrier électronique
- Noms de mode de paiement
- Messages d’affichage de ligne

La langue du magasin est également utilisée pour l’écran de connexion principal du PDV, puisque l’utilisateur n’est pas connu avant de se connecter. Si une traduction dans la langue du magasin n’est pas disponible, le PDV reviendra à la langue de la société.

### <a name="configuring-the-stores-language-setting"></a>Configuration du paramètre de langue du magasin

Le paramètre de langue du magasin est défini à partir de **Tous les magasins** dans la page **Magasin** sous **Général &gt; Paramètres régionaux &gt; Langue**. Utilisez la liste déroulante pour choisir la langue de chaque magasin.

## <a name="user-interface-language"></a>Langue de l’interface utilisateur

Le paramètre de langue de l’utilisateur du PDV détermine les traductions utilisées dans l’interface utilisateur de l’application. Cela inclut tous les noms, menus et listes qui ne sont pas considérés comme des données. Une exception est le texte affiché dans les groupes de boutons du PDV. Elles ne prennent pas en charge les traductions, donc elles affichent toujours le texte tel que défini sous le bouton. Afin de prendre en charge les boutons traduits, vous devez copier et conserver des grilles de bouton distinctes et les affecter aux utilisateurs concernés.

### <a name="configuring-the-users-language-setting"></a>Configuration du paramètre de langue de l’utilisateur

Le paramètre de langue de l’utilisateur du PDV est défini à partir de **Tous les collaborateurs** dans la page **Collaborateur** sous **Retail et Commerce &gt; Langue**. Il n’est pas défini dans l’onglet principal Profil. Ce paramètre n’est pas utilisé par le PDV. Si la langue de l’utilisateur n’est pas définie ou si elle est définie sur une langue dans laquelle les traductions ne sont pas disponibles, le PDV reviendra à la langue du magasin.

| &nbsp;      | Langue de l’interface utilisateur                | Langue des données (produits, formats d’accusé de réception, vue de ligne, etc.). |
|-------------|----------------------------|---------------------------------------------------------------|
| **Société** | Valeur par défaut                    | Valeur par défaut                                                       |
| **Magasin**   | Remplace la société          | Remplace la société                                             |
| **Utilisateur**    | Remplace le magasin ou la société | Jamais                                                         |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
