---
title: Espace de travail de la solution Invoice capture
description: Cet article fournit des informations sur l’espace de travail de la solution Invoice Capture.
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
ms.openlocfilehash: 4f3af7abf94542437be6132344d6bb7ffaf33d07
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691152"
---
# <a name="invoice-capture-solution-workspace"></a>Espace de travail de la solution Invoice capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="side-by-side-viewer-for-the-invoice-capture-solution"></a>Visionneuse côte à côte pour la solution Invoice capture

La saisie des factures dans le système est généralement un processus long et sujet aux erreurs, car les employés doivent parcourir plusieurs fichiers et fenêtres de pièces jointes pour collecter les informations correctes. La visionneuse de documents côte à côte vous aide à améliorer votre expérience lorsque vous travaillez sur des factures, en simplifiant le processus, pour gagner en efficacité et en précision.

La visionneuse de documents côte à côte permet aux utilisateurs d’avoir le document original et la facture ouverts côte à côte dans la même fenêtre. La page de facture est remplie d’informations provenant du document de facture d’origine. La visionneuse établit la connexion entre les champs de la page de facture et le document de facture d’origine. La visionneuse aide également les utilisateurs à trouver les erreurs qui existent sur la page de facture.

### <a name="open-the-side-by-side-viewer"></a>Ouvrir la visionneuse côte à côte

Dans Microsoft Dynamics 365 Finance, vous pouvez ouvrir la visionneuse côte à côte à partir de la liste de la page de résumé ou de la page de liste des factures. Vous pouvez également l’ouvrir en appuyant deux fois (ou en double-cliquant) sur un enregistrement ou en sélectionnant le numéro de facture.

### <a name="using-the-side-by-side-viewer"></a>Utilisation de la visionneuse côte à côte

#### <a name="manually-review-an-invoice"></a>Vérifier manuellement une facture

Un document de facture qui a été importé peut nécessiter une révision manuelle en raison d’erreurs ou d’avertissements. Dans la visionneuse côte à côte, l’en-tête du document affiche un état **Importé**, et la version actuelle est **Version originale**.

Pour commencer à réviser la facture, sélectionnez **Démarrer la révision**. Tous les champs deviennent modifiables. Le champ **Statut** est mis à jour sur **En révision**, et le champ **Version actuelle** est mis à jour sur **Version modifiée**.

#### <a name="view-and-work-with-messages"></a>Afficher et utiliser les messages

Les utilisateurs doivent démarrer le processus de révision à partir du volet des messages. Les messages d’erreur sont indiqués par un X rouge, les messages d’avertissement sont indiqués par un triangle et les messages d’information sont indiqués par un cercle. Les messages liés au score de confiance peuvent être classés comme des avertissements ou des erreurs, selon le seuil défini par le groupe de configuration. Pour plus d’informations, voir [Groupes de configuration de la solution Invoice capture](invoice-capture-config-group.md).

Les messages d’avertissement et d’erreur peuvent être ignorés à partir du volet des messages, de l’en-tête de facture ou des lignes de facture. Une fois qu’un message est ignoré, il n’apparaît plus comme une erreur ou un avertissement, et la facture n’échoue pas à la validation.

- Pour ignorer les messages du volet des messages, sélectionnez **Ignorer**. Pour réinitialiser un message qui a été ignoré, sélectionnez à nouveau **Ignorer**. Son type passe alors d’erreur ou d’avertissement à information.
- Pour ignorer les messages de l’en-tête de facture ou de la ligne de facture, sélectionnez **Ignorer** sur le champ. Le symbole de message disparaît. Cependant, il réapparaît si le message est réinitialisé à partir du volet Messages.

Pour les messages liés aux champs d’en-tête de facture, lorsque vous sélectionnez le message dans le volet Messages, le curseur est déplacé vers le champ correspondant dans la section d’en-tête.

#### <a name="proofread-and-edit-fields"></a>Relire et corriger les champs

Si la valeur d’un champ est lue à partir de la facture d’origine via la reconnaissance optique de caractères (OCR), un symbole apparaît sur le champ. Si vous sélectionnez le symbole, la visionneuse de documents effectue un zoom avant et met en surbrillance l’endroit à partir duquel la valeur du champ est lue, pour vous aider à vérifier les données de la facture.

Pour réinitialiser la visionneuse de documents à son grossissement d’origine, suivez l’une de ces étapes :

- Sélectionnez le même symbole que vous avez sélectionné précédemment.
- Sélectionnez le bouton dans le coin supérieur droit de la visionneuse de documents.

Modifiez les champs comme requis. Les modifications sont automatiquement enregistrées lorsque le curseur quitte un champ. Un symbole à droite d’un champ indique que le champ a été mis à jour manuellement. Lorsque la page est actualisée, le symbole est supprimé.

#### <a name="check-an-invoice-to-get-up-to-date-messages"></a>Vérifier une facture pour obtenir des messages à jour

Lorsque vous modifiez un champ, la valeur du champ est mise à jour, mais aucun nouveau message de validation n’est généré. Pour obtenir des messages de validation à jour, sélectionnez **Vérifier**. Les messages dans le volet des messages, sur l’en-tête de facture et sur les lignes de facture sont mis à jour.

#### <a name="complete-the-review"></a>Effectuer la révision

Pour terminer la révision, sélectionnez **Effectuer la révision**. Les factures sont validées. Si des erreurs sont détectées, le statut du document reste défini sur **En révision**, et une barre de message apparaît. Tous les messages dans le volet Messages et sur l’en-tête et les lignes de la facture sont automatiquement mis à jour pour fournir des informations sur les causes de l’échec de la validation.

Une fois toutes les erreurs de blocage corrigées, la révision peut être terminée. Le statut du document est mis à jour sur **Révisé**, et les champs ne peuvent plus être modifiés. Vous pouvez relancer la révision en sélectionnant à nouveau **Démarrer la révision**.

#### <a name="generate-a-pending-vendor-invoice-in-finance"></a>Générer une facture fournisseur en attente dans Finance

Pour envoyer le document de facturation à l’environnement Finance connecté, sélectionnez **Générer**. Si la génération de la facture échoue, un message d’erreur apparaît dans une barre de message.

#### <a name="void-an-invoice"></a>Annuler une facture

Pour annuler une facture, sélectionnez **Annuler**. Les factures annulées ne peuvent pas être révisées et ne sont pas affichées dans la liste **Les factures doivent être révisées manuellement**.

### <a name="validation-logic"></a>Logique de validation

Certains champs clés de la visionneuse côte à côte n’existent pas dans les données de préparation des factures, mais sont requis pour générer des factures en attente dans Finance. Ces champs sont dérivés d’une combinaison des données de préparation de facture actuelles et des données de base de Finance.

Les champs qui doivent être dérivés sont **Entité juridique**, **Compte fournisseur** et **Numéro d’article**. Ils doivent être dérivés dans l’ordre suivant. Si la dérivation d’un champ échoue, le processus s’arrête.

1. **Entité juridique** : l’entité juridique est dérivée en premier. Si une règle de mise en correspondance active est trouvée pour l’entité juridique, l’entité juridique est dérivée en fonction du nom et de l’adresse de la société.
2. **Compte fournisseur** : ensuite, le compte fournisseur est dérivé sur la base d’une règle de mise en correspondance active et d’une combinaison de l’entité juridique dérivée et du nom et de l’adresse du fournisseur.
3. **Numéro d’article** : enfin, le nom de l’élément est dérivé de la mise en scène, sur la base des trois types d’informations suivants :

    - Une règle de mise en correspondance configurée
    - L’entité juridique dérivée
    - Le compte fournisseur dérivé

Pour exécuter une validation, sélectionnez **Vérifier** dans la visionneuse côte à côte. Actuellement, la validation effectue les vérifications suivantes :

- **Vérification obligatoire** : cette vérification valide les champs obligatoires pour la visionneuse côte à côte. Les utilisateurs peuvent sélectionner les champs qui doivent être obligatoires sur la page **Paramètre de configuration**.
- **Note de confiance** : les utilisateurs peuvent définir le seuil d’avertissement et le seuil d’erreur pour le score de confiance. Cette vérification se concentre sur le score de confiance de l’OCR qui est inférieur à ces seuils. Des messages d’erreur ou d’avertissement s’affichent en fonction du résultat de la validation.
- **Entité juridique** : cette vérification valide qu’une entité juridique est dans Finance. Si l’entité juridique n’existe pas dans l’environnement Finance, la validation échoue.

Lorsque la visionneuse côte à côte est utilisée pour la première fois et que l’utilisateur sélectionne **Vérification**, les processus de dérivation et de validation sont exécutés. Si les factures sont exactes, le processus de validation est exécuté lorsque l’utilisateur sélectionne **Exécuter la révision**. Il est également exécuté lorsque l’utilisateur sélectionne **Générer une facture fournisseur**.

Le processus de dérivation se produit avant le processus de validation, et tous les avertissements ou erreurs proviennent du processus de validation. Les avertissements et les erreurs sont consignés dans Finance.
