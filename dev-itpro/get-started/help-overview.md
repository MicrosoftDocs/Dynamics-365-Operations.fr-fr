---
title: Vue d&quot;ensemble de l&quot;Aide
description: "Cet article fournit une vue d&quot;ensemble des composants du système d&quot;aide Microsoft Dynamics 365 for Operations. Il décrit également comment fournir de la documentation et une formation personnalisées à votre organisation."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16381
ms.assetid: 018c148c-9cbd-41e0-8186-d75dbf66288f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6f785ac8b9a8be503bf9122f21716f745b17115b
ms.openlocfilehash: f08434b4c818460009644e77da1b37ba86cc1d54
ms.contentlocale: fr-fr
ms.lasthandoff: 04/27/2017


---

# <a name="help-overview"></a>Vue d'ensemble de l'Aide

[!include[banner](../includes/banner.md)]


Cet article fournit une vue d'ensemble des composants du système d'aide Microsoft Dynamics 365 for Operations. Il décrit également comment fournir de la documentation et une formation personnalisées à votre organisation. 

Dynamics 365 for Operations comprend un système d'aide basé sur deux composants principaux :

-   Site de documentation
-   Guides de tâche

Vous pouvez accéder aussi bien aux guides de tâche qu'aux articles à partir du volet Aide dans Dynamics 365 for Operations, comme le montre la copie d'écran suivante. [![Volet Aide](./media/help-pane-ops-task-guides-1024x741.png)](./media/help-pane-ops-task-guides.png) Cet article décrit le système d'aide, et explique comment créer une documentation personnalisée et des ressources de formation pour votre organisation.

## <a name="help-on-docsmicrosoftcom"></a>Aide sur docs.microsoft.com
Le site docs.microsoft.com ([docs.microsoft.com/dynamics365/operations](/dynamics365/#pivot=solutions&panel=solutions_operations) est la principale source de documentation de produit pour Dynamics 365 for Operations. Le site offre les fonctions suivantes :

-   **L'accès au contenu le plus récent** – Le site est un moyen plus rapide et plus flexible pour créer, mettre à disposition et mettre à jour la documentation produit . Par conséquent, il aide à garantir que vous avez accès aux dernières informations techniques.
-   **Un contenu rédigé par des experts** – Le site fournit un ensemble plus riche de documentation produit pouvant être amélioré par les membres de la Communauté, aussi bien à l'intérieur qu'à l'extérieur de Microsoft.
-   **Accès à différents types de contenu** – Le site permet d'accéder rapidement à différents types de contenu sur Dynamics 365 for Operations, comme les présentations Microsoft Office Mix, les guides de tâche, les vidéos et les rubriques.
-   **Un contenu utile pour vos processus métier** – Le site inclut des contenus orientés sur les processus métier, qui tirent profit du modeleur de processus métier (BPM) des LCS (Lifecycle Services) de Microsoft Dynamics.

Nous avons migré tout le contenu de notre wiki d'aide précédent vers les documents. Nous sommes très contents de notre nouveau site et espérons que vous le serez aussi.

### <a name="when-can-we-use-it"></a>Quand peut-on l'utiliser ?

Vous pouvez lire le contenu des documents dès maintenant -- il est entièrement public et ouvert aux recherches sans demander de connexion. Vous pouvez utiliser n'importe lequel de vos moteurs de recherche favoris pour explorer son contenu. Vous pouvez commenter des articles sur le site si vous le souhaitez, en vous connectant.


## <a name="task-guides"></a>Guides de tâche
Un guide de tâche est une expérience contrôlée, guidée, interactive qui vous accompagne le long des étapes d'une tâche ou d'un processus métier. Vous pouvez lire un guide de tâche à partir du volet Aide. Lorsque vous cliquez sur un guide de tâche, le volet Aide affiche les instructions pas-à-pas concernant la tâche. Des guides des tâches localisés sont désormais disponibles. [![Vue de lecture du Guide de tâche](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png) Pour démarrer l'expérience guidée et interactive, cliquez sur **Démarrer le guide de tâche** au bas du volet Aide. Un pointeur noir apparaît et indique l'action que vous devez effectuer. Suivez les instructions qui s'affichent dans l'IU et entrez les données telles qu'elles sont indiquées. [![Instruction d'étape du Guide de tâche](./media/task-guide-step-1-ops.png)](./media/task-guide-step-1-ops.png) **Important :** les données que vous entrez dans un guide de tâche sont réelles. Si vous êtes dans un environnement de production, les données seront saisies dans la société que vous utilisez actuellement.

### <a name="it-all-begins-with-task-recorder"></a>Tout commence avec l'enregistreur de tâches

Les guides de tâche sont créés à l'aide de l'enregistreur de tâches. Lorsque vous utilisez Enregistreur de tâches, toutes les actions effectuées dans l'IU de Dynamics 365 for Operations (cliquer sur des menus, modifier les paramètres, entrer des données) sont enregistrées. Les étapes que vous enregistrez sont collectivement appelées un enregistrement de tâche. Comme nous l'avons expliqué dans la section précédente, les enregistrements de tâche peuvent être affichés dans le volet Aide et lus en tant que guides de tâche. Il existe toutefois d'autres manières d'utiliser les enregistrements de tâches :

-   **Enregistrer les enregistrements de tâches dans BPM** – Vous pouvez enregistrer un enregistrement de tâche dans la bibliothèque BPM dans le crédit. Lorsque vous enregistrez un enregistrement de tâche dans BPM, un organigramme est généré et affiché avec les étapes de l'enregistrement. **Remarque :** pour afficher un enregistrement de tâche dans le volet Aide de Dynamics 365 for Operations et le lire comme un guide de tâche, vous devrez enregistrer l'enregistrement dans une bibliothèque BPM.
-   **Enregistrer les enregistrements de tâche en tant que documents Word** – en enregistrant un enregistrement de tâche en tant que document Microsoft Word, vous pouvez facilement créer des manuels de formation imprimables pour votre organisation.

Pour plus d'informations sur l'enregistrement de tâche, consultez [Enregistreur de tâches dans Dynamics 365 for Operations](../user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Création d'enregistrements de tâche personnalisés

Vous pouvez créer vos propres enregistrements de tâche, ou vous pouvez télécharger et personnaliser un enregistrement de tâche fourni par Microsoft. Par conséquent, vous pouvez créer une Aide personnalisée pour votre organisation qui reflète votre implémentation particulière de Dynamics 365 for Operations. Remarque : pour afficher un enregistrement de tâche dans le volet Aide de Dynamics 365 for Operations et le lire comme un guide de tâche, vous devrez enregistrer l'enregistrement dans une bibliothèque BPM dans LCS. Si vous êtes un partenaire et que vous faites d'une bibliothèque une bibliothèque d'entreprise et la comprenez dans une solution, elle sera à la disposition de vos clients. Pour obtenir des instructions complètes, consultez [Utiliser des enregistrements de tâche pour créer de la documentation ou des formations](../user-interface/task-recorder.md).

## <a name="in-product-help"></a>Aide intégrée au produit
Pour accéder au contenu de l'aide dans Dynamics 365 for Operations, cliquez sur l'icône (**?**) ou sur **Aide**, puis choisissez Aide ou appuyez sur Ctrl+Shift+ ?. Dans les deux cas, le volet Aide s'ouvre. Dans le volet Aide, vous pouvez accéder à des articles ou à des guides de tâche. [![Volet Aide](./media/help-pane-wiki-1024x684.png)](./media/help-pane-wiki.png)

### <a name="accessing-articles-from-the-help-pane"></a>Accès aux articles à partir du volet Aide

À partir du volet Aide, vous pouvez accéder aux articles qui s'appliquent au client Dynamics 365 for Operations. Lorsque vous ouvrez le volet d'aide et que vous cliquez sur l'onglet **Wiki**, vous verrez les articles qui s'appliquent à la page sur laquelle vous vous trouvez dans Dynamics 365 for Operations. Si aucun article n'est trouvé, vous pouvez entrer des mots clés pour affiner votre recherche. Lorsque vous cliquez sur un article dans le volet Aide, un nouvel onglet s'ouvre dans votre navigateur et affiche l'article. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Accès aux guides de tâche à partir du volet Aide

Avant de pouvoir accéder aux guides de tâche à partir du volet Aide, un administrateur système doit accéder à la page **Paramètres système** dans Dynamics 365 for Operations et configurer certains paramètres. **Remarques :**

-   Pour configurer l'aide, vous devez être connecté avec un compte dans le même locataire que le locataire que celui dans lequel Dynamics 365 for Operations est déployé.
-   Il n’est pas possible de se connecter à une bibliothèque LCS depuis une instance de Dynamics 365 for Operations s’exécutant sur un disque dur virtuel (VHD) local.

[![Écran Paramètres système avec les paramètres d'aide](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Sur la page **Paramètres système**, procédez comme suit :

1.  **Important :**la première fois que vous ouvrez l'onglet Aide, vous devez vous connecter à Lifecycle Services. Veillez à cliquer sur le lien au milieu de l'écran, attendez la connexion, fermez la boîte de dialogue, puis cliquez sur OK pour obtenir à l'écran Paramètres.[![Se connecter à LCS](./media/connect-to-lcs-crop-1024x365.png)](./media/connect-to-lcs-crop.png)
2.  Sélectionnez le projet Lifecycle Services auquel se connecter.
3.  Sélectionnez les bibliothèques BPM (dans le projet sélectionné) à partir desquelles récupérer les enregistrements de tâche.
4.  Sélectionnez l'ordre d'affichage des bibliothèques BPM. Cela déterminer l'ordre dans lequel les enregistrements de tâche des bibliothèques s'affichent dans le volet Aide.

Une fois qu'un administrateur système a terminé ces étapes, vous pouvez ouvrir le volet Aide puis cliquer sur l'onglet **Guides de tâche**. Les guides de tâche qui s'appliquent à la page sur laquelle vous vous trouvez dans Dynamics 365 for Operations s'affichent. Si aucun guide de tâche n'est trouvé, vous pouvez entrer des mots clés pour affiner votre recherche. Après avoir cliqué sur le guide de tâche dans le volet Aide, le volet Aide affiche les instructions pas-à-pas et vous pouvez lire le guide de tâche. [![Vue de lecture du Guide de tâche](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png)

### <a name="where-are-the-translated-task-guides"></a>Où se trouvent les guides de tâche traduits ?

Les guides de tâche traduits sont disponibles dans les bibliothèques avec la mention « All languages » dans le titre. Dans Dynamics 365 for Operations, pour afficher l'aide du guide de tâche localisé, assurez-vous que vous êtes connecté à une bibliothèque appropriée. La langue dans laquelle s'affiche un guide de tâche est contrôlée pour chaque utilisateur par les paramètres de langue sous **Options** &gt; **Préférences**. 
-   Si un guide de tâche a été traduit, lorsque vous ouvrez ce guide de tâche, tout le texte du guide de tâche s’affiche dans la langue sélectionnée.
-   Si un guide de tâche n'a pas encore été traduit, lorsque vous ouvrez ce guide de tâche, une partie du texte (texte des commandes) s’affiche dans la langue sélectionnée.

## <a name="additional-resources"></a>Ressources supplémentaires
Le tableau suivant répertorie les sites Web fournissant du contenu Dynamics 365 for Operations. Le contenu de nos sites Web est organisé de manière à suivre le cycle de vie du client. Chaque phase est prise en charge par un ensemble de sites différent. Les sites qui ont un astérisque (\*) en regard de leur nom nécessitent une identification de connexion à l'aide d'un compte associé à un plan de service.

| site ;                                                                     | description ;                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Docs.microsoft.com](/dynamics365/#pivot=solutions&panel=solutions_operations) | Hôtes ou liens vers toute la documentation produit pour Dynamics 365 for Operations.                                                                                                                                                               |
| [Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Fournit un espace de travail collaboratif basé sur le cloud que les clients et leurs partenaires peuvent utiliser pour gérer les projets Dynamics 365 for Operations des préventes à la mise en œuvre et aux opérations. Ce site est utile dans toutes les phases d'une implémentation. |
| [CustomerSource](http://www.customersource.com/)\*                       | Héberge des ressources de formation approfondie et est le principal site de support pour Dynamics 365 for Operations. Une identification peut être demander pour accéder à des ressources spécifiques sur le site.                                                                      |
| [Blog de support](http://aka.ms/AXSupportBlog)                              | Fournit des conseils et des astuces publiés par l'équipe de support de Dynamics 365 for Operations.                                                                                                                                                  |
| [MSDN](http://aka.ms/AXMSDN)                                             | Héberge du contenu de versions précédentes, rédigé pour les développeurs.                                                                                                                                                                       |
| [TechNet](http://aka.ms/TechNet)                                         | Héberge du contenu de versions précédent rédigé pour les informaticiens et les utilisateurs de l'application.                                                                                                                                           |
| [Communauté Dynamics](http://community.dynamics.com/)                  | Héberge des blogs, des forums et des vidéos.                                                                                                                                                                                                           |
| [Microsoft.com/Dynamics/](http://www.microsoft.com/dynamics/)                 | Fournit une évaluation et des informations commerciales.                                                                                                                                                                                                 |



<a name="see-also"></a>Voir également :
--------

[Système d'aide de Dynamics 365 for Operations (fiche téléchargeable)](https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Enregistreur de tâches de Microsoft Dynamics 365 for Operations](../user-interface/task-recorder.md)

[Création d'une documentation ou d'une formation à l'aide d'enregistrements de tâche](../user-interface/task-recorder.md)

[Guides de tâches nouveaux ou mis à jour (novembre 2016)](new-task-guides-november-2016.md)
[Guides de tâches nouveaux ou mis à jour (août 2016)](new-updated-task-guides-available-august-2016.md)
[Guides de tâches nouveaux ou mis à jour (mai 2016)](new-updated-task-guides-available-may-2016.md)
[Guides de tâches nouveaux ou mis à jour (février 2016)](new-task-guides-available-february-2016.md)








