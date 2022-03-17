---
title: Configurer un canal SharePoint
description: Cette rubrique explique comment configurer un canal Microsoft SharePoint pour recevoir des factures électroniques entrantes.
author: dkalyuzh
ms.date: 02/09/2022
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
ms.openlocfilehash: ea3e14ed00b0661d3923c1839135378a8a550499
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371683"
---
# <a name="configure-a-sharepoint-channel"></a>Configurer un canal SharePoint

[!include [banner](../includes/banner.md)]

Comme condition préalable à la configuration d’un canal Microsoft SharePoint pour traiter les documents entrants, suivez les étapes décrites dans [Configurer une connexion SharePoint](e-invoicing-create-sharepoint-connection.md).

Vous pouvez ensuite utiliser le canal SharePoint pour importer des factures de fournisseurs électroniques à partir de fichiers stockés dans vos dossiers SharePoint.

1. Sur votre site SharePoint, créez les dossiers suivants :

    - **Dossier principal** –  Le dossier à partir duquel le service traitera les fichiers.
    - **Dossier d’archives** –  Le dossier dans lequel les fichiers traités seront stockés.
    - **Dossier d’erreur** –  Le dossier dans lequel le système déplacera les fichiers si le traitement échoue.

2. Dans Regulatory Configuration Service (RCS), sélectionnez la fonctionnalité de facturation électronique que vous avez créée. Assurez-vous de sélectionner la version dont le statut est défini sur **Brouillon**.
3. Dans l’onglet **Configurations**, sélectionnez **Ajouter**.
4. Dans la boîte de dialogue déroulante **Créer une configuration de fonctionnalité**, dans le groupe de champs **Nouveau**, sélectionnez l’option **Configuration personnalisée**.
5. Dans le groupe de champ **Type de configuration**, sélectionnez l’option **Canal de données**.
6. Dans le champ **Sélectionner le canal de données**, sélectionnez **Dossier SharePoint**.
7. Cliquez sur **Créer**.
8. Sélectionnez la ligne créée, puis sélectionnez **Modifier**.
9. Sur l’onglet **Canal de données**, dans la section **Paramètres**, définissez les champs obligatoires suivants.

    | Champ                 | Description |
    |-----------------------|-------------|
    | Canal de données          | Entrez un nom unique pour identifier le canal de données. Le nom peut avoir un maximum de 10 caractères. Il sera référencé dans les règles d’applicabilité et dans les applications connectées lors du processus de communication. |
    | Adresse SharePoint    | Entrez l’URL SharePoint. Par exemple, entrez `<domain>.sharepoint.com`. |
    | ID application        | Saisissez le nom de clé secrète Azure Key Vault qui contient l’ID du compte utilisateur SharePoint. Cette clé secrète doit être créée dans Key Vault et configurée dans votre environnement de service. La valeur est la valeur **ID de l’application (client)** depuis [Configurer la connexion SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Secret d’application    | Saisissez le nom de clé secrète Key Vault qui contient le mot de passe du compte utilisateur SharePoint. La valeur est la valeur **Clé secrète de l’inscription de l’application** depuis [Configurer la connexion SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Nom du site             | Entrez le nom du site SharePoint. |
    | Nom de la bibliothèque de documents | Entrez le nom de la bibliothèque de documents SharePoint. |
    | Délai d’attente               | Sélectionnez le délai maximal, en millisecondes (ms), pendant lequel le système doit attendre une réponse. La valeur par défaut est de 10 000 ms (10 secondes). |
    | Dossier principal           | Spécifiez la source d’importation des fichiers ou le dossier à partir duquel le service doit traiter les fichiers. |
    | Dossier d’archivage        | Spécifiez le dossier dans lequel les fichiers traités doivent être stockés. |
    | Dossier d’erreurs          | Spécifiez le dossier dans lequel le système doit déplacer les fichiers si le traitement échoue. |
    | Taille maximale de fichier         | Entrez la taille maximale, en octets, d’un seul fichier qui est traité. La valeur par défaut est 20 000 000 octets. |
    | Nombre maximal de fichiers      | Saisissez le nombre maximal de fichiers à traiter pour une action unique. Si vous ne souhaitez pas limiter le nombre de fichiers, définissez la valeur sur **0** (zéro). |
    | Filtre de fichiers           | Entrez une chaîne pour filtrer par nom de fichier. Ce champ est facultatif. Un simple masque tel que **\*smth\*.ext** est pris en charge, où chaque astérisque (\*) représente zéro ou plusieurs occurrences de n’importe quel caractère. Par exemple, entrez **\*.pdf** pour configurer le canal pour lire les fichiers PDF. |
    | Nom de fichier personnalisé      | Saisissez le nom de fichier personnalisé du client. |

10. Dans l’onglet **Règles d’applicabilité**, vérifiez et mettez à jour les critères si nécessaire. La valeur du champ **Canal** doit être égal à la valeur que vous avez saisie dans le champ **Canal de données** à l’étape précédente.
11. Cliquez sur **Enregistrer**, puis fermez la page.
