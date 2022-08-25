---
title: Regulatory Configuration Services (RCS) – Fonctions de globalisation
description: Cet article explique comment utiliser Microsoft Regulatory Configuration Services (RCS) et le référentiel global pour créer et utiliser des fonctions de globalisation.
author: kfend
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.custom: 97423
ms.assetid: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
ms.openlocfilehash: 5df0b37741103c7beba4cc43f0aba25a5af52be0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279768"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a>Regulatory Configuration Services (RCS) – Fonctions de globalisation

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser Microsoft Regulatory Configuration Services (RCS) pour créer une fonctionnalité de globalisation utilisable dans les services de globalisation, tels qu’un service de facturation électronique. RCS vous permet d’effectuer ces tâches :

- Définir les composants associés à une fonction.
- Gérer le cycle de vie des fonctionnalités via le statut des fonctionnalités.
- Rendre une fonctionnalité disponible pour des environnements définis.
- Partager une fonctionnalité avec d’autres organisations.

Les procédures suivantes expliquent comment un utilisateur dans RCS peut ajouter une fonctionnalité de globalisation et des composants associés, mettre à jour le statut de la fonctionnalité et rendre la fonctionnalité disponible afin qu’elle puisse être utilisée dans les services de globalisation.

Avant de terminer les procédures, vous devez effectuer les étapes liées aux tâches suivantes :

- Accéder à une instance RCS.
- Créer et activer un fournisseur de configuration. Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Dans votre instance d’application de finances et d’opérations, procédez comme suit.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **Gestion des états électroniques**.
2. Si vous n’avez pas d’environnement RCS configuré dans votre société, sélectionnez **Regulatory services – Configuration** et suivez les instructions pour en mettre un en service.

> [!NOTE]
> Si un environnement RCS a déjà été configuré pour votre entreprise, utilisez l’URL de la page pour accéder à l’environnement en sélectionnant l’option de connexion.

## <a name="turn-on-the-globalization-features"></a>Activer les fonctionnalités de globalisation

1. Dans votre instance RCS, sélectionnez la vignette **Gestion des fonctionnalités**.
2. Dans l’espace de travail **Gestion des fonctionnalités**, sélectionnez **Fonctionnalités de globalisation** dans la liste, puis sélectionnez **Activer maintenant**.

    ![Fonctionnalités de globalisation dans la gestion des fonctionnalités.](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a>Fonctionnalités de globalisation

Pour utiliser une fonctionnalité de globalisation, vous devez d’abord l’importer à partir du référentiel global et en créer votre propre version. Il existe deux façons d’ajouter des fonctionnalités de globalisation :

- Ajouter une fonctionnalité dérivée basée sur une fonctionnalité existante qui a été publiée ou partagée.
- Ajouter une nouvelle fonctionnalité que vous avez créée à partir de zéro.

## <a name="access-globalization-features"></a>Accéder aux fonctionnalités de globalisation

1. Assurez-vous que la fonctionnalité **Fonctionnalités de globalisation** est activée dans la gestion des fonctionnalités, comme décrit précédemment dans cet article.
2. Ouvrez le nouvel espace de travail **Fonctionnalités de globalisation**, puis, sous **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.

    ![Espace de travail Fonctionnalités globales.](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    La page **Fonctionnalités de facturation électronique** est ouverte.

    ![Page Fonctionnalités de facturation électronique.](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a>Ajouter une fonctionnalité de globalisation dérivée

Vous pouvez ajouter une nouvelle fonctionnalité de globalisation en la dérivant d’une fonctionnalité existante qui a été publiée ou partagée.

1. Sélectionnez **Importation** pour ouvrir la page **Importer une fonctionnalité depuis le référentiel global**.

    ![Importer une fonctionnalité depuis le référentiel global.](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. Sélectionnez **Synchroniser** pour obtenir les fonctionnalités les plus récentes.

    La liste synchronisée comprend les fonctionnalités qui vous sont disponibles, soit parce qu’elles ont été publiées par Microsoft, soit parce qu’elles ont été partagées avec vous par un autre fournisseur de configuration.

    ![Liste synchronisée des fonctionnalités.](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. Dans la liste, sélectionnez les fonctionnalités à importer, puis sélectionnez **Importation**. Vous recevez un message lorsque les fonctionnalités sélectionnées ont été importées avec succès.

    ![Message d’importation réussie.](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. Sélectionnez **Ajouter** puis, dans la boîte de dialogue déroulante, sélectionnez l’option **Basé sur une version existante**.
5. Entrez un nom et une description de la fonctionnalité.
6. Dans la liste des fonctionnalités disponibles, sélectionnez la version de base de la fonctionnalité, puis sélectionnez **Créer la fonctionnalité**.

    ![Ajout d’une fonctionnalité dérivée.](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    La fonctionnalité que vous avez ajoutée est créée et a le statut **Brouillon**.

    ![Fonctionnalité dérivée ayant le statut Brouillon.](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. Passez en revue les composants de la fonctionnalité pour déterminer si des mises à jour sont requises :

    - Passez en revue les configurations, au cas où vous auriez besoin de personnaliser les formats de gestion des états électroniques (ER) et leur liaison avec les mappages de format pour la version de la fonctionnalité.
    - Passez en revue la configuration, au cas où vous auriez besoin de personnaliser l’onglet **Actions**, l’onglet **Règles d’applicabilité** ou l’onglet **Variables** pour la version de la fonctionnalité.

8. Dans l’onglet **Versions**, sélectionnez une **Date d’effet** et entrez une description si le champ **Description** est vide.
9. Sélectionnez **Modifier le statut** pour terminer la fonctionnalité. Les fonctionnalités terminées peuvent être mises à disposition pour un environnement spécifique afin de pouvoir être utilisées dans les services de globalisation ou être publiées dans le référentiel global.

> [!NOTE]
> Les fonctionnalités dont la valeur **Statut de version de la fonctionnalité** est **Publié** peuvent être partagées avec des organisations externes.

## <a name="add-a-new-globalization-feature"></a>Ajouter une nouvelle fonctionnalité de globalisation

Vous pouvez ajouter une nouvelle fonctionnalité de globalisation en la créant à partir de zéro.

1. Dans la page **Importer une fonctionnalité depuis le référentiel global**, sélectionnez **Ajouter** puis, dans la boîte de dialogue déroulante, sélectionnez l’option **Nouvelle fonctionnalité**.
2. Entrez un nom et une description de la fonctionnalité.
3. Sélectionnez **Créer une fonctionnalité**.

    ![Ajout d’une nouvelle fonctionnalité.](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. Dans l’onglet **Versions**, sélectionnez une **Date d’effet**, puis sélectionnez **Modifier le statut** pour terminer la fonctionnalité. Les fonctionnalités terminées peuvent être mises à disposition pour un environnement spécifique afin de pouvoir être utilisées dans les services de globalisation ou être publiées dans le référentiel global.

> [!NOTE]
> Les fonctionnalités dont la valeur **Statut de version de la fonctionnalité** est **Publié** peuvent être partagées avec des organisations externes.

## <a name="feature-component-overview"></a>Vue d’ensemble des composants de la fonctionnalité

Les fonctionnalités de globalisation comportent plusieurs composants :

- **Version** – Ce composant prend en charge la gestion du cycle de vie des fonctionnalités et permet aux utilisateurs de gérer le statut des différentes versions de la fonctionnalité.
- **Configurations** – Ce composant permet aux utilisateurs de gérer, d’afficher et de modifier les formats de gestion des états électroniques et les mappages de formats associés.
- **Paramétrages** – Ce composant permet aux utilisateurs des services de globalisation, tels qu’un service de facturation électronique, de gérer les paramètres de la version de fonctionnalité associée. Par conséquent, il permet une construction flexible des règles de communication et de réaction.
- **Environnement** – Ce composant permet aux utilisateurs des services de globalisation, tels qu’un service de facturation électronique, de gérer l’environnement dans lequel le paramétrage de la version de la fonctionnalité est utilisé et d’accorder une autorisation aux utilisateurs qui y auront accès.
- **Organisations** – Ce composant permet aux utilisateurs de partager la fonctionnalité avec des organisations externes.

## <a name="configuring-feature-components"></a>Configuration des composants de la fonctionnalité

### <a name="version-and-status"></a>Version et statut

La version est utilisée pour gérer le cycle de vie de la fonctionnalité de globalisation.

Le statut peut être modifié dans le champ **Statut** de l’onglet **Version**. Les statuts suivants sont disponibles :

- **Brouillon** – La fonctionnalité ne peut être modifiée que lorsqu’elle est dans cet état.
- **Terminée** – La fonctionnalité et tous les composants associés ont été finalisés (terminés) et ne peuvent pas être modifiés.
- **Publiée** – La fonctionnalité et tous les composants associés ont été publiés dans le référentiel global.
- **Partagée** – La fonctionnalité et tous les composants associés ont été partagés avec des organisations externes.
- **Activée** – La fonctionnalité et tous les composants associés ont été activés pour être utilisés dans un service de globalisation, tel qu’un service de facturation électronique.

> [!NOTE]
> Les fonctionnalités doivent passer séquentiellement par certains de ces statuts. Par conséquent, tous les statuts peuvent ne pas être disponibles à chaque étape du cycle de vie.

### <a name="configurations"></a>Configurations

Les actions suivantes sont disponibles pour les configurations :

- **Afficher** – Permet d’afficher les configurations de fonctionnalités sous-jacentes qui ne nécessitent aucune mise à jour.
- **Modifier** – Permet de créer une version provisoire d’une configuration sélectionnée afin de pouvoir modifier le format ou le mappage de format dans le Concepteur de format.
- **Supprimer** – Permet de supprimer une configuration sélectionnée de la fonctionnalité.
- **Redéfinir** – Permet de redéfinir la fonctionnalité. Pour plus d’informations, voir la section [Redéfinir les fonctionnalités de globalisation dérivées](#rebase) située plus loin dans cet article.

### <a name="setups"></a>Paramétrages

Les actions suivantes sont disponibles pour les paramétrages de fonctionnalité :

- **Ajouter** – Permet de créer une nouvelle configuration de fonctionnalité. Ce paramétrage de fonctionnalité peut être dérivé d’un paramétrage de fonctionnalité existant ou être créé à partir de zéro.
- **Supprimer** – Permet de supprimer un paramétrage de fonctionnalité sélectionné.
- **Afficher** – Permet d’afficher un paramétrage de fonctionnalité sous-jacent qui ne nécessite aucune modification.
- **Modifier** – Permet de créer, supprimer ou modifier les attributs des trois principaux composants d’un paramétrage de fonctionnalité :

    - Actions et leurs paramètres
    - Règles d’applicabilité
    - Variables

![Page de paramétrage d’une version de fonctionnalité.](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a>Environnements

Les actions suivantes sont disponibles pour les environnements :

- **Activer** – Pour une version de fonctionnalité sélectionnée, sélectionnez un environnement publié et sélectionnez une **Date d’effet** à compter de laquelle elle devrait être disponible. Pour plus d’informations, voir la section [Configurer des environnements pour l’activation](#configureenvironment) située plus loin dans cet article.
- **Annuler** – Permet de supprimer un environnement pour un paramétrage de fonctionnalité.

### <a name="organizations"></a>Organisations

Suivez ces étapes pour partager une fonctionnalité de globalisation avec une organisation externe.

1. Dans la page **Fonctionnalités de facturation électronique**, sélectionnez la fonctionnalité et la version de la fonctionnalité à partager.
2. Dans l’onglet **Organisations**, sélectionnez **Partager avec** puis, dans la boîte de dialogue déroulante, entrez le nom de domaine de l’organisation.
3. Sélectionnez **Partager**.

    ![Partage d’une fonctionnalité avec une organisation.](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

La fonctionnalité est partagée avec l’organisation sélectionnée et lui est disponible dans le référentiel global. De là, la fonctionnalité peut être importée dans l’instance RCS de l’organisation ou dans Dynamics 365 Finance afin de pouvoir être utilisée.

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a>Redéfinir les fonctionnalités de globalisation dérivées

Vous pouvez redéfinir une fonction de globalisation dérivée vers une nouvelle version ou la version de base mise à jour de la fonctionnalité. De cette façon, les modifications survenues dans la version de base peuvent être automatiquement mises à jour. La version de base mise à jour de la fonctionnalité est créée par le fournisseur de configuration d’origine, puis est publiée ou partagée.

![Version de base mise à jour de la fonctionnalité.](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

Par exemple, si vous souhaitez redéfinir la version dérivée d’une fonctionnalité que vous avez créée, vous devez d’abord obtenir la dernière version de la fonctionnalité en l’important à partir du référentiel global.

1. Dans la page **Fonctionnalités de facturation électronique**, sélectionnez **Importation**.
2. Sélectionnez **Synchroniser** pour obtenir les fonctionnalités les plus récentes.
3. Dans la liste des fonctionnalités, sélectionnez les fonctionnalités à importer, puis sélectionnez **Importation**.

    ![Importation de la dernière version d’une fonctionnalité.](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. Dans la liste des fonctionnalités, sélectionnez la fonctionnalité à redéfinir.
5. Dans l’onglet **Version**, sélectionnez **Nouveau** pour créer une version de brouillon.

    ![Nouvelle version de brouillon créée.](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. Sélectionnez **Redéfinir**.
7. Dans la boîte de dialogue **Redéfinir**, sélectionnez la dernière version de la fonctionnalité à redéfinir.

    ![Boîte de dialogue Redéfinir.](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. Cliquez sur **OK**.
9. Passez en revue les composants de la fonctionnalité et apportez les modifications nécessaires.
10. Sélectionnez **Modifier le statut** pour terminer la fonctionnalité redéfinie. Une fois la redéfinition terminée, vous pouvez effectuer des actions supplémentaires. Par exemple, vous pouvez publier la fonctionnalité et la rendre disponible pour être utilisée dans les services de globalisation.

    ![Statut de la fonctionnalité mis à jour sur Terminé.](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a>Configurer les environnements pour les fonctionnalités de globalisation

Les utilisateurs des services de globalisation peuvent gérer l’environnement pour paramétrer une fonctionnalité de globalisation et accorder une autorisation aux autres utilisateurs qui y auront accès.

1. Dans l’espace de travail **Fonctionnalités de globalisation**, sous **Environnements**, sélectionnez la vignette **Facturation électronique**.

    ![Espace de travail Fonctionnalités de globalisation.](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. Sélectionnez **Paramètres du coffre de clés**, puis sélectionnez **Nouveau** pour créer un secret Azure Key Vault.
3. Entrez un nom et une description pour le coffre de clés puis, dans le champ **URI Key Vault**, entrez l’URL qui identifie la ressource Key Vault dans Azure.
4. Dans le raccourci **Certificats**, sélectionnez **Ajouter** pour ajouter le certificat et entrez un nom et une description pour chaque certificat.

    ![Certificat ajouté.](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. Sélectionnez **Nouveau** pour créer un environnement.
6. Entrez un nom, une description et le secret du jeton de signature de l’accès partagé requis pour le stockage.
7. dans le raccourci **Utilisateurs**, sélectionnez **Nouveau** pour ajouter un utilisateur qui sera autorisé à accéder à cet environnement.
8. Saisissez l’ID utilisateur et l’adresse e-mail de l’utilisateur.
9. Répétez les étapes 7 et 8 pour ajouter d’autres utilisateurs.
10. Sélectionnez **Publier** pour publier l’environnement.

    ![Environnement publié.](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
