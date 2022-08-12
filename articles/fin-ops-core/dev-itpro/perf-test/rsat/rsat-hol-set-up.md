---
title: Didacticiel pour la configuration et l’installation de Regression Suite Automation Tool
description: Cet article est un didacticiel qui indique comment configurer et installer l’outil Regression Suite Automation Tool (RSAT).
author: tonyafehr
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: ced1300b268df9a6503ce1d33d74cae85ade3f20
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103148"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a>Didacticiel pour la configuration et l’installation de Regression Suite Automation Tool

Cet article est un didacticiel qui vous aide à paramétrer et faire vos premiers pas avec RSAT et les outils qui y sont associés.

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Utilisez les outils du navigateur Internet pour télécharger et enregistrer cette page au format PDF.

## <a name="key-concepts"></a>Concepts clés

- Appréhendez l’installation et le paramétrage préalable requis pour les différentes applications qui prennent en charge l’outil RSAT (Regression Suite Automation Tool).
- Découvrez comment la fonction d’enregistrement de tâches, ainsi que Microsoft Dynamics Lifecycle Services (LCS) et Microsoft Azure DevOps vous aident à créer, configurer, exécuter, étudier, et générer des rapports sur des scénarios de test.
- Donnez aux utilisateurs fonctionnels les moyens d’enregistrer les tâches métier à l’aide de l’enregistreur de tâches, puis de convertir ces enregistrements en une suite de tests automatisés, sans devoir écrire de code source.

## <a name="before-you-begin"></a>Avant de commencer

### <a name="prerequisites"></a>Conditions préalables

- Un environnement qui exécute la version 10.0 de Microsoft Dynamics 365 for Finance and Operations (avril 2019) ou une version ultérieure est requis pour ce didacticiel. Pour les clients utilisant Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, Platform Update 20 (PU20) ou version ultérieure est également prise en charge.
- L’utilisateur doit disposer de droits d’administrateur dans cet environnement.
- Vous devez avoir accès au LCS du client et à Azure DevOps (auparavant connu sous le nom de Microsoft Visual Studio Team Services \[VSTS\]).
- L’utilisateur qui crée et gère les suites de tests doit disposer d’une licence de plan de test ou de responsable de tests Azure DevOps. Les licences suivantes vous octroient également l’accès aux plans de test :
    - Licence Visual Studio Enterprise
    - Licence Visual Studio Test Professional
    - Licence d’abonné de plateformes MSDN
- RSAT doit avoir accès à l’environnement de test via un navigateur Web.
- Pour générer et modifier les paramètres de test, vous devez avoir Microsoft Excel installé.

## <a name="configure-azure-devops"></a>Configurer Azure DevOps

### <a name="user-eligibility"></a>Admissibilité des utilisateurs

Assurez-vous que l’utilisateur est créé dans Azure DevOps et dispose d’un niveau d’abonnement qui permet d’accéder aux plans de test Azure. Une licence de plans de test Azure DevOps n’est requise que si l’utilisateur crée et traite des scénarios de test (autrement dit, tous les utilisateurs de RSAT n’ont pas besoin de cette licence). Pour plus d’informations sur les exigences de licence, voir [Exigences relatives aux licences](/azure/devops/test/manual-test-permissions#license-requirements).

### <a name="create-a-new-azure-devops-project"></a>Créer un nouveau projet Azure DevOps

RSAT utilise Azure Devops pour gérer les scénarios de test et les suites de test, la génération d’états, et l’examen des résultats des essais.

> [!NOTE]
> Vous pouvez utiliser un projet Azure DevOps existant. Toutefois, si votre projet Azure DevOps existant est paramétré de sorte à disposer d’un modèle personnalisé, vous recevez un message d’erreur « Échec de synchronisation de VSTS » lors de la synchronisation de scénarios de test issus du Concepteur de processus d’entreprise (BPM) avec Azure DevOps (voir la section [Test de la synchronisation entre BPM et Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)). Si les bonnes pratiques suivantes ont été suivies pour le modèle personnalisé, vous pourrez synchroniser les scénarios de test avec Azure DevOps. (Ces bonnes pratiques sont répertoriées dans le message d’erreur.)

- Ne pas supprimer les types d’éléments de travail ou les champ prédéfinis.
- Ne pas supprimer l’état d’un type d’élément de travail.
- Ne pas ajouter de champs obligatoires à un type d’élément de travail.

![Message d’erreur avec une liste de pratiques recommandées.](./media/setup_rsa_tool_02.png)

Sinon, pour ce didacticiel, nous vous recommandons de créer un nouveau projet Azure DevOps. Pour plus d’informations, voir [Problèmes lors de la synchronisation avec BPM à l’aide d’un modèle de processus Azure DevOps (VSTS) personnalisé](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).

1. Ouvrez l’URL Azure DevOps (`https://dev.azure.com/<Azure DevOps Name>`).
2. Sélectionnez **Créer un projet** dans le coin supérieur droit de la page Azure DevOps.

    ![Créer un bouton de projet.](./media/setup_rsa_tool_03.png)

3. Renseignez les champs suivants, puis sélectionnez **Créer** :

    - **Nom du projet**
    - **Contrôle de version** – Sélectionnez **Contrôle de version Team Foundation**. Notez que l’option par défaut, **Git**, n’est pas prise en charge.
    - **Traitement d’élément de travail**

    ![Créer une boîte de dialogue de nouveau projet.](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a>Créer un jeton d’accès personnel

Dans ce didacticiel, vous allez utiliser le Concepteur de processus d’entreprise (BPM) LCS pour créer une bibliothèque de scénario de test et synchroniser vos scénarios de test avec Azure DevOps. Vous avez besoin d’un jeton personnel d’accès pour synchroniser BPM avec Azure DevOps.

1. Sélectionnez l’icône de profil dans le coin supérieur droit de la page pour le projet Azure DevOps, puis sélectionnez **Sécurité**.

    ![Commande de sécurité.](./media/setup_rsa_tool_05.png)

2. Dans le volet de gauche, sous **Sécurité**, sélectionnez **Jetons personnels d’accès**. Sélectionnez **Nouveau jeton**.

    ![Bouton Nouveau jeton de l’onglet Jetons personnels d’accès dans les Paramètres utilisateur.](./media/setup_rsa_tool_06.png)

3. Renseignez les champs suivants, puis sélectionnez **Créer** :

    - **Nom**
    - **Expiration (UTC)** – Sélectionnez **Personnalisé**, puis utilisez le sélecteur de date pour sélectionner la dernière date disponible.
    - **Champs d’application** – Sélectionnez l’option **Accès total**.

    ![Créer une boîte de dialogue de nouveau jeton personnel d’accès.](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > Notez le jeton personnel d’accès créé. Vous aurez besoin de lui ultérieurement lors du paramétrage de la configuration de RSAT.

    ![Jeton d’accès personnel.](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a>Configurer le projet LCS

Vous devez disposer d’un projet LCS (Lifecycle Services) pour votre bibliothèque de tests principale. Le Concepteur de processus d’entreprise (BPM) est utilisé comme bibliothèque principale pour les scénarios de test. BPM permet de gérer et répartir les bibliothèques de test sur plusieurs projets LCS. Par exemple, un partenaire Microsoft ou un éditeur de logiciels indépendant (ISV) créateur de bibliothèques de tests publiera des scénarios de tests sous la forme de bibliothèque BPM. Dans BPM, les scénarios de test sont organisés par processus métier. BPM ne définit pas l’ordre d’exécution ou la fréquence de vos tests. Ces détails sont gérés dans Azure DevOps, comme décrit plus loin dans cet article.  

Pour votre projet LCS, vous pouvez utiliser un projet d’implémentation existant d’un client ou d’un partenaire.

### <a name="update-the-lcs-language"></a>Mettre à jour la langue de LCS

> [!NOTE]
> Pour que l’interface utilisateur affiche correctement les processus métier, la langue privilégiée de LCS doit être définie sur **Anglais (États-Unis)**.

1. Accédez au projet d’implémentation LCS.
2. Sélectionnez le bouton **Paramètres** (le symbole d’engrenage) dans le coin supérieur droit de la page, puis sélectionnez **Préférences linguistiques**.

    ![Mettre à jour la préférence de langue.](./media/setup_rsa_tool_09.png)

3. Dans le champ **Langue favorite**, sélectionnez **Anglais (États-Unis)**, puis sélectionnez **Enregistrer**.

    ![Onglet Préférences linguistiques dans les Paramètres utilisateur.](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a>Configurer LCS pour se connecter au projet Azure DevOps

Si vous avez créé un projet Azure DevOps auparavant, configurez le projet LCS pour vous y connecter. Sinon, si votre projet LCS est déjà connecté à votre projet Azure DevOps, vous pouvez passer à la section suivante.

1. Accédez au projet d’implémentation LCS.
2. Sélectionnez le bouton **Menu**, puis sélectionnez **Paramètres de projet**.

    ![Commande des paramètres du projet.](./media/setup_rsa_tool_11.png)

3. Dans le volet gauche, sélectionnez **Visual Studio Team Services**, puis sélectionnez **Configuration de Visual StudioTeam Services**.

    ![Onglet Visual Studio Team Services dans les Paramètres du projet.](./media/setup_rsa_tool_12.png)

4. Dans le champ **URL de site Azure DevOps**, saisissez l’URL du site Azure DevOps. Dans le champ **Jeton personnel d’accès**, entrez le jeton personnel d’accès créé précédemment.

    > [!NOTE]
    > Bien que VSTS s’appelle désormais Azure DevOps, connectez LCS à votre projet Azure DevOps, utilisez l’ancienne URL. Par exemple, l’URL Azure DevOps qui est utilisée dans ce didacticiel est `https://dev.azure.com/D365FOFastTrack/`. Toutefois, dans l’illustration suivante, elle est saisie comme `https://D365FOFastTrack.visualstudio.com/`.

    ![Étape 1 de Configuration de Visual Studio Team Services.](./media/setup_rsa_tool_13.png)

5. Sélectionnez **Continuer**.
6. Dans le champ **Projet Visual Studio Team Services**, sélectionnez le projet VSTS sur le site sélectionné pour le lier au projet LCS. Le champ **Modèle de traitement** est défini sur **Agile** par défaut. Pour un modèle personnalisé, examinez les bonnes pratiques recommandées de la section [Créer un nouveau projet Azure DevOps](#create-a-new-azure-devops-project). Ensuite, sélectionnez **Continuer**.

    ![Étape 2 de Configuration de Visual Studio Team Services.](./media/setup_rsa_tool_14.png)

7. Vérifiez vos paramètres, puis sélectionnez **Enregistrer**.

    ![Étape 3 de Configuration de Visual Studio Team Services.](./media/setup_rsa_tool_15.png)

8. Sélectionnez **Autoriser** pour autoriser LCS à accéder au site Azure DevOps configuré en votre nom et pour activer les fonctions qui s’intègrent avec VSTS.

    ![Bouton Autoriser.](./media/setup_rsa_tool_16.png)

9. Une boîte de message s’affiche. Elle indique « Vous êtes sur le point d’être redirigé(e) vers un site externe pour autoriser LCS à se connecter à Visual Studio Team Services en votre nom. Voulez-vous continuer ? » Cliquez sur **Oui**.

    ![Boîte de message.](./media/setup_rsa_tool_17.png)

10. Sélectionner **Accepter**.

    ![Autoriser l’accès.](./media/setup_rsa_tool_18.png)

11. Si vous êtes un utilisateur autorisé, l’IU doit revenir à la page Paramètres du projet LCS.

    ![Utilisateur autorisé.](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a>Créer une bibliothèque BPM

1. Accédez au projet d’implémentation LCS.
2. Sélectionnez le bouton **Menu**, puis sélectionnez **Concepteur de processus d’entreprise**.

    ![Commande Concepteur de processus d’entreprise.](./media/setup_rsa_tool_20.png)

3. Sélectionnez **Nouvelle bibliothèque**.

    ![Bouton Nouvelle bibliothèque.](./media/setup_rsa_tool_21.png)

4. Dans le champ **Nom de la bibliothèque**, entrez un nom, puis sélectionnez **Créer**. Pour ce didacticiel, nommez la bibliothèque BPM **RSAT**.

    ![Créer une boîte de dialogue de nouvelle bibliothèque.](./media/setup_rsa_tool_22.png)

5. Ouvrez la nouvelle bibliothèque BPM **RSAT**.
6. Sélectionnez le processus **Exemple de processus métier essentiel**, puis, à droite, sélectionnez **Mode d’édition**.

    ![Bouton Mode d’édition.](./media/setup_rsa_tool_23.png)

7. Modifiez la valeur du champ **Nom** et du champ **Description** en **Créer un produit**. Sélectionnez ensuite **Enregistrer**.

    ![Champs Nom et description.](./media/setup_rsa_tool_24.png)

## <a name="environment"></a>Environnement

### <a name="version-requirement"></a>Exigences relatives à la version

Un environnement de test ou de sandbox exécutant la version 10 est requis. Pour les clients utilisant la version 7.3, Platform Update 20 ou une version ultérieure est également prise en charge.

> [!NOTE]
> RSAT doit avoir accès à votre environnement de test via un navigateur Web.

### <a name="user-criteria"></a>Critères utilisateur

L’utilisateur doit disposer de droits d’administrateur dans cet environnement.

### <a name="set-up-help-settings-to-connect-with-lcs"></a>Configuration des Paramètres d’aide pour la connexion à LCS

Cette étape est obligatoire pour se connecter à LCS de manière à pouvoir enregistrer les enregistrements de tâches dans la bibliothèque BPM appropriée dans LCS par l’intermédiaire du client.

1. Ouvrez le client.
2. Accédez à **Administration système \> Paramétrage \> Paramètres système**.
3. Dans l’onglet **Aide**, dans le champ **Configuration de l’aide de Lifecycle Services**, sélectionnez le projet LCS approprié (**RSAT** pour ce didacticiel).

    ![Champ Aide de Lifecycle Services sous l’onglet d’aide.](./media/setup_rsa_tool_25.png)

    Les bibliothèques BPM sont renseignées sous le projet LCS approprié.

4. Sélectionnez **Enregistrer**.
5. Vous devez actualiser le navigateur pour afficher le contenu de l’aide mis à jour.

    ![Notification sur l’actualisation du navigateur.](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a>Enregistrements de tâches

> [!NOTE]
> Assurez-vous que tous les enregistrements de tâches démarrent dans le tableau de bord principal. Faites en sorte que les différents enregistrements soient courts et concentrez-vous sur une tâche métier, comme la création d’une commande client.

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a>Créer un enregistrement de tâche et l’enregistre dans la bibliothèque BPM

Créez un enregistrement de tâche correspondant que vous pouvez associer au processus métier simple qui a été créé dans la nouvelle bibliothèque BPM.

1. Ouvrez le client.
2. Dans le tableau de bord principal, sélectionnez le bouton **Paramètres** (le symbole d’engrenage), puis sélectionnez **Enregistreur de tâches**.

    ![Sélectionner Enregistreur de tâches dans le menu Paramètres.](./media/setup_rsa_tool_27.png)

3. Sélectionnez **Créer un enregistrement**.

    ![Bouton Créer un enregistrement.](./media/setup_rsa_tool_28.png)

4. Renseignez les champs **Nom de l’enregistrement** et **Description de l’enregistrement**, puis sélectionnez **Démarrer**.

    ![Champs Nom de l’enregistrement et Description de l’enregistrement.](./media/setup_rsa_tool_29.png)

5. Enregistrez les étapes de la création d’un produit. Lorsque vous avez terminé, sélectionnez **Arrêter** pour arrêter l’enregistrement.

    ![Étapes pour créer un produit.](./media/setup_rsa_tool_30.png)

6. Sélectionnez **Enregistrer sur Lifecycle Services**.

    ![Enregistrer l’enregistrement de tâches dans Lifecycle Services.](./media/setup_rsa_tool_31.png)

    Les informations sur la bibliothèque sont chargées à partir de LCS.

    ![Chargement des informations de la bibliothèque.](./media/setup_rsa_tool_32.png)

7. Sélectionnez la bibliothèque BPM pour y associer l’enregistrement de tâche Pour ce didacticiel, sélectionnez la bibliothèque BPM **RSAT** créée précédemment et le processus métier **Créer un produit** sous celle-ci. Puis sélectionnez **OK**.

    ![Associer l’enregistrement de tâche avec une bibliothèque PM et un processus métier.](./media/setup_rsa_tool_33.png)

    Un message « L’enregistrement dans Lifecycle Services a réussi » s’affiche.

    ![Message d’enregistrement réussi dans LCS.](./media/setup_rsa_tool_34.png)

8. Si vous souhaitez enregistrer l’enregistrement de tâche localement, puis le charger dans BPM via LCS, procédez comme suit :

    1. Une fois l’enregistrement terminé, sélectionnez **Enregistrer sur ce PC**.

        ![Enregistrer sur le PC.](./media/setup_rsa_tool_35.png)

    2. Dans la barre de Notifications du navigateur, sélectionnez **Enregistrer** ou **Enregistrer sous** pour enregistrer le fichier sur votre ordinateur local.

        ![Barre de notifications.](./media/setup_rsa_tool_36.png)

    3. Accédez à la bibliothèque BPM **RSAT**, puis sélectionnez le processus métier par rapport auquel enregistrer l’enregistrement de tâche.
    4. Dans l’onglet **Vue d’ensemble**, sélectionnez **Charger**.

        ![Bouton Charger.](./media/setup_rsa_tool_37.png)

    5. Sélectionnez **Parcourir**, puis sélectionnez le fichier de .axtr que vous enregistré précédemment. Sélectionnez **Charger**.

        ![Sélection du fichier .axtr à charger.](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a>Tester la synchronisation de BPM avec Azure DevOps

Maintenant que l’enregistrement de tâche est associé au processus métier, vous devez valider le fait que le processus métier et l’enregistrement de tâche associé peuvent être synchronisés avec Azure DevOps en tant que fonction et scénario de test (respectivement) à l’aide de la fonction de synchronisation de VSTS dans LCS.

> [!NOTE]
> Le type d’élément de travail correspondant qui est créé dans Azure DevOps est variable selon le modèle de processus sélectionné lors de la configuration du projet LCS avec Azure DevOps, comme décrit dans la section [Créer un nouveau projet Azure DevOps](#create-a-new-azure-devops-project).

1. Accédez à la bibliothèque BPM, puis ouvrez la bibliothèque **RSAT** que vous avez créée précédemment.
2. Sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Synchronisation VSTS**.

    ![Commande Synchronisation VSTS dans le menu Points de suspension.](./media/setup_rsa_tool_39.png)

    Une fois la synchronisation de VSTS terminée, un onglet **Configuration requise** apparaît sur la gauche. Il comprend l’élément de travail Azure DevOps correspondant.

    > [!NOTE]
    > L’élément de travail créé dans Azure DevOps a le nom de la bibliothèque BPM en préfixe de titre.

    ![Onglet Configuration requise.](./media/setup_rsa_tool_40.png)

3. Actualisez la page.
4. Sélectionnez le bouton représentant des points de suspension (**...**). Vous obtenez une option supplémentaire, **Synchroniser les cas de test**. Sélectionnez cette option.

    ![Commande Synchroniser les cas de test dans le menu Points de suspension.](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > Si l’option **Synchroniser les cas de test** n’est pas disponible lorsque vous actualisez la page, accédez à la page principale de BPM, puis sélectionnez **Synchroniser les cas de test** pour toute la bibliothèque. Ainsi, vous forcez efficacement la synchronisation pour toute la bibliothèque.
    >
    > ![Sélection de Synchroniser les cas de test pour toute la bibliothèque.](./media/setup_rsa_tool_42.png)

    Une fois la synchronisation des cas de test terminée, un nouveau scénario de test est créé dans l’onglet **Configuration requise**.

    ![Nouveau scénario de test sous l’onglet Configuration requise.](./media/setup_rsa_tool_43.png)

5. Accédez à votre projet Azure DevOps, puis sélectionnez **Tableaux \> Éléments de travail**.

    ![Commande Éléments de travail sous Tableaux.](./media/setup_rsa_tool_44.png)

6. Vérifiez que l’élément de travail et le scénario de test que vous avez créés via la synchronisation de BPM existent.

    ![Élément de travail et scénario de test.](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a>Installer et configurer RSAT

RSAT peut être installé sur tout ordinateur qui exécute Windows 10 et pouvant se connecter à l’environnement via un navigateur Web (Internet Explorer ou Google Chrome).

> [!NOTE]
> Avant d’installer une nouvelle version de l’outil, nous vous recommandons de désinstaller la version précédente.

### <a name="install-an-authentication-certificate"></a>Installation d’un certificat d’authentification

Pour activer l’authentification, vous devez générer et installer un certificat sur l’ordinateur où RSAT s’exécute.

#### <a name="generate-a-certificate"></a>Générer un certificat

1. Pour générer un fichier de certificat, ouvrez une fenêtre Microsoft Windows PowerShell en tant qu’administrateur, puis exécutez la commande suivante.

    ```powershell
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. Ouvrez le Gestionnaire de certificat en entrant **certlm.msc** dans la boîte de dialogue **Exécuter**, et vérifiez que le certificat **Certificat de test automatisé D365** est créé sous **Personnel \> Certificats**.

    > [!NOTE]
    > Veillez à entrer **certlm.msc**, pas **certmgr.msc**, car les certificats sont stockés sur l’ordinateur local.

    ![Certificat de test automatisé D365.](./media/setup_rsa_tool_46.png)

3. Cliquez avec le bouton droit sur le certificat, puis sélectionnez **Copier**.
4. Accédez à **Autorités de certification racines de confiance \> Certificats**.

    ![Dossier Certificats sous le dossier Autorités de certification racines de confiance.](./media/setup_rsa_tool_47.png)

5. Dans le menu **Action**, sélectionnez **Coller** pour copier le certificat à l’emplacement **Autorités de certification racines de confiance**.

    ![Commande Coller dans le menu Action.](./media/setup_rsa_tool_48.png)

6. Pour obtenir l’empreinte du certificat installé, mais sans espaces ni caractères spéciaux, ouvrez une fenêtre Windows PowerShell en tant qu’administrateur, puis exécutez les commandes suivantes.

    ```powershell
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > Enregistrez l’empreinte, car vous en aurez besoin ultérieurement lorsque vous mettrez à jour les fichiers .wif du serveur d’objets d’application (AOS) et paramétrerez la configuration de RSAT.

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a>Configurer l’ordinateur AOS pour approuver la connexion

> [!NOTE]
> Si l’environnement est un environnement de niveau 2 ou plus, l’empreinte du certificat doit être mise à jour dans le fichier wif.config pour **tous** les ordinateurs AOS de l’environnement.

1. Établissez une connexion RDP (Remote Desktop Protocol) à l’ordinateur AOS. Les informations de connexion sont disponibles dans la page de détails d’environnement dans LCS.
2. Ouvrez Microsoft Internet Information Services (IIS), puis recherchez **AOSService** dans la liste des sites.

    ![AOSService dans la liste des sites.](./media/setup_rsa_tool_49.png)

3. Cliquez avec le bouton droit sur **Explorer** pour ouvrir le dossier **\<Drive\>: \\AosService\\Webroot**. Cherchez le fichier **wif.config**.

    ![Fichier wif.config dans le dossier Webroot.](./media/setup_rsa_tool_50.png)

4. Mettez à jour le fichier **wif.config** en ajoutant une nouvelle entrée d’autorité pour votre certificat et le nom de l’autorité, comme indiqué dans l’exemple suivant.

    ```Xml
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > Si plusieurs utilisateurs utilisent la même application, chaque utilisateur doit générer des empreintes distinctes, et chacune de ces empreintes doit être ajoutée dans la section **\<keys\>**.

5. S’il existe plusieurs ordinateurs AOS, répétez les étapes 3 à 4 pour chaque ordinateur supplémentaire.

    > [!NOTE]
    > Contrairement aux environnements plus anciens de niveau 2, les nouveaux environnements de niveau 2 sont déployés avec deux instances AOS.

6. Exécutez **iisreset** sur tous les ordinateurs AOS.

    > [!NOTE]
    > Si vous n’avez pas les droits d’administrateur pour exécuter **iisreset** sur un ordinateur de niveau 1, dans la page des détails d’environnement de LCS, sélectionnez Maintenance > Redémarrer les services.

#### <a name="tier-2-environment"></a>Environnement de niveau 2 ou plus

Si un environnement de niveau 2 ou plus (sandbox de test d’acceptation standard ou supérieur) est utilisé, vérifiez ou définissez le paramètre de registre suivant sur l’ordinateur où RSAT est installé. Cette étape est obligatoire car elle permet d’éviter les erreurs d’authentification ou de connexion de RSAT.

```PowerShell
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a>Installation de RSAT

1. Accédez à <https://www.microsoft.com/download/details.aspx?id=57357>, puis sélectionnez **Télécharger**.
2. Sélectionnez tous les fichiers, puis sélectionnez **Suivant**.

    ![Sélectionner tous les fichiers.](./media/setup_rsa_tool_51.png)

3. Double-cliquez sur le module .msi pour exécuter le programme d’installation. Puis, lorsque l’installation est terminée, sélectionnez **Terminer**.

    ![Fichier de programme d’installation de RSAT.](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a>Installer Selenium et les pilotes du navigateur

Dans les versions précédentes de RSAT, vous deviez installer Selenium et les pilotes du navigateur. Il n’est plus nécessaire d’installer ces pilotes. C’est fait automatiquement.

1. La première fois que vous ouvrez RSAT, vous êtes invité à télécharger et installer Selenium. Pour plus d’informations, voir la section [Configuration de RSAT](#configure-rsat).
2. Avant d’exécuter scénario de test, vous êtes invité à télécharger et installer automatiquement le pilote de navigateur correspondant au navigateur par défaut sélectionné dans la configuration de RSAT. Pour plus d’informations, voir la section [Charger et exécuter des scénarios de test](#load-and-run-test-cases).

## <a name="get-started-with-rsat"></a>Mise en route de RSAT

### <a name="create-a-test-plan-and-test-suites"></a>Création d’un plan de test et de suites de tests

1. Accédez au projet Azure DevOps, puis sélectionnez **Plans de test**.

    ![Commande Plans de test.](./media/setup_rsa_tool_53.png)

2. Sélectionnez **Nouveau plan de test**.

    ![Bouton nouveau plan de test.](./media/setup_rsa_tool_54.png)

3. Renseignez le champ **Nom**, puis sélectionnez **Créer**. Pour ce didacticiel, nommez le plan de test **Plan de test RSAT**.

    ![Boîte de dialogue Nouveau plan de test.](./media/setup_rsa_tool_55.png)

4. Sélectionnez le signe plus (**+**), puis sélectionnez **Suite statique** pour créer une suite statique dans le nouveau plan de test. Nommez la suite de tests **T01 – Make to Stock**.

    > [!NOTE]
    > Vous pouvez également créer une suite à base de requêtes, si vous souhaitez que les nouveaux scénarios de test BPM soient automatiquement envoyés à la suite de tests RSAT.

    ![Créer une suite statique.](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a>Associer des scénarios de test à des suites de tests

1. Sélectionnez **Ajouter existant** sur le côté droit pour ajouter les scénarios de test existants à la suite de tests.

    ![Bouton Ajouter existant.](./media/setup_rsa_tool_57.png)

2. Dans la page **Ajouter les scénarios de test à la suite**, sélectionnez **Exécuter la requête**, puis sélectionnez le scénario de test à ajouter à la suite de tests. Pour ce didacticiel, sélectionnez le scénario de test **Créer un nouveau produit**. Sélectionnez ensuite **Ajouter des scénarios de test** dans le coin inférieur droit de la page (ce bouton n’est pas affiché dans l’illustration suivante).

    ![Bouton Exécuter la requête.](./media/setup_rsa_tool_58.png)

    Le scénario de test est ajouté à la suite de tests **T01-Make to Stock**.

    ![Scénario de test ajouté à la suite de tests.](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a>Configurer le RSAT

1. Ouvrez RSAT.

    ![Icône RSAT.](./media/setup_rsa_tool_60.png)

2. Vous recevez un message d’avertissement indiquant que « Regression Suite Automation Tool a besoin de Selenium ; souhaitez-vous automatiquement le télécharger et l’installer maintenant ? » Cliquez sur **Oui**.

    ![Message d’avertissement indiquant que Regression Suite Automation Tool requiert Selenium.](./media/setup_rsa_tool_61.png)

3. Sélectionnez le bouton **Paramètres** (le symbole d’engrenage) dans l’angle supérieur droit, puis, dans la boîte de dialogue qui s’affiche, renseignez les champs suivants :

    - **URL Azure DevOps** – Saisissez l’URL de votre projet Azure DevOps, telle que `https://yourAzureDevOpsUrlHere.visualStudio.com`.
    - **Jeton d’accès** – Saisissez le jeton d’accès qui permet à l’outil de se connecter à Azure DevOps. Utilisez le jeton personnel d’accès créé précédemment dans ce didacticiel. Pour plus d’informations, voir [Authentifier l’accès à l’aide de jetons d’accès personnels](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).
    - **Nom du projet** – Sélectionnez le nom de votre projet Azure DevOps.
    - **Plan de test** – Sélectionnez le plan de test Azure DevOps qui contient vos scénarios de test. Pour plus d’informations, voir [Création d’un plan de test et de suites de tests](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan). Après avoir sélectionné un plan de test, sélectionnez **Tester la connexion** pour tester votre connexion à Azure DevOps.
    - **Nom d’hôte** – Saisissez le nom d’hôte de l’environnement de test, tel que **\<myaos\>.cloudax.dynamics.com**. N’incluez pas le préfixe **https://** ou **http://**.
    - **Nom d’hôte SOAP** – Saisissez le nom d’hôte SOAP de l’environnement de test. Généralement, le nom d’hôte SOAP est identique au nom d’hôte, mais avec le suffixe **SOAP**. Voici un exemple : **\<myaos\>soap.cloudax.dynamics.com**. N’incluez pas le préfixe **https://** ou **http://**.

        > [!NOTE]
        > Pour rechercher le nom d’hôte et le nom d’hôte SOAP, ouvrez le Gestionnaire IIS, cliquez avec le bouton droit sur **Sites \> AOSService**, puis sélectionnez **Modifier les liaisons**. Les valeurs de la colonne **Nom d’hôte** vous indiquent le nom d’hôte et le nom d’hôte SOAP (le nom d’hôte SOAP a le suffixe **soap** dans l’URL).

        ![Nom d’hôte et nom d’hôte SOAP dans la colonne Nom d’hôte.](./media/setup_rsa_tool_63.png)

    - **Nom d’utilisateur administrateur** – Saisissez l’adresse e-mail de l’utilisateur administrateur dans l’environnement de test.
    - **Empreinte** – Saisissez l’empreinte du certificat d’authentification, comme décrit précédemment dans ce didacticiel.
    - **Répertoire de travail** – Spécifiez l’emplacement du dossier de stockage des fichiers d’automatisation des tests, tels que les fichiers des données de test Excel. Par exemple, entrez ou sélectionnez **C:\\Temp\\RegressionTool**.

        > [!NOTE]
        > Si le nom du dossier comporte des espaces, l’exécution échouera car le dossier sera introuvable. Ce problème est connu et doit être résolu dans la dernière version de l’outil.

    - **Navigateur par défaut** – Sélectionnez **Internet Explorer** ou **Google Chrome**. Assurez-vous que les pilotes de navigateur appropriés ont été installés.
    - **Délai d’exécution du test** – Spécifiez le délai d’expiration, en minutes, pour l’exécution des tests. Une fois le délai d’expiration dépassé, toutes les fenêtres actives sont fermées et les scénarios de test en attente échouent.
    - **Délai d’action du test** – Ce champ détermine la période d’expiration, en minutes, pour les requêtes de serveur de l’environnement Finance and Operation. Généralement, la valeur par défaut (2 minutes) doit être suffisante. Toutefois, pour les environnements plus lents, vous aurez peut-être besoin d’augmenter cette valeur en cas d’erreurs liées au délai d’expiration.
    - **Nom de la société** – Entrez le nom de la société à utiliser comme votre société par défaut lors de la création des fichiers de paramètres Excel. Vous pourrez modifier la société ultérieurement en modifiant le fichier de paramètres Excel.

    ![Boîte de dialogue Paramètres.](./media/setup_rsa_tool_62.png)

4. Sélectionnez **Appliquer** pour appliquer et enregistrer les paramètres.

    Pour enregistrer vos paramètres actuels dans un fichier de configuration sur votre ordinateur, sélectionnez **Enregistrer sous**. Pour restaurer vos paramètres à partir d’un fichier de configuration sur votre ordinateur, sélectionnez **Ouvrir**.

5. Sélectionnez **Fermer** pour fermer la boîte de dialogue.

### <a name="load-and-run-test-cases"></a>Charger et exécuter des scénarios de test

1. Sélectionner **Charger** pour charger le **Plan de test RSAT** à partir du projet Azure DevOps.

    ![Bouton Charger.](./media/setup_rsa_tool_64.png)

2. Sélectionnez le scénario de test **Créer un nouveau produit** à partir de la suite de test, puis sélectionnez **Nouveau \> Générer des fichiers de paramètre et d’exécution de test**.

    ![Commande Générer des fichiers de paramètre et d’exécution de test dans le menu Nouveau.](./media/setup_rsa_tool_65.png)

    Le fichier de paramètres Excel est créé dans le dossier local que vous avez spécifié dans la configuration RSAT (par exemple, **C:\\Temp\\RegressionTool**).

    ![Fichier de paramètres Excel créé.](./media/setup_rsa_tool_66.png)

3. Si vous souhaitez enregistrer les fichiers de paramètres, sélectionnez **Charger**. Les fichiers d’automatisation de test de tous les scénarios de test sélectionnés sont chargés vers Azure DevOps pour une utilisation ultérieure. (Ils incluent les fichiers de paramètres de test Excel.)

    De cette manière, vous pouvez sélectionner **Charge** pour charger les fichiers de paramètres (et les fichiers d’automatisation) du scénario de test directement depuis Azure DevOps. Vous n’avez pas besoin de générer de nouveau les fichiers de paramètres. Cette approche aura de l’importance ultérieurement, lorsque vous souhaiterez conserver les modifications dans le fichier de paramètres et ne souhaiterez pas qu’elles soient écrasées.

4. Pour vérifier que les fichiers d’automatisation et les fichiers de paramètres sont enregistrés dans Azure DevOps, accédez au projet Azure DevOps, sélectionnez **Tableaux \> Éléments de travail**, puis sélectionnez le scénario de test **Créer un nouveau produit**. Dans l’onglet **Pièces jointes**, vous devez voir quatre fichiers :

    - **.cs** – Fichier d’automatisation C\#
    - **.dll** – Fichier d’automatisation compilé comme assembly
    - **.xlsx** – Fichier de paramètres Excel
    - **.xml** – Fichier d’enregistrement

    ![Fichiers sous l’onglet Pièces jointes.](./media/setup_rsa_tool_67.png)

5. Sélectionnez le scénario de test à exécuter, puis sélectionnez **Exécuter**.

    > [!NOTE]
    > Avant d’exécuter des scénarios de test, si vous utilisez Internet Explorer comme navigateur, vérifiez que la résolution de votre bureau est définie sur **100%** dans les **Paramètres d’affichage Windows \> Échelle et mise en page**. Si vous ne pouvez pas modifier ce paramètre sur un ordinateur virtuel (VM), changez-le sur le client (ordinateur portable) à partir duquel vous accédez à l’ordinateur virtuel. Les paramètres de résolution seront alors hérités par les paramètres d’affichage de l’ordinateur virtuel.

    ![Résolution du bureau définie sur 100 %.](./media/setup_rsa_tool_68.png)

6. Si les pilotes de navigateur ne sont pas installés dans le système, vous recevez un message d’avertissement qui indique « Cette opération nécessite le pilote \<browser name\> ; souhaitez-vous automatiquement le télécharger et l’installer maintenant ? » Cliquez sur **Oui**.

    ![Message d’avertissement pour Internet Explorer.](./media/setup_rsa_tool_69.png)

    ![Message d’avertissement pour Chrome.](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > Si votre navigateur est Chrome et que vous recevez un message d’erreur indiquant que la session n’a pas été créée car la version de Chrome n’est pas appropriée, chargez le dernier pilote Chrome depuis <http://chromedriver.chromium.org/downloads> vers le dossier **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium**.

    ![Message d’erreur pour Chrome.](./media/setup_rsa_tool_71.png)

    Le scénario de test est exécuté, et le champ **Résultat** est mis à jour.

    ![Champ de résultat mis à jour.](./media/setup_rsa_tool_72.png)

    Si vous avez suivi ce didacticiel tel qu’il a été écrit, le scénario de test **Créer un nouveau produit** doit échouer, car l’enregistrement de tâche de création de produit a enregistré le nom du produit comme une valeur codée en dur. Si vous réexécutez le même scénario de test, vous devez recevoir un message d’erreur, car le produit existe déjà.

    ![Champ de résultat défini sur Échec.](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a>Afficher les résultats du test

1. Double-cliquez sur le scénario de test défaillant.

    Vous recevez un message d’erreur.

    ![Message d’erreur.](./media/setup_rsa_tool_73.png)

2. Sélectionnez **Détails** pour afficher le message d’erreur entier.

    ![Message d’erreur entier.](./media/setup_rsa_tool_74.png)

3. Pour afficher une version détaillée du message d’erreur dans Azure DevOps, sélectionnez **Ouvrir dans Azure DevOps**. Dans Azure DevOps, vous pouvez afficher le statut du scénario de test et le message d’erreur détaillé.

    ![Message d’erreur détaillé dans Azure DevOps.](./media/setup_rsa_tool_75.png)

4. Pour afficher les résultats du test directement dans le projet Azure DevOps, accédez à **Plans de test \> Plans de test \> Exécutions**. Double-cliquez sur le test exécuté pour lequel vous souhaitez afficher plus de détails.

    ![Liste des exécutions de test dans Azure DevOps.](./media/setup_rsa_tool_76.png)

5. L’onglet **Récapitulatif d’exécution** indique que le scénario de test a échoué, mais il ne comprend pas le message d’erreur proprement dit. Pour afficher le message d’erreur détaillé, sélectionnez l’onglet **Résultats du test**.

    ![Onglet Récapitulatif d’exécution.](./media/setup_rsa_tool_77.png)

    L’onglet **Résultats du test** fournit des informations sur le scénario de test, ainsi que les résultats et le message d’erreur.

    ![Onglet Résultats du test.](./media/setup_rsa_tool_78.png)

6. Double-cliquez sur l’enregistrement approprié pour afficher le message d’erreur détaillé.

    ![Message d’erreur détaillé.](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > Tous les messages d’erreur sont également disponibles localement dans **C:\\Utilisateurs\\\$Notrenomdutilisateur\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.

7. Vous pouvez également exporter les résultats d’exécution de test depuis le niveau de plan de test en sélectionnant **Exporter**.

    ![Exporter un plan de test.](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a>Modifier le fichier de paramètres Excel

1. Ouvrez RSAT.
2. Sélectionnez le scénario de test, puis sélectionnez **Modifier** pour ouvrir le fichier de paramètres Excel.

    Dans l’écran **EcoResProductCreate**, notez que la valeur du champ **Numéro de produit** est codée en dur. Vous devez mettre ce champ à jour à un nouveau numéro de produit avant d’exécuter de nouveau le scénario de test.

3. Pour générer un numéro de produit unique pour chaque exécution sans devoir rouvrir le fichier de paramètres Excel et mettre manuellement le numéro de produit à jour à chaque fois, utilisez la formule Excel suivante.

    ```vba
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > Outre l’onglet **Général**, le fichier de paramètres Excel contient un onglet de données pour chaque page de formulaire visitée par le scénario de test.

    ![Champ Numéro de produit.](./media/setup_rsa_tool_81.png)

4. Sélectionnez **Enregistrer**, puis fermez le classeur Excel.
5. Sélectionnez **Charger** pour enregistrer le fichier de paramètres Excel dans Azure DevOps.

    ![Message de chargement réussi.](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > Pour exécuter des scénarios de test dans un contexte d’utilisateur spécifique, entrez l’identificater e-mail de l’utilisateur dans le champ **Utilisateur du test** de l’onglet **Général** du fichier de paramètres Excel. Dans la dernière version de RSAT, la mise en page des champs dans le fichier de paramètres Excel a été mise à jour, mais le concept reste le même.
    >
    > ![Champ Utilisateur du test.](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a>Valider les résultats

- Sélectionnez **Exécuter** pour réexécuter le scénario de test, puis vérifier que le scénario de test a réussi. Vous pouvez afficher les résultats du test de la manière décrite dans la section [Afficher les résultats du test](#view-the-test-results).

    ![Champ de résultat défini sur Réussite.](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a>Enchaînement de scénarios de test

Une des fonctions essentielles de RSAT est l’enchaînement de scénarios de test (c’est-à-dire, la capacité d’un test de transmettre des valeurs à d’autres tests). Les scénarios de test sont exécutés dans l’ordre défini dans le plan de test Azure DevOps. (Cet ordre peut également être mis à jour dans l’outil de test lui-même.) Par conséquent, si vous souhaitez transmettre des variables d’un scénario de test à un autre, il est primordial que les tests soient dans l’ordre correct.

Dans cette section, vous allez créer une variable enregistrée dans le premier scénario de test, créer un second scénario de test, puis transmettre la variable enregistrée du premier scénario de test vers le second. Vous exécuterez ensuite les scénarios de test comme scénario de test enchaîné dans RSAT.

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a>Modifier un enregistrement de tâche existant pour créer une variable enregistrée

1. Ouvrez le client.
2. Sélectionnez le bouton **Paramètres** (le symbole d’engrenage), puis sélectionnez **Enregistreur de tâches**.
3. Sélectionnez **Modifier l’enregistrement**.

    ![Bouton Modifier l’enregistrement.](./media/setup_rsa_tool_85.png)

4. Sélectionnez **Ouvrir à partir de Lifecycle Services**.

    ![Bouton Ouvrir à partir de Lifecycle Services.](./media/setup_rsa_tool_86.png)

5. Sélectionnez **Sélectionner la bibliothèque Lifecycle Services**.

    ![Bouton Sélectionner la bibliothèque Lifecycle Services.](./media/setup_rsa_tool_87.png)

    Les bibliothèques BPM sont chargées depuis LCS.

    ![Chargement des bibliothèques BPM.](./media/setup_rsa_tool_88.png)

6. Une fois les bibliothèques BPM chargées depuis LCS, sélectionnez la bibliothèque BPM **RSAT** et le processus métier **Créer un nouveau produit** auquel l’enregistrement de tâche a été associé. Puis sélectionnez **OK**.

    ![Sélection d’une bibliothèque BPM et d’un processus métier.](./media/setup_rsa_tool_89.png)

7. Nom de l’enregistrement de tâche approprié est entré dans le champ **Nom de l’enregistrement**. Sélectionnez **Démarrer**.

    ![Nom de l’enregistrement de tâche dans le champ Nom de l’enregistrement.](./media/setup_rsa_tool_90.png)

8. Accédez à **Gestion des informations produit \> Produits**, puis sélectionnez **Nouveau** pour ouvrir la page dans lequel l’enregistrement de tâche d’origine, **Créez un produit**, a été enregistré.
9. Sélectionnez **Insérer une étape**.

    > [!NOTE]
    > La nouvelle étape est insérée **après** l’étape sélectionnée dans le volet.

    ![Bouton Insérer une étape.](./media/setup_rsa_tool_91.png)

10. Cliquez avec le bouton droit sur le champ **Numéro de produit**, puis sélectionnez **Enregistreur de tâches \> Copier**.

    ![Commande Copier.](./media/setup_rsa_tool_92.png)

11. Une nouvelle étape est ajoutée dans le volet. Notez la valeur dans le champ **Numéro de produit**, car vous en aurez besoin ultérieurement.

    ![Nouvelle étape ajoutée.](./media/setup_rsa_tool_93.png)

12. Sélectionnez **Modification terminée**.
13. Sélectionnez **Enregistrer sur Lifecycle Services**, puis associez le nouvel enregistrement de tâche avec les mêmes bibliothèque BPM et processus métier que ceux auxquels était associé l’enregistrement de tâche d’origine. Pour plus d’informations, voir la section [Créer un enregistrement de tâche et l’enregistrer dans la bibliothèque BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).
14. Accédez à la bibliothèque de BPM, puis sélectionnez **Synchroniser les cas de test** pour remplacer l’enregistrement de tâche associé au scénario de test dans Azure DevOps, comme décrit dans la section [Tester la synchronisation de BPM avec Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).
15. Ouvrez RSAT, et sélectionnez **Charger** pour recharger tous les scénarios de test dans la suite de tests. Vous devez recréer les fichiers d’automatisation et de paramètre pour le scénario de test approprié en sélectionnant le scénario de test, puis en sélectionnant **Nouveau \> Générer des fichiers de paramètre et d’exécution de test**, comme décrit dans la section [Charger et exécuter des scénarios de test](#load-and-run-test-cases).

    > [!NOTE]
    > Si le fichier de paramètres Excel a été laissé ouvert, la régénération échoue. Par conséquent, veillez à ce que le fichier de paramètres Excel du scénario de test soit fermé avant de générer le nouveau fichier de paramètres Excel.

16. Sélectionnez **Éditer** pour ouvrir le nouveau fichier de paramètres Excel. Vous obtenez une nouvelle entrée **Variable enregistrée** sur la ligne 9. Cette variable, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, est enregistrée dans le fichier XML de l’enregistrement de tâche et peut être utilisé pour les tests suivants.

    ![Entrée de variable enregistrée.](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a>Créer un nouveau scénario de test

1. Accédez à la bibliothèque BPM **RSAT**.
2. Sélectionnez le processus **Exemple de processus métier accessoire**, puis, à droite, sélectionnez **Mode d’édition**.
3. Modifiez la valeur du champ **Nom** et du champ **Description** en **Lancer un produit**. Sélectionnez ensuite **Enregistrer**.

    ![Nom et description modifiés pour Lancer un produit.](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a>Créer un nouvel enregistrement de tâche possédant une fonction de validation

- Créez un enregistrement de tâche pour lancer le produit créé précédemment dans l’entité juridique USRT. Pour plus d’informations, voir la section [Créer un enregistrement de tâche et l’enregistrer dans la bibliothèque BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).

    > [!NOTE]
    > Pour les scénarios de test enchaînés, nous vous recommandons de toujours rechercher ou filtrer l’enregistrement désiré en *saisissant manuellement la valeur du champ*. Ainsi, l’outil peut déterminer sur quel enregistrement appliquer l’action par rapport au scénario de test suivant.

    ![Nouvel enregistrement de tâche possédant une fonction de validation.](./media/setup_rsa_tool_96.png)

    Comme le montre l’illustration précédente, lorsque le produit est trouvé à l’aide du filtre rapide, mais avant de sélectionner **Lancer des produits**, vous validez la valeur du champ **Numéro de produit** pour vous assurer que l’identificateur du produit est bien celui qui a été créé précédemment. Pour valider la valeur, cliquez avec le bouton droit sur le champ **Numéro de produit**, puis sélectionnez **Enregistreur de tâches \> Valider \> Valeur actuelle**.

    ![Validation de la valeur actuelle.](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a>Enregistrer l’enregistrement de tâche dans BPM

1. Une fois l’enregistrement de tâche terminé, sélectionnez **Enregistrer sur Lifecycle Services**.

    ![Enregistrer l’enregistrement de tâches terminé dans Lifecycle Services.](./media/setup_rsa_tool_98.png)

2. Les informations sur la bibliothèque sont chargées à partir de LCS.

    ![Chargement des informations de la bibliothèque de LCS.](./media/setup_rsa_tool_99.png)

3. Sélectionnez la bibliothèque BPM pour y associer l’enregistrement de tâche Pour ce didacticiel, sélectionnez la bibliothèque BPM **RSAT** créée précédemment et le processus métier **Lancer un produit** sous celle-ci. Puis sélectionnez **OK**.

#### <a name="sync-bpm-to-azure-devops"></a>Synchronisation de BPM avec Azure DevOps

1. Accédez à la bibliothèque BPM, puis ouvrez la bibliothèque **RSAT**.
2. Sélectionnez **Synchronisation VSTS**, puis **Synchroniser les cas de test**. Pour plus d’informations, voir la section [Tester la synchronisation de BPM avec Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.

    Une fois la synchronisation terminée, le nouvel élément de travail et le scénario de test correspondant pour le processus métier **Lancer un produit** s’affiche dans Azure DevOps dans **Tableaux \> Éléments de travail**.

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a>Ajouter le nouveau scénario de test à la suite de tests existante

1. Accédez à **Plans de test \> Plans de test**, puis sélectionnez le plan **Plan de test RSAT**.
2. Sélectionnez **Ajouter existant**.
3. Dans la page **Ajouter des scénarios de test à la suite**, sélectionnez **Exécuter la requête**.
4. Sélectionnez le nouveau scénario de test créé pour **Lancer un produit**, puis sélectionnez **Ajoutez des scénarios de test** dans le coin inférieur droit de la page (ce bouton n’est pas affiché dans l’illustration suivante).

    ![Page Ajouter des scénarios de test à la suite.](./media/setup_rsa_tool_100.png)

    La suite de tests comporte désormais deux scénarios de test.

    ![Deux scénarios de test dans la suite de test.](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a>Charger les scénarios de test dans RSAT

1. Ouvrez RSAT, et sélectionnez **Charger**.
2. Les scénarios de test sont chargés, et vous recevez un avertissement indiquant « Cette action va remplacer les fichiers de données de test Excel, les modifications locales seront perdues. Voulez-vous continuer ? » Sélectionnez **Oui** pour mettre à jour les fichiers de paramètres Excel dans le système local, mais pas les fichiers de paramètres Excel qui ont été chargés dans Azure DevOps.

    ![Cette action remplacera les fichiers de données de test de Excel.](./media/setup_rsa_tool_102.png)

    Les deux scénarios de test sont chargés, ainsi que le fichier de paramètres Excel pour le premier scénario de test. Comme vous avez sélectionné **Charger** dans la dernière exécution, les fichiers de paramètres sont extraits d’Azure DevOps.

    ![Scénarios de test chargés.](./media/setup_rsa_tool_103.png)

3. Sélectionnez uniquement le second scénario de test, puis sélectionnez **Nouveau \> Générer des fichiers de paramètre et d’exécution de test**.

#### <a name="edit-the-excel-parameter-file"></a>Éditer le fichier de paramètres Excel

1. Sélectionnez seulement le deuxième scénario de test, puis sélectionnez **Modifier** pour ouvrir le fichier de paramètres Excel correspondant.
2. Copiez la variable enregistrée **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** (voir la section [Modifier un enregistrement de tâche existant pour créer une variable enregistrée](#modify-an-existing-task-recording-to-create-a-saved-variable) ) du premier scénario de test dans tous les champs dans lesquels le numéro de produit est utilisé. Dans ce cas, vous copiez la variable dans les champs **Numéro de produit** et **Valider le numéro de produit** de la feuille **EcoResProductListPage**.

    ![Champs Numéro de produit et Valider le numéro de produit.](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > Les variables ne peuvent être transférées entre tests que pendant la même exécution de test. Les noms des variables doivent correspondre parfaitement.

3. Sélectionnez **Enregistrer**, puis fermez le classeur Excel.
4. Sélectionnez **Charger** pour enregistrer les modifications apportées au fichier de paramètres Excel.

#### <a name="run-the-chained-test-cases"></a>Exécuter des scénarios de test enchaînés

1. Sélectionnez les deux scénarios de test, puis sélectionnez **Exécuter**.
2. Vérifiez que les deux scénarios de test sont réussis.

    ![Champ de résultat défini sur Réussi pour les deux scénarios de test.](./media/setup_rsa_tool_105.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
