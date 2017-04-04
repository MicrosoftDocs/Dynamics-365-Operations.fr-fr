---
title: "Paramètres de langue d&quot;application et d&quot;utilisateur de PDV"
description: "Cette rubrique décrit la procédure de modification des paramètres de langue dans POS du Retail Modern POS (MPOS) et du cloud."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf5b75572529bb497d3079752de187f30aa59294
ms.lasthandoff: 03/31/2017


---

# <a name="pos-application-and-user-language-settings"></a>Paramètres de langue d'application et d'utilisateur de PDV

Cette rubrique décrit la procédure de modification des paramètres de langue dans POS du Retail Modern POS (MPOS) et du cloud.

<a name="overview"></a>Vue d'ensemble
========

Environnements de support POS du Retail Modern POS (MPOS) et du cloud où les paramètres et les traductions de langues peuvent varier entre le magasin et les paramètres utilisateur. Par exemple, le magasin peut être situé dans région où l'anglais est le plus courant pour ses clients, mais certains travailleurs préfèrent pour utiliser l'application avec les traductions française.

## <a name="data-language"></a>Langue des données
Quels que soient les paramètres de l'utilisateur, MPOS et PDV de cloud emploieront toujours les paramètres de langue du magasin pour déterminer les traductions utilisées pour les données. Cela garantira que tous les utilisateurs et clients ont une expérience cohérente.  Exemples de données comprennent :

-   Produits
-   Attributs et valeurs
-   Noms de catégorie
-   Reçus de transaction imprimés ou envoyés par courrier électronique
-   Noms de mode de paiement
-   Messages d'affichage de ligne

Langue du magasin est également utilisée pour l'écran principal de connexion du PDV, car l'utilisateur n'est pas connu avant de se connecter. Si une traduction n'est pas disponible pour la langue du magasin, le POS rétablira à celle de la société.

### <a name="configuring-the-stores-language-setting"></a>Configuration du paramètre de langue du magasin

La définition de la langue du magasin est défini dans ** tous les magasins de vente au détail ** sur ** magasin de vente au détail ** FRx sous ** la langue &gt; régionale générale &gt; des paramètres. ** La déroulante pour sélectionner la langue pour chaque magasin.

## <a name="user-interface-language"></a>Langue de l'interface utilisateur
Le paramètre de celle de l'utilisateur POS détermine les traductions utilisées dans l'interface utilisateur de l'application. Notamment tous les libellés, menus, et listes qui ne sont pas considérées comme des données. Une exception est le texte affiché dans les groupes de boutons du PDV. Les groupes de boutons ne prennent pas en charge les traductions, afin qu'ils toujours le texte tel que défini sous le bouton. Afin de prendre en charge est traduit les boutons, vous devez copier et de tenir à jour les groupes de boutons distincts et les affecter aux utilisateurs appropriés.

### <a name="configuring-the-users-language-setting"></a>Configuration du paramètre de langue de l'utilisateur

Le paramètre de celle de l'utilisateur POS est défini dans ** tous les travailleurs ** sur ** travailleur ** la page sous ** langue &gt; au détail **.  Il n'est pas défini sous l'onglet principal de profil.  Ce paramètre n'est pas utilisée par PDV. Si la langue de l'utilisateur n'est pas définie ou si elle est définie sur une langue dans laquelle les traductions ne sont pas disponibles, le PDV reviendra à la langue du magasin.  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| ** **       | ** Langue du IU ** ** **      | **Langue des données (produits, formats d'accusé de réception, vue de ligne, etc.).** |
| **Société** | Valeur par défaut                    | Valeur par défaut                                                           |
| **Magasin**   | Remplace la société          | Remplace la société                                                 |
| **User**    | Remplace le magasin ou la société | Jamais                                                             |




