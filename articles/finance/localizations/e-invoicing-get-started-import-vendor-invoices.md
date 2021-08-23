---
title: Utiliser le service de facturation électronique pour importer des factures fournisseur
description: Cette rubrique fournit des informations sur la façon d’importer des factures fournisseur à l’aide du service de facturation électronique.
author: gionoder
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 434bf1f6a5a727a71592493b85ab166cbeff2f0980c2c968c99973a03f4dc660
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751250"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>Utiliser le service de facturation électronique pour importer des factures fournisseur

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Cette rubrique donne des informations qui vous aideront à démarrer avec l’importation de factures fournisseur en utilisant le service de facturation électronique. Elle vous guide à travers les étapes de configuration que vous devez suivre dans Regulatory Configuration Services (RCS), Dynamics 365 Finance et Dynamics 365 Supply Chain Management pour recevoir les factures fournisseur électroniques envoyées par les fournisseurs.

## <a name="set-up-vendor-invoice-import-in-rcs"></a>Paramétrer l’importation des factures fournisseur dans RCS
Pour paramétrer l’importation de factures fournisseur dans RCS, procédez comme suit :

1. Consultez la liste des [Fonctionnalités de facturation électronique généralement disponibles](e-invoicing-configuration-rcs.md#generally-available-features).
2. Sélectionnez et importez la fonctionnalité de facturation électronique. Pour plus d’informations, voir [Importer une fonctionnalité de facturation électronique à partir du fournisseur de configuration Microsoft](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider).
3. Créez une fonctionnalité de facturation électronique pour votre organisation. Pour plus d’informations, voir [Créer une fonctionnalité de facturation électronique sous votre fournisseur d’organisation](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider).

## <a name="configure-an-email-account-channel"></a>Configurer un canal de compte de messagerie

Configurez un canal de compte de messagerie si la fonctionnalité de facturation électronique que vous avez créée importe des factures fournisseur électroniques à partir de fichiers joints reçus par e-mail.

1. Dans RCS, sélectionnez la fonctionnalité de facturation électronique que vous avez créée. Assurez-vous de sélectionner la version avec un statut **Brouillon**.
2. Dans l’onglet **Paramétrages**, dans la grille, sélectionnez un paramétrage de fonctionnalité, puis sélectionnez **Modifier**.
3. Dans l’onglet **Canal de données**, dans le groupe de champs **Paramètres**, sélectionnez **Adresse du serveur** et entrez le fournisseur de compte de messagerie.
4. Sélectionnez **Port du serveur** et entrez le port utilisé par le fournisseur de compte de messagerie.
5. Sélectionnez **Secret nom d’utilisateur** et entrez le nom du secret Key Vault qui contient l’ID du compte d’utilisateur de messagerie.
6. Sélectionnez **Secret mot de passe utilisateur** et entrez le nom du secret Key Vault qui contient le mot de passe du compte d’utilisateur de messagerie.
7. Sélectionnez **Filtre objet**. Vérifiez et mettez à jour la chaîne qui contient l’objet e-mail par défaut pour identifier l’e-mail contenant la facture fournisseur électronique à importer.
8. Dans l’onglet **Règles d’applicabilité**, vérifiez et mettez à jour les critères si nécessaire. Pour plus d’informations, voir [Règles d'applicabilité](e-invoicing-configuration-rcs.md#applicability-rules).
9. Cliquez sur **Enregistrer**, puis fermez la page.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Configurer un canal Microsoft SharePoint

Configurez un canal Microsoft SharePoint si la fonction de facturation électronique importe des factures fournisseur électroniques à partir de fichiers placés dans des dossiers SharePoint.

1. Dans RCS, sélectionnez la fonctionnalité de facturation électronique que vous avez créée. Assurez-vous de sélectionner la **version** avec un statut **Brouillon**.
2. Dans l’onglet **Paramétrages**, dans la grille, sélectionnez un paramétrage de fonctionnalité, puis sélectionnez **Modifier**.
3. Dans l’onglet **Canal de données**, dans le groupe de champs **Paramètres**, sélectionnez **Adresse SharePoint** et entrez l’URL SharePoint.
4. Sélectionnez **Port du serveur** et entrez le port utilisé par le fournisseur de compte de messagerie.
5. Sélectionnez **ID d’application** et entrez le nom du secret Key Vault qui contient l’ID du client SharePoint.
6. Sélectionnez **Secret d’application** et entrez le nom du secret Key Vault qui contient le mot de passe du client SharePoint.
7. Sélectionnez **Filtre de fichier**. Vérifiez et mettez à jour le masque pour filtrer les fichiers contenant la facture fournisseur électronique à importer.
8. Dans l’onglet **Règles d’applicabilité**, vérifiez et mettez à jour les critères si nécessaire. Pour plus d’informations, voir [Règles d'applicabilité](e-invoicing-configuration-rcs.md#applicability-rules).
9. Cliquez sur **Enregistrer**, puis fermez la page.

### <a name="deploy-an-electronic-invoicing-feature"></a>Déployer une fonctionnalité de facturation électronique

Pour déployer la fonctionnalité de facturation électronique, voir [Déployer la fonctionnalité de facturation électronique dans l’environnement de service](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="set-up-vendor-invoice-import-in-finance-and-supply-chain-management"></a>Paramétrer l’importation de factures fournisseur dans Finance et Supply Chain Management
Suivez les étapes des deux sections suivantes pour paramétrer différents types d’importation de factures fournisseur.

### <a name="import-vendor-invoices-from-email"></a>Importer des factures fournisseur à partir d’un e-mail

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
2. Sélectionnez **Modèle de contexte de facture client** et créez une configuration dérivée.
3. Dans la version **Brouillon**, sélectionnez **Concepteur**.
4. Dans l’arborescence **Modèle de données**, sélectionnez **Facture client**, puis **Mettre en correspondance le modèle à la source de données**.
5. Dans l’arborescence **Définitions**, sélectionnez **Facture client**, puis sélectionnez **Concepteur**.
6. Dans l’arborescence **Sources de données**, sélectionnez **Contexte\_Canal**. Dans le champ **Valeur**, sélectionnez **PEPPOL**. Il s’agit du nom du canal donné dans la configuration du canal de données pour la fonctionnalité de facturation électronique dans RCS. 
7. Cliquez sur **Enregistrer**, puis fermez la page.
8. Fermez la page.
9. Sélectionnez **Modèle de contexte de facture client**, puis, dans le raccourci **Versions**, sélectionnez **Modifier le statut** > **Terminé**.
10. Accédez à **Administration d’organisation** > **Paramétrage** > **Paramètres des documents électroniques** et, dans l’onglet **Fonctionnalités**, assurez-vous que **Factures électroniques globales PEPPOL** est sélectionné. 
11. Dans l’onglet **Canaux externes**, dans le groupe de champs **Canaux**, sélectionnez **Ajouter**.
12. Dans le champ **Canal**, entrez **PEPPOL**. Entrez une description dans le champ **Description**.
13. Sélectionnez l’entité juridique dans le champ **Société**. Dans le champ **Contexte du document**, sélectionnez **Contexte de la facture client - Modèle de contexte de facture client**.
14. Sélectionnez **Enregistrer**, puis fermez la page.


## <a name="receive-electronic-invoices"></a>Recevoir des factures électroniques
Pour recevoir des factures électroniques, procédez comme suit :

1. Accédez à **Administration d’organisation** > **Périodique** > **Documents électroniques** > **Recevoir des documents électroniques**.
2. Cliquez sur **OK**, puis fermez la page.

## <a name="view-receive-logs-for-electronic-invoices"></a>Afficher les journaux de réception des factures électroniques

Pour afficher les journaux de réception des factures électroniques, accédez à **Administration d’organisation** > **Périodique** > **Documents électroniques** > **Journal de réception des documents électroniques**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
