---
title: Traitement des reçus de dépenses
description: Cette rubrique fournit des informations sur le traitement de reconnaissance optique de caractères (OCR) pour les reçus. Cette fonctionnalité est conçue pour améliorer l'expérience utilisateur lors de la création de notes de frais dans Microsoft Dynamics 365 Finance.
author: stsporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 2e819521828b054f70476b1eb061ee08c486d09f
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113684"
---
# <a name="public-preview-expense-receipt-processing"></a>Aperçu public : traitement des reçus de dépenses

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


La saisie des dépenses a été améliorée grâce à l'introduction du traitement de reconnaissance optique de caractères (OCR) pour les reçus. Cette fonctionnalité est conçue pour améliorer l'expérience utilisateur lors de la création de notes de frais.

## <a name="key-features"></a>Fonctions principales

- Le nom du commerçant, la date et le montant total sont extraits des reçus.
- La fonctionnalité essaie de faire correspondre les reçus non associés aux transactions de dépenses non associées.
- Les utilisateurs peuvent créer des transactions de dépenses saisies manuellement à partir des reçus.

## <a name="usage-examples"></a>Exemples d'utilisation

- **Joignez automatiquement des reçus qui incluent des transactions par carte de crédit lors de la création d'un rapport de dépenses.**

    1. Ouvrez l'espace de travail **Gestion des dépenses**.
    2. Sur l'onglet **Reçus**, vérifiez que des reçus non associés existent. Vous pouvez également télécharger des reçus sur l'onglet **Reçus**.
    3. Sur l'onglet **Dépenses**, vérifiez que des dépenses non associées existent. En règle générale, l'administrateur des dépenses importe ces dépenses depuis le fournisseur de carte de crédit.
    4. Sélectionnez **Nouvel état de dépenses**. Notez que vous pouvez désormais inclure des dépenses et des reçus lorsque vous créez un rapport de dépenses. Si vous ajoutez des dépenses et des reçus, l'appariement automatique des reçus avec les dépenses est déclenché.

- **Créez une dépense ou faites correspondre une dépense à partir d'un reçu.**

    1. Sur un rapport de dépenses, sur l'onglet **Reçus**, joignez un reçu en sélectionnant **Ajouter des reçus**.
    2. Sous l'image téléchargée du reçu, notez les options **Créer**et **Correspondance**.

        - Sélectionnez **Créer** pour créer une transaction de dépenses saisie manuellement et remplir les valeurs extraites du reçu.
        - Si vous sélectionnez **Correspondance**, le système essaie de faire correspondre une dépense existante au reçu.

## <a name="installation"></a>Installation

Cette fonctionnalité fonctionne en combinaison avec la fonctionnalité **États de dépenses repensés** pour simplifier l'expérience des dépenses.

Pour utiliser ces capacités de dépenses avancées, installez le complément Expense Management Service pour Microsoft Dynamics 365 Finance et activez les fonctionnalités dans votre instance. Vous pouvez accéder au complément à partir de votre projet dans Microsoft Dynamics Lifecycle Services (LCS).

1. Connectez-vous à LCS, et ouvrez l'environnement souhaité.
2. Accédez à **Détails complets**.
3. Sélectionnez **Mettre à jour**, ou faites défiler jusqu'à l'organisateur **Compléments d'environnement**.
4. Sélectionnez **Installer un nouveau complément**.
5. Sélectionnez **Expense Management Service**.
6. Suivez le guide d'installation, et acceptez les conditions générales du contrat.
7. Sélectionnez **Installer**.

Dans l'espace de travail **Gestion des fonctionnalités**, activez les fonctionnalités suivantes.

- États de dépenses repensés
- Mise en correspondance automatique et création de dépenses à partir du reçu

Lorsque vous activez ces fonctionnalités, les actions suivantes se produisent :

- L'espace de travail **Gestion des dépenses** existant est remplacé par le nouvel espace de travail.
- Une nouvelle option de menu pour la visibilité du champ de dépenses est ajoutée.
- Vous pouvez toujours ouvrir l'ancienne page **États de dépenses** en accédant à **Gestion des dépenses > Mes dépenses > États de dépenses**.
- Les workflows et les approbations vous dirigent toujours vers la page d'états de dépenses existante.
- Les reçus seront traités par Microsoft Azure Cognitive Services et les métadonnées seront extraites et ajoutées.
- Une option est ajoutée vous permettant de créer un rapport de dépenses qui inclut les reçus non associés correspondants.
- Une option qui est ajoutée aux notes de frais vous permet de créer une ligne de dépenses à partir d'un reçu ou tente de faire correspondre un reçu existant à une ligne de dépenses existante.

Pour plus d'informations sur la fonction repensée des rapports de dépenses, voir [États de dépenses repensés](ExpenseWorkspaceNew.md).

## <a name="frequently-asked-questions"></a>Forum aux questions

**Microsoft utilise-t-il mes données pour ses modèles ?**

Non, Microsoft a construit un modèle général d'apprentissage automatique pour son service de traitement des reçus. Ce modèle n'est pas basé sur les reçus que vous téléchargez.

**Où cette fonctionnalité est-elle disponible et traitée ?**

Actuellement, les États-Unis sont pris en charge.

**Où vont mes reçus ?**

La Finance contactera Cognitive Services pour extraire les données de terrain. Cognitive Services conservera une copie de votre reçu jusqu'à 24 heures pendant le traitement. Une fois le traitement terminé, Cognitive Services supprimera le reçu. Les reçus sont toujours stockés dans Finance.

Pour plus d'informations, voir [Activer la reconnaissance des reçus avec la nouvelle fonctionnalité de reconnaissance](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).
