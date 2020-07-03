---
title: Configurer un canal de centre d'appels
description: Cette rubrique décrit comment créer un canal de centre d'appels dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: bdaabad39484cb12537bc5f94c34dcb2575a5b2f
ms.sourcegitcommit: ef27189efc15ce79c3c31ce2e41ef8a606fc5429
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3410411"
---
# <a name="set-up-a-call-center-channel"></a>Configurer un canal de centre d'appels


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer un canal de centre d'appels dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble


Dans Dynamics 365 Commerce, un centre d'appels est un type de canal Commerce qui peut être défini dans l'application. La définition d'un canal pour vos entités de centre d'appels permet au système de lier des données spécifiques et des valeurs par défaut de traitement des commandes aux commandes client. Bien qu'une entreprise puisse définir plusieurs canaux de centre d'appels dans Commerce, il est important de noter qu'un utilisateur individuel ne peut pas être lié à un seul canal de centre d'appels. 

Avant de créer un centre d'appel, assurez-vous d'avoir rempli la [Configuration requise de paramétrage de canaux](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Créer et configurer un centre d'appels

Pour créer et configurer un centre d'appels, procédez comme suit.

1. Dans le volet de navigation, accédez à **Retail et Commerce \> Canaux \> Centres d'appels \> Tous les centres d'appels**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Nom**, fournissez un nom pour le nouveau canal.
1. Sélectionnez l'**Entité juridique** adéquate dans la liste déroulante.
1. Sélectionnez l'emplacement **Entrepôt** adéquat dans la liste déroulante. Cet emplacement sera utilisé par défaut sur les commandes client créées pour ce canal de centre d'appels, sauf si d'autres valeurs par défaut ont été définies au niveau du client ou de l'article.
1. Dans le champ **Client par défaut**, indiquez un client par défaut valide. Ces données sont utilisées pour faciliter le remplissage automatique des valeurs par défaut lors de la création de nouveaux enregistrements client. Lors de la création de commandes de centre d'appels, il n'est pas conseillé de créer des commandes pour le client par défaut.
1. Dans le champ **Profil de notification par e-mail**, fournissez un profil de notification par e-mail valide. Au fur et à mesure que les commandes du centre d'appels sont créées et traitées, le profil de notification par e-mail est utilisé pour déclencher des alertes par e-mail automatiques aux clients avec des informations sur l'état de leur commande.
1. Fournissez un code info **Prix manuel**. Vous devrez peut-être d'abord créer un code info. Ce code info fournit l'ensemble des codes motif que l'utilisateur sera invité à choisir lors de l'utilisation de la fonctionnalité de substitution de prix sur une commande de centre d'appels.
1. Fournissez un code info **Code de blocage**. Vous devrez peut-être d'abord créer un code info. Ce code info fournit l'ensemble des codes motif en option que l'utilisateur sera invité à choisir lors du passage d'une commande en attente.
1. Fournissez un code info **Crédit**. Vous devrez peut-être d'abord créer un code info. Ce code d'information fournit l'ensemble des codes de motif que l'utilisateur peut choisir lors de l'utilisation de la fonctionnalité de crédit de commande du centre d'appels pour donner des remboursements divers au client pour des raisons de service client.
1. En option : configurez les dimensions financières sur le raccourci **Dimensions financières**. Les dimensions saisies ici figureront par défaut sur n'importe quelle commande client créée dans ce canal de centre d'appels.
1. Cliquez sur **Enregistrer**.

L'image suivante montre la création d'un canal de centre d'appels.

![Nouveau canal de centre d'appels](media/channel-setup-callcenter-1.png)

L'image suivante présente un exemple de canal de centre d'appels.

![Exemple de canal de centre d'appels](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Configuration de canal supplémentaire

Les tâches supplémentaires requises pour la configuration du canal de centre d'appels comprennent la configuration des modes de paiement et des modes de livraison.

L'image suivante montre les options de configuration **Modes de livraison** et **Modes de paiement** de l'onglet **Configurer**.

![Actions supplémentaires de configuration de canal de centre d'appels](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>paramétrer les modes de paiement ;

Pour configurer des modes de paiement, pour chaque type de paiement pris en charge sur ce canal, procédez comme suit. Les utilisateurs devront sélectionner des modes de paiement prédéfinis pour les lier au canal du centre d'appels. Avant de configurer vos modes de paiement de centre d'appels, configurez d'abord vos modes de paiement principaux dans **Retail et Commerce \>Configuration des canaux \> Modes de payement \> Modes de payement**.

1. Dans le volet Actions, sélectionnez l'onglet **Configurer**, puis **Modes de paiement**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le volet de navigation, sélectionnez un mode de paiement parmi les paiements prédéfinis disponibles.
1. Configurez tous les autres paramètres requis pour le type de paiement. Pour les cartes de crédit, les cartes-cadeaux ou les cartes de fidélité, une configuration supplémentaire est requise en sélectionnant la fonction **Configuration de la carte**. 
1. Configurez les comptes de validation appropriés pour le type de paiement dans la section **Affectation**.
1. Dans le volet Actions, cliquez sur **Enregistrer**.

L'image suivante présente un exemple de mode de paiement au comptant.

![Exemple de modes de paiement](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a>Paramétrer des modes de livraison

Vous pouvez voir les modes de livraison configurés en sélectionnant **Modes de livraison** dans l'onglet **Paramétrer** du **Volet Actions**.  

Pour modifier ou ajouter un mode de livraison à associer au canal du centre d'appels, procédez comme suit.

1. Dans le formulaire Modes de livraison du centre d'appels, sélectionnez **Gérer les modes de livraison**
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un mode de livraison ou sélectionnez un mode existant.
1. Dans la section **Canaux de vente au détail**, cliquez sur **Ajouter une ligne** pour ajouter le canal du centre d'appels. L'ajout de canaux à l'aide de nœuds d'organisation au lieu d'ajouter chaque canal individuellement peut rationaliser l'ajout de canaux.
1. Assurez-vous que le mode de livraison a été configuré avec des données sur le raccourci **Produits** et le raccourci **Adresses**. Si aucun produit ou aucune adresse de livraison n'est valide pour le mode de livraison, le choisir lors de la saisie de la commande entraînera des erreurs.
1. Une fois que les modifications ont été apportées aux configurations du mode de livraison du centre d'appels, la tâche **Traiter les modes de livraison** doit être exécutée pour faire exploser la matrice de changement. Ce travail peut être trouvé en accédant à **Retail et Commerce \> Retail et Commerce IT \> Traiter les modes de livraison**.

L'image suivante présente un exemple de mode de livraison.

![Paramétrer des modes de livraison](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a>Configurer des utilisateurs de canal

Pour créer une commande client associée au canal du centre d'appels à partir du Commerce Headquarters, l'utilisateur qui crée la commande client doit être lié au canal du centre d'appels. L'utilisateur ne peut pas lier manuellement une commande client créée dans Commerce Headquarters au canal du centre d'appels. Le lien est systématique et est basé sur l'utilisateur et la relation de l'utilisateur avec le canal du centre d'appels. Un utilisateur ne peut être lié qu'à un seul canal du centre d'appels.

1. Dans le volet Actions, sélectionnez l'onglet **Canal**, puis **Utilisateurs du canal**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Choisissez un **Identifiant d'utilisateur** existant dans la liste déroulante de sélection pour lier cet utilisateur au canal du centre d'appels

Une fois la configuration de l'utilisateur du canal effectuée, et lorsque l'utilisateur crée une commande client dans Commerce Headquarters, la commande client sera associée à leur canal du centre d'appels associé. Toutes les configurations de ce canal seront appliquées systématiquement à la commande client. Un utilisateur peut confirmer le canal du centre d'appels auquel la commande client est liée en affichant la référence du nom du canal dans l'en-tête de la commande client.


### <a name="set-up-price-groups"></a>Paramétrer des groupes de prix

Les groupes de prix sont facultatifs, mais s'ils sont utilisés, ils peuvent contrôler les prix de vente qui seront proposés aux clients passant des commandes dans le canal du centre d'appels. Si aucun groupe de prix n'a été configuré pour le client, ou si des groupes de prix de catalogue ne sont pas appliqués à la commande client (à l'aide du champ **ID du code source** dans l'en-tête de commande du centre d'appels), le groupe de prix du canal est utilisé pour localiser les prix des articles. Si aucun groupe de prix n'est trouvé sur le canal du centre d'appels, les prix principaux par défaut des articles sont utilisés. 

Pour configurer un groupe de prix, procédez comme suit.

1. Dans le volet Actions, cliquez sur l'onglet **Canal**, puis sélectionnez **Groupes de prix**.
1. Dans le volet Actions, cliquez sur **Nouveau**.
1. Sélectionnez un **Groupe de prix de détail** dans la liste déroulante de sélection.

## <a name="additional-resources"></a>Ressources supplémentaires

[Conditions préalables à la configuration de canal](channels-prerequisites.md)

[Fonctionnalité de vente du centre d'appels](call-center-functionality.md)

[Configurer des options de traitement de commandes de centre d'appels](set-up-order-processing-options.md)

[Catalogues de centre d'appels](call-center-catalogs.md)

[Paramétrer et utiliser les alertes pour fraude](set-up-fraud-alerts.md)

[Paramétrer des programmes périodiques pour les centres d'appels](set-up-continuity-program.md)
