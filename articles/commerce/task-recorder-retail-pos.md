---
title: Enregistreur de tâches et aide pour Retail Modern POS (MPOS) et Cloud POS
description: Cet article décrit comment utiliser l’enregistreur de tâches dans Retail Modern POS et Cloud POS.
author: josaw1
ms.date: 06/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 1205393
ms.assetid: 2f13e9cf-55b5-458b-8c32-3f8cd98c9ecf
ms.search.industry: Retail
ms.search.form: RetailTerminalTable, SystemParameters
ms.openlocfilehash: 32d5c959c044a628a6ed1044b6e30f3363680293
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267456"
---
# <a name="task-recorder-and-help-for-retail-modern-pos-mpos-and-cloud-pos"></a>Enregistreur de tâches et aide pour Retail Modern POS (MPOS) et Cloud POS

[!include [banner](includes/banner.md)]

Cet article décrit comment utiliser l’enregistreur de tâches dans Retail Modern POS et Cloud POS.

## <a name="overview"></a>Présentation

L’enregistreur de tâches dans Retail Modern POS ou Cloud POS est une nouvelle solution qui met l’accent sur la réactivité élevée. Il fournit une interface de programmation d’applications flexible (API) pour l’extensibilité et l’intégration transparente avec les consommateurs d’enregistrements de processus d’entreprise. En outre, l’intégration de l’enregistreur de tâches avec l’outil Concepteur de processus d’entreprise (BPM) sur Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) a été mise en avant. Par conséquent, les utilisateurs peuvent continuer à produire des diagrammes de processus d’entreprise complets à partir des enregistrements pour analyser et créer leurs applications.

## <a name="architecture"></a>Architecture

L’enregistreur de tâches peut enregistrer les actions de l’utilisateur dans le client avec une fidélité exacte. Chaque contrôle est instrumenté pour informer l’enregistreur de tâches de l’exécution d’une action de l’utilisateur. Le contrôle informe l’enregistreur de tâches qu’un événement s’est produit et lui transmet toutes les informations pertinentes sur l’action utilisateur correspondante en temps réel. À partir de ces informations, l’enregistreur de tâches peut capturer le type d’action de l’utilisateur (par exemple un clic sur un bouton, une saisie de valeur ou une navigation) et les données associées à l’action de l’utilisateur (par exemple, la valeur et le type de données de saisie, le contexte d’écran ou le contexte d’enregistrement). L’enregistreur de tâches présente les informations avec suffisamment de détails pour garantir que la lecture de l’enregistrement peut exécuter les actions enregistrées exactement comme l’utilisateur les a exécutées. (La fonction de lecture n’est pas encore implémentée dans Retail Modern POS ou Cloud POS).

## <a name="basic-configuration"></a>Configuration de base

Pour activer l’enregistrement de tâches dans POS, procédez comme suit :

1. Cliquez sur **Retail et Commerce** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Caisses enregistreuses**.
2. Cliquez sur la caisse enregistreuse sur laquelle activer l’enregistrement de tâches.
3. Sous l’onglet **Caisse enregistreuse**, sous l’organisateur **Général**, définissez l’option **Activer enregistrement de tâche** sur **Oui**.
4. Cliquez sur **Enregistrer**.
5. Accédez à **Retail et Commerce** &gt; **Informatique Retail et Commerce** &gt; **Programme de distribution**.
6. Sélectionnez la tâche **Caisses enregistreuses (1090)**, puis cliquez sur **Exécuter maintenant**.

## <a name="create-a-recording"></a>Créer un enregistrement

Pour créer un enregistrement à l’aide de l’enregistreur de tâches, procédez comme suit :

1. Démarrez Retail Modern POS ou Cloud POS, puis connectez-vous.
2. Dans la page **Paramètres**, dans la section **Enregistreur de tâches**, cliquez sur **Ouvrir l’enregistreur de tâches**. Le volet **Enregistreur de tâches** apparaît. Vous pouvez cliquer sur le bouton **Fermer** (**X**) dans l’angle supérieur droit pour fermer le volet **Enregistreur de tâches** avant de commencer un nouvel enregistrement. Pour rouvrir le volet, répétez l’étape 2.

    [![Volet Enregistreur de tâches.](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)

3. Entrez un nom et une description pour l’enregistrement, puis cliquez sur **Démarrer**. La session d’enregistrement commence dès que vous cliquez sur **Démarrer**.

    > [!NOTE]
    > Si vous cliquez sur le bouton **Fermer** (**X**) dans l’angle supérieur droit alors que l’enregistrement est en cours, le volet **Enregistreur de tâches** se ferme, mais la session d’enregistrement n’est pas terminée. Pour rouvrir le volet Enregistreur de tâches, cliquez sur le bouton **Aide** (point d’interrogation) en haut de l’écran.
    >
    > [![Point d’interrogation.](./media/help.jpg)](./media/help.jpg)

4. Une fois que vous cliquez sur **Démarrer**, l’enregistreur de tâches active le mode enregistrement. Le volet **Enregistreur de tâches** affiche des informations et des contrôles associés au processus d’enregistrement.
5. Exécutez les actions souhaitées dans l’interface utilisateur de Retail Modern POS ou de Cloud POS.
6. Pour terminer la session d’enregistrement, cliquez sur **Arrêter**.

## <a name="download-options"></a>Options de téléchargement

Une fois la session d’enregistrement terminée, plusieurs options s’affichent pour vous permettre de télécharger votre enregistrement.

[![Options de téléchargement.](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)

### <a name="save-to-this-pc"></a>Enregistrer sur le PC

Vous pouvez utiliser le package d’enregistrement pour lire un guide de tâche, tenir à jour l’enregistrement ou modifier les annotations de l’enregistrement. (Cette fonction n’est pas encore implémentée dans Retail Modern POS et Cloud POS).

### <a name="export-as-word-document"></a>Exporter comme document Word

Vous pouvez enregistrer l’enregistrement en tant que document Microsoft Word. Le document contient les étapes enregistrées et les écrans capturés.

### <a name="save-as-developer-recording"></a>Enregistrer comme enregistrement du développeur

Le fichier d’enregistrement brut est utile dans les scénarios de développement, tels que la génération de code de test. (Cette fonction n’est pas encore implémentée.)

## <a name="recording-controls"></a>Contrôles d’enregistrement

[![Contrôles d’enregistrement.](./media/controls.jpg)](./media/controls.jpg)

### <a name="stop"></a>Arrêter

Cliquez sur **Arrêter** pour terminer la session d’enregistrement. Notez que vous ne pouvez pas redémarrer une session après l’avoir terminée. Par conséquent, vérifiez que l’enregistrement est terminé avant d’y mettre fin.

### <a name="pause"></a>Suspendre

Cliquez sur **Suspendre** pour arrêter temporairement (suspendre) la session d’enregistrement et poursuivre l’opération. Les étapes que vous effectuez après avoir cliqué sur **Suspendre** ne sont pas enregistrées.

### <a name="continue"></a>Continuer

Pour reprendre une session d’enregistrement suspendue, cliquez sur **Continuer**.

### <a name="capture-screenshots"></a>Capturer les écrans

L’enregistreur de tâches peut effectuer des captures d’écran de l’interface utilisateur de Retail Modern POS lorsque vous enregistrez un processus d’entreprise. Pour activer la fonction de capture d’écran, définissez l’option **Capturer les écrans** sur **Oui**, puis effectuez l’enregistrement. Une fois que l’enregistrement est terminé, cliquez sur **Arrêter** et téléchargez le document Word. Le document contient les étapes avec les captures d’écran appropriées.

> [!NOTE]
> La fonctionnalité de capture d’écran n’est pas prise en charge dans Store Commerce, Commerce Modern POS et Cloud POS.

### <a name="start-task-and-end-task"></a>Commencer la tâche et Terminer la tâche

Vous pouvez spécifier le début et la fin d’un ensemble d’étapes groupées en utilisant les boutons **Commencer la tâche** et **Terminer** **la tâche**. Cliquez sur **Commencer la tâche** pour ajouter une étape « Commencer la tâche », puis effectuez les étapes qui doivent être incluses dans le groupe. Lorsque vous avez terminé d’effectuer les étapes pour le groupe, cliquez sur **Terminer la tâche**. Les tâches vous aident à organiser vos procédures. Les tâches peuvent être imbriquées dans d’autres tâches. Vous pouvez ainsi mieux organiser les processus d’entreprise très longs et complexes.

## <a name="adding-annotations"></a>Ajout d’annotations

Une annotation est un texte supplémentaire que vous ajoutez à une étape d’un enregistrement. Par exemple, vous pouvez utiliser des annotations pour fournir à l’utilisateur plus de contexte ou d’instructions. Vous pouvez ajouter des annotations avant ou après une étape. Vous pouvez ajouter une annotation à une étape en cliquant sur le bouton **Modifier** (symbole de crayon) à droite de l’étape.

[![Bouton Modifier pour une étape.](./media/annotate.jpg)](./media/annotate.jpg)

### <a name="texts-and-notes"></a>Textes et notes

Vous pouvez utiliser les champs **Textes** et **Notes** pour ajouter du texte à associer à une étape dans un guide de tâche.

[![Champs Texte et Notes.](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)

#### <a name="text"></a>Détails

Le texte que vous entrez dans le champ **Texte** apparaît *au-dessus* du texte de l’étape dans le guide de tâche. Cet emplacement est approprié pour le texte que l’utilisateur doit lire avant de terminer l’étape.

#### <a name="notes"></a>Notes

Le texte que vous entrez dans le champ **Notes** apparaît *en dessous* du texte de l’étape dans le guide de tâche. Pour lire le texte de la note, l’utilisateur peut développer le texte de l’étape dans la fenêtre contextuelle. Cet emplacement est approprié pour la documentation facultative à lire ou d’autres informations qui peuvent être utiles à l’utilisateur, mais ne sont pas nécessaires pour exécuter l’action.

## <a name="help-in-retail-modern-pos-and-cloud-pos"></a>Aide dans Retail Modern POS et Cloud POS

Pour afficher vos propres enregistrements personnalisés de tâche dans le volet Aide de Retail Modern POS et de Cloud POS afin qu’ils puissent être affichés comme texte, vous devez enregistrer vos enregistrements de tâches dans votre propre bibliothèque BPM, puis mettre à jour vos paramètres du système d’aide pour pointer vers votre bibliothèque BPM. Pour plus d’informations, consultez [Connexion au système d’aide](../fin-ops-core/fin-ops/get-started/help-connect.md). L’aide Retail Modern POS et Cloud POS effectue des recherches dans LCS en temps réel. Elle effectue des recherches dans toutes les bibliothèques BPM sélectionnées dans les paramètres du système d’aide de Commerce et affiche les résultats pertinents. Pour accéder au menu **Aide**, cliquez sur le bouton **Aide** (point d’interrogation) en haut de l’écran, puis dans la zone de recherche, tapez le nom de votre processus et cliquez sur le bouton de recherche.

[![Bouton Aide.](./media/help.jpg)](./media/help.jpg)

Lorsque vous cliquez sur un Guide des tâches dans les résultats de la recherche, vous pouvez afficher les étapes sous forme d'article d’aide et exporter les étapes dans un document Word.

> [!NOTE]
> L’aide de Retail Modern POS et de Cloud POS n’affiche pas les guides de tâches en fonction de l’écran que vous affichez ou de l’opération que vous effectuez. Vous devez taper le nom du processus dans la zone de recherche et cliquer sur **Rechercher**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
