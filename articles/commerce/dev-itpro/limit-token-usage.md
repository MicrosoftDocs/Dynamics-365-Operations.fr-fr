---
title: Limiter l’utilisation des jetons de paiement
description: Cet article décrit la fonctionnalité qui limite l’utilisation des jetons de paiement dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/20/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 8092ab0724f33f21759aa84d25e0bdcb5b2ad5dd
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709654"
---
# <a name="limit-payment-token-usage"></a>Limiter l’utilisation des jetons de paiement

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cet article décrit la fonctionnalité qui limite l’utilisation des jetons de paiement dans Microsoft Dynamics 365 Commerce. L’utilisation du jeton est limitée à la portée d’une commande client ou, si le consentement du client est accordé, le jeton est stocké sous forme de carte dans le fichier.

## <a name="key-terms"></a>Termes clés

| Terme | Description |
|---|---|
| Jeton | Un blob XML référencé dans le système Dynamics 365 qui stocke les références de paiement à des fins transactionnelles. |
| Carte du fichier | Jeton de référence de carte enregistré dont l’utilisation est prévue ultérieurement dans le système Dynamics 365 ou la passerelle de paiement, et qui est spécifique au compte d’un client. |

Les limites d’utilisation des jetons de paiement s’appliquent à tout environnement qui utilise un service de passerelle de paiement où des jetons récurrents sont utilisés. Le [Connecteur de paiement Dynamics 365 pour Adyen](adyen-connector.md) prêt à l’emploi utilise des jetons de paiement récurrents pour effectuer des actions de commande ultérieures, telles que des ajustements d’autorisation et des réautorisations.

Pour faciliter le contrôle de la façon dont ces jetons de paiement récurrents sont utilisés dans tout le système, la limite **Restreindre l’utilisation du jeton de paiement au contexte de la commande** restreint l’utilisation d’un jeton récurrent à la portée d’une commande client dans le système. Lorsqu’elle est activée, cette fonctionnalité modifie l’interface utilisateur (UI) de Commerce headquarters en mettant à jour les pages d’entrée de paiement et en limitant la possibilité de sélectionner des références de paiement client antérieures à utiliser dans de nouvelles instances de transaction.

Cette fonctionnalité permet de respecter les règles d’utilisation de certains émetteurs de paiement tels que Visa. Dans ses [Règles de base de Visa et règles relatives aux produits et services Visa](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf), Visa précise que l’utilisation des jetons de paiement doit être limitée à la portée d’une transaction, sauf accord contraire du détenteur de la carte.

La fonctionnalité **Restreindre l’utilisation du jeton de paiement au contexte de la commande** n’est pertinente que si vous utilisez un service de passerelle de paiement qui se sert des références de jeton de paiement récurrentes.

## <a name="enable-the-feature"></a>Activer la fonctionnalité

Pour activer la fonctionnalité **Restreindre l’utilisation du jeton de paiement au contexte de la commande**, dans Commerce headquarters pour votre environnement, accédez à **Espaces de travail \> Gestion des fonctionnalités**, recherchez et sélectionnez **Restreindre l’utilisation du jeton de paiement au contexte de la commande** dans la liste, puis sélectionnez **Activer maintenant**.

## <a name="limit-payment-token-usage"></a>Limiter l’utilisation des jetons de paiement

Lorsque cette fonctionnalité est activée, les pages de Commerce headquarters utilisées pour la capture des modes de paiement mettent à jour la manière dont elles référencent les modes de paiement enregistrés pour le client. Cette mise à jour affectera principalement deux domaines de fonctionnement :

- La façon dont une fiche client enregistrée est entrée au nom d’un client
- La façon dont les informations de paiement d’un client sont stockées pour les futures entrées de paiement de commande client

Lorsqu’un client effectue une transaction via les canaux de Commerce, les détails de paiement sont stockés avec un contexte de commande client. Le contexte de la commande client limite le jeton de paiement afin qu’il ne soit pas utilisé comme référence de paiement par rapport à l’enregistrement client sur les pages de paiement pour les paiements de commande client nouveaux ou modifiés dans Commerce headquarters.

### <a name="payment-form-changes"></a>Modifications du formulaire de paiement

Lorsqu’un utilisateur du centre d’appels ou de Commerce headquarters accepte un paiement pour un client par rapport à une commande client, la page de paiement présente les détails de la sélection du mode de paiement. Lorsque la fonctionnalité **Restreindre l’utilisation du jeton de paiement au contexte de la commande** est activée, si un utilisateur sélectionne le signe plus (**+**) sur la page de paiement, seuls les enregistrements de « carte dans le fichier » sont affichés. Les modifications exigent que l’utilisateur du centre d’appels ou de Commerce headquarters entre les détails de paiement complets que le client a fournis lorsqu’il a rempli la page **Entrer les informations relatives au paiement client** pour la nouvelle transaction de commande client.

La liste des valeurs pour le champ **Numéro** inclut uniquement les références de carte associées au client qui dont la carte est dans le fichier. Elle filtre toutes les références de paiement passées qui ne sont pas liées à une commande client.

Le signe plus (**+**) sous le champ **Numéro** reste disponible et peut être utilisé pour saisir les informations de paiement fournies par le client pour la transaction associée à la commande client en cours de traitement.

### <a name="how-cards-on-file-work"></a>Fonctionnement des cartes dans le fichier

Quand la fonctionnalité **Restreindre l’utilisation du jeton de paiement au contexte de la commande** est activée, une carte du fichier est un jeton de paiement récurrent qui est enregistré dans un enregistrement client et qui n’est pas limité à la portée d’une commande client. Une carte du fichier permet une référence rapide pour les utilisateurs de Commerce headquarters lorsqu’ils remplissent la page de paiement pour un nouveau paiement de commande client. Cette référence de jeton s’applique uniquement à l’environnement Dynamics 365. Pour les canaux en ligne qui utilisent un service de passerelle de paiement permettant aux utilisateurs d’enregistrer un mode de paiement pour une utilisation future dans le module iFrame de paiement, la passerelle de paiement stocke en toute sécurité ces références en tant que référence distincte à la carte Dynamics 365 dans le fichier.

Par exemple, si le Connecteur de paiement Dynamics 365 Commerce pour Adyen est utilisé dans un canal en ligne, les clients qui entrent leurs informations de carte de crédit dans le module iFrame de paiement ne voient que les références de cartes enregistrées du service de passerelle pour leur prochain achat en ligne lorsqu’ils ont été authentifiés. Ils ne voient pas la carte stockée dans le fichier de l’environnement Dynamics 365 comme une option dans le module iFrame de paiement. De la même manière, lorsque les acheteurs passent une commande via le centre d’appels, leurs références de carte enregistrées en ligne ne sont pas présentées comme des options à l’utilisateur du centre d’appels. L’utilisateur du centre d’appels ne voit que la carte précédente sur les références de fichiers du système Dynamics 365 (comme convenu par le client) à enregistrer pour les commandes futures.

Les utilisateurs de Commerce headquarters peuvent enregistrer une carte dans le fichier pour un client en accédant à **Vente au détail et commerce \> Clients** et en sélectionnant l’enregistrement de compte client. Dans la section **Client \> Configurer**, les utilisateurs disposant d’autorisations pour traiter les pages de paiement peuvent utiliser la page **Cartes de crédit** pour entrer une carte de paiement qui sera stockée dans le fichier pour des transactions futures. Cette opération permet de gagner du temps lors du traitement des futurs paiements de commandes pour le client. Les utilisateurs du centre d’appels et de Commerce headquarters ne doivent entrer la carte dans les détails des cartes du fichier que si le client accepte d’utiliser la référence de la carte pour des transactions futures.

Une case à cocher **Enregistrer pour une utilisation future** située en bas des pages de paiement de Commerce headquarters permet aux utilisateurs d’enregistrer la carte dans un fichier pour une utilisation future. Cette case à cocher ne doit être utilisée que si le client accepte d’utiliser la carte du fichier pour de futures transactions. Vous pouvez afficher ou restreindre la case à cocher **Enregistrer pour une utilisation future** en utilisant l’option **Autoriser la carte client du fichier** dans l’onglet **Paiement** de la page **Paramètres du centre d’appels** de Commerce headquarters. Lorsque cette option est définie sur **Oui**, les utilisateurs de Commerce headquarters autorisés à traiter les pages de paiement peuvent enregistrer une carte dans un fichier à l’aide de la case à cocher **Enregistrer pour une utilisation future**. Lorsque cette option est définie sur **Non**, la case à cocher n’est pas disponible pour les utilisateurs de Commerce headquarters qui sont autorisés à traiter les pages de paiement. L’option **Autoriser la carte client du fichier** peut être utilisée si votre société souhaite restreindre l’utilisation de jetons récurrents dans Commerce headquarters, mais qu’elle ne souhaite pas encore autoriser l’enregistrement d’une carte dans le fichier sans procédure pour garantir que le consentement du client est accordé.

### <a name="commerce-headquarters-pages-where-the-recurring-token-restrictions-are-enforced"></a>Pages de Commerce headquarters où les restrictions de jeton récurrentes sont appliquées

L’étendue de la restriction des jetons affecte les zones suivantes de Commerce headquarters lorsque la fonctionnalité est activée :

- Informations de paiement du client sur **Commande client \> Paiements \> Entrer le paiement client**
- Commandes périodiques
- Paiements échelonnés
- Paiements par carte de crédit de la comptabilité client

### <a name="manage-payment-tokens-archiving-or-removal"></a>Gérer les jetons de paiement (archivage ou suppression)

Les jetons de paiement créés avant l’activation de l’indicateur de fonctionnalité **Restreindre l’utilisation du jeton de paiement au contexte de la commande** (ou pendant que la fonctionnalité était désactivée) resteront « hors de portée » dans le système et peuvent être référencés dans les listes de sélection sur la page de paiement de Commerce headquarters. Ces jetons peuvent être supprimés régulièrement de deux manières dans Commerce headquarters :

- Utilisez la page **Archiver les données de transaction par carte de crédit** pour mettre en place une tâche qui purge ou archive régulièrement les jetons de paiement. Si vous définissez l’option **Supprimer des données sans archiver** sur **Oui**, les jetons qui correspondent au paramètre **Âge minimal des transactions (en jours)** seront supprimés. Pour plus d’informations, voir [Archiver les données de transaction de carte de crédit](archive-cc-data.md).
- Utilisez la nouvelle page **Purger les jetons de carte de crédit** (**Comptabilité client \> Demandes et rapports \> Nettoyer \> Purger les jetons de carte de crédit**), qui vous permet d’exécuter ou de configurer une tâche par lots afin de supprimer les jetons de paiement. Définissez les paramètres suivants :

    - La valeur **Âge minimal des jetons en jours** doit être de 90 jours ou plus.
    - Les paramètres **Exécuter en arrière-plan** peuvent être utilisés pour définir les paramètres **Récurrence** ou **Alertes**.
    - Un groupe de lots peut être affecté pour exécuter la tâche d’un groupe spécifique.
    - Si l’option **Privé** est définie sur **Oui**, seul l’utilisateur qui crée la tâche peut l’exécuter.
    - Le paramètre **Oui** pour l’option **Tâche critique** permet de s’assurer que le système suit activement le statut de la tâche.

Les jetons supprimés ne peuvent pas être récupérés. Définissez le champ **Âge minimal des jetons en jours** sur une plage qui convient à la durée de vie transactionnelle la plus longue de votre environnement (de l’autorisation à la capture ou au remboursement).

## <a name="additional-resources"></a>Ressources supplémentaires

[FAQ Paiements](payments-retail.md)

[Module Validation](../add-checkout-module.md)

[Module Paiement](../payment-module.md)
