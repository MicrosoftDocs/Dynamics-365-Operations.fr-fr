---
title: Configurer les destinations spécifiques aux enregistrements de gestion de l'impression d’états électroniques
description: Cette rubrique explique comment configurer des destinations spécifiques aux enregistrements de gestion de l'impression pour un format de gestion des états électroniques configuré pour générer des documents sortants.
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1e06fafe8d8bbe92ddf4fcd94d7271a1fbb6362a
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413593"
---
# <a name="configure-print-management-record-specific-er-destinations"></a>Configurer les destinations spécifiques aux enregistrements de gestion de l'impression d’états électroniques

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment un utilisateur doté du rôle Administrateur système ou Commis à la comptabilité client peut effectuer les tâches suivantes :

- Configurer des destinations nommées [États électroniques (ER)](general-electronic-reporting.md) pour une solution ER qui génère des factures financières.
- Attribuer une destination ER à un seul enregistrement de [gestion de l'impression](document-reporting-services.md).

Les procédures peuvent être effectuées dans la société USMF. Aucun codage n’est requis.

## <a name="introduction"></a>Introduction

Vous pouvez configurer les [destinations](electronic-reporting-destinations.md) pour chaque dossier dans le composant de sortie de fichier d’une [configuration](general-electronic-reporting.md#Configuration) de [format](general-electronic-reporting.md#FormatComponentOutbound) de gestion des états électroniques utilisée pour générer un document sortant. Lorsque vous exécutez un format pour la gestion des états électroniques de ce type, si vous avez les droits d’accès appropriés, vous pouvez également changer les paramètres de destination configurés au moment de l’exécution.

Dans Microsoft Dynamics 365 Finance **version 10.0.17 et ultérieure**, un code d’action peut être [configuré](er-apis-app10-0-17.md) pour un format de gestion des états électroniques pour spécifier l'action que les utilisateurs effectuent en exécutant ce format de gestion des états électroniques. Par exemple, dans le module **Comptabilité client**, dans les paramètres de gestion de l’impression, vous pouvez sélectionner un format de gestion des états électroniques qui génère un document commercial spécifique, comme une facture financière. Vous pouvez ensuite sélectionner **Afficher** pour prévisualiser la facture ou **Imprimer** pour l’envoyer à une imprimante. Si une action est transmise pour le format de gestion des états électroniques en cours d’exécution au moment de l’exécution, vous pouvez [configurer différentes destinations des états électroniques pour différentes actions utilisateur](er-action-dependent-destinations.md).

Dans Finance **version 10.0.21 et versions ultérieures**, une destination nommée peut être [configurée](er-apis-app10-0-21.md) pour un format ER et affecté à l'enregistrement de gestion d'impression qui est traité lorsque ce format ER est exécuté. Par exemple, dans le module **Comptabilité client**, dans les paramètres de gestion d'impression, vous souhaitez configurer l'enregistrement **d'origine** pour effectuer les actions suivantes :

- Exécuter un format de gestion des états électroniques.
- Envoyer par e-mail la facture générée à un client.
- Configurer la **Copie** pour exécuter le même format.
- Imprimer une copie de la facture sur une imprimante réseau.

Dans ce cas, vous devez configurer différentes destinations des états électroniques pour le format ER en cours d'exécution et vous devez sélectionner les destinations pour différents enregistrements de gestion d'impression.

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, la fonctionnalité **Permettre la configuration des destinations pour la gestion des états électroniques par élément de gestion d'impression** doit être activée dans l'espace de travail [Gestion des fonctionnalités](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace). Le code source doit également être modifié pour permettre la configuration des destinations pour la gestion des états électroniques nommées dans l'instance Finance actuelle et pour activer le [nouvel](er-apis-app10-0-21.md) API de gestion des états électroniques.

De plus, la configuration ER de **Facture financière (Excel)** doit être [importée](er-download-configurations-global-repo.md) dans votre instance Finance.

## <a name="configure-a-new-er-destination"></a>Configurer une nouvelle destination des états électroniques

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Sélectionnez une facture pour le compte client **US-001**.
3. Sur la page **Facture financière**, sur l'onglet **Facture**, dans le groupe **Gestion de l'impression**, sélectionnez **Gestion de l'impression**.
4. Sur la page **Configuration de la gestion de l'impression**, développez **Module - Comptabilité client** \> **Documents** \> **Facture financière**, sélectionnez l'enregistrement **d'origine**, puis procédez comme suit :

    1.  Observez les paramètres actuels de l'enregistrement sélectionné :
        -   Le rapport SSRS par défaut **FreeTextInvoice.Report** est sélectionné dans le champ **Format d'état**.
        -   Le nom **\<Default\>** est affiché dans le champ **Destination**, indiquant qu'aucune destination personnalisée n'a été sélectionnée pour le rapport SSRS attribué. 
    2.  Dans le champ **Format d’état**, sélectionnez la configuration de format ER **Facture financière (Excel)**.
        -   Le nom du champ **Destination** est remplacé par **Nom de destination**.
        -   Le nom **\<No named destination\>** est affiché dans le champ **Nom de destination**, indiquant qu'aucune destination nommée n'a été sélectionnée pour le format ER attribué.
    3.  Sélectionnez le bouton de flèche vers la droite du champ **Nom de destination**.    
    4. Sur la page **Destination nommée d'états électroniques**, dans le champ **Nom**, entrez **Destination principale**.
    5. Sélectionnez **Enregistrer**.
    6. Sur le raccourci **Destination du fichier**, [configurez](er-destination-type-email.md) la destination **E-mail** pour le composant **État**.
    7. Fermez la page **Destination nommée des états électroniques**.
    8. Sur la page **Configuration de la gestion de l'impression**, dans le champ **Nom de destination**, sélectionnez la destination nommée **Destination principale**.

    ![Configurer une destination ER nommée pour le format ER sélectionné et l'affecter à un enregistrement de gestion d'impression configuré sur la page de configuration de la gestion d'impression](./media/er-named-destinations-01.gif)

    Vous avez maintenant configuré la destination ER nommée **Destination principale** pour le format **Facture financière (Excel)** et l'avez affecté à l'enregistrement **d'origine** de gestion d'impression sous **Module - Comptabilité client** \> **Documents** \> **Facture financière**.

5. Développez **Module - comptabilité client** \> **Compte - US-001** \> **Facture financière**, sélectionnez l'enregistrement **d'origine**, puis procédez comme suit :

    1. Sélectionnez et maintenez la sélection (ou cliquez avec le bouton droit) sur l'enregistrement, puis sélectionnez **Remplacer**.
    2. Sélectionnez le bouton de flèche vers la droite du champ **Nom de destination**.
    3. Sur la page **Destination nommée d'états électroniques**, dans le volet Actions, sélectionnez **Nouveau**.
    4. Dans le champ **Nom**, entrez **destination US-001**.
    5. Sur le raccourci **Destination du fichier**, [configurez](er-destination-type-print.md) la destination **Imprimante** pour le composant **État**.
    6. Fermez la page **Destination nommée des états électroniques**.
    7. Sur la page **Configuration de la gestion de l'impression**, dans le champ **Nom de destination**, sélectionnez la destination nommée **destination US-001**.

    ![Configurer une destination ER nommée pour le format ER sélectionné et l'affecter à l'enregistrement de gestion d'impression configuré sur la page de configuration de la gestion d'impression](./media/er-named-destinations-02.gif)

    Vous avez maintenant configuré la destination ER nommée **destination US-001** pour le format **Facture financière (Excel)** et l'avez affecté à l'enregistrement **d'origine** de gestion d'impression sous **Module - Comptabilité client** \> **Documents** \> **Facture financière**.

Désormais, lorsqu'une facture financière est traitée, le format ER **Facture financière (Excel)** est exécuté et l'un des événements suivants se produit :

- Si la facture financière est destinée à un client autre que US-001, le document généré est envoyé par e-mail.
- Si la facture financière est destinée au client US-001, le document généré est imprimé.

> [!NOTE]
> Lorsqu'une destination nommée n'a pas été définie pour un enregistrement de gestion d'impression qui est traité au moment de l'exécution, les destinations ER par défaut sont utilisées si elles sont disponibles pour le format ER en cours d'exécution.

> [!IMPORTANT]
> Sur la page **Destination des états électroniques** (**Administration d'organisation** \> **Gestion des états électroniques** \> **Destination des états électroniques**), si vous sélectionnez un format ER pour lequel au moins une destination nommée a été configurée, vous êtes averti de la présence de destinations nommées.
>
> ![Notification concernant l'existence de destinations nommées configurées pour le format ER sélectionné sur la page Destination des états électroniques](./media/er-named-destinations-03.png)
>
> Si vous supprimez la destination par défaut, toutes les destinations nommées sont également supprimées. Si ces destinations nommées ont été sélectionnées pour les enregistrements de gestion d'impression, la sélection de ces destinations nommées est annulée.

## <a name="copy-an-existing-er-destination-as-a-new-named-destination"></a>Copier une destination ER existante en tant que nouvelle destination nommée

Lorsque la destination ER nommée par défaut est disponible pour un format ER, elle peut être utilisée comme modèle pour les nouvelles destinations ER. Pour créer une nouvelle destination ER basée sur la destination par défaut, sélectionnez **Copier par défaut** sur la page **Destination nommée des états électroniques**. La nouvelle destination est nommée **Défaut**. Vous pouvez répéter cette étape autant de fois que nécessaire.

Vous pouvez sélectionner n'importe quelle destination nommée existante comme modèle pour une nouvelle destination nommée. Pour créer une destination ER nommée basée sur une destination nommée sélectionnée, sélectionnez **Copier** sur la page **Destination nommée des états électroniques**. La nouvelle destination porte le même nom que la destination nommée sélectionnée, mais le suffixe « Copie » est ajouté. Vous pouvez répéter cette étape autant de fois que nécessaire.

## <a name="security-considerations"></a>Considérations de sécurité

Vous pouvez configurer des destinations ER nommées sur la page **Configuration de la gestion de l'impression** uniquement si vous avez une [autorisation](../sysadmin/role-based-security.md#permissions) pour effectuer cette tâche. Une autorisation peut vous être accordée si le [droit](../sysadmin/role-based-security.md#duties) **Configurer la destination du format des états électroniques** est affecté à l'un de vos [rôles de sécurité](../sysadmin/role-based-security.md#security-roles). Pour plus d’informations, voir [Considérations de sécurité](electronic-reporting-destinations.md#security-considerations).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états électroniques](general-electronic-reporting.md)

[Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)

[Modifications de l’API de la structure de gestion des états électroniques pour Application update 10.0.17](er-apis-app10-0-17.md)

[Modifications de l’API de la structure de gestion des états électroniques pour Application update 10.0.21](er-apis-app10-0-21.md)

[Modifier le code pour permettre aux utilisateurs de configurer et d'utiliser des destinations ER nommées](er-api-named-destinations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
