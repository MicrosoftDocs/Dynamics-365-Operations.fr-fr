---
title: Configurer la solution Invoice capture
description: Cet article explique comment configurer la solution Invoice capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: e297dafc930368f14f2e68213ce4153ba792ef4d
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691149"
---
# <a name="configure-the-invoice-capture-solution"></a>Configurer la solution Invoice capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Une fois la solution Invoice capture installée, vous devez configurer l’environnement. Le processus inclut les étapes de base suivantes.

1. **Obligatoire :** Synchroniser les entités juridiques de Microsoft Dynamics 365 Finance. Cette étape est utilisée pour mettre en place la structure de l’organisation dans Microsoft Power Platform.
2. **Obligatoire :** Configurez les canaux pour l’importation des images de facture. La solution est compatible avec les canaux suivants :

    - Office 365 Outlook (par défaut)
    - Outlook.com
    - OneDrive
    - SharePoint

3. **Facultatif :** Définissez des groupes de configuration supplémentaires pour le service de reconnaissance optique de caractères (OCR).
4. **Facultatif :** Définissez des règles de mise en correspondance pour l’entité juridique, le compte fournisseur, l’article et le type d’approvisionnement.

Cet article se concentre sur les deux étapes requises du processus. Pour plus d’informations sur les groupes de configuration, voir [Groupes de configuration de la solution Invoice capture](invoice-capture-config-group.md). Pour plus d’informations sur les règles de mise en correspondance, voir [Règles de mise en correspondance de la solution Invoice capture](invoice-capture-mapping-rules.md).

## <a name="manage-legal-entities"></a>Gérer les entités juridiques

Finance définit les entités juridiques en tant qu’organisations identifiées via l’inscription auprès des autorités juridiques. Les activités commerciales sont exercées et enregistrées dans des entités juridiques distinctes. Dans Microsoft Power Platform, les unités commerciales, les rôles de sécurité et les utilisateurs sont liés d’une manière conforme au modèle de sécurité basé sur les rôles.

Les unités commerciales sont utilisées avec les rôles de sécurité pour contrôler l’accès aux données. Les utilisateurs ne voient que les informations dont ils ont besoin pour faire leur travail. La solution Invoice capture fournit un espace de configuration dans lequel vous pouvez charger des informations de base à partir d’entités juridiques existantes dans Finance et gérer les entités créées manuellement. Les entités juridiques sont utilisées sur les factures fournisseurs et dans le contrôle de sécurité.

Lorsqu’une entité juridique est créée et affichée dans la vue de liste, une unité commerciale par défaut portant le même nom est automatiquement créée. L’équipe se voit accorder le rôle de sécurité **Assistant Comptabilité fournisseur**. Lorsque des entités juridiques sont importées, les données principales de base de Finance sont importées. Les éléments inexistants sont identifiés par entité juridique et nous les ajoutons à la solution Invoice capture. Le groupe de configuration par défaut est attribué aux nouvelles entités juridiques.

### <a name="sync-legal-entities"></a>Synchroniser les entités juridiques

Vous ne pouvez pas créer directement des entités juridiques. Cependant, vous pouvez synchroniser les entités juridiques à partir de Finance. Pour synchroniser les entités juridiques, procédez comme suit.

1. Accédez à **Configuration \> Configuration système \> Gérer les entités juridiques**.
2. Sélectionnez **Synchroniser les entités juridiques**, puis sélectionnez **OK** dans la boîte de dialogue de confirmation.

Une fois la synchronisation terminée, le nombre de nouvelles entités juridiques s’affiche. Les nouvelles entités juridiques sont affichées dans la vue de liste. Le groupe de configuration par défaut est attribué aux nouvelles entités juridiques.

## <a name="configure-invoice-import-channels"></a>Configurer les canaux d’importation des factures

Les fournisseurs envoient des factures depuis différents canaux (e-mail, espace de travail de fichiers ou portail de facturation) via différents formats (papier ou image). La solution Invoice capture peut gérer différents canaux et formats. Les types suivants sont pris en charge :

- Office 365 Outlook
- Outlook.com
- SharePoint
- OneDrive

Lorsqu’un canal est créé pour un compte spécifique, un flux automatisé doté d’un modèle prédéfini est construit pour surveiller les e-mails ou fichiers entrants dans la boîte de réception ou l’espace. Tout fichier qui a une facture valide peut être reconnu et envoyé à la zone de facturation pour attendre le traitement par l’assistant Comptabilité fournisseur. La pièce jointe doit être au format PDF ou image. Les factures peuvent être chargées dans la solution Invoice capture en fonction de la configuration du canal.

### <a name="create-a-channel"></a>Créer un canal

Si vous avez importé le package de solution supplémentaire (Dynamics 365 Invoice capture - Outils d’installation), la connexion par défaut pour Office 365 Outlook est prête à être utilisée. Si vous souhaitez créer plus de connexions pour différents comptes de messagerie ou d’autres types de canaux, consultez [Créer des connexions supplémentaires pour les canaux](invoice-capture-advanced-settings.md#create-additional-connections-for-channels).

Pour créer un canal, procédez comme suit.

1. Accédez à **Configuration \> Configuration système \> Canaux de configuration**.
2. Cliquez sur **Nouveau**.
3. Définissez les champs suivants :

    - Nom de canal
    - Description
    - Type
    - Connexion

Seuls les e-mails ou les fichiers correspondant aux critères suivants peuvent être importés dans la solution.

| Type               | Configuration  | Plus d’informations |
|--------------------|----------------|------------------|
| Office 365 Outlook | Dossier         | Le dossier de messagerie doit se trouver sous le répertoire racine. Par défaut, le dossier Boîte de réception est utilisé. Aucun sous-dossier n’est pris en charge. |
|                    | Filtre Objet | (Facultatif) Une sous-chaîne à inclure en objet. |
|                    | Origine           | (Facultatif) L’adresse e-mail des expéditeurs. Si vous spécifiez plusieurs adresses, utilisez un point-virgule (;) comme séparateur. |
| SharePoint         | Adresse du site   | URL de l’adresse du site. |
|                    | Dossier         | Dossier dans l’adresse du site. |

### <a name="activate-the-channel"></a>Activer le canal

Lorsqu’un flux est enregistré, les champs affichent le statut du canal et l’heure à laquelle il a été créé. Par défaut, le champ **Statut** est défini sur **Inactif**. Le champ **Raison du statut** indique que le canal a été initialisé et est prêt à être activé.

Pour activer le canal, sélectionnez **Activer**. Les champs **Statut** et **Raison du statut** sont mis à jour.

Si un canal n’est pas requis, vous pouvez le désactiver. Pour désactiver un canal, sélectionnez **Désactiver**. Les champs **Statut** et **Raison du statut** sont mis à jour.

### <a name="manage-flows-in-flow-management"></a>Gérer les flux dans la gestion des flux

Vous pouvez afficher une chaîne sur la page **Canaux de configuration** ou dans la gestion des flux.

Pour voir plus de détails, accédez à **Système d’administration \> Solution par défaut \> Flux de cloud** et sélectionnez le flux cible. Les détails affichés incluent les connexions liées, les propriétaires et les historiques d’exécution.

Pour synchroniser l’état, sélectionnez **Vérifier** pour confirmer que l’état du canal correspond à l’état du flux.

Certains cas de gestion des exceptions sont présentés dans le champ **Raison du statut** :

- **Connexion Dataverse manquante** : l’utilisateur actuel n’a pas créé au moins une référence de connexion **Microsoft Dataverse**.
- **Introuvable** : le flux lié au canal a été supprimé dans la gestion des flux. Le canal doit être enregistré à nouveau pour créer un canal.
- **Désactivé dans la gestion des flux** : le flux a été désactivé dans la gestion des flux, et l’état du canal est différent de l’état du flux.
- **Activé dans la gestion des flux** : le flux a été activé dans la gestion des flux, et l’état du canal est différent de l’état du flux.
- **Une erreur inattendue est apparue** : l’utilisateur doit confirmer que le site est un « Site de communication » et que le dossier est « Bibliothèque de documents ».
