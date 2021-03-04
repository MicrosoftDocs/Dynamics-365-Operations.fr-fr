---
title: Configurer le BOPIS dans un environnement d'évaluation Dynamics 365 Commerce
description: Cette rubrique explique comment configurer l'achat en ligne, le retrait en magasin (BOPIS) dans un environnement d'évaluation de Microsoft Dynamics 365 Commerce après qu'il a été mis en service.
author: rubendel
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 62dabaa2610341cc8ad8e85812a317ac3123fcb1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412165"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a>Configurer le BOPIS dans un environnement d'évaluation Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cette rubrique explique comment configurer l'achat en ligne, le retrait en magasin (BOPIS) dans un environnement d'évaluation de Microsoft Dynamics 365 Commerce après qu'il a été mis en service.

## <a name="prerequisite"></a>Logiciel requis

Effectuez les procédures de cette rubrique uniquement une fois que votre environnement d'évaluation de Commerce a été mis en service et configuré. Pour plus d'informations sur l'approvisionnement et la configuration de votre environnement, voir [Mettre en service un environnement d'évaluation Dynamics 365 Commerce](provisioning-guide.md) et [Configurer un environnement d'évaluation Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).

Une fois que votre environnement Commerce a été approvisionné et configuré de bout en bout, vous pouvez utiliser cette rubrique pour activer les scénarios BOPIS.

## <a name="configure-the-pos"></a>Configuration du PDV

### <a name="configure-modern-pos"></a>Configuration de Modern POS

Les scénarios BOPIS impliquant un paiement par carte de crédit nécessitent une station matérielle. La station matérielle est intégrée dans les Modern POS pour les clients Windows et Android. Si vous utilisez Cloud POS ou Modern POS pour iOS, le client du point de vente (PDV) doit être associé à une station matérielle partagée. Cette rubrique explique comment configurer BOPIS pour les clients Windows et Android. Pour plus d'informations sur la configuration d'une station matérielle partagée, voir [Configurer et installer la station matérielle Retail](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).

1. Allez dans **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> Caisses enregistreuses**.
2. Sélectionnez enregistrer **SANFRAN-5**, puis sélectionnez **Modifier**.
3. Modifiez la valeur du champ **Profil matériel** de **HW002** sur **HW001**, puis sélectionnez **Enregistrer**.
4. Pour synchroniser les modifications, accédez à **Retail et Commerce \> Informatique vente au détail et Commerce \> Programme de distribution**.
5. Sélectionnez le programme de distribution **1090**, puis sur le volet Action, sélectionnez **Exécuter maintenant**.
6. Sélectionnez **Oui**, puis **OK** pour lancer la synchronisation des données. 

### <a name="install-modern-pos"></a>Installer Modern POS

1. Allez dans **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> Appareils**.
2. Sélectionnez l'appareil **SANFRANCIS-5**.
3. Dans le volet Actions, sélectionnez **Télécharger**, puis sélectionnez **Fichier de configuration**.
4. Sélectionnez **Télécharger**, puis **Retail Modern POS**. 
5. Une fois le téléchargement du fichier **ModernPOSSetup.exe** terminé, sélectionnez **Ouvrir le fichier**.

    ![Ouvrir le fichier](./dev-itpro/media/PAYMENTS/openfile.png)

6. Sélectionnez **Suivant** pour passer par le processus d'installation. Une fois l'installation terminée, sélectionnez **Fermer**.

### <a name="activate-modern-pos"></a>Activer Modern POS

1. Sur le Bureau Windows, sélectionnez le bouton **Démarrer** et entrez **Retail Modern POS**.
2. Sélectionnez l'application **Retail Modern POS** pour lancer l'activation.
3. Sélectionnez **Suivant**. Les champs **URL du serveur**, **Référence de l'appareil** et **Numéro d'enregistrement** doivent être prédéfinis en utilisant les informations du fichier de configuration que vous avez téléchargé dans la procédure précédente.
4. Sélectionnez **Activer**.
5. Une boîte de dialogue d'authentification apparaît. Sélectionnez le compte qui utilise l'adresse e-mail précédemment associée au collaborateur **000713 - Andrew Collette**.

    > [!NOTE]
    > Si vous n'avez pas encore associé de collaborateur à votre identité, l'activation échouera. Dans ce cas, suivez les étapes de la section « Associer un collaborateur à votre identité » dans la rubrique [Configurer un environnement d'évaluation Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).
    
6. Lorsque vous êtes invité à laisser votre organisation gérer l'appareil, sélectionnez **Cette application uniquement**.
7. Une fois l'activation terminée, sélectionnez **Mise en route**.

### <a name="enable-bopis-in-modern-pos"></a>Activer BOPIS dans Modern POS

1. Connectez-vous à Modern POS en utilisant **000713** comme ID opérateur et **123** comme mot de passe.
2. Pendant la lecture de la vidéo d'introduction, cochez les deux cases dans le coin inférieur gauche de la boîte de dialogue, puis fermez la boîte de dialogue.
3. Si vous n'êtes pas invité à fermer le quart de travail, faites défiler vers la droite la page **Bienvenue**, sélectionnez **Fermer l'équipe**, puis reconnectez-vous au PDV.
4. Une fois connecté, lorsque vous y êtes invité, sélectionnez **Effectuer une opération sans tiroir-caisse**.
5. Sur la page **Bienvenue**, faites défiler vers la droite et sélectionnez l'opération **Sélectionner la station matérielle**.
6. Sélectionnez **Gérer**, définissez l'option **Utiliser la station matérielle** sur **Activé**, puis sélectionnez **OK**.
7. Déconnectez-vous du PDV et puis reconnectez-vous.
8. Une fois connecté, sélectionnez **Ouvrir un nouveau quart de travail**, puis sélectionnez **Tiroir-caisse**.

## <a name="complete-a-bopis-scenario"></a>Terminer un scénario BOPIS

### <a name="create-a-storefront-order-for-in-store-pickup"></a>Créer une commande dans la vitrine pour un retrait en magasin

1. Accédez à l'URL spécifiée à l'étape [Initialiser e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) lors de la configuration de l'environnement.
2. Sélectionnez un article, puis **Ajouter au panier**.
3. Sur la page du panier, sélectionnez **Retrait** pour la ligne de commande que vous venez d'ajouter.
4. Dans la boîte de dialogue **Sélectionner un magasin**, entrez **San Francisco**, puis cliquez sur le bouton **Rechercher**.
5. Dans la liste des résultats, recherchez le magasin de San Francisco et sélectionnez **Retirer ici**.
6. Sur la page du panier, sélectionnez **Passer la commander en tant qu'invité**. 

    > [!NOTE]
    > Pour continuer avec le paiement, vous devez accepter l'avis relatif aux cookies. Cet avis apparaît sous la forme d'une bannière en haut de la page de paiement.

7. Pour le mode de paiement par carte de crédit, entrez les détails suivants :

    - **Nom du titulaire de la carte :** Entrez n'importe quel nom.
    - **Numéro de carte :** Entrez **4111-1111-1111-1111**.
    - **Date d'expiration :** Entrez **10/20**.
    - **Code de valeur de la vérification de la carte (CVV) :** Entrez **737**.

    > [!IMPORTANT]
    > En aucun cas vous ne devez tenter d'utiliser des informations de carte de crédit réelle sur le site de test.

8. Continuez le paiement en entrant les détails de l'adresse de facturation, puis cliquez sur **Enregistrer et continuer**.
9. Lorsque la commande est prête à être passée, sélectionnez **Paiement**.

### <a name="synchronize-online-orders-to-the-back-office"></a>Synchronisez les commandes en ligne avec le back office

Pour plus d'informations sur la synchronisation des commandes en ligne, voir [Validation des ventes et paiements en ligne](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).

### <a name="pick-up-an-order-in-the-store"></a>Retirer une commande en magasin

1. Connectez-vous au PDV.
2. Sur l'écran **Bienvenue**, sélectionnez **Exécution de la commande**
3. Dans la liste des articles à retirer en magasin, sélectionnez la ligne de la commande passée en ligne.
4. Pendant que la ligne de commande est sélectionnée, sélectionnez **Retrait**.

    L'article de la ligne est ajouté à l'écran de transaction, et **0,00 $** est indiqué comme le solde dû.

5. Sélectionnez le solde dû **0,00 $** ou sélectionnez un mode de paiement pour conclure la transaction.

## <a name="troubleshooting"></a>Dépannage

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a>Les commandes en ligne récupérées dans le PDV ont un solde dû non nul

Lorsqu'une commande est récupérée pour un retrait en magasin, si le solde dû n'est pas de 0 (zéro), assurez-vous que Modern POS est en cours d'utilisation et que la station matérielle est active. Si Cloud POS ou Modern POS pour iOS est en cours d'utilisation, assurez-vous qu'une station matérielle partagée est active. Une certaine forme de station matérielle active est requise pour récupérer les paiements effectués en ligne.

### <a name="general-issues-with-payment-capture"></a>Problèmes généraux avec la capture de paiement

Pour tous les problèmes généraux, vous devez toujours consulter les journaux des événements de la station matérielle Modern POS ou Services Internet (IIS) dans un premier temps. Vous pouvez trouver ces journaux sous les nœuds suivants dans le journal des événements Windows :

- Journaux des applications et des services \> Microsoft \> Dynamics \> Commerce-ModernPOS
- Journaux des applications et des services \> Microsoft \> Dynamics \> Commerce-Station matérielle

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble d'un environnement d'évaluation Dynamics 365 Commerce](cpe-overview.md)

[Mettre en service un environnement d'évaluation Dynamics 365 Commerce](provisioning-guide.md)

[Configurer des fonctionnalités facultatives pour un environnement d'évaluation Dynamics 365 Commerce](cpe-optional-features.md)

[FAQ des environnements d'évaluation Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portail Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site web Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Connecteur de paiement Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)

[Enregistrement des instruments de paiement en ligne avec le connecteur Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector-listpi)

[Vue d'ensemble des paiements omnicanaux](https://docs.microsoft.com/dynamics365/commerce/omni-channel-payments)


[!INCLUDE[footer-include](../includes/footer-banner.md)]