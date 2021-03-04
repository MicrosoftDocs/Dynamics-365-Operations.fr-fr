---
title: Paramétrage des recouvrements
description: Cet article décrit la procédure de paramétrage de la fonctionnalité de recouvrement.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustCollectionsActivitiesListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14031
ms.assetid: dcc6da2f-9af5-4f1d-abaa-b72967b66979
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f8e066b1df3eb3a26d488e1c014f4ae3f31395a
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4443392"
---
# <a name="set-up-collections"></a>Paramétrage des recouvrements

[!include [banner](../includes/banner.md)]

Cet article décrit la procédure de paramétrage de la fonctionnalité de recouvrement. Vous devez terminer certaines étapes de configuration lorsque vous utilisez la fonction de recouvrement. Il existe également des fonctions facultatives, dont les regroupements de clients et les équipes de recouvrement. 

- Définitions des périodes de balances âgées
- Instantanés de balance âgée
- Noms de journal
- Codes motif pour les transactions d’annulation
- Agents de recouvrement
- Compte d’annulation
- Informations de fonds insuffisants (impayés)
- Paramètres Outlook pour ceux qui utilisent la page **Recouvrements**
- Adresses e-mail

Ces points sont davantage abordés dans la suite de cette rubrique. 

<a name="set-up-aging-period-definitions"></a>Paramétrer les définitions de périodes de balances âgées
-------------------------------

Paramétrez une définition de plage âgée. Une définition de plage âgée définit les colonnes qui s’affichent sur les pages de liste **Soldes chronologiques**, **Activités de recouvrement** et **Dossiers de recouvrement**. Elle définit également les périodes qui s’affichent sur la page **Recouvrement**. Si vous paramétrez un regroupement de clients, la définition de plage âgée extraite de celui-ci est utilisée. Si aucun regroupement n’est paramétré, la définition de plage âgée par défaut spécifiée sur la page **Paramètres des ventes** est utilisée. Si aucune définition de plage âgée par défaut n’est spécifiée, la première définition de plage âgée figurant sur la page **Définitions des plages âgées** est utilisée.

## <a name="create-an-aging-snapshot"></a>Création d’un instantané de balance âgée
Créez des enregistrements d’instantané de balance âgée pour tous les clients ou pour les clients d’un regroupement de clients. Les informations relatives aux instantanés de balance âgée s’affichent sur la page de liste **Soldes chronologiques** et sur la page **Recouvrements**. Vous devez créer un instantané de balance âgée avant d’utiliser la page de liste. La page de liste affiche des informations uniquement pour les clients pour lesquels un instantané de balance âgée a été créé.

## <a name="optional-set-up-customer-pools"></a>Paramétrer des regroupements de clients (facultatif)
Vous pouvez paramétrer des regroupements de clients pour représenter des groupes de clients. Vous pouvez utiliser les regroupements de clients en tant que filtres des informations client qui s’affichent sur les pages de liste **Recouvrements**, sur la page **Recouvrements**, ou lors de la création d’instantanés de balance âgée.

## <a name="optional-create-a-collections-team"></a>Créer une équipe de recouvrement (facultatif)
Si plusieurs personnes de votre organisation effectuent des recouvrements, vous pouvez paramétrer une équipe de recouvrement. Vous pouvez sélectionner l’équipe sur la page **Paramètres des ventes**. Si vous ne créez pas d’équipe de recouvrement, une équipe est créée automatiquement lorsque vous paramétrez des agents de recouvrement sur la page **Agent de recouvrement**.

## <a name="set-up-a-collections-case-category"></a>Paramétrage d’une catégorie d’incidents de recouvrement
Pour utiliser des incidents pour organiser votre travail de recouvrement, configurez catégorie d’incident dont le type est **Recouvrements**. Cela est obligatoire si vous voulez utiliser la fonctionnalité d’incident sur la page **Recouvrements**.

## <a name="set-up-journal-names-settlement-writeoff-and-nsf"></a>Paramétrage des noms de journaux (règlement, annulation et impayés)
Paramétrez les noms des journaux utilisés lorsque les transactions sont traitées sur la page **Recouvrements**. Ce traitement inclut le règlement d’une transaction, l’annulation d’une transaction et le traitement d’un paiement de fonds insuffisants (impayés).

| Description | Type de journal     |
|-------------|------------------|
| Lettrage  | Client - Paiements |
| Annulation   | Quotidienne            |
| Impayés         | Client - Paiements |

## <a name="set-up-a-reason-code-for-writeoff-transactions"></a>Paramétrage d’un code motif pour les transactions d’annulation
Paramétrez le code motif par défaut utilisé lorsque les transactions sont annulées sur la page **Recouvrements**. Vous pouvez modifier le code lors du processus d’annulation.

## <a name="set-up-a-folder-for-email-attachments-and-create-email-templates"></a>Paramétrage d’un dossier pour les pièces jointes et création de modèles d’e-mail
Si vous envoyez des messages e-mail avec des documents Microsoft Excel en pièces jointes à partir de la page **Recouvrements**, vous pouvez créer des modèles d’e-mail facultatifs pour ces messages.

## <a name="set-up-accounts-receivable-parameters-for-collections"></a>Paramétrage des paramètres des ventes pour les recouvrements
Configurez les paramètres de ventes qui s’affichent sous l’onglet **Recouvrements**.

## <a name="optional-set-up-collections-agents"></a>Paramétrer des agents de recouvrement (facultatif)
Si plusieurs personnes de votre organisation effectuent des recouvrements, vous pouvez paramétrer des agents de recouvrement. Un agent de recouvrement est un collaborateur paramétré en tant qu’utilisateur sur la page **Relations utilisateur**. Vous pouvez affecter des regroupements de clients (requêtes client) aux agents de recouvrement pour les aider à organiser leur travail. Les agents de recouvrement sont ajoutées à l’équipe sélectionnée sur la page **Paramètres des ventes**. Si aucune équipe n’est sélectionnée sur cette page, une équipe appelée **Recouvrements** est créée automatiquement et les agents de recouvrement y sont ajoutés.

## <a name="set-up-a-writeoff-account"></a>Paramétrage d’un compte d’annulation
Paramétrez le compte d’annulation utilisé pour l’écriture d’annulation dans la comptabilité lors de l’annulation d’une transaction. Ce compte est stocké dans le profil de validation client.

## <a name="set-up-nsf-information-for-bank-accounts"></a>Paramétrage d’informations sur les impayés pour les comptes bancaires
Mettez à jour les comptes bancaires afin qu’ils soient dotés du journal approprié lorsque les paiements des impayés sont identifiés sur la page **Recouvrements**. Sous l’onglet **Gestion des devises**, dans le champ **Journal de paiement des impayés**, sélectionnez un journal des paiements.

## <a name="set-up-outlook-settings-for-users-of-the-collections-page"></a>Configuration des paramètres Outlook pour les utilisateurs de la page Recouvrements
Avant que les collaborateurs puissent créer des activités ou envoyer des messages e-mail par l’intermédiaire de la page **Recouvrements**, vous devez vérifier que la clé de configuration **Synchronisation Microsoft Outlook** est sélectionnée et que la synchronisation Outlook est paramétrée pour ces collaborateurs.

## <a name="set-up-email-and-addresses"></a>Configurer les e-mails et les adresses
Vous pouvez utiliser l’e-mail pour communiquer avec les clients et les commerciaux sur les problèmes de recouvrement afin d’envoyer des e-mails à partir de la page **Recouvrements**. 

### <a name="set-up-email-and-address-settings-for-collections-customer-contacts"></a>Définition des paramètres d’adresse et d’e-mail pour les contacts de recouvrement (clients)
Configurez les adresses e-mail des clients pour leur envoyer des e-mails à partir de la page **Recouvrements**. Le contact de recouvrement est utilisé comme contact par défaut sur la page **Recouvrements**. Vous pouvez paramétrer une adresse de relevé pour un client si l’adresse du relevé est différente de l’adresse principale. 

Dans l’organisateur **Crédit et relances** pour un client, dans le champ **Contact de recouvrement**, sélectionnez la personne de l’organisation cliente qui collabore avec votre agent de recouvrement. Cette personne est utilisée comme contact par défaut sur la page **Recouvrements**. Il s’agit du destinataire des messages e-mail. 

> [!NOTE] 
> Si aucun contact de recouvrement n’est spécifié pour le client, le contact principal du client est utilisé. Si aucun contact principal n’est spécifié, les messages e-mail sont envoyés à la première adresse répertoriée sur la page **Contacts**.

### <a name="set-up-email-settings-for-salespeople"></a>Définition des paramètres d’e-mail pour les commerciaux
Configurez les adresses e-mail des commerciaux pour leur envoyer des e-mails à partir de la page **Recouvrements**. Paramétrez une adresse e-mail pour chaque commercial de chaque groupe de ventes de commission. Le commercial pour lequel l’option **Contact** est sélectionnée est le commercial par défaut auquel les messages e-mails sont envoyés. 

Si aucun commercial n’est spécifié, le commercial principal de l’organisation cliente est utilisé. Si aucun commercial principal n’est spécifié, les messages e-mail sont envoyés au premier commercial répertorié sur la page.


Pour plus d’informations, voir les rubriques suivantes :

 - [Créer une série de lettres de relance](tasks/create-collection-letter-sequence.md)

 - [Traiter les lettres de relance](tasks/process-collection-letters.md)

 - [Réviser les informations de recouvrement](tasks/review-collections-information.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]