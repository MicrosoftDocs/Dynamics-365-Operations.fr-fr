---
title: Activer la recherche de commande pour les caisses d'invité
description: Cette rubrique explique comment activer la recherche de commande pour les caisses d'invité dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 0368f567898210f122047a9f298bcb28b7540de1
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472608"
---
# <a name="enable-order-lookup-for-guest-checkouts"></a>Activer la recherche de commande pour les caisses d'invité

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique explique comment activer la recherche de commande pour les caisses d'invité dans Microsoft Dynamics 365 Commerce.

La fonction de recherche de commande pour les caisses d'invité permet aux clients qui effectuent des achats en tant qu'utilisateurs invités de rechercher leurs commandes. La fonctionnalité de recherche de commande est utile lorsque les clients souhaitent effectuer des actions telles que vérifier le statut d'exécution des produits d'une commande, vérifier l'adresse à laquelle une commande a été expédiée, commander à nouveau un produit ou confirmer le magasin dans lequel leur commande sera récupérée.

Les clients qui passent des commandes en tant qu'utilisateurs enregistrés peuvent voir les détails de leur commande lorsqu'ils sont connectés, mais les clients qui utilisent la caisse d'invité pour passer des commandes ne le peuvent pas. Cependant, lorsque la fonction de recherche de commande pour les caisses d'invité est activée, elle fournit un formulaire que les clients peuvent utiliser pour rechercher les commandes qu'ils ont passées en tant qu'invités. Dans ce formulaire, les clients entrent l'ID de confirmation de commande et (éventuellement) l'adresse e-mail qu'ils ont spécifiée lors du paiement.

De plus, un lien ou un bouton qui amène le client directement à la page des détails de sa commande peut être inclus dans tous les e-mails transactionnels liés à la commande. Ce lien ou bouton fonctionnera pour les commandes passées à la fois par des utilisateurs enregistrés et par des utilisateurs invités.

## <a name="turn-on-necessary-features-in-commerce-headquarters"></a>Activer les fonctionnalités nécessaires dans Commerce Headquarters

Pour activer la recherche de commande pour les caisses d'invité, vous devez activer les fonctionnalités suivantes dans **Espaces de travail\> Gestion des fonctionnalités** dans Commerce Headquarters.

| Fonctionnalité | Objectif |
|---------|---------|
| Fonctionnalité de choix des détails de la commande de recherche d’utilisateur anonyme de Retail | Cette fonctionnalité expose l'interface utilisateur dans les paramètres Commerce qui vous permet d'activer l'API de recherche de commande pour les utilisateurs non authentifiés et de configurer l'affichage des données personnelles. |
| Activer la génération d’un ID référence de canal plus fort | Cette fonctionnalité génère un ID de référence de canal à 12 caractères plus sécurisé (ID de confirmation de commande) qui peut être transmis dans la chaîne de requête lors de la recherche d'une commande. |
| Générer un format d’ID référence de canal cohérent sur les canaux | Cette fonctionnalité génère un identifiant de référence de canal sécurisé pour les commandes passées via un site de commerce électronique, le point de vente au détail (PDV) ou un centre d'appels. Avant de pouvoir activer cette fonction, la fonction **Activer la génération d'un ID de référence de canal plus fort** doit être activée. |

Après avoir activé la **Fonctionnalité d'option des détails de la commande pour une recherche par un utilisateur anonyme dans Retail**, vous devez activer l'API qui prend en charge la recherche de commandes non authentifiées dans Commerce Headquarters. Accédez à **Retail et Commerce \> Configuration Headquarters \> Paramètres \> Commandes client**. Sur la page **Commandes clients**, dans le raccourci **Recherche de commande**, définissez l'option **Activer la recherche de commande non authentifiée** sur **Oui**, comme le montre l'illustration suivante.

## <a name="manage-the-display-of-personal-data"></a>Gérer l'affichage des données personnelles

Le raccourci **Recherche de commande** de la page **Commandes client** de Commerce Headquarters comprend un champ **Inclure les données personnelles dans la recherche de commande d'invité**, qui vous permet de contrôler si les informations personnelles sont présentées aux clients. Ces informations personnelles comprennent l'adresse de livraison du client et les quatre derniers chiffres du numéro de carte de crédit du client. Par défaut, les informations personnelles ne sont pas présentées aux clients lorsque la recherche de commande non authentifiée est activée. Le tableau ci-dessous décrit les options disponibles.

| Option | Résultat |
|--------|--------|
| Jamais | Valeur par défaut. Aucune information personnelle n'est affichée dans les recherches de commandes. Lorsque les utilisateurs enregistrés qui sont connectés recherchent une commande qu'ils ont créée alors qu'ils étaient connectés, ils pourront voir leurs informations personnelles. |
| Commandes d’invité uniquement | Les informations personnelles sont affichées dans les recherches de commandes pour les commandes que les clients ont créées en tant qu'invités. Si une commande a été créée par un utilisateur enregistré, cet utilisateur doit se connecter pour voir ses informations personnelles. |
| Toutes les commandes | Les informations personnelles s'affichent dans toutes les recherches de commandes. |

> [!NOTE]
> Ces options déterminent quand les données personnelles, telles que l'adresse du client et les quatre derniers chiffres du numéro de carte de crédit du client, sont affichées aux utilisateurs invités anonymes. Pour aider à protéger la confidentialité des clients enregistrés, nous vous recommandons de sélectionner l'option **Commandes d'invités uniquement**. Cependant, l'option la plus sûre est **Jamais**.

Après avoir modifié la valeur du champ **Inclure les données personnelles dans la recherche de commande d'invité**, vous devez exécuter la tâche 1070 (**Configuration des canaux**) dans Commerce Headquarters en vous rendant sur **Retail et Commerce \> IT Retail et Commerce \> Programme de distribution**.

## <a name="configure-the-order-lookup-module"></a>Configurer le module de recherche de commande

Le module de recherche de commandes dans la bibliothèque de modules Commerce sert à afficher le formulaire que les utilisateurs invités utilisent pour rechercher des commandes. Le module de recherche de commande peut être inclus dans l'emplacement du corps de n'importe quelle page qui ne nécessite pas de connexion client. Pour plus d'informations sur la configuration du module, voir [Module de recherche de commande](order-lookup-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Module de recherche de commande](order-lookup-module.md)

[Configurer un profil de notification par e-mail](email-notification-profiles.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
