---
title: Expédition de petits colis
description: Cet article fournit des informations sur la fonctionnalité d’expédition de petits colis (SPS). Cette fonctionnalité permet à Microsoft Dynamics 365 Supply Chain Management d’envoyer des détails sur un conteneur emballé au transporteur, puis de recevoir une étiquette d’expédition, des frais d’expédition et un numéro de suivi de ce transporteur.
author: Mirzaab
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 7bafd4a5118de5ca6025c6bd74fe436aa6abd1c8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855901"
---
# <a name="small-parcel-shipping"></a>Expédition de petits colis

[!include [banner](../../includes/banner.md)]

La fonctionnalité d’expédition de petits colis (SPS) permet à Microsoft Dynamics 365 Supply Chain Management d’interagir directement avec les transporteurs en fournissant un cadre de communication via les API du transporteur. Cette fonctionnalité est utile lorsque vous expédiez des commandes client individuelles via des transporteurs commerciaux au lieu d’utiliser l’expédition par conteneur ou l’expédition par chargement partiel (LTL).

La fonctionnalité SPS interagit avec votre transporteur via un *moteur de frais* dédié. Votre organisation doit développer ce moteur de frais en collaboration avec votre transporteur ou votre service de transport. Le moteur de frais permet à Supply Chain Management d’envoyer des détails sur un conteneur emballé à votre transporteur, puis de recevoir une étiquette d’expédition, des frais d’expédition et un numéro de suivi de ce transporteur.

Les frais d’expédition renvoyés sont ajoutés à la commande client associée en tant que frais divers. L’étiquette d’expédition renvoyée peut ensuite être imprimée automatiquement à l’aide d’une imprimante Zebra Programming Language (ZPL) et appliquée à l’expédition. Le transporteur scanne cette étiquette d’expédition lorsqu’il récupère les colis dans votre entrepôt.

## <a name="prepare-your-system-to-support-sps"></a>Préparer votre système pour prendre en charge SPS

Avant de pouvoir commencer à utiliser la fonctionnalité SPS, vous devez l’activer dans le module Gestion des fonctionnalités, ajouter votre moteur de frais et configurer les modules **Gestion du transport** et **Gestion des entrepôts** pour la prendre en charge.

### <a name="turn-on-the-sps-feature"></a>Activer la fonctionnalité SPS

Avant de pouvoir utiliser la fonctionnalité SPS, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Vidéos sur la gestion du transport*
- **Nom de la fonctionnalité :** *Expédition de petits colis*

### <a name="deploy-and-set-up-rate-engines"></a>Déployer et configurer les moteurs de frais

Supply Chain Management n’inclut aucun moteur de frais. Vous devez obtenir ou créer tous les moteurs de frais nécessaires, puis les ajouter à votre système. Cependant, Microsoft fournit un moteur de frais de démonstration que vous pouvez utiliser pour les tests.

#### <a name="download-and-deploy-the-demo-rate-engine"></a>Télécharger et déployer le moteur de frais de démonstration

Procédez comme suit pour obtenir le moteur de frais de démonstration.

1. Sur GitHub, téléchargez la [bibliothèque de liens dynamiques (DLL) pour le moteur de frais de démonstration](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).
1. Sur votre serveur Supply Chain Management, enregistrez la DLL dans le dossier **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.

#### <a name="create-and-deploy-functional-rate-engines"></a>Créer et déployer des moteurs de frais fonctionnels

Pour plus d’informations sur la création et le déploiement de moteurs de frais fonctionnels afin qu’ils puissent être utilisés dans un environnement de production ou de test, consultez les articles suivants :

- [Créer un moteur de gestion du transport](../transportation/create-new-transportation-management-engine.md)
- [Paramétrage de moteurs de gestion du transport](/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

Pour plus d’informations sur la création d’un moteur de frais SPS, consultez le billet de blog suivant : [Expédition de petits colis : comment tirer parti de la fonctionnalité d’expédition de petits colis dans Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a>Configurer un moteur de frais dans Supply Chain Management

Une fois que vous avez créé et déployé un moteur de frais pour SPS, procédez comme suit pour le configurer.

1. Accédez à **Gestion du transport \> Configuration \> Moteurs \> Moteur de frais**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les champs suivants :

    - **Moteur de frais** : entrez un nom unique pour le moteur de frais. Si vous utilisez le moteur de frais de démonstration, entrez *Moteur de frais de démonstration*.
    - **Nom** : entrez une brève description du moteur de frais. Si vous utilisez le moteur de frais de démonstration, entrez *Moteur de frais de démonstration*.
    - **ID des métadonnées de taux** : sélectionnez la base à utiliser pour calculer vos frais. Par exemple, vos frais peuvent être calculés en fonction de la distance. Si vous utilisez le moteur de frais de démonstration, vous pouvez laisser ce champ vide.
    - **Assembly de moteur** : entrez le nom de fichier du package DLL que vous avez déployé. Si vous utilisez le moteur de frais de démonstration, entrez *TMSSmallParcelShippingEngine.dll*.
    - **Classe de moteur** : entrez le nom de la classe qui a été établi pour votre moteur de frais. Si vous utilisez le moteur de frais de démonstration, entrez *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.

## <a name="example-scenario"></a>Exemple de scénario

Cet exemple de scénario montre comment configurer et utiliser SPS une fois que vous avez préparé votre système comme décrit plus haut dans cet article. Ce scénario utilise le moteur de frais de démonstration mentionné précédemment.

### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Pour utiliser ce scénario avec les enregistrements et les valeurs de démonstration spécifiés ici, vous devez utiliser un système dans lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

### <a name="set-up-the-scenario"></a>Paramétrage du scénario

Pour cet exemple de scénario, vous devez avoir un transporteur de démonstration, un groupe de transporteurs, une stratégie d’emballage et un profil d’emballage. Les sous-sections suivantes expliquent comment préparer les enregistrements nécessaires pour le scénario. Dans un scénario de production, le processus de configuration ressemble généralement au processus décrit ici. Cependant, vous définirez des valeurs différentes.

#### <a name="set-up-carriers"></a>Configurer des transporteurs

Procédez comme suit pour configurer un transporteur.

1. Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Transporteurs**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un transporteur.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Transporteur :** *Transporteur de démonstration*
    - **Nom :** *Transporteur de démonstration*
    - **Mode :** *Terrestre*

1. Dans l’organisateur **Vue d’ensemble**, définissez les valeurs suivantes :

    - **Activer le transporteur :** *Oui*
    - **Activer le classement du transporteur :** *Oui*

1. Dans le raccourci **Services**, sélectionnez **Nouveau** pour ajouter un service à la grille.
1. Définissez les valeurs suivantes pour le nouveau service :

    - **Service de transporteur :** *Service de transporteur de démonstration*
    - **Nom :** *Service de transporteur de démonstration*
    - **Mode de transport :** *Terrestre*

    Entrez des valeurs arbitraires pour tous les autres champs, au besoin. (Lorsque vous enregistrez le nouvel enregistrement de transporteur, un nouveau mode de livraison est créé et le champ **Mode de livraison** est défini automatiquement.)

1. Dans le raccourci **Profils de classement**, sélectionnez **Nouveau** pour ajouter un profil de classement à la grille.
1. Définissez les valeurs suivantes pour le nouveau profil :

    - **Profil de classement :** *Service de transporteur de démonstration*
    - **Nom :** *Service de transporteur de démonstration*
    - **Moteur de frais :** *Moteur de frais de démonstration*

    Entrez des valeurs arbitraires pour tous les autres champs, au besoin.

1. Dans le volet Actions, sélectionnez **Enregistrer**.

Pour plus d’informations sur la configuration des transporteurs, voir [Paramétrer des transporteurs](../transportation/tasks/set-up-shipping-carriers.md).

#### <a name="set-up-carrier-service-accounts"></a>Configurer des comptes de service de transporteur

Procédez comme suit pour configurer un compte de service de transporteur.

1. Accédez à **Gestion du transport \> Configuration \> Classement \> Compte de service de transporteur**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un compte de service de transporteur.
1. Définissez les valeurs suivantes pour le nouveau compte :

    - **Transporteur :** *Transporteur de démonstration*
    - **Service de transporteur :** *Service de transporteur de démonstration*
    - **Numéro de compte client du transporteur :** numéro de compte client du transporteur utilisé pour vérifier et authentifier la connexion au transporteur. Votre transporteur fournira cette valeur. Si vous utilisez le service de démonstration, vous pouvez entrer une valeur arbitraire.
    - **Site :** *6*
    - **Entrepôt :** *62*

    > [!NOTE]
    > Souvent, la valeur **Numéro de compte client du transporteur** est la seule valeur nécessaire pour authentifier la connexion. Toutefois, si votre transporteur requiert des paramètres d’authentification supplémentaires, votre organisation doit personnaliser cette page pour ajouter des champs supplémentaires, le cas échéant.

#### <a name="set-up-a-container-packing-policy"></a>Définir une stratégie d’emballage de conteneur

Procédez comme suit pour définir une stratégie d’emballage de conteneur.

1. Si vous n’avez pas encore configuré de définition d’imprimante ZPL, utilisez l’application Agent d’acheminement de documents pour la configurer. Pour plus d’informations, voir [Vue d’ensemble de l’impression de documents](../../fin-ops-core/dev-itpro/analytics/print-documents.md) et les articles connexes.
1. Accédez à **Gestion des entrepôts \> Configuration \> Conteneurs \> Stratégies d’emballage de conteneur**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une stratégie d’emballage de conteneur.
1. Dans l’en-tête de la nouvelle stratégie, définissez les valeurs suivantes :

    - **Stratégie d’emballage de conteneur :** *Stratégie d’emballage de démonstration*
    - **Description :** description de la stratégie

1. Dans l’organisateur **Vue d’ensemble**, définissez les valeurs suivantes :

    - **Entrepôt :** *62*
    - **Emplacement par défaut pour l’expédition finale :** *Baydoor*
    - **Unité de poids :** *KG*
    - **Stratégie de fermeture des conteneurs :** *Libération automatique*
    - **Stratégie de libération des conteneurs :** *Rendre disponible à l’emplacement d’expédition final*

1. Dans le raccourci **Manifeste du conteneur**, définissez les valeurs suivantes :

    - **Manifeste automatique à la fermeture du conteneur :** *Oui*
    - **Conditions requises du manifeste pour le conteneur :** *Gestion du transport*
    - **Imprimer le contenu du conteneur :** *Non*

1. Dans le raccourci **Impression de l’étiquette du transporteur**, définissez les valeurs suivantes :

    - **Imprimer l’étiquette d’expédition du conteneur :** *Toujours*
    - **Nom de l’imprimante :** Nom de l’imprimante ZPL qui doit imprimer les étiquettes d’expédition

#### <a name="set-up-a-packing-profile"></a>Configurer un profil d’emballage

Procédez comme suit pour configurer un profil d’emballage.

1. Accédez à **Gestion des entrepôts \> Configuration \> Emballage \> Profils d’emballage**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un profil d’emballage à la grille.
1. Définissez les valeurs suivantes pour le nouveau profil :

    - **ID profil d’emballage :** *Profil d’emballage de démonstration*
    - **Description :** description du profil
    - **Stratégie d’emballage de conteneur :** *Stratégie d’emballage de démonstration*
    - **Mode d’identification du conteneur :** *Auto*
    - **Type de conteneur :** *Petite boîte*

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a>Configurer un client pour utiliser le transporteur SPS

Suivez ces étapes pour configurer un client afin qu’il puisse utiliser le transporteur que vous avez créé.

1. Accédez à **Comptabilité client \> Clients \> Tous les clients**.
1. Dans la grille, recherchez et sélectionnez le client *US-027*.
1. Dans le volet Actions, sous l’onglet **Général**, dans le groupe **Configuration**, sélectionnez **Comptes client du transporteur**.
1. Sur la page **Comptes client du transporteur**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter un compte à la grille.
1. Définissez les valeurs suivantes pour le nouveau compte :

    - **Transporteur :** *Transporteur de démonstration*
    - **Numéro de compte client du transporteur :** *12345* (La valeur n’est pas importante pour ce scénario, mais elle est mentionnée dans la section suivante.)

### <a name="go-through-the-example-scenario"></a>Exécuter l’exemple de scénario

Une fois que vous avez configuré tous les exemples de données comme décrit dans la section précédente, vous êtes prêt à exécuter l’exemple de scénario.

#### <a name="create-a-sales-order-and-process-the-work"></a>Créer une commande client et traiter le travail

Procédez comme suit pour créer une commande client.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour créer une commande client.
1. Dans la boîte de dialogue **Créer une commande client**, définissez le champ **Compte client** sur *US-027*.
1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte. Dans le raccourci **En-tête de commande client**, définissez le champ **Numéro de compte client du transporteur** sur la valeur que vous avez précédemment sélectionnée pour ce client (*12345*).
1. Dans la section **Lignes de commande client**, ajoutez une ligne de vente et définissez les valeurs suivantes :

    - **Numéro d’article :** *A0002*
    - **Quantité :** *1*
    - **Site :** *6*
    - **Entrepôt :** *62*

1. Basculez sur la vue **En-tête**.
1. Dans le raccourci **Livraison**, définissez les valeurs suivantes :

    - **Transporteur :** *Transporteur de démonstration*
    - **Service de transporteur :** *Service de transporteur de démonstration*

1. Revenez à la vue **Lignes**. Si vous êtes invité à mettre à jour le mode de livraison des lignes de vente, sélectionnez **Oui**.
1. Dans la section **Lignes de commande client**, sélectionnez la ligne de commande que vous avez configurée précédemment, puis sélectionnez **Stock \> Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.
1. Fermez la page **Réservation** pour revenir à la commande client.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Le travail est créé pour déplacer les articles de l’emplacement de prélèvement vers la station de conditionnement.

1. Dans la section **Lignes de commande client**, sélectionnez **Entrepôt \> Détails de l’expédition**.
1. Sur la page **Détails de l’expédition**, notez l’ID d’expédition. Vous en aurez besoin lorsque vous emballerez l’expédition à la station de conditionnement.
1. Fermez la page **Détails de l’expédition** pour revenir à la commande client.
1. Notez le numéro de la commande client, puis accédez à **Gestion des entrepôts \> Travail \> Tout le travail**.
1. Utilisez le numéro de commande client pour rechercher et sélectionner le travail qui a été créé pour la commande.
1. Dans le volet Actions, sous l’onglet **Travail**, sélectionnez **Terminer le travail**.
1. Sur la page **Achèvement du travail**, dans le champ **ID utilisateur**, sélectionnez un ID utilisateur. Ensuite, dans le volet Actions, sélectionnez **Valider le travail**.
1. Si le travail réussit la validation, sélectionnez **Terminer le travail** dans le volet Actions.

    Le travail est marqué comme terminé pour simuler le mouvement des articles vers la station de conditionnement.

#### <a name="pack-the-shipment"></a>Emballer l’expédition

Procédez comme suit pour emballer l’expédition.

1. Accédez à **Gestion des entrepôts \> Configuration \> Collaborateur** et assurez-vous que votre compte d’utilisateur est associé à un compte de collaborateur pour la gestion des entrepôts.
1. Accédez à **Gestion des entrepôts \> Prélèvement et mise en conteneur \> Emballage**.
1. Dans la boîte de dialogue **Sélectionner une station de conditionnement**, définissez les valeurs suivantes :

    - **Site :** *6*
    - **Entrepôt :** *62*
    - **Emplacement :** *Emballer*
    - **ID profil d’emballage :** *Profil d’emballage de démonstration*

1. Cliquez sur **OK**.
1. La page **Emballage** s’affiche. Dans un scénario de production, un collaborateur numérise un contenant ou un ID d’expédition. Cependant, pour ce scénario, ouvrez la page **Toutes les expéditions** et recherchez le numéro de l’expédition que vous venez de créer. Ensuite, entrez cette valeur dans le champ **Contenant ou expédition** de la page **Emballage**. Vous pouvez également entrer l’ID d’expédition que vous avez noté précédemment.
1. Dans le volet Actions, sélectionnez **Nouveau conteneur**.
1. La boîte de dialogue qui apparaît affiche des détails sur le nouveau conteneur. Conservez les valeurs par défaut, puis sélectionnez **OK**.
1. Sur la page **Emballage**, dans le raccourci **Emballage de l’article**, dans le champ **Identifiant**, sélectionnez *A0002* pour emballer cet article. L’article est ajouté au conteneur.
1. Dans le volet Actions, sélectionnez **Conteneur pour expédition**.

    La page **Conteneurs pour expédition** qui apparaît a une ligne pour le conteneur que vous venez de créer. Cependant, le champ **ID manifeste du conteneur** de cette ligne est actuellement vide, car vous n’avez pas encore reçu l’étiquette d’expédition et le numéro de suivi du transporteur.

1. Dans le volet Actions, sélectionnez **Fermer le conteneur**.
1. Dans la boîte de dialogue **Fermer le conteneur**, définissez le champ **Poids brut** sur *1 kg*, puis sélectionnez **OK**.

    L’étiquette d’expédition doit maintenant être imprimée sur l’imprimante ZPL que vous avez sélectionnée précédemment. Elle doit ressembler à l’exemple ci-dessous.

    ![Exemple d’étiquette d’expédition.](media/sps-label-example.png "Exemple d’étiquette d’expédition")

1. Notez que les valeurs **ID manifeste du conteneur** et **Transport total** ont été ajoutées telles qu’elles ont été reçues du transporteur.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]