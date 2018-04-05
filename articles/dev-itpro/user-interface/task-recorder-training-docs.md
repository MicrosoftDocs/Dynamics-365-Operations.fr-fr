---
title: "Création d'une documentation ou d'une formation à l'aide d'enregistrements de tâche"
description: "Cette rubrique explique ce que sont l'enregistreur de tâches et les guides de tâche, comment créer des enregistrements de tâches, et comment personnaliser les guides de tâches Microsoft et les inclure dans votre rubrique d'aide."
author: josaw1
manager: AnnBe
ms.date: 10/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 9550faec1bbbdc233631e149c09b8e4faf25f5ff
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="create-documentation-or-training-using-task-recordings"></a>Création d'une documentation ou d'une formation à l'aide d'enregistrements de tâche

[!include[banner](../includes/banner.md)]

Cette rubrique explique ce que sont l'enregistreur de tâches et les guides de tâche, comment créer des enregistrements de tâches, et comment personnaliser les guides de tâches Microsoft et les inclure dans votre rubrique d'aide.

> [!IMPORTANT]
> Vous pouvez enregistrer vos propres guides de tâche pour Dynamics 365 for Talent mais vous ne pourrez pas les enregistrer dans une bibliothèque Concepteur de processus d'entreprise (BPM) ou les ouvrir à partir du volet d'aide pour le moment. Vous pouvez les enregistrer localement ou dans un emplacement réseau, puis les ouvrir et les relire à l'aide de l'enregistreur de tâches. 

<a name="learn-about-task-recorder"></a>Découverte de l'Enregistreur de tâche
-------------------------

L'enregistreur de tâches est un outil que vous pouvez utiliser pour enregistrer les actions que vous effectuez dans l'interface utilisateur du produit. Lorsque vous utilisez l'enregistreur de tâches, tous les événements que vous effectuez dans l'IU qui sont exécutés par rapport au serveur (notamment l'ajout de valeurs, la modification de paramètres, la suppression de données) sont capturés. Les étapes que vous enregistrez sont collectivement appelées un *enregistrement de tâche*. Les enregistrements de tâche peuvent être utilisés de plusieurs manières :

-   **Les enregistrements de tâches peuvent être lus comme guides de tâche.** Les guides de tâches font partie intégrante de l'expérience d'aide. Un guide de tâche est une expérience contrôlée, guidée et interactive qui parcourt les étapes d'un processus métier. L'utilisateur est invité à compléter chaque étape par une invite contextuelle (ou « bulle »), qui anime l' IU et pointe vers l'élément de l'IU avec lequel l'utilisateur doit interagir. La « bulle » fournit également des informations sur la manière d'interagir avec l'élément, par exemple « Cliquez ici » « ou « Dans ce champ, entrez une valeur ». Un Guide de tâche s'exécute pour l'ensemble de données de l'utilisateur actif et les données entrées sont enregistrées dans l'environnement de l'utilisateur.
-   **Les enregistrements de tâche peuvent être affichés en tant que procédures décomposées en étapes dans le volet Aide.** Vous pouvez utiliser le volet Aide pour chercher et afficher des enregistrements de tâche. Vous pouvez accéder au volet Aide en cliquant sur l'icône **?** dans la barre de navigation supérieure, ou vous pouvez utiliser la combinaison de touches de raccourci, **Ctrl+Shift+?**. Vous pouvez lire les étapes d'un enregistrement de tâche dans le volet Aide, ou vous pouvez choisir de lire l'enregistrement comme guide de tâche, ce qui vous guide dans l'IU.
-   **Les enregistrements de tâches peuvent être enregistrés dans BPM.** Vous pouvez sauvegarder votre enregistrement de tâche dans une ligne de hiérarchie d'une bibliothèque BPM dans LCS (Lifecycle Services). Une liste des étapes et un schéma de flux de processus entreprise sera généré à partir de l'enregistrement. Les enregistrements de tâche qui ont été enregistrés dans une bibliothèque BPM peuvent être affichés en tant qu'aide.
-   **Les enregistrements de tâche peuvent être enregistrés comme documents Word.** Cela permet de créer facilement des manuels de formation imprimables.

Vous pouvez créer vos propres enregistrements de tâche, lire des enregistrements de tâche fournis par Microsoft, ou modifier des enregistrements de tâche Microsoft pour mieux refléter votre configuration. Pour plus d'informations sur l'enregistreur de tâches, consultez [Enregistreur de tâches](task-recorder.md).

## <a name="plan-your-task-recording"></a>Planifier votre enregistrement de tâche
Que vous créiez un enregistrement de tâche à partir de rien ou en le fondant sur un enregistrement Microsoft, conservez les informations suivantes à l'esprit.

-   Organisez votre enregistrement comme vous le feriez d'une vidéo. Prenez toutes vos décisions par avance.
-   Parcourez le processus d'entreprise une fois ou deux sans l'enregistrer pour comprendre les étapes.
-   Lorsque vous parcourez le processus avant de l'enregistrer, notez où vous utilisez les touches de raccourci ou la touche **Entrée**, afin d'éviter de les utiliser lors de l'enregistrement réel.
-   Identifiez les éléments suivants :
    -   Souhaitez-vous grouper des étapes en sous-tâches ? Les sous-tâches divisent les sections d'un processus. Par exemple, si vous créez un enregistrement pour « Créer et lancer un produit », vous pouvez souhaiter regrouper ensemble les étapes requises pour créer un produit, puis grouper ensemble les étapes requises pour lancer le produit. Les tâches facilitent également la compréhension des processus longs.
    -   Souhaitez-vous ajouter des annotations, et si oui, où ? Consultez « Comprendre les différents types d'annotations » ci-dessous pour plus d'informations.
    -   Quelles valeurs ajouterez-vous dans les divers champs à mesure que vous effectuez les étapes du processus d'entreprise ? Il est judicieux de savoir ce que vous sélectionnerez ou entrerez au fil de votre parcours, de sorte de ne pas faire d'erreur ou devoir revenir en arrière au cours de l'enregistrement.

**Écrivez vos descriptions et annotations à l'avance**

-   Au début de chaque enregistrement de tâche, il se trouve un champ de description qui vous permet d'entrer une présentation de l'enregistrement. Il est bon d'écrire et enregistrer à l'avance cette description dans un document distinct, de sorte de pouvoir la copier et coller dans l'enregistrement de tâche au cours de l'enregistrement. vous pouvez de cette manière consacrer du temps à peaufiner le texte en dehors de l'enregistrement. Le fait de copier-coller le texte facilite et accélère la procédure d'enregistrement.
-   Pour chaque étape de l'enregistrement de tâche, vous pouvez créer des annotations. Lors de la lecture d'un guide des tâche, des annotations apparaissent dans des « bulles » au-dessus ou au-dessous du texte des étapes. Quand elles sont affichées comme texte dans le volet Aide, les annotations apparaissent comme texte inclus dans l'étape. Comme pour la description, il est bon d'écrire et enregistrer à l'avance les annotations dans un document distinct. Lorsque vous enregistrez l'enregistrement de tâche, coupez et collez les annotations à partir de ce document.

**Comprendre les différents types d'annotations** Toutes les annotations sont facultatives. Ne les ajoutez que si elles apportent des informations utiles pour l'utilisateur.

-   **Titre** : une annotation de titre s'affiche avant le texte d'étape généré automatiquement par l'enregistreur de tâche. Dans le guide de tâche, l'annotation de titre s'affiche au-dessus du texte généré automatiquement. Utilisez ce type d'annotation pour expliquer la raison pour laquelle l'utilisateur effectue l'étape ou pour donner du contexte supplémentaire.

Ceci est le volet de modification proposé lorsque vous ajoutez une annotation à mesure que vous créez votre enregistrement. Entrez une annotation de titre dans la zone **Titre**. 

[![screen1](./media/screen1.png)](./media/screen1.png) 

Voilà à quoi ressemble l'annotation de titre dans la « bulle » dans le Guide de tâche. 

[![screen2](./media/screen2.png)](./media/screen2.png)

-   **Remarques :** une annotation de remarque s'affiche après le texte d'étape généré automatiquement par l'enregistreur de tâche. Dans le guide de tâche, elle n'est visible que si l'utilisateur clique sur le lien **Afficher plus** dans la bulle du guide de tâche. Utilisez ce type d'annotation pour décrire tout ce que l'utilisateur a besoin de savoir pour effectuer l'étape.

Ceci est le volet de modification proposé lorsque vous ajoutez une annotation à mesure que vous créez votre enregistrement. Entrez une annotation de notes dans la zone **Notes**. 

[![screen3](./media/screen3.png)](./media/screen3.png) 

Voilà à quoi ressemble l'annotation de notes dans la « bulle » dans le Guide de tâche.

[![screen4](./media/screen4.png)](./media/screen4.png)

-   **Étape d'informations** : ces annotations sont créées en cliquant avec le bouton droit sur un contrôle ou n'importe où dans un écran &lt; **Enregistreur de tâche** &lt; **Ajouter une étape d'informations. **Les étapes d'informations apparaissent comme une étape numérotée au point où vous l'insérez, même si aucune action n'a été enregistrée dans l'IU. Vous pouvez ajouter une étape d'informations au niveau de l'écran ou une étape d'informations associée à un contrôle. Lorsqu'une étape d'informations est associée à un écran, la « bulle » du guide de tâche apparaît quelque part dans l'écran, sans pointeur, lors de la lecture du guide. Lorsqu'une étape d'informations est associée à un contrôle, la « bulle » du guide de tâche pointe vers le contrôle lors de la lecture du guide. Dans le volet Aide, une annotation d'étape d'informations s'affiche comme une étape numérotée, indépendamment du texte que vous avez entré. Utilisez les étapes d'informations pour préparer l'utilisateur aux étapes suivantes, pour décrire les étapes qui doivent être effectuées en dehors de Microsoft Dynamics 365 for Finance and Operations ou pour faire référence à d'autres enregistrements (bien que vous ne puissiez pas créer d'hyperliens dans les annotations.).

**Déterminez la longueur votre enregistrement**

-   L'utilisateur lira ou généralement l'enregistrement du début à la fin, alors ne combinez pas d'étapes ou de tâches qu'il vaut mieux effectuer séparément.
-   Ne tentez pas d'enregistrer un long scénario qui s'étend sur plusieurs sous-processus. Par exemple, « Fonctionnement du service client en magasin » est trop vaste ; divisez-le en tâches plus courtes comme « Accepter les retours » et « Ajouter à la carte-cadeau ».
-   Si une tâche peut être effectuée dans le cadre de différents processus d'entreprise, créez un enregistrement distinct pour elle auquel vous pouvez faire référence dans d'autres enregistrements.
-   Si le processus implique plusieurs tâches que la personne est susceptible de faire en une seule fois, vous pouvez les garder dans un seul enregistrement, par exemple, « Paramétrage et affectation de profils de fonctionnalités. »
-   Si la tâche est une action que l'utilisateur fait une fois (par exemple la configuration), puis qu'elle est suivie immédiatement d'une autre tâche qui peut être répétée, séparez-les dans deux enregistrements de tâche.

**Décidez où, dans l'IU, démarrer un enregistrement** La page où vous vous trouvez lorsque vous commencez un enregistrement de tâche affecte la page pour laquelle s'affiche le guide de tâche. Par exemple, si vous souhaitez que votre enregistrement de tâche soit répertorié dans le volet Aide lorsque l'utilisateur clique sur Aide dans la page des paramètres de comptabilité, vous devez commencer votre enregistrement dans la page Paramètres de comptabilité. **Sauvegardez les enregistrements en tant que fichiers .axtr** Lorsque vous avez terminé de créer ou modifier un enregistrement de tâche, vous avez le choix entre plusieurs options pour télécharger ou sauvegarder l'enregistrement. Vous pouvez télécharger le fichier comme package d'enregistrement de tâche (.axtr), le télécharger comme fichier brut d'enregistrement (.xml), le télécharger comme document Word, ou l'enregistrer dans une bibliothèque LCS. Il est bon de toujours sauver vos enregistrements de tâche comme fichiers de package d'enregistrement de tâche (.axtr). Cela facilite la maintenance des fichiers si les procédures ou les annotations doivent être modifiées ultérieurement. Si vous souhaitez télécharger le fichier comme document Word, sauvegardez-le également comme package d'enregistrement de tâche.

## <a name="create-your-task-recording"></a>Créer votre enregistrement de tâche
Pour les étapes détaillées du parcours, voir [Création d'un enregistrement de tâche](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>Copie et personnalisation des enregistrements de tâche Microsoft
Vous pouvez télécharger et modifier les enregistrements de tâche de Microsoft pour les utiliser pour votre propre documentation d'aide ou vos propres supports de formation. Pour télécharger un enregistrement de tâche Microsoft, procédez comme suit :

1.  Ouvrez l'enregistreur de tâches. L'enregistreur de tâche se trouve dans le menu **Paramètres**.
2.  Dans le volet Enregistreur de tâche, cliquez sur **Tenir à jour un enregistrement.**
3.  Sous **Où est l'enregistrement**, cliquez sur **Il est dans une bibliothèque LCS**.
4.  Cliquez sur **Sélectionner la bibliothèque LCS**.
5.  Sélectionnez la bibliothèque globale Microsoft.
6.  Dans l'arborescence, sélectionnez le nœud de la bibliothèque de processus d'entreprise avec lequel l'enregistrement de tâche est associé.
7.  Cliquez sur **OK**.
8.  Cliquez sur **Démarrer**.
9.  À ce stade, parcourez l'enregistrement par étapes, en modifiant toutes les étapes souhaitées en les réenregistrant. **Remarque** : si vous souhaitez seulement modifier le texte d'un enregistrement, vous pouvez ouvrir l'enregistrement en mode **Modifier les annotations d'un enregistrement**, puis l'enregistrer.
10. Une fois que l'enregistrement a été lu jusqu'à la fin, cliquez sur **Arrêter** dans la barre de l'enregistreur de tâche en haut de l'écran.
11. Choisissez la manière dont vous souhaitez enregistrer l'enregistrement de tâche.

## <a name="include-your-task-recordings-in-the-help-pane"></a>Intégrer vos enregistrements de tâche dans le volet Aide
Pour afficher vos propres enregistrements personnalisés de tâche dans le volet Aide afin qu'ils puissent être lus comme guides de tâche ou affichés comme texte, vous devez enregistrer vos enregistrements de tâches dans votre propre bibliothèque BPM, puis mettre à jour vos paramètres du système d'aide pour pointer vers votre bibliothèque BPM. Pour plus d'informations, voir [Connexion au système d'aide.](../../fin-and-ops/get-started/help-connect.md)

<a name="see-also"></a>Voir également :
--------

[Aperçu de l'aide](../../fin-and-ops/get-started/help-overview.md)

[Se connecter à l'aide](../../fin-and-ops/get-started/help-connect.md)

[Enregistreur de tâches](task-recorder.md)

[Création de rubriques d'aide enrichies grâce à l'enregistreur de tâches (lien externe)](https://mbspartner.microsoft.com/AX/Videos/970)

