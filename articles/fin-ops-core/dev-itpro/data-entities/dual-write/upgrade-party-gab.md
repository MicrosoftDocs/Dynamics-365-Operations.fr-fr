---
title: Effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global
description: Cette rubrique décrit comment mettre à niveau les données à double écriture en modèle de carnet d’adresses global et de partie.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: eaafe8d98049cb8838317396f28e9d6ca720a677
ms.sourcegitcommit: 08dcbc85e372d4e4fb3ba64389f6d5051212c212
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2022
ms.locfileid: "8015713"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Les [modèles Microsoft Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema) vous aide à mettre à niveau les données suivantes en double écriture vers le modèle de partie et de carnet d’adresses globales : données des tables **Compte**, **Contact** et **Fournisseurs** et les adresses postales et électroniques.

Les trois modèles Data Factory suivants sont fournis. Ils facilitent le rapprochement des données des applications Finances et Opérations et des applications d’engagement client.

- **[Modèle de la partie](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/arm_template.json) (Mettre à niveau des données vers un schéma dual-write Party-GAB/arm_template.json)** – Ce modèle permet de mettre à niveau les données de **Partie** et de **Contact** associées aux données de **Compte**, **Contact** et **Fournisseur**.
- **[Modèle d’adresse postale de la partie](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Postal%20Address%20-%20GAB/arm_template.json) (Mettre à niveau les données vers le schéma dual-write Party-GAB/Mettre à niveau vers l’adresse postale de partie - GAB/arm_template.json)** – Ce modèle permet de mettre à niveau les adresses postales associées aux données de **Compte**, **Contact** et **Fournisseur**.
- **[Modèle d’adresse électronique de la partie](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Electronic%20Address%20-%20GAB/arm_template.json) (Mettre à niveau les données vers le schéma dual-write Party-GAB/Mettre à niveau vers l’adresse électronique de la partie - GAB/arm_template.json)** – Ce modèle permet de mettre à niveau les adresses électroniques associées aux données de **Compte**, **Contact** et **Fournisseur**.

À la fin du processus, les fichiers de valeurs séparées par des virgules (.csv) suivants sont générés.

| Nom de fichier | Objectif |
|---|---|
| FONewParty.csv | Ce fichier permet de créer de nouveaux enregistrements **Partie** dans l’application Finances et Opérations. |
| ImportFONewPostalAddressLocation.csv | Ce fichier permet de créer de nouveaux enregistrements **Emplacements d’adresse postale** dans l’application Finances et Opérations. |
| ImportFONewPartyPostalAddress.csv | Ce fichier permet de créer de nouveaux enregistrements **Adresse postale de partie** dans l’application Finances et Opérations. |
| ImportFONewPostalAddress.csv | Ce fichier permet de créer de nouveaux enregistrements **Adresse postale** dans l’application Finances et Opérations. |
| ImportFONewElectronicAddress.csv | Ce fichier permet de créer de nouveaux enregistrements **Adresse électronique** dans l’application Finances et Opérations. |

Cette rubrique comment utiliser les modèles Data Factory et mettre à niveau vos données. Si vous n’avez aucune personnalisation, vous pouvez utiliser les modèles tels quels. Toutefois, si vous avez des personnalisations pour les données de **Compte**, **Contact** et **Fournisseur**, vous devez modifier les modèles comme décrit dans cette rubrique.

> [!IMPORTANT]
> Des instructions spéciales s’appliquent si vous exécutez les modèles d’adresse postale et d’adresse électronique de partie. Vous devez d’abord exécuter le modèle Partie, puis le modèle d’adresse postale Partie, puis le modèle d’adresse électronique Partie. Chaque modèle est conçu pour être importé dans une fabrique de données distincte.

## <a name="prerequisites"></a>Conditions préalables

Les conditions préalables suivantes doivent être satisfaites avant de pouvoir effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global :

+ Vous devez avoir un [abonnement Azure](https://portal.azure.com/).
+ Vous devez avoir accès [aux modèles](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
+ Vous devez déjà être client de la double écriture.

## <a name="prepare-for-the-upgrade"></a>Préparation pour la mise à niveau

Une mise à niveau nécessite la préparation suivante :

+ **Synchronisation complète :** l’environnement Finance and Operations et l’environnement Customer Engagement sont dans un état entièrement synchronisé pour les tables **Compte (Client)**, **Contact**, et **Fournisseur**.
+ **Clés d’intégration** : les tables **Compte (client)**, **Contact** et **Fournisseur** dans les applications Customer Engagement utilisent les clés d’intégration prêtes à l’emploi. Si vous avez personnalisé les clés d’intégration, vous devez personnaliser le modèle.
+ **Numéro de partie :** tous les enregistrements **Compte (Client)**, **Contact** et **Fournisseur** qui seront mis à niveau ont un numéro de partie. Les enregistrements qui n’ont pas de numéro de partie seront ignorés. Si vous souhaitez mettre à niveau ces enregistrements, ajoutez-leur un numéro de partie avant de commencer le processus de mise à niveau.
+ **Panne du système** : pendant le processus de mise à niveau, vous devrez mettre hors connexion les environnements Finance and Operations et Customer Engagement.
+ **Instantané** : prenez un instantané des applications Finances et Opérations et des applications d’engagement client. Vous pouvez utiliser les instantanés pour restaurer l’état précédent si nécessaire.

## <a name="deployment"></a>Déploiement

1. Téléchargez les modèles depuis [Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
2. Connectez-vous au [portail Azure](https://portal.azure.com/).
3. Créez un [groupe de ressources](/azure/azure-resource-manager/management/manage-resource-groups-portal).
4. Créez un [compte de stockage](/azure/storage/common/storage-account-create?tabs=azure-portal) dans le groupe de ressources que vous avez créé.
5. Créez une [fabrique de données](/azure/data-factory/quickstart-create-data-factory-portal) dans le groupe de ressources que vous avez créé.
6. Ouvrez la fabrique de données et sélectionnez la vignette **Créer et surveiller**.
7. Dans l’onglet **Gérer**, sélectionnez **Modèle ARM**.
8. Sélectionnez **Importer un modèle ARM** pour importer le modèle **Partie**.
9. Importez le modèle dans la fabrique de données. Entrez les valeurs suivantes pour les **Détails du projet** et les **Détails de l’instance**.

    | Champ | Valeur |
    |---|---|
    | Abonnement | L’abonnement Azure |
    | Groupe de ressources | Indiquez la même ressource que celle sous laquelle le compte de stockage est créé. |
    | Région | La région |
    | Nom de la fabrique | Le nom de la fabrique |
    | FO Linked Service_service Principal Key | La clé de l’application |
    | Azure Blob Storage_connection String | La chaîne de connexion de stockage Blob Azure |
    | Dynamics Crm Linked Service_password | Le mot de passe du compte utilisateur que vous spécifiez comme nom d’utilisateur. |
    | FO Linked Service_properties_type Properties_url | `https://sampledynamics.sandbox-operationsdynamics.com/data` |
    | FO Linked Service_properties_type Properties_tenant | Les informations (nom de domaine ou ID de locataire) à propos du locataire sous lequel réside votre application. |
    | FO Linked Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com` |
    | FO Linked Service_properties_type Properties_service Principal Id | L’ID du client de l’application. |
    | Dynamics Crm Linked Service_properties_type Properties_username | Le nom d’utilisateur utilisé pour se connecter à Dynamics 365 |

    Pour plus d’informations, voir les rubriques suivantes :

    - [Promouvoir manuellement un modèle Resource Manager pour chaque environnement](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Propriétés du service lié](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Copier des données à l’aide d’Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Après le déploiement, vérifiez les jeux de données, le flux de données et le service lié de la fabrique de données.

    ![Jeux de données, flux de données et service lié.](media/data-factory-validate.png)

11. Accédez à **Gérer**. En dessous de **Connexions**, sélectionnez **Service lié**. Sélectionnez ensuite **DynamicsCrmLinkedService**. Dans la boîte de dialogue **Modifier le service lié (Dynamics CRM)**, entrez les valeurs suivantes.

    | Champ | Valeur |
    |---|---|
    | Name | DynamicsCrmLinkedService |
    | Description | Services liés pour se connecter à l’instance CRM pour récupérer les données des entités |
    | Connexion via le runtime d’intégration | AutoResolvelntegrationRuntime |
    | Type de déploiement | En ligne |
    | URI du service | `https://<organization-name>.crm[x].dynamics.com` |
    | Type d’authentification | Office365 |
    | Nom d’utilisateur | |
    | Mot de passe ou Azure Key Vault | Mot de passe |
    | Mot de passe | |

## <a name="prepare-to-run-the-data-factory-templates"></a>Préparez-vous à exécuter les modèles Data Factory

Cette section décrit la configuration requise avant d’exécuter les modèles Adresse postale de partie et Adresse électronique de partie Data Factory.

### <a name="setup-to-run-the-party-postal-address-template"></a>Configuration pour exécuter le modèle d’adresse postale de partie

1. Connectez-vous aux applications Customer Engagement et accédez à **Paramètres** \> **Paramètres de personnalisation**. Puis, sur l’onglet **Général**, configurez le paramètre de fuseau horaire pour le compte d’administrateur système. Le fuseau horaire doit être en temps universel coordonné (UTC) pour mettre à jour les dates « valide à partir de » et « valide jusqu’au » des adresses postales à partir des applications Finances et Opérations.

    ![Paramètre de fuseau horaire pour le compte d’administrateur système.](media/ADF-1.png)

2. Dans Data Factory, sur l’onglet **Gérer**, sous **Paramètres globaux**, créez le paramètre global suivant.

    | Nombre | Name | Type | Valeur |
    |---|---|---|---|
    | 1 | PostalAddressIdPrefix | chaîne | Ce paramètre ajoute un numéro de série aux adresses postales nouvellement créées en tant que préfixe. Assurez-vous de fournir une chaîne qui n’entre pas en conflit avec les adresses postales dans les applications Finances et Opérations et les applications d’engagement client. Pour cet exemple, utilisez **ADF-PAD-**. |

    ![Paramètre global PostalAddressIdPrefix créé dans l’onglet Gérer.](media/ADF-2.png)

3. Lorsque vous avez terminé, sélectionnez **Publier tous**.

    ![Bouton Publier tous.](media/ADF-3.png)

### <a name="setup-to-run-the-party-electronic-address-template"></a>Configuration pour exécuter le modèle d’adresse électronique de partie

1. Dans Data Factory, sur l’onglet **Gérer**, sous **Paramètres globaux**, créez les paramètres globaux suivants.

    | Nombre | Name | Type | Valeur |
    |---|---|---|---|
    | 1 | IsFOSource | bool | Ce paramètre détermine quelles adresses système principales sont remplacées en cas de conflit. Si la valeur est **true**, les adresses principales dans les applications Finances et Opérations remplaceront les adresses principales dans les applications d’engagement client. Si la valeur est **false**, les adresses principales dans les applications d’engagement client remplaceront les adresses principales dans les applications Finances et Opérations. |
    | 2 | ElectronicAddressIdPrefix | chaîne | Ce paramètre ajoute un numéro de série aux adresses électroniques nouvellement créées en tant que préfixe. Assurez-vous de fournir une chaîne qui n’entre pas en conflit avec les adresses électroniques dans les applications Finances et Opérations et les applications d’engagement client. Pour cet exemple, utilisez **ADF-EAD-**. |

    ![Paramètres globaux IsFOSource et ElectronicAddressIdPrefix créés dans l’onglet Gérer.](media/ADF-4.png)

2. Lorsque vous avez terminé, sélectionnez **Publier tous**.

## <a name="run-the-templates"></a>Exécution des modèles

1. Arrêtez les mappages de double écriture de **Compte**, **Contact** et **Fournisseur** qui utilisent l’application Finances et Opérations :

    + Clients V3 (accounts)
    + Clients V3 (contacts)
    + CDS Contacts V2 (contacts)
    + CDS Contacts V2 (contacts)
    + Fournisseurs V2 (msdyn_vendor)

2. Assurez-vous que les cartes sont supprimées de la table **msdy_dualwriteruntimeconfig** dans Dataverse.
3. Installez [Solutions de double écriture pour les Carnets d’adresses global et de partie](https://aka.ms/dual-write-gab) à partir de AppSource.
4. Dans l’application Finances et Opérations, exécutez la **Synchronisation initiale** si les tables suivantes contiennent des données :

    + Salutations
    + Type de caractère personnel
    + Politesses
    + Titres des contacts
    + Rôles de prise de décision
    + Niveaux de fidélité

5. Dans l’application Customer Engagement, désactivez les étapes suivantes du plug-in :

    + Mise à jour du compte

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity : Mise à jour du compte
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes : Mise à jour du compte

    + Mise à jour du contact

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity : Mise à jour du contact
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact : Mise à jour du contact

    + Mise à jour de msdyn_party

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity : Mise à jour de msdyn_party

    + Mise à jour de msdyn_vendor

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity : Mise à jour de msdyn_vendor

    + Customeraddress

        + Créer

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: création de l’adresse client

        + Mettre à jour

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: mise à jour de l’adresse client

        + Supprimer

            + Microsoft.Dynamics.GABExtended.Plugins.DeleteCustomerAddress: suppression de l’adresse client

    + msdyn_partypostaladdress

        + Créer

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: création de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: création de msdyn_partypostaladdress

        + Mettre à jour

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: mise à jour de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: mise à jour de msdyn_partypostaladdress

    + msdyn_postaladdress

        + Créer

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: création de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: création de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: création de msdyn_postaladdress

        + Mettre à jour

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: mise à jour de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: mise à jour de msdyn_postaladdress

    + msdyn_partyelectronicaddress

        + Créer

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: création de msdyn_partyelectronicaddress

        + Mettre à jour

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: mise à jour de msdyn_partyelectronicaddress

        + Supprimer

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: suppression de msdyn_partyelectronicaddress

6. Dans l’application d’engagement client, désactivez les workflows suivants :

    + Créer des fournisseurs dans la table Comptes
    + Créer des fournisseurs dans la table Comptes
    + Créer des fournisseurs de type Personne dans la table Contacts
    + Créer des fournisseurs de type Personne dans la table Fournisseurs
    + Mettre à jour des fournisseurs dans la table Comptes
    + Mettre à jour des fournisseurs dans la table Fournisseurs
    + Mettre à jour des fournisseurs de type Personne dans la table Contacts
    + Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs

7. Dans la fabrique de données, exécutez le modèle en sélectionnant **Déclencher maintenant**, comme indiqué dans l’illustration suivante. Ce processus peut prendre quelques heures, en fonction du volume de données.

    ![Exécution du modèle.](media/data-factory-trigger.png)

    > [!NOTE]
    > Si vous avez des personnalisations pour **Compte**, **Contact** et **Fournisseur**, vous devez modifier le modèle.

8. Importez les nouveaux enregistrements **Partie** dans l’application Finances et Opérations.

    1. Téléchargez le fichier **FONewParty.csv** à partir du stockage blob Azure. Le chemin est **partybootstrapping/output/FONewParty.csv**.
    2. Convertissez le fichier **FONewParty.csv** en fichier Excel et importez le fichier Excel dans l’application Finances et Opérations. Si l’importation CSV fonctionne pour vous, vous pouvez importer le fichier .csv directement. Cette étape peut prendre quelques heures, en fonction du volume de données. Pour plus d’informations, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../data-import-export-job.md).

    ![Importation des enregistrements de partie Dataverse.](media/data-factory-import-party.png)

9. Dans la fabrique de données, exécutez les modèles d’adresse postale de partie et d’adresse électronique de partie, l’un après l’autre.

    + Le modèle d’adresse postale de partie met à jour tous les enregistrements d’adresses postales dans l’application Customer Engagement et les associe aux enregistrements **Compte**, **Contact**, et **Fournisseur**. Il génère également trois fichiers .csv : ImportFONewPostalAddressLocation.csv, ImportFONewPartyPostalAddress.csv et ImportFONewPostalAddress.csv.
    + Le modèle d’adresse électronique de partie met à jour toutes les adresses électroniques dans l’application Customer Engagement et les associe aux enregistrements **Compte**, **Contact**, et **Fournisseur**. Il génère également un fichier .csv : ImportFONewElectronicAddress.csv.

    ![Exécution des modèles d’adresse postale et d’adresse électronique de partie.](media/ADF-7.png)

10. Pour mettre à jour l’application Finances et Opérations avec ces données, vous devez convertir les fichiers .csv en classeur Excel et [les importer dans l’application Finances et Opérations](/data-entities/data-import-export-job). Si l’importation CSV fonctionne pour vous, vous pouvez importer les fichiers .csv directement. Cette étape peut prendre quelques heures, en fonction du volume de données.

    ![Importation réussie.](media/ADF-8.png)

11. Dans l’application Customer Engagement, désactivez les étapes suivantes du plug-in :

    + Mise à jour du compte

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity : Mise à jour du compte
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes : Mise à jour du compte

    + Mise à jour du contact

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity : Mise à jour du contact
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact : Mise à jour du contact

    + Mise à jour de msdyn_party

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity : Mise à jour de msdyn_party

    + Mise à jour de msdyn_vendor

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity : Mise à jour de msdyn_vendor

    + msdyn_partypostaladdress

        + Créer

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: création de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: création de msdyn_partypostaladdress

        + Mettre à jour

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: mise à jour de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: mise à jour de msdyn_partypostaladdress

    + msdyn_postaladdress

        + Créer

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: création de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: création de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: création de msdyn_postaladdress

        + Mettre à jour

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: mise à jour de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: mise à jour de msdyn_postaladdress
 
    + msdyn_partyelectronicaddress

        + Créer

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: création de msdyn_partyelectronicaddress

        + Mettre à jour

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: mise à jour de msdyn_partyelectronicaddress

        + Supprimer

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: suppression de msdyn_partyelectronicaddress

12. Dans l’application Customer Engagement, activez les workflows suivants si vous les avez désactivés précédemment :

    + Créer des fournisseurs dans la table Comptes
    + Créer des fournisseurs dans la table Comptes
    + Créer des fournisseurs de type Personne dans la table Contacts
    + Créer des fournisseurs de type Personne dans la table Fournisseurs
    + Mettre à jour des fournisseurs dans la table Comptes
    + Mettre à jour des fournisseurs dans la table Fournisseurs
    + Mettre à jour des fournisseurs de type Personne dans la table Contacts
    + Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs

13. Exécutez les cartes associées à l’enregistrement **Partie** comme indiqué dans [Partie et carnet d’adresses global](party-gab.md).

## <a name="explanation-of-the-data-factory-templates"></a>Explication des modèles de Data Factory

Cette section vous guide à travers les étapes de chaque modèle Data Factory.

### <a name="steps-in-the-party-template"></a>Étapes du modèle Partie

1. Les étapes 1 à 6 identifient les entreprises qui sont activées pour la double écriture et créent une clause de filtre pour elles.
2. Les étapes 7-1 à 7-9 récupèrent les données à la fois de l’application Finances et Opérations et de l’application d’engagement client, et préparent ces données pour la mise à niveau.
3. Les étapes 8 à 9 comparent le numéro de partie pour les enregistrements **Compte**, **Contact** et **Fournisseur** entre l’application Finances et Opérations et l’application d’engagement client. Les enregistrements qui n’ont pas de numéro de partie sont ignorés.
4. L’étape 10 génère deux fichiers .csv pour les enregistrements de partie qui doivent être créés dans l’application d’engagement client et l’application Finances et Opérations.

    - **FOCDSParty.csv** : Ce fichier contient tous les enregistrements de partie des deux systèmes, que l’entreprise soit ou non activée pour la double écriture.
    - **FONewParty.csv** : ce fichier contient un sous-ensemble des enregistrements de partie connus de Dataverse (par exemple, les comptes de type **Prospect**).

5. L’étape 11 crée les parties dans l’application Customer Engagement.
6. L’étape 12 récupère les identificateurs globaux uniques (GUID) des parties à partir de l’application Customer Engagement et les adapte afin qu’ils puissent être associés aux enregistrements de **Compte**, **Contact**, et **Fournisseur** dans les étapes suivantes.
7. L’étape 13 associe les enregistrements de **Compte**, **Contact**, et **Fournisseur** avec des GUID de partie.
8. Les étapes 14-1 à 14-3 mettent à jour les enregistrements de **Compte**, **Contact**, et **Fournisseur** dans l’application Customer Engagement avec les GUID de partie.
9. Les étapes 15-1 à 15-3 préparent les enregistrements de **Contact pour la partie** pour les enregistrements de **Compte**, **Contact**, et **Fournisseur**.
10. Les étapes 16-1 à 16-7 récupèrent les données de référence telles que les salutations et les types de caractères personnels, et les associent aux enregistrements de **Contact pour la partie**.
11. L’étape 17 fusionne les enregistrements de **Contact pour la partie** pour les enregistrements de **Compte**, **Contact**, et **Fournisseur**.
12. L’étape 18 importe les enregistrements de **Contact pour la partie** dans l’application Customer Engagement.

### <a name="steps-in-the-party-postal-address-template"></a>Étapes du modèle d’adresse postale de partie.

1. Les étapes 1-1 à 1-10 récupèrent les données à la fois de l’application Finances et Opérations et de l’application d’engagement client, et préparent ces données pour la mise à niveau.
2. L’étape 2 dénormalise les données d’adresse postale dans l’application Finances et Opérations en joignant l’adresse postale et l’adresse postale de partie.
3. L’étape 3 déduplique et fusionne les données de compte, de contact et d’adresse du fournisseur à partir de l’application Customer Engagement.
4. L’étape 4 crée des fichiers .csv pour l’application Finances et Opérations pour créer de nouvelles données d’adresse basées sur les adresses de compte, de contact et de fournisseur.
5. L’étape 5-1 crée des fichiers .csv pour l’application Customer Engagement afin de créer toutes les données d’adresse, en fonction de l’application Finances et Opérations et de l’application d’engagement client.
6. L’étape 5-2 convertit les fichiers .csv dans le format d’importation Finance and Operations pour l’importation manuelle.

    - ImportFONewPostalAddressLocation.csv
    - ImportFONewPartyPostalAddress.csv
    - ImportFONewPostalAddress.csv

7. L’étape 6 importe les données de collecte d’adresses postales dans l’application Customer Engagement.
8. L’étape 7 récupère les données de collecte d’adresses postales de l’application Customer Engagement.
9. L’étape 8 crée des données d’adresse client et associe un ID de collecte d’adresse postale.
10. Les étapes 9-1 à 9-2 associent les ID de collecte de partie et d’adresse postale aux adresses postales et aux adresses postales de partie.
11. Les étapes 10-1 à 10-3 importent les adresses des clients, les adresses postales et les adresses postales de partie dans l’application Customer Engagement.

### <a name="steps-in-the-party-electronic-address-template"></a>Étapes du modèle d’adresse électronique de partie.

1. Les étapes 1-1 à 1-5 récupèrent les données à la fois de l’application Finances et Opérations et de l’application d’engagement client, et préparent ces données pour la mise à niveau.
2. L’étape 2 consolide les adresses électroniques dans l’application Customer Engagement à partir des entités de compte, de contact et de fournisseur.
3. L’étape 3 fusionne les données d’adresse électronique principales de l’application d’engagement client et de l’application Finances et Opérations.
4. L’étape 4 crée des fichiers .csv.

    - Créez de nouvelles données d’adresse électronique pour l’application Finances et Opérations, en fonction des adresses de compte, de contact et de fournisseur.
    - Créez de nouvelles données d’adresse électronique pour l’application d’engagement client, en fonction de l’adresse électronique, du compte, des adresses de contact et de fournisseur dans l’application Finances et Opérations.

5. L’étape 5-1 importe les adresses électroniques dans l’application Customer Engagement.
6. L’étape 5-2 crée des fichiers .csv pour mettre à jour les adresses principales des comptes et des contacts dans l’application Customer Engagement.
7. Les étapes 6-1 à 6-2 importent les comptes et les adresses principales de contact dans l’application Customer Engagement.

## <a name="troubleshooting"></a>Résolution des problèmes

1. Si le processus échoue, ré-exécutez la fabrique de données. Commencez à partir de l’activité ayant échoué.
2. Certains fichiers qui sont générés par la fabrique de données peuvent être utilisés à des fins de validation des données.
3. La fabrique de données s’exécute sur la base de fichiers .csv. Par conséquent, si une valeur de champ comporte une virgule, cela peut interférer avec les résultats. Vous devez supprimer toutes les virgules des valeurs de champ.
4. L’onglet **Surveillance** fournit des informations sur toutes les étapes et les données qui ont été traitées. Sélectionnez une étape spécifique pour la déboguer.

    ![Onglet Surveillance.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>En savoir plus sur le modèle

Pour plus d’informations sur le modèle, voir [Commentaires pour le fichier Lisez-moi du modèle Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).
