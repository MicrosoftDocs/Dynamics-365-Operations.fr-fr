---
title: Utiliser le service de facturation électronique pour importer des factures fournisseur
description: Cet article fournit des informations sur la façon d’importer des factures fournisseur à l’aide du service de facturation électronique.
author: gionoder
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: c98f33345b37a72c4099f01e37c82e27002ac687
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283143"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>Utiliser le service de facturation électronique pour importer des factures fournisseur

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Cet article donne des informations qui vous aideront à démarrer avec l’importation de factures fournisseur en utilisant le service de facturation électronique. Il vous guide à travers les étapes de configuration que vous devez suivre dans Regulatory Configuration Services (RCS), Dynamics 365 Finance et Dynamics 365 Supply Chain Management pour recevoir les factures fournisseur électroniques envoyées par les fournisseurs.

## <a name="set-up-vendor-invoice-import-in-rcs"></a>Paramétrer l’importation des factures fournisseur dans RCS
Pour paramétrer l’importation de factures fournisseur dans RCS, procédez comme suit :

1. Consultez la liste des [Fonctionnalités de facturation électronique généralement disponibles](e-invoicing-configuration-rcs.md#generally-available-features).
2. Sélectionnez et importez la fonctionnalité de facturation électronique. Pour plus d’informations, voir [Importer une fonctionnalité de facturation électronique à partir du fournisseur de configuration Microsoft](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider).
3. Créez une fonctionnalité de facturation électronique pour votre organisation. Pour plus d’informations, voir [Créer une fonctionnalité de facturation électronique sous votre fournisseur d’organisation](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider).

## <a name="configure-an-email-account-channel"></a>Configurer un canal de compte de messagerie

Configurez un canal de compte de messagerie si la fonctionnalité de facturation électronique que vous avez créée importe des factures fournisseur électroniques à partir de fichiers joints reçus par e-mail.

1. Dans RCS, sélectionnez la fonctionnalité de facturation électronique que vous avez créée. Assurez-vous de sélectionner la version avec un statut **Brouillon**.
2. Dans l’onglet **Paramétrages**, dans la grille, sélectionnez un paramétrage de fonctionnalité, puis sélectionnez **Modifier**.
3. Dans l’onglet **Canal de données** du groupe de champs **Paramètres**, dans le champ **Canal de données**, entrez le nom du canal. Le nom du canal ne doit pas comporter plus de dix caractères.
4. Dans le champ **Adresse du serveur**, entrez le fournisseur du compte de messagerie électronique. Par exemple, l’adresse du serveur pour **https://outlook.live.com/** est **imap-mail.outlook.com**.
5. Dans le champ **Port du serveur**, entrez le port utilisé par le fournisseur de compte de messagerie. Par exemple, le port du serveur pour **https://outlook.live.com/** est **993**.
6. Dans le champ **Secret nom d’utilisateur**, entrez le nom du secret Key Vault qui contient l’ID du compte d’utilisateur de messagerie. Ce secret doit être créé dans Azure Key Vault et configuré dans votre environnement de service. 
7. Dans le champ **Secret mot de passe d’utilisateur**, entrez le nom du secret Key Vault qui contient le mot de passe du compte d’utilisateur de messagerie.
8. Facultatif : saisissez des valeurs dans les champs **Filtre De**,**Filtre Objet** et **Filtre Date**.
9. Entrez le nom des dossiers de la boîte de réception où les courriers seront :

    - Importés depuis : **Dossier principal**
    - Enregistrés après un traitement réussi : **Dossier d’archives**
    - Enregistrés après un traitement infructueux : **Dossier d’erreur**. Vous n’êtes pas obligé de créer ces dossiers dans la boîte de réception. Les dossiers sont créés automatiquement après l’importation et le traitement de la première facture électronique. 
   
10. Dans le groupe de champs **Filtre des pièces jointes**, ajoutez les informations de filtrage de fichier. Seules les pièces jointes qui satisfont au filtre défini sont traitées. Par exemple, vous pouvez configurer « \*.xml » pour les pièces jointes avec une extension xml. Le nom de la pièce jointe est utilisé dans Dynamics 365 Finance ou Dynamics 365 Supply Chain Management lors de la configuration. 
11. Dans l’onglet **Règles d’applicabilité**, vérifiez et mettez à jour les critères si nécessaire. Le champ **Canal** doit être égal au **Canal de données** indiqué précédemment. Pour plus d’informations, voir [Règles d’applicabilité](e-invoicing-configuration-rcs.md#applicability-rules).
12. Cliquez sur **Enregistrer**, puis fermez la page.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Configurer un canal Microsoft SharePoint

Configurez un canal Microsoft SharePoint si la fonction de facturation électronique importe des factures fournisseur électroniques à partir de fichiers placés dans des dossiers SharePoint.

1. Dans RCS, sélectionnez la fonctionnalité de facturation électronique que vous avez créée. Assurez-vous de sélectionner la **version** avec un statut **Brouillon**.
2. Dans l’onglet **Paramétrages**, dans la grille, sélectionnez un paramétrage de fonctionnalité, puis sélectionnez **Modifier**.
3. Dans l’onglet **Canal de données**, dans le groupe de champs **Paramètres**, sélectionnez **Adresse SharePoint** et entrez l’URL SharePoint.
4. Sélectionnez **Port du serveur** et entrez le port utilisé par le fournisseur de compte de messagerie.
5. Sélectionnez **ID d’application** et entrez le nom du secret Key Vault qui contient l’ID du client SharePoint.
6. Sélectionnez **Secret d’application** et entrez le nom du secret Key Vault qui contient le mot de passe du client SharePoint.
7. Sélectionnez **Filtre de fichier**. Vérifiez et mettez à jour le masque pour filtrer les fichiers contenant la facture fournisseur électronique à importer.
8. Dans l’onglet **Règles d’applicabilité**, vérifiez et mettez à jour les critères si nécessaire. Pour plus d’informations, voir [Règles d’applicabilité](e-invoicing-configuration-rcs.md#applicability-rules).
9. Cliquez sur **Enregistrer**, puis fermez la page

### <a name="deploy-an-electronic-invoicing-feature"></a>Déployer une fonctionnalité de facturation électronique

Pour déployer la fonctionnalité de facturation électronique, voir [Déployer la fonctionnalité de facturation électronique dans l’environnement de service](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="set-up-vendor-invoice-import-in-finance-or-supply-chain-management"></a>Paramétrer l’importation de factures fournisseur dans Finance ou Supply Chain Management
Suivez les étapes des deux sections suivantes pour paramétrer différents types d’importation de factures fournisseur.

### <a name="import-brazilian-nf-e-from-email"></a>Importer le format NF-e pour le Brésil à partir d’e-mails

1. Connectez-vous à votre environnement Finance ou Supply Chain Management et vérifiez que vous êtes dans la bonne entité juridique.
2. Accédez à **Administration de l’organisation** > **Paramétrage** > **Paramètres des documents électroniques**.
3. Dans l’onglet **Fonctionnalités**, assurez-vous que **NF-e Federal - Facture électronique pour le Brésil** est sélectionné.
4. Dans l’onglet **Canaux externes**, dans le groupe de champs **Canaux**, sélectionnez **Ajouter**.
5. Dans le champ **Canal**, entrez **NFe** (nom du canal donné dans la configuration du canal de données pour la fonction de facturation électronique dans RCS).
6. Entrez une description dans le champ **Description**. Sélectionnez l’entité juridique dans le champ **Société**.
7. Dans le champ **Contexte du document**, sélectionnez **Contexte du document fiscal - Modèle de contexte de facture client**.
8. Dans le groupe de champ **Importer des sources**, sélectionnez **Ajouter**.
9. Dans le champ **Nom**, entrez **XmlFile** (nom du **filtre de pièce jointe** donné dans la configuration du canal de données pour la fonctionnalité de facturation électronique dans RCS).
10. Dans le champ **Description**, entrez une description, et dans le champ **Nom de l’entité de données**, sélectionnez **Documents XML NF-e reçus**.
11. Dans le champ **Mappage de modèles**, sélectionnez **Importation de courriers NF-e – Importation d’e-mails NF-e (BR)**, puis cliquez sur **Enregistrer**.
12. Dans l’onglet **Document électronique**, dans le groupe de champs **Gestion des états électroniques**, sélectionnez **Ajouter**, et dans le champ **Nom de la table**, sélectionnez **Document XML NF-e reçu**.
13. Dans le champ **Contexte du document**, sélectionnez **Interroger le contexte du document fiscal – Contexte de facture client**.
14. Dans le champ **Mappage du modèle de document électronique**, sélectionnez **Interroger le mappage – Mappage des documents fiscaux**.
15. Sélectionnez **Types de réponse**, puis sélectionnez **Nouveau**.
16. Dans le champ **Type de réponse**, entrez **Réponse**. Dans le champ **Statut d’envoi**, entrez **Planifié**.
17. Dans le champ **Mappage de modèle**, sélectionnez **Mappage de modèle à partir du message de réponse – Format d’importation du message de réponse**.
18. Sélectionnez **Enregistrer**, puis fermez la page.

### <a name="import-peppol-electronic-vendor-invoices"></a>Importer des factures fournisseur électroniques PEPPOL

1. Accédez à l’espace de travail **Gestion des états électroniques** et sélectionnez **Configurations des états**.
2. Sélectionnez **Modèle de contexte de facture client**, puis sélectionnez **Créer une configuration** > **Dériver du nom : modèle de contexte de facture client, Microsoft** pour créer une configuration dérivée.
3. Dans la version **Brouillon**, sélectionnez **Concepteur** puis, dans l’arborescence **Modèle de données**, sélectionnez **Mapper le modèle sur la source de données**.
4. Dans l’arborescence **Définitions**, sélectionnez **Canal de données**, puis sélectionnez **Concepteur**.
5. Dans l’arborescence **Source de données**, développez le conteneur **$Contexte\_Canal**. Dans le champ **Valeur**, sélectionnez **Modifier** et entrez le nom du canal de données. Il s’agit du nom du canal donné dans la configuration du canal de données pour la fonctionnalité de facturation électronique dans RCS. 
7. Cliquez sur **Enregistrer**, puis fermez la page.
8. Fermez la page.
9. Sélectionnez la configuration dérivée que vous venez de créer à partir du **Modèle de contexte de facture client** et, dans le raccourci **Versions**, sélectionnez **Modifier le statut** > **Terminé**.
10. Accédez à **Administration d’organisation** > **Paramétrage** > **Paramètres des documents électroniques** et, dans l’onglet **Fonctionnalités**, assurez-vous que **Factures électroniques globales PEPPOL** est sélectionné. 
11. Dans l’onglet **Canaux externes**, dans le groupe de champs **Canaux**, sélectionnez **Ajouter**.
12. Dans le champ **Canal**, entrez le nom du canal de données et, dans le champ **Description**, entrez une description.
13. Sélectionnez l’entité juridique dans le champ **Société**. 
14. Dans le champ **Contexte du document**, sélectionnez la nouvelle configuration dérivée à partir du **Modèle de contexte de facture client**. La description du mappage doit être **Contexte du canal de données**.
15. Dans le groupe de champ **Importer des sources**, sélectionnez **Ajouter**.
16. Dans le champ **Nom**, entrez **Nom du filtre des pièces jointes** et dans le champ **Nom de l’entité de données**, sélectionnez **En-tête de facture fournisseur**.
17. Dans le champ **Mappage du modèle**, sélectionnez **Importation de facture fournisseur - Importer la facture fournisseur**.
18. Cliquez sur **Enregistrer**, puis fermez la page.


## <a name="receive-electronic-invoices"></a>Recevoir des factures électroniques

Le service de facturation électronique effectue deux étapes lors de l’importation de factures à partir des canaux de données :

1. Accéder à la boîte de réception et lire les e-mails.
2. Traiter les e-mails. 
    
Pour effectuer ces deux étapes, le client doit appeler le service manuellement pour chaque étape. Cependant, nous vous recommandons de configurer un traitement par lots pour la réception de documents électroniques.

Pour recevoir des factures électroniques, procédez comme suit :

1. Accédez à **Administration d’organisation** > **Périodique** > **Documents électroniques** > **Recevoir des documents électroniques**.
2. Cliquez sur **OK**, puis fermez la page.


## <a name="view-receive-logs-for-electronic-invoices"></a>Afficher les journaux de réception des factures électroniques

Pour afficher les journaux de réception des factures électroniques, accédez à **Administration d’organisation** > **Périodique** > **Documents électroniques** > **Journal de réception des documents électroniques**.
Si vous ne voyez pas les factures traitées avec succès, supprimez le filtre de la table.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
