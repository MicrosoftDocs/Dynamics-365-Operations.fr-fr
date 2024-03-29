---
title: Paramétrer un canal de vente au détail
description: Cet article décrit comment créer un canal de vente au détail dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 96723f24f879b38f0582f5f321e03624151117af
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276344"
---
# <a name="set-up-a-retail-channel"></a>Configurer un canal de vente au détail

[!include [banner](includes/banner.md)]

Cet article décrit comment créer un canal de vente au détail dans Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce prend en charge plusieurs canaux de vente au détail. Ces canaux de vente au détail comprennent les magasins en ligne, les centres d’appels et les magasins de vente au détail (également appelés magasins traditionnels). Chaque canal de magasin de vente au détail peut proposer son propre mode de paiement, ses propres groupes de prix, ses propres caisses enregistreuses de PDV, ses propres comptes de revenus et de dépenses et son propre personnel. Vous devez paramétrer tous ces éléments avant de pouvoir créer un canal de magasin de vente au détail. 

Avant de créer un canal de vente au détail, assurez-vous de suivre les [Conditions préalables du canal](channels-prerequisites.md).

## <a name="create-and-configure-a-new-retail-channel"></a>Créer et configurer un canal de vente au détail

1. Dans le volet de navigation, accédez à **Modules \> Canaux \> Magasins \> Tous les magasins**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Nom**, fournissez un nom pour le nouveau canal.
1. Dans le champ **Numéro de magasin**, fournissez un numéro de magasin unique. Ce numéro peut être alphanumérique avec un maximum de 10 caractères.
1. Dans la liste déroulante **Entité juridique**, entrez l’entité juridique appropriée.
1. Dans la liste déroulante **Entrepôt**, entrez l’entrepôt approprié.
1. Dans le champ **Fuseau horaire du magasin**, sélectionnez le fuseau horaire adéquat.
1. Dans la liste déroulante **Groupe de taxe**, sélectionnez un groupe de taxe approprié pour le magasin.
1. Sélectionnez la devise adéquate dans le champ **Devise**.
1. Dans le **Carnet d’adresses client**, fournissez un carnet d’adresses valide.
1. Dans le champ **Client par défaut**, indiquez un client par défaut valide.
1. Dans le champ **Profil de la fonctionnalité**, sélectionnez un profil de fonctionnalité le cas échéant.
1. Dans le champ **Profil de notification par e-mail**, fournissez un profil de notification par e-mail valide.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’image suivante montre la création d’un canal de vente au détail.

![Nouveau canal de vente au détail.](media/channel-setup-retail-1.png)

L’image suivante présente un exemple de canal de vente au détail.

![Exemple de canal de vente au détail.](media/channel-setup-retail-2.png)

## <a name="other-settings"></a>Autres paramètres

De nombreux autres paramètres facultatifs peuvent être configurés dans les sections **Relevé/clôture** et **Divers**, en fonction des besoins du magasin de vente au détail.

De plus, voir [Mises en page de l’écran pour le point de vente (PDV)](pos-screen-layouts.md) pour plus d’informations sur la configuration de la disposition d’écran par défaut dans la section **Mise en page de l’écran** et [Configuration et installation d’une Retail Hardware Station](retail-hardware-station-configuration-installation.md) pour des informations de configuration sur la section **Stations matérielles**.

L’image suivante présente un exemple de paramétrage de canal de vente au détail.

![Exemple de paramétrage de canal de vente au détail.](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a>Paramétrage de canal supplémentaire

Des éléments supplémentaires doivent être configurés pour un canal disponible dans le volet Actions dans la section **Paramétrer**.

Les tâches supplémentaires requises pour le paramétrage du canal en ligne comprennent la configuration des modes de paiement, la déclaration des montants en caisse, les modes de livraison, le compte de revenus/dépenses, les sections, l’affectation du groupe d’exécution et les coffres-forts.

L’image suivante montre diverses autres options de paramétrage de canal de vente au détail dans l’onglet **Paramétrer**.

![Paramétrer un canal.](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a>paramétrer les modes de paiement ;

Pour configurer des modes de paiement, pour chaque type de paiement pris en charge sur ce canal, procédez comme suit.

1. Dans le volet Actions, sélectionnez l’onglet **Configurer**, puis **Modes de paiement**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le volet de navigation, sélectionnez un mode de paiement souhaité.
1. Dans la section **Général**, fournissez un **Nom de l’opération** et configurez tous les autres paramètres souhaités.
1. Configurez tous les autres paramètres requis pour le type de paiement.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’image suivante présente un exemple de mode de paiement au comptant.

![Exemple de modes de paiement.](media/channel-setup-retail-5.png)

L’image suivante montre un exemple de mode de paiement au comptant et la configuration de l’onglet **Montant**.

![Exemple de paramétrage de mode de paiement pour les montants.](media/payment-methods-recount.png)

> [!NOTE]
> Les valeurs pour l’onglet **Montant** sont mis en cache dans Retail Server et ne prendront pas effet immédiatement après l’exécution des travaux de planification de distribution. Vous devrez peut-être redémarrer Cloud Scale Unit pour appliquer immédiatement ces valeurs pour les tests.

### <a name="set-up-cash-declaration"></a>Paramétrer une déclaration des montants en caisse

1. Dans le volet Actions, sélectionnez l’onglet **Configurer**, puis **Déclaration des montants en caisse**.
1. Dans le volet Actions, sélectionnez **Nouveau**, puis créez toutes les dénominations **Pièce** et **Billet** applicables.

L’image suivante présente un exemple de mode de déclaration des montants en caisse.

![Paramétrer des déclaration des montants en caisse.](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a>Paramétrer des modes de livraison

Vous pouvez voir les modes de livraison configurés en sélectionnant **Modes de livraison** dans l’onglet **Paramétrer** du volet Actions.  

Pour modifier ou ajouter un mode de livraison, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Gestion des stocks \> Modes de livraison**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un mode de livraison ou sélectionnez un mode existant.
1. Dans la section **Canaux de vente au détail**, sélectionnez **Ajouter une ligne** pour ajouter le canal. L’ajout de canaux à l’aide de nœuds d’organisation au lieu d’ajouter chaque canal individuellement peut rationaliser l’ajout de canaux.

L’image suivante présente un exemple de mode de livraison.

![Paramétrer des modes de livraison.](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a>Paramétrer le compte de revenus/dépenses

Pour paramétrer le compte de revenus/dépenses, procédez comme suit.

1. Dans le volet Actions, sélectionnez l’onglet **Paramétrer**, puis **Compte de revenus/dépenses**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Sous **Nom**, entrez un nom.
1. Sous **Nom de recherche**, entrez un nom de recherche.
1. Sous **Type de compte**, entrez le type de compte.
1. Saisissez du texte pour **Ligne de message 1**, **Ligne de message 2**, **Texte de bon 1** et **Texte de bon 2**, selon les besoins.
1. Sous **Validation**, saisissez les informations sur la validation.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’image suivante montre un exemple de compte de revenus/dépenses.

![Paramétrer des comptes de revenus/dépenses.](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a>Paramétrer des sections

Pour paramétrer des sections, procédez comme suit.

1. Dans le volet Actions, sélectionnez l’onglet **Paramétrer** puis cliquez sur **Sections**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Sous **Numéro de section**, entrez un numéro de section.
1. Sous **Description**, entrez une description.
1. Sous **Taille de la section**, entrez une taille de section.
1. Configurez des paramètres supplémentaires pour **Général** et **Statistiques vente**, selon les besoins.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-a-fulfillment-group-assignment"></a>Paramétrer une affectation de groupe d’exécution

Pour paramétrer une affectation de groupe d’exécution, procédez comme suit.

1. Dans le volet Actions, sélectionnez l’onglet **Paramétrer**, puis **Affectation du groupe d’exécution**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la liste déroulante **Groupe d’exécution**, sélectionnez un groupe d’exécution.
1. Dans la liste déroulante **Description**, entrez une description.
1. Dans le volet Actions, sélectionnez **Enregistrer**

L’image suivante montre un exemple de configuration d’affectation de groupe d’exécution.

![Paramétrer l’affectation du groupe d’exécution.](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a>Configurer des coffres-forts

Pour configurer des coffres-forts, procédez comme suit.

1. Dans le volet Actions, sélectionnez l’onglet **Paramétrer** puis cliquez sur **Coffres-forts**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Entrez un nom pour le coffre-fort.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="ensure-unique-transaction-ids"></a>Garantir des identifiants de transaction uniques

À partir de la version 10.0.18 de Commerce, les ID de transaction générés pour le point de vente (PDV) sont séquentiels et comprennent les éléments suivants :

- Une partie fixe, qui est une concaténation de l’ID de magasin et de l’ID de terminal. 
- Une partie séquentielle, qui est une séquence de nombres. 

Plus précisément, le format est *{store}-{terminal} -{numbersequence}*. 

Étant donné que les ID de transaction peuvent être générés en mode hors ligne et en ligne, des instances d’ID de transaction en double ont été générées. L’élimination des ID de transaction en double nécessite de nombreuses corrections manuelles. 

Avec Commerce version 10.0.19, le format de l’ID de transaction a été mis à jour pour supprimer la partie séquentielle et utilise à la place un nombre à 13 chiffres généré en calculant le temps en millisecondes depuis 1970. Avec ce changement, le nouveau format d’ID de transaction est *{store}-{terminal}-{millisecondsSince1970}*. Cette mise à jour rend l’ID de transaction non séquentiel et garantit que les ID de transaction sont toujours uniques. 

> [!NOTE]
> Les ID de transaction sont uniquement destinés à un usage interne au système, ils ne doivent donc pas être séquentiels. Cependant, de nombreux pays exigent que les ID de reçu soient séquentiels.

La nouvelle fonctionnalité de format d’ID de transaction peut être activée à partir de l’espace e travail **Gestion des fonctionnalités**. 

Pour activer l’utilisation de nouveaux ID de transaction, procédez comme suit :

1. Dans Commerce Headquarters, accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.
1. Filtrez pour trouver le module « Retail et Commerce ».
1. Recherchez le nom de la fonction **Activer le nouvel identifiant de transaction pour éviter les identifiants de transaction en double**.
1. Sélectionnez la fonctionnalité, puis sélectionnez **Activer maintenant** dans le volet de droite.  
1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Exécutez les tâches **Configuration des canaux 1070** et **Enregistreur de tâches 1170 POS** pour synchroniser la fonction activée avec les magasins.
1. Une fois les modifications envoyées aux magasins, les terminaux PDV doivent être fermés et rouverts pour utiliser le nouveau format d’ID de transaction. 

> [!NOTE]
> Une fois la nouvelle fonctionnalité de format d’ID de transaction activée, vous ne pourrez pas la désactiver. Si elle doit être désactivée, veuillez contacter le support commercial.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des canaux](channels-overview.md)

[Conditions préalables à la configuration de canal](channels-prerequisites.md)

[Paramétrer un canal en ligne](channel-setup-online.md)

[Paramétrer un canal de centre d’appels](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
