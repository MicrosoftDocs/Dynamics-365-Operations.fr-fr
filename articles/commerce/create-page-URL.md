---
title: Créer une URL de page
description: Cette rubrique présente les concepts et les procédures fondamentaux pour créer une URL de page sur votre site.
author: bicyclingfool
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 062a49df93e442dbe402ac9a78244c966958aaa2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965251"
---
# <a name="create-a-page-url"></a>Créer une URL de page


[!include [banner](includes/banner.md)]

Cette rubrique présente les concepts et les procédures fondamentaux pour créer une URL de page sur votre site.

## <a name="overview"></a>Vue d'ensemble

L'URL totale, ou absolue, qui désigne une page sur votre site est constituée de pièces distinctes. Par exemple, l'URL `https://www.contoso.com/en-us/contactus` a les éléments suivants :

- `https://www.contoso.com` – Le protocole HTTP et le domaine du site.
- `/en-us` – Le chemin de la langue du site.
- `/contactus` – L'URL relative de la page **Nous contacter**. Une URL relative est également appelée *slug* URL.

Vous établissez le domaine du site et le chemin d'accès facultatif de la langue lorsque vous paramétrez le site. Vous pouvez ajouter des chemins de domaines et de langue à votre site via la page de magasins en ligne dans les paramètres du site.

Le slug URL pour une page existe comme entité autonome dans le site de création de l'environnement. Une URL de page est composé de deux parties : un nom qui représente le slug URL, et un pointeur vers une page sur votre site ou un site externe. Une URL de page peut également être configurée pour servir de redirection vers une autre page sur votre site ou un site externe.

## <a name="create-a-page-url"></a>Créer une URL de page

Il existe deux façons de créer des URL de la page :

- Automatiquement, lorsque vous créez une page
- Manuellement, dans la page **URL**

### <a name="create-a-page-url-when-you-create-a-page"></a>Créer une URL de page lorsque vous créez une page

Si vous fournissez un nom dans le champ **URL** lorsque vous créez une page, une URL de page qui indique cette page est automatiquement créée dans la page **URL**. Une fois publié l'URL et la page vers laquelle elle pointe, les utilisateurs de sites (vos clients) peuvent accéder à la page associée à l'URL.

> [!NOTE]
> Si vous publiez une URL sans publier la page vers laquelle elle pointe, les utilisateurs de site reçoivent une erreur 404 lorsqu'ils essayent d'accéder à la page. Si vous publiez une page sans publier l'URL pour pointer vers celle-ci, la page ne peut pas accéder à l'aide d'une URL.

### <a name="manually-create-a-page-url"></a>Créer manuellement une URL de page

Lorsque vous créez des pages, vous n'êtes pas obligé de spécifier une URL de la page. Si vous laissez le champ vide URL, la page est créée dans un état dissocié. Dans ce cas, les clients ne peuvent pas accéder à la page, même si elle est publiée. Pour rendre la page accessible, vous devez créer manuellement l'URL et la lier à la page.

Pour créer manuellement l'URL de page pour une page, procédez comme suit.

1. Dans la page **URL**, sélectionnez **Nouveau**.
1. Sélectionnez la page du site à associer à l'URL.
1. Entrez le slug URL, puis sélectionnez **OK**.

À ce stade, l'URL est dans un état de brouillon. Elle doit être publiée avant que les utilisateurs de site puissent accéder à la page associée.

## <a name="update-a-page-url"></a>Mettre à jour une URL de page

Pour mettre à jour la page cible d'une URL de page, procédez comme suit.

1. Dans la page **URL**, sélectionnez l'URL à mettre à jour.
1. Dans le volet de propriétés à droite, sélectionnez le bouton représentant des points de suspension (**...**) en regard de le champ cible de page.
1. Dans la boîte de dialogue, sélectionnez une autre page, puis sélectionnez **OK**.
1. Enregistrez et publiez l'URL.

## <a name="redirect-a-page-url"></a>Rediriger une URL de page

Parfois, vous pouvez vouloir que vos clients affichent une autre page lorsqu'ils demandent une URL spécifique. Dans ces cas, la meilleure approche, et la plus simple, est souvent de modifier la page vers laquelle l'URL pointe. Toutefois, vous pouvez avoir des motifs légitimes pour l'utilisation de redirections HTTP 301 ou 3023 pour rediriger les demandes d'URL vers une URL différent.

Pour rediriger une URL vers une URL différent, procédez comme suit.

1. Dans la page **URL**, sélectionnez l'URL à mettre à jour.
1. Dans le volet de propriétés de droite, sélectionnez **Redirigez**.
1. Sélectionnez une destination pour la redirection :

    - Pour pointer vers une autre page sur votre site, sélectionnez **URL interne**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez l'URL pour rediriger sur.
    - Pour pointer vers une page sur un site externe, sélectionnez **URL externe**, puis entrez l'URL complète de cette page. Veillez à inclure le protocole. Par exemple, entrez `https://domain.com/new/page`. Si l'URL redirige déjà vers une URL interne, vous devez sélectionner **Effacer la sélection** avant de pouvoir entrer une URL externe.

1. Sélectionner un type de redirection :

    - **Redirection permanente (301)** – Sélectionnez cette option si vous savez que votre contenu se déplacera en permanence et ne rétablira pas son URL précédent. Les moteurs de recherche affecteront la valeur de l'optimisation du moteur de recherche (SEO) de l'URL de redirection à l'URL vers laquelle elle est redirigée et mettront à jour leur enregistrement pour afficher la nouvelle URL. 
    - **Redirection provisoire (302)** – Sélectionnez cette option pour rediriger le trafic sans mettre à jour les moteurs de recherche. Cette méthode est généralement utilisée si le contenu reviendra bientôt à son URL précédent.

1. Lorsque vous êtes prêt à implémenter la redirection, enregistrez et publiez l'URL.

## <a name="additional-resources"></a>Ressources supplémentaires

[Personnaliser la navigation dans le site](customize-site-navigation.md)

[Ajouter une nouvelle page de site](add-new-page.md)

[Configuration du nom de domaine](configure-your-domain-name.md)

[Ajouter des langues à votre site](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]