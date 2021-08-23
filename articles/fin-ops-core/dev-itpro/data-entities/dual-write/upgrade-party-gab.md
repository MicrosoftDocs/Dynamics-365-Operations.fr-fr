---
title: Effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global
description: Cette rubrique décrit comment mettre à niveau les données à double écriture en modèle de carnet d’adresses global et de partie.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 673c3a68e2eccdabdfc2df281389537297ec3524bee5e744e910c50d38b8d298
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720686"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Le [Modèle Microsoft Azure Data Factory](https://aka.ms/dual-write-gab-adf) vous aide à mettre à niveau les données des tables **Compte**, **Contact** et **Fournisseur** existantes en double écriture vers le modèle de partie et de carnet d’adresses global. Le modèle rapproche les données des applications Finance and Operations et des applications Customer Engagement. À la fin du processus, les champs **Partie** et **Contact** des enregistrements **Partie** seront créés et associés aux enregistrements **Compte**, **Contact** et **Fournisseur** dans les applications d’engagement client. Un fichier .csv (`FONewParty.csv`) est généré pour créer de nouveaux enregistrements de **Partie** à l’intérieur de l’application Finance and Operations. Cette rubrique fournit des instructions sur l’utilisation du modèle Data Factory et la mise à niveau de vos données.

Si vous n’avez aucune personnalisation, vous pouvez utiliser le modèle tel quel. Si vous avez des personnalisations pour **Compte**, **Contact** et **Fournisseur**, vous devez modifier le modèle en suivant les instructions ci-après.

> [!NOTE]
> Le modèle ne met à niveau que les données de **Partie**. Dans une prochaine version, les adresses postales et électroniques seront incluses.

## <a name="prerequisites"></a>Conditions préalables

Les conditions préalables suivantes sont requises pour effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global :

+ [Abonnement Azure](https://portal.azure.com/)
+ [Accès au modèle](https://aka.ms/dual-write-gab-adf)
+ Vous devez déjà être client de la double écriture.

## <a name="prepare-for-the-upgrade"></a>Préparation pour la mise à niveau
Les activités suivantes sont nécessaires pour préparer la mise à niveau :

+ **Entièrement synchronisé** : les deux environnements sont dans un état entièrement synchronisé pour **Compte (client)**, **Contact** et **Fournisseur**.
+ **Clés d’intégration** : les tables **Compte (client)**, **Contacter** et **Fournisseur** dans les applications d’engagement client utilisent les clés d’intégration livrées prêtes à l’emploi. Si vous avez personnalisé les clés d’intégration, vous devez personnaliser le modèle.
+ **Numéro de partie** : tous les enregistrements **Compte (client)**, **Contact** et **Fournisseur** qui seront mis à niveau ont un numéro de **Partie**. Les enregistrements sans numéro de **Partie** seront ignorés. Si vous souhaitez mettre à niveau ces enregistrements, ajoutez-leur un numéro de **Partie** avant de commencer le processus de mise à niveau.
+ **Panne du système** : pendant le processus de mise à niveau, vous devrez mettre hors connexion les environnements Finance and Operations et Customer Engagement.
+ **Instantané** : prenez des instantanés des applications Finance and Operations et des applications Customer Engagement. Utilisez les instantanés pour restaurer l’état précédent si nécessaire.

## <a name="deployment"></a>Déploiement

1. Téléchargez le modèle depuis [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).

2. Connectez-vous à [Microsoft Azure](https://portal.azure.com/).

3. Créez un [groupe de ressources](/azure/azure-resource-manager/management/manage-resource-groups-portal).

4. Créez un [compte de stockage](/azure/storage/common/storage-account-create?tabs=azure-portal) dans le groupe de ressources que vous avez créé.

5. Créez une [fabrique de données](/azure/data-factory/quickstart-create-data-factory-portal) dans le groupe de ressources que vous avez créé ci-dessus.

6. Ouvrez la fabrique de données et sélectionnez la vignette **Créer et surveiller**.

7. Dans l’onglet **Gérer**, sélectionnez **Modèle ARM**.

8. Sélectionnez **Importer un modèle ARM** pour importer le modèle **Partie**.

9. Importez le modèle dans la fabrique de données. Entrez les valeurs suivantes pour les **Détails du projet** et les **Détails de l’instance**.

    Champ | Valeur
    ---|---
    Abonnement | Abonnement Azure
    Groupe de ressources | Indiquez la même ressource sous laquelle le compte de stockage est créé.
    Région | Spécifiez la région.
    Nom de la fabrique | Spécifiez le nom de la fabrique.
    FO Linked Service_service Principal Key | Spécifiez la clé de l’application.
    Azure Blob Storage_connection String | Chaîne de connexion au Stockage Blob Azure
    Dynamics Crm Linked Service_password | Le mot de passe du compte d’utilisateur que vous avez spécifié comme nom d’utilisateur.
    FO Linked Service_properties_type Properties_url  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    FO Linked Service_properties_type Properties_tenant | Spécifiez les informations de locataire (nom de domaine ou ID de locataire) sous lesquelles réside votre application.
    FO Linked Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com`
    FO Linked Service_properties_type Properties_service Principal Id | Spécifiez l’ID du client de l’application.
    Dynamics Crm Linked Service_properties_type Properties_username | Le nom d’utilisateur pour se connecter à Dynamics 365.

    Pour des informations supplémentaires, consultez l’une des rubriques suivantes : 
    
    - [Promouvoir manuellement un modèle Resource Manager pour chaque environnement](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Propriétés du service lié](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Copier des données à l’aide d’Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Après le déploiement, vérifiez les jeux de données, le flux de données et le service lié de la fabrique de données.

   ![Jeux de données, flux de données et service lié.](media/data-factory-validate.png)

11. Accédez à **Gérer**. En dessous de **Connexions**, sélectionnez **Service lié**. Sélectionnez **DynamicsCrmLinkedService**. Dans le formulaire **Modifier le service lié (Dynamics CRM)**, entrez les valeurs suivantes.

    Champ | Valeur 
    ---|---
    Nom | DynamicsCrmLinkedService
    Description  | Services liés pour se connecter à l’instance CRM pour récupérer les données des entités
    Connexion via le runtime d’intégration | AutoResolvelntegrationRuntime
    Type de déploiement | En ligne
    URI du service | `https://<organization-name>.crm[x].dynamics.com`
    Type d’authentification | Office365
    Nom d’utilisateur |
    Mot de passe ou Azure Key Vault | Mot de passe
    Mot de passe |

## <a name="run-the-template"></a>Exécution du modèle

1. Arrêtez les mappages de double écriture de **Compte**, **Contact** et **Fournisseur** suivants à l’aide de l’application Finance and Operations.

    + Clients V3 (accounts)
    + Clients V3 (contacts)
    + CDS Contacts V2 (contacts)
    + CDS Contacts V2 (contacts)
    + Fournisseurs V2 (msdyn_vendor)

2. Assurez-vous que les cartes sont supprimées de la table `msdy_dualwriteruntimeconfig` dans Dataverse.

3. Installez [Solutions de double écriture pour les Carnets d’adresses global et de partie](https://aka.ms/dual-write-gab) à partir de AppSource.

4. Dans l’application Finance and Operations, si les tables suivantes contiennent des données, exécutez la **Synchronisation initiale** pour elles.

    + Salutations
    + Type de caractère personnel
    + Politesses
    + Titres des contacts
    + Rôles de prise de décision
    + Niveaux de fidélité

5. Dans l’application Customer Engagement, désactivez les étapes suivantes du plug-in.

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

6. Dans l’application d’engagement client, désactivez les workflows suivants :

    + Créer des fournisseurs dans la table Comptes
    + Créer des fournisseurs dans la table Comptes
    + Créer des fournisseurs de type Personne dans la table Contacts
    + Créer des fournisseurs de type Personne dans la table Fournisseurs
    + Mettre à jour des fournisseurs dans la table Comptes
    + Mettre à jour des fournisseurs dans la table Fournisseurs
    + Mettre à jour des fournisseurs de type Personne dans la table Contacts
    + Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs

7. Dans la fabrique de données, exécutez le modèle en sélectionnant **Déclencher maintenant**, comme indiqué dans l’image suivante. Ce processus peut prendre quelques heures, en fonction du volume de données.

    ![Déclencher l’exécution.](media/data-factory-trigger.png)

    > [!NOTE]
    > Si vous avez des personnalisations pour **Compte**, **Contact** et **Fournisseur**, vous devez modifier le modèle.

8. Importez les nouveaux enregistrements **Partie** dans l’application Finance and Operations.

    + Téléchargez le fichier `FONewParty.csv` à partir du stockage blob Azure. Le chemin d’accès est `partybootstrapping/output/FONewParty.csv`.
    + Convertissez le fichier `FONewParty.csv` en fichier Excel et importez le fichier Excel dans l’application Finance and Operations. Si l’importation csv fonctionne pour vous, vous pouvez importer le fichier csv directement. L’importation peut prendre quelques heures, selon le volume de données. Pour plus d’informations, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../data-import-export-job.md).

    ![Importer les enregistrements de partie de Dataverse.](media/data-factory-import-party.png)

9. Dans les applications Customer Engagement, désactivez les étapes suivantes du plug-in :

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

10. Dans les applications d’engagement client, activez les workflows suivants si vous les avez désactivés lors des étapes précédentes :

    + Créer des fournisseurs dans la table Comptes
    + Créer des fournisseurs dans la table Comptes
    + Créer des fournisseurs de type Personne dans la table Contacts
    + Créer des fournisseurs de type Personne dans la table Fournisseurs
    + Mettre à jour des fournisseurs dans la table Comptes
    + Mettre à jour des fournisseurs dans la table Fournisseurs
    + Mettre à jour des fournisseurs de type Personne dans la table Contacts
    + Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs

11. Exécutez les cartes associées à la **Partie** comme indiqué dans [Carnet d’adresses global et de partie](party-gab.md).

## <a name="troubleshooting"></a>Résolution des problèmes

1. Si le processus échoue, réexécutez la fabrique de données à partir de l’activité qui a échoué.
2. Certains fichiers sont générés par la fabrique de données ; vous pouvez les utiliser à des fins de validation des données.
3. La fabrique de données s’exécute sur la base de fichiers csv séparés par des virgules. Si une valeur de champ comporte une virgule, cela peut interférer avec les résultats. Vous devez supprimer les virgules.
4. L’onglet **Surveillance** fournit des informations sur toutes les étapes et les données traitées. Sélectionnez une étape spécifique pour la déboguer.

    ![Onglet Surveillance.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>En savoir plus sur le modèle

Vous trouverez des informations supplémentaires sur le modèle dans [Commentaires pour le fichier Lisez-moi du modèle Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).
