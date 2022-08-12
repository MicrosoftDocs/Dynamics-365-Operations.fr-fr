---
title: Activer la recherche des données de base pour la configuration du calcul des taxes
description: Cet article explique comment configurer et activer la fonctionnalité de recherche de données principales pour le calcul des taxes.
author: kai-cloud
ms.date: 07/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3642bb88d5b0570014513b64eef5fdab6d1ee9d3
ms.sourcegitcommit: 5b721f6fc1ba4350b5bd0eae457f71d80246db42
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/20/2022
ms.locfileid: "9181122"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Activer la recherche des données de base pour la configuration du calcul des taxes 

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer et activer la fonctionnalité de recherche de données principales pour le calcul des taxes. Une liste déroulante est disponible pour sélectionner des valeurs dans la configuration de calcul des taxes pour des champs tels que **Entité juridique**, **Compte fournisseur**, **Code article** et **Conditions de livraison**. Ces valeurs proviennent du de l’environnement connecté Microsoft Dynamics 365 Finance en utilisant la source de données Microsoft Dataverse.

> [!NOTE] 
> La fonctionnalité de recherche des données principales du calcul des taxes est une fonctionnalité facultative. Vous pouvez ignorer les étapes suivantes si vous désactivez la fonctionnalité **Prise en charge des sources de données Dataverse du service fiscal** dans le service Regulatory Configuration Service (RCS). Cependant, dans ce cas, la liste déroulante ne sera pas disponible dans la configuration du calcul des taxes.

Pour activer la liste déroulante dans la configuration de la version de fonctionnalité du calcul de la taxe, procédez comme suit.

1. [Activez l’intégration Microsoft Power Platform et ouvrez l’environnement Dataverse.](#enable)
2. [Installez les entités virtuelles des applications de finances et d’opérations.](#install)
3. [Enregistrez une application Azure Active Directory Azure AD.](#register)
4. [Accordez des autorisations d’application dans les applications de finances et d’opérations.](#grant)
5. [Configurez la source de données d’entité virtuelle.](#configure)
6. [Activez les entités virtuelles de Dataverse.](#virtual)
7. [Configurez l’application connectée pour le calcul des taxes.](#set-up)
8. [Importez et configurez la mise en correspondance de modèle Dataverse.](#import)

## <a name="enable-microsoft-power-platform-integration-and-open-the-dataverse-environment"></a><a name='enable'></a>Activer l’intégration Microsoft Power Platform et ouvrir l’environnement Dataverse

L’intégration des applications de finances et d’opérations avec Microsoft Power Platform peut être activée lorsque vous créez un environnement d’applications de finances et d’opérations dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir la rubrique [Intégration de Microsoft Power Platform - Vue d’ensemble des compléments](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Une fois cette étape terminée, le nom d’un environnement Microsoft Power Platform apparaîtra dans la section **Intégration Power Platform**.

1. Dans LCS, dans votre environnement de finances et d’opérations, dans la section **Intégration Power Platform**, recherchez et notez la valeur **Nom de l’environnement** pour l’environnement lié.

    [![Valeur du nom de l’environnement.](./media/tcs-dataverse-master-data-lookup-1.png)](./media/tcs-dataverse-master-data-lookup-1.png)

2. Dans le [centre d’administration Power Platform](https://admin.powerplatform.microsoft.com/environments), sur l’onglet **Environnements**, sélectionnez l’environnement qui correspond à la valeur **Nom de l’environnement** que vous avez notée.
3. Sur la page **Détails**, recherchez la valeur **URL de l’environnement** de l’environnement Dataverse. Notez cette valeur, car vous en aurez besoin dans [Étape 7. Configurer l’application connectée pour le calcul des taxes](#set-up).
4. Assurez-vous que vous pouvez ouvrir l’environnement Dataverse dans votre navigateur en sélectionnant la valeur **URL de l’environnement**.

    [![Page de l’environnement Dataverse.](./media/tcs-dataverse-master-data-lookup-2.png)](./media/tcs-dataverse-master-data-lookup-2.png)

    > [!NOTE]
    > Gardez l’environnement Dataverse ouvert dans votre navigateur. Vous en aurez besoin dans [Étape 5. Configurer la source de données de l’entité virtuelle](#configure).

Pour plus d’informations, voir [Activer l’intégration de Microsoft Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

## <a name="install-finance-and-operations-virtual-entities"></a><a name='install'></a>Installer les entités virtuelles des applications de finances et d’opérations

La solution Dataverse pour les entités virtuelles des finances et des opérations doit être installée à partir de la solution d’entité virtuelle Microsoft AppSource.

1. Dans AppSource, recherchez l’[entité virtuelle de finances et d’opérations](https://appsource.microsoft.com/product/dynamics-365/mscrm.finance_and_operations_virtual_entity).
2. Sélectionnez **L’obtenir maintenant**.
3. Dans le champ **Sélectionner un environnement**, saisissez la valeur **Nom de l’environnement** que vous avez notée précédemment.
4. Cochez les cases, puis sélectionnez **Installer**.

Lorsque l’installation est terminée, vous pouvez trouver l’application **Entité virtuelle de finances et d’opérations** dans le [centre d’administration Power Platform](https://admin.powerplatform.microsoft.com/), sous **Ressources** \>**Applications Dynamics 365**.

Pour plus d’informations, voir [Obtenir la solution des entités virtuelles](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution).

## <a name="register-an-azure-ad-application"></a><a name='register'></a>Inscrire une application Azure AD

Vous devez enregistrer une application Azure AD sur le même client que les applications de finances et d’opérations, afin qu’elles puissent être appelées par Dataverse.

1. Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory \> Inscriptions d’applications**.
2. Sélectionnez **Nouvelle inscription**, puis entrez les informations suivantes :

    - **Nom** : saisissez un nom unique.
    - **Type de compte** : saisissez **Tout répertoire Azure AD** (mono-client ou multi-client).
    - **URI de redirection :** laissez ce champ vide.

3. Sélectionnez **Enregistrer**.
4. Notez la valeur dans le champ **ID d’application (client)**, car vous en aurez besoin ultérieurement.

    [![Valeur d’ID (client) d’application Azure AD.](./media/tcs-dataverse-master-data-lookup-3.png)](./media/tcs-dataverse-master-data-lookup-3.png)

5. Créez une clé symétrique pour l’application.
6. Dans la nouvelle application, sélectionnez **Certificats et clés secrètes**.
7. Sélectionnez **Nouvelle clé secrète client**.
8. Saisissez une description, sélectionnez une date d’expiration, puis **Enregistrer**. Une clé sera créée et affichée. Copiez la valeur pour une utilisation ultérieure.

Pour plus d’informations, voir [Inscrire l’application Azure AD](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#register-the-app-in-the-azure-portal).

## <a name="grant-app-permissions-in-finance-and-operations-apps"></a><a name='grant'></a>Accorder des autorisations d’application dans les applications de finances et d’opérations

Dataverse utilise l’application Azure AD que vous avez créée pour appeler des applications de finances et d’opérations. Par conséquent, l’application doit être approuvée par les applications de finances et d’opérations et associée à un compte utilisateur disposant des droits appropriés. Dans les applications de finances et d’opérations, vous devez créer un utilisateur de service spécial qui dispose de droits **seulement** à la fonctionnalité d’entité virtuelle. Cet utilisateur du service ne doit avoir aucun autre droit. Après avoir terminé cette étape, toute application disposant de la clé secrète de l’application Azure AD que vous avez créée pourra appeler l’environnement des applications de finances et d’opérations et accéder à la fonctionnalité d’entité virtuelle.

1. Dans votre environnement, accédez à **Administration système** \> **Utilisateurs** \> **Utilisateurs**.
2. Sélectionnez **Nouveau** pour ajouter un nouvel utilisateur et entrez les informations de champ suivantes :

    - **Identifiant utilisateur** : saisissez **dataverseintegration** ou une autre valeur.
    - **Nom d’utilisateur** : saisissez **intégration dataverse** ou une autre valeur.
    - **Fournisseur** : définissez ce champ sur **NonAAD**.
    - **E-mail** : saisissez **dataverseintegration** ou une autre valeur. (La valeur ne doit pas nécessairement être un compte de messagerie valide.)

3. Affectez le rôle de sécurité à l’utilisateur **application de l’entité virtuelle CDS**.
4. Supprimez tous les autres rôles, y compris **Utilisateur système**.
5. Accédez à **Administration système** \> **Paramétrage** \> **Applications Azure Active Directory** pour inscrire Dataverse. 
6. Ajoutez une ligne, puis, dans le champ **ID client**, saisissez la valeur **ID (client) de l’application** que vous avez notée précédemment.
7. Dans le champ **Nom**, entrez un nom. Pour cet exemple, saisissez **Intégration Dataverse**.
8. Dans le champ **ID utilisateur**, saisissez l’identifiant utilisateur créé précédemment.

Pour plus d’informations, voir [Accorder des autorisations d’application dans les applications de finances et d’opérations](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#grant-app-permissions-in-finance-and-operations-apps).

## <a name="configure-the-virtual-entity-data-source"></a><a name='configure'></a>Configurer la source de données d'entité virtuelle

Vous devez fournir Dataverse avec l’instance d’application de finances et d’opérations à laquelle se connecter.

1. Votre environnement Dataverse doit toujours être ouvert dans votre navigateur depuis [Étape 1. Activer l’intégration Microsoft Power Platform et ouvrir l’environnement Dataverse](#enable). Sélectionnez le bouton Paramètres (le symbole d’engrenage) dans l’angle de droite, puis sélectionnez **Paramètres avancés**.

    [![Ouverture des paramètres avancés dans l’environnement Dataverse.](./media/tcs-dataverse-master-data-lookup-4.png)](./media/tcs-dataverse-master-data-lookup-4.png)

2. Dans le menu déroulant **Paramètres**, sélectionnez **Administration**.

    [![Administration.](./media/tcs-dataverse-master-data-lookup-5.png)](./media/tcs-dataverse-master-data-lookup-5.png)

3. Sélectionnez **Sources de données d’entité virtuelle**.

    [![Sources de données d’entité virtuelle.](./media/tcs-dataverse-master-data-lookup-6.png)](./media/tcs-dataverse-master-data-lookup-6.png)

4. Sélectionnez la source de données intitulée **Finances et opérations**.

    [![Source de données de finances et d’opérations.](./media/tcs-dataverse-master-data-lookup-7.png)](./media/tcs-dataverse-master-data-lookup-7.png)

5. Entrez les informations suivantes depuis les étapes précédentes :

    - **URL cible** : entrez l’URL où vous pouvez accéder aux applications de finances et d’opérations.
    - **URL OAuth** : saisissez `https://login.windows.net/`.
    - **ID de client** : précisez votre client. Cette valeur peut être le nom de domaine de l’e-mail de votre entreprise (comme contoso.com).
    - **ID de l’application AAD** : saisissez la valeur de l’**ID (client) d’application** que vous avez créé précédemment.
    - **Clé secrète de l’application AAD** : saisissez la clé secrète qui a été générée précédemment.
    - **Ressource AAD** : saisissez **00000015-0000-0000-c000-000000000000**. Cette valeur est l’application Azure AD qui représente les applications de finances et d’opérations. Il doit toujours s’agir de cette même valeur.

6. Enregistrez vos modifications.
7. Fermez la page pour revenir à la page **Administration**, où vous commencerez à l’[Étape 6. Activer les entités virtuelles Dataverse](#virtual).

    [![Fermeture de l’entité pour modification.](./media/tcs-dataverse-master-data-lookup-8.png)](./media/tcs-dataverse-master-data-lookup-8.png)

Pour plus d’informations, voir [Configurer la source de données des entités virtuelles](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#configure-the-virtual-entity-data-source).

## <a name="enable-dataverse-virtual-entities"></a><a name='virtual'></a>Activer les entités virtuelles de Dataverse

La visibilité des entités virtuelles à partir des applications de finances et d’opérations doit être définie sur **Oui** avant qu’elles puissent être utilisées par la configuration du calcul des taxes.

> [!NOTE]
> Vous pouvez ignorer cette étape en activant les entités virtuelles liées au calcul des taxes en un seul clic à l’[Étape 8. Configurer l’application connectée pour le calcul des taxes](#import). Cependant, nous vous recommandons d’activer manuellement au moins une entité virtuelle, pour indiquer que la connexion entre les applications de finances et d’opérations et Dataverse est bien établie.

1. Dans votre environnement Dataverse, sur la page **Administration**, sélectionnez le bouton de filtre (symbole d’entonnoir) dans l’angle supérieur droit.

    [![Bouton de filtre.](./media/tcs-dataverse-master-data-lookup-9.png)](./media/tcs-dataverse-master-data-lookup-9.png)

2. Dans la fenêtre **Recherche avancée**, dans le champ **Rechercher**, sélectionnez **Entités de finances et d’opérations disponibles**.
3. Ajoutez la règle suivante : **Nom** – **Contient** – **CompanyInfoEntity**. Puis sélectionnez **Résultats**.

    [![Fenêtre de recherche avancée.](./media/tcs-dataverse-master-data-lookup-10.png)](./media/tcs-dataverse-master-data-lookup-10.png)

4. Sélectionnez **CompanyInfoEntity** dans les résultats de la recherche, cochez la case **Visible**, puis sélectionnez **Enregistrer**.

    [![Définition de la visibilité de l’entité.](./media/tcs-dataverse-master-data-lookup-11.png)](./media/tcs-dataverse-master-data-lookup-11.png)

5. Répétez les étapes précédentes pour les entités suivantes auxquelles il est fait référence dans la configuration du calcul des taxes :

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity
    - InventOperationalSiteV2Entity
    - TaxExemptCodeEntity
    - InventWarehouseEntity

    > [!NOTE]
    > Seuls les 5 000 premiers enregistrements d’une entité peuvent être récupérés par Dataverse et mis à disposition dans la liste déroulante de la configuration Calcul des taxes.

Pour plus d’informations, consultez [Activer des entités virtuelles Microsoft Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="set-up-the-connected-application-for-tax-calculation"></a><a name='set-up'></a>Configurer l’application connectée pour le calcul des taxes

1. Dans RCS, ouvrez l’espace de travail **Gestion des fonctionnalités**, puis activez les fonctionnalités suivantes :

    - Prise en charge des sources de données de la gestion des états électroniques Dataverse
    - Prise en charge des sources de données Dataverse du service fiscal
    - Fonctionnalités de globalisation

2. Accédez à **Génération d’états électroniques**, dans la section **Liens connexes**, sélectionnez **Applications connectées**.

    [![Applications connectées.](./media/tcs-dataverse-master-data-lookup-12.png)](./media/tcs-dataverse-master-data-lookup-12.png)

3. Sélectionnez **Nouveau** pour ajouter un enregistrement et entrez les informations suivantes.

    - **Nom** – Entrez un nom.
    - **Type** : sélectionnez **Dataverse**.
    - **Application** : saisissez la valeur de l’environnement Dataverse, **URL de l’environnement**, que vous avez notée à l’[Étape 1. Activer l’intégration de Microsoft Power Platform et ouvrez votre environnement Dataverse](#enable).
    - **Client** : saisissez votre client.
    - **Custom URL** : saisissez votre URL Dataverse, et ajoutez-y **/api/data/v9.1**.

4. Sélectionnez **Vérifier la connexion**, puis, dans la boîte de dialogue qui s’affiche, sélectionnez **Cliquer ici pour vous connecter à l’application distante sélectionnée**.

    [![Vérification de la connexion.](./media/tcs-dataverse-master-data-lookup-13.png)](./media/tcs-dataverse-master-data-lookup-13.png)
5. Veillez à bien recevoir un message « Réussi ! » indiquant que la connexion a été établie avec succès.

    [![Message de réussite.](./media/tcs-dataverse-master-data-lookup-14.png)](./media/tcs-dataverse-master-data-lookup-14.png)

## <a name="import-and-set-up-the-dataverse-model-mapping-configuration"></a><a name='import'></a>Importer et configurer la mise en correspondance de modèle Dataverse

Microsoft fournit des configurations de mappage de modèle par défaut pour les entités des applications de finances et d’opérations au calcul des taxes.

1. Dans RCS, accédez à **États électroniques**.
2. Dans la section **Fournisseurs de configuration**, sur la vignette du fournisseur **Microsoft**, sélectionnez **Référentiels**.

    [![Référentiels.](./media/tcs-dataverse-master-data-lookup-15.png)](./media/tcs-dataverse-master-data-lookup-15.png)

3. Sélectionnez l’enregistrement **Référentiel de configuration globale**, puis sélectionnez **Ouvrir**.
4. Sous **Modèle de données fiscales** \>**Modèle de données de calcul des taxes**, sélectionnez la configuration **Mappage du modèle Dataverse**.
5. Sur le raccourci **Versions**, sélectionnez une version qui correspond à la version de vos applications de finances et d’opérations, puis sélectionnez **Importer**.

    [![Importer la configuration de mise en correspondance des modèles Dataverse.](./media/tcs-dataverse-master-data-lookup-16.png)](./media/tcs-dataverse-master-data-lookup-16.png)

    > [!IMPORTANT]
    > La configuration de la **mise en correspondance des modèles Dataverse** n’est effective que sur sa version importée au numéro le plus élevé. Par conséquent, vous ne devez pas importer une version de la configuration de la **mise en correspondance des modèles Dataverse** supérieure à la version de la configuration de calcul des taxes que vous prévoyez d’implémenter. Par exemple, si vous prévoyez d’implémenter la version 40.50.225 de la configuration du calcul des taxes, vous ne devez importer que la version 40.50.13 de la configuration de la **mise en correspondance des modèles Dataverse**. Vous ne devez pas importer la version 40.54.14. Sinon, il y aura une incompatibilité de modèle de données dans la configuration.

6. Revenez à **Gestion des états électroniques**, et sélectionnez la vignette **Configurations de taxe**.
7. Sélectionnez la configuration **Mise en correspondance des modèles Dataverse**, puis sélectionnez **Modifier**.
8. Définissez l’option **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.
9. Dans la champ **Application connectée**, sélectionnez l’application connectée que vous avez configurée à l’[Étape 7. Configurer l’application connectée pour le calcul des taxes](#set-up).
10. Définissez l’option **Définir la visibilité de la table virtuelle** sur **Oui** pour définir toutes les entités virtuelles associées au calcul des taxes sur visibles.

Vous avez maintenant terminé la configuration de la fonctionnalité de recherche des données de base. Une liste déroulante pour des champs tels que **Entité juridique**, **Compte fournisseur**, **Code de l’article**, et **Conditions de livraison** de Dynamics 365 Finance sera désormais activée dans la configuration **Version de la fonctionnalité de calcul des taxes**.

[![Liste déroulante des entités juridiques.](./media/tcs-dataverse-master-data-lookup-17.png)](./media/tcs-dataverse-master-data-lookup-17.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
