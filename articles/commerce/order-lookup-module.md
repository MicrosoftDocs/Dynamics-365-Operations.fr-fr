---
title: Module de recherche de commande
description: Cette rubrique couvre le module Recherche de commande et explique comment le configurer dans Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: fa61a20ffd9a31f800c48b71832be7547952119f
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472607"
---
# <a name="order-lookup-module"></a>Module de recherche de commande

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique couvre le module Recherche de commande et explique comment le configurer dans Microsoft Dynamics 365 Commerce.

Le module de recherche de commande fournit un formulaire que les clients peuvent utiliser pour rechercher des commandes qu'ils ont passées sur un site de commerce électronique. Il est utilisé dans le cadre de la fonction [Activer la recherche de commande pour les caisses d'invité](order-lookup-guest.md). Le module de recherche de commande peut être utilisé pour rechercher des commandes qui ont été soumises via un site de commerce électronique, un point de vente au détail (PDV) ou un centre d'appels. Le formulaire peut récupérer les commandes qui ont été soumises à la fois par les utilisateurs invités et par les utilisateurs enregistrés.

L'illustration suivante montre un exemple du formulaire rendu par le module de recherche de commande. Lorsque les clients remplissent le formulaire et sélectionnent **Rechercher votre commande**, ils sont redirigés vers la page des détails de la commande.

![Formulaire pour le module de recherche de commande sur une page.](./media/OrderLookup_module.PNG)

## <a name="order-lookup-module-properties"></a>Propriétés du module de recherche de commande

| Nom de la propriété     | Valeur     | Description |
|-------------------|-----------|-------------|
| Titre           | Détails      | L'en-tête qui apparaît en haut du formulaire (par exemple, « Rechercher votre commande »). |
| Texte enrichi         | Texte enrichi | Texte explicatif facultatif qui apparaît sous le titre. |
| Type de statut de commande | Énumération      | <p>Sélectionnez le type d'informations que le formulaire demandera au client en plus de l'ID de confirmation de commande. Les valeurs suivantes sont actuellement prises en charge :</p><ul><li><b>E-mail</b> : le formulaire comprendra un champ où les clients pourront saisir l'adresse e-mail qu'ils ont utilisée lors de la commande.</li><li><b>Aucun</b> : le formulaire ne demandera aucune information autre que l'ID de confirmation de commande.</li></ul> |

## <a name="add-an-order-lookup-module-to-a-page"></a>Ajouter un module de recherche de commande à une page

Le module de recherche de commande peut être ajouté au corps de n'importe quelle page de votre site de commerce électronique. Si vous souhaitez utiliser le module de recherche de commande pour activer la recherche de commande pour les caisses d'invité, assurez-vous de l'ajouter à une page qui ne nécessite pas que l'utilisateur soit connecté. Pour trouver le paramètre **Connexion requise ?** d'une page dans l'arborescence du générateur de site de Commerce, sélectionnez l'emplacement **Page par défaut (obligatoire)** et regardez en bas du volet de droite.

## <a name="additional-resources"></a>Ressources supplémentaires

[Activer la recherche de commande pour les caisses d'invité](order-lookup-guest.md)

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]