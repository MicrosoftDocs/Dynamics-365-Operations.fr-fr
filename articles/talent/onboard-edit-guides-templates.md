---
title: Modifier les guides et les modèles d'intégration dans Dynamics 365 Talent - Onboard
description: Cette rubrique explique comment ajouter des activités et d'autres informations aux guides et modèles d'intégration dans Microsoft Dynamics 365 Talent - Onboard.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 291f7aefac61c26dfab81cfff28c1c6580d46de5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461179"
---
# <a name="edit-onboarding-guides-and-templates"></a>Modifier les guides et les modèles d'intégration

[!include [banner](includes/banner.md)]

Après avoir créé un guide ou un modèle d'intégration dans Microsoft Dynamics 365 Talent: Onboard, vous devez ajouter une introduction, des activités, des contacts et des ressources. Onboard vous permet d'ajouter du contenu enrichi à vos guides d'intégration, notamment :

- Vidéos YouTube
- Présentations Microsoft Sway
- Applications Microsoft PowerApps
- Vidéos Microsoft Stream
- Formulaires Microsoft Forms
- Iframes contenant du contenu Web

## <a name="edit-introductions-or-activities-imported-from-a-template"></a>Modifier des introductions ou des activités importées à partir d'un modèle

Si vous créez un guide d'intégration à partir d'un modèle, ou si vous importez des activités d'un modèle vers un autre, vous remarquerez un bouton **Verrouiller** sur les activités importées. Celles-ci sont appelées des *activités gérées*.

[![Activités gérées](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)

Lorsque vous sélectionnez une activité gérée, le modèle source s'affiche en haut de l'activité.

[![Source de l'activité gérée](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)

Si vous modifiez une activité dans un modèle, Onboard envoie les modifications à tous les modèles et guides non envoyés basés sur ce modèle. Si vous sélectionnez un guide non envoyé basé sur un modèle que vous avez modifié, puis vous sélectionnez l'onglet **Activités** dans le guide, une notification de modification de votre guide s'affiche. Pour ignorer la notification, sélectionnez **OK**. 

[![Notification de modification](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)

Un point noir s'affiche en regard des activités mises à jour.

[![Activité modifiée](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)

Vous ne pouvez pas modifier des activités gérées en dehors du modèle d'origine, sauf pour ajouter un destinataire, une date d'échéance ou d'autres informations dans la section à droite de l'activité.

Si vous souhaitez modifier une activité gérée, ou si une activité ne doit pas recevoir de mises à jour du modèle d'origine, sélectionnez le bouton **Verrouiller** pour cette activité. Le bouton **Verrouiller** disparaîtra. L'activité ne sera plus gérée par le modèle d'origine, et elle ne recevra plus de mises à jour de ce modèle. Les mises à jour apportées à une activité n'affectent pas le modèle d'origine.

Si vous supprimez une activité d'un guide et envoyez les modifications du modèle de ce guide, l'activité reste supprimée dans le guide.

> [!NOTE]
> Les contacts et les ressources ne sont pas gérées par les modèles. En outre, les sections ne sont pas gérées, donc si vous ajoutez ou modifiez une section dans un modèle, les modifications ne sont pas envoyées aux guides ou aux modèles qui utilisent ce modèle.
> 
> Si vous ajoutez de nouvelles activités à un modèle, les nouvelles activités sont envoyées aux guides et aux modèles basés sur ce modèle, et les nouvelles activités s'affichent en haut.

## <a name="import-activities-from-another-template"></a>Importer des activités à partir d'un autre modèle

Vous pouvez importer des activités d'un ou de plusieurs modèles vers un guide ou un modèle.

1. Sélectionnez le guide ou le modèle à modifier.

2. Sélectionnez l'onglet **Activités**.

3. Sélectionnez l'onglet **Importer** dans la section à droite.

   [![Importer des activités](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)

4. Pour afficher un aperçu des tâches dans un nouvel onglet de votre navigateur, sélectionnez le bouton **Ouvrir dans un nouvel onglet** sur n'importe quel modèle.

   [![Importer des activités](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)

5. Glissez et déplacez le modèle souhaité vers l'emplacement dans votre modèle de guide où vous souhaitez faire apparaître les activités. Continuez à modifier votre guide ou votre modèle.

Les activités importées contiennent un bouton **Verrouiller**, qui indique que ces activités sont gérées par le modèle d'importation. Lorsque vous apportez des modifications au modèle que vous avez importé, ces activités sont mises à jour dans le modèle d'importation. Toutefois, les modifications ne sont pas envoyées automatiquement aux guides créés à partir du modèle d'importation.

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a>Envoyer les modifications d'un modèle vers d'autres modèles ou guides

Si vous modifiez un modèle contenant des activités qui sont utilisées dans d'autres modèles ou guides, vous devez envoyer les modifications si vous souhaitez les faire apparaître dans les autres modèles ou guides.

Si vous ne savez pas si les activités de votre modèle sont utilisées dans d'autres modèles ou guides, sélectionnez l'onglet **Utilisé dans** pour voir où ces activités apparaissent.

   [![Afficher les guides et les modèles dans lesquels les activités sont utilisées](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)

Pour envoyer vos modifications :

1. Enregistrez vos modifications en sélectionnant le bouton **Enregistrer**. Dans le cas contraire, vous serez invité à enregistrer vos modifications dans l'étape suivante.

2. Sélectionnez **Envoyer ces modifications**.

   
## <a name="add-or-edit-an-introduction"></a>Ajouter ou modifier une introduction

1. Sous l'onglet **Introduction**, entrez un titre pour votre guide et un message de présentation. Pour utiliser l'exemple de texte, sélectionnez **Utiliser ce message**.

    [![Onglet Introduction dans un modèle Onboard](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)

2. Utilisez les boutons de mise en forme pour ajouter une légende au texte si nécessaire, ou ajouter des images ou des liens.
3. Sélectionnez **Enregistrer** pour enregistrer votre travail.

## <a name="add-or-edit-activities"></a>Ajouter ou modifier des activités

1. Sous l'onglet **Activités**, faites glisser des éléments de la droite vers la zone de modification.
2. Pour organiser votre guide en sections, faites glisser l'élément **Nouvelle section** vers la zone de modification, puis entrez un nom et une description facultative pour la section.

    ![[Ajout d'une nouvelle section à un guide ou modèle d'intégration](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. Pour ajouter des activités que votre nouvelle recrue doit effectuer, faites glisser l'élément **Nouvelle activité** vers la zone de modification, puis entrez un nom et une description pour l'activité.

    ![[Ajout d'une nouvelle activité à un guide ou modèle d'intégration](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. Ajouter du contenu enrichi à votre guide d'intégration :

    - Pour ajouter une vidéo YouTube, faites glisser l'élément **YouTube** vers la zone de modification, entrez un nom et une description pour l'activité, puis entrez l'URL de la vidéo YouTube.
    - Pour ajouter une présentation Sway ou un bulletin d'informations, faites glisser l'élément **Sway** vers la zone de modification, entrez un nom et une description pour l'activité, puis entrez l'URL intégrée de la présentation Sway ou du bulletin d'informations.
    - Pour ajouter une application Microsoft Power Apps, faites glisser l'élément **Power Apps** vers la zone de modification, entrez un nom et une description pour l'activité, puis sélectionnez l'application Power Apps ou entrez l'ID de l'application Power Apps.
    - Pour ajouter une vidéo Microsoft Stream, faites glisser l'élément **Microsoft Stream** vers la zone de modification, entrez un nom et une description pour l'activité, puis entrez l'URL de la vidéo Microsoft Stream.
    - Pour ajouter un formulaire Microsoft Forms, faites glisser l'élément **Microsoft Forms** vers la zone de modification, entrez un nom et une description pour l'activité, entrez l'URL du formulaire Microsoft Forms, puis spécifiez la taille de la zone d'écran.
    - Pour ajouter un iframe contenant du contenu Web, faites glisser l'élément **Contenu Web (iframe)** vers la zone de modification, entrez un nom et une description pour l'activité, entrez l'URL du contenu Web, puis spécifiez la taille de la zone d'écran.

    ![[Ajout de contenu enrichi à un guide ou modèle d'intégration](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. Facultatif : dans la zone à droite de chaque activité, affectez l'activité à une personne ou un rôle spécifique, ajoutez une date d'échéance et une personne à contacter, puis affectez une couleur de catégorie. Lorsque vous affectez une activité à une personne ou un rôle, une tâche est créée pour chaque individu. Cette tâche apparaît dans le menu **Tâches** d'Onboard.

    [![Affectation d'une activité dans un guide ou un modèle d'intégration](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)

3. Sélectionnez **Enregistrer** pour enregistrer votre travail.

Pour supprimer une activité ou une section, sélectionnez le bouton **Supprimer** (le symbole de poubelle) dans le coin supérieur droit de l'activité ou de la section.

Pour réorganiser les activités et les sections, faites-les glisser vers un nouvel emplacement.

## <a name="add-or-edit-contacts"></a>Ajouter ou modifier des contacts

Vous pouvez ajouter des personnes à contacter qui peuvent aider votre nouvelle recrue à réussir dès le premier jour. Ces contacts peuvent être des recruteurs, des membres de l'équipe, des parrains, des mentors, des administrateurs et du personnel d'assistance informatique.

1. Sous l'onglet **Contacts**, sélectionnez **Nouveau contact**.
2. Dans la boîte de dialogue **Ajouter un membre de l'équipe**, entrez le nom ou l'adresse e-mail de la personne à contacter, entrez une brève description expliquant comment la personne à contacter peut aider la nouvelle recrue, puis sélectionnez **Ajouter**. 

    ![[Ajout de contacts à un guide ou modèle d'intégration](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    Vous pouvez également sélectionner un ou plusieurs contacts sous **Suggestions**.

3. Sélectionnez **Enregistrer** pour enregistrer votre travail.

Pour supprimer un contact, sélectionnez le bouton **Supprimer** (le symbole de poubelle) à droite du contact.

Pour modifier un contact, sélectionnez le bouton **Modifier** (le symbole de crayon) à droite du contact.

## <a name="add-or-edit-resources"></a>Ajouter ou modifier des ressources

Vous pouvez ajouter des fichiers, cartes et liens utiles à la section **Ressources** de votre guide d'intégration.

1. Sous l'onglet **Ressources**, sélectionnez **Nouvelle ressource**.
2. Utilisez l'une des procédures suivantes :

    - Pour ajouter un fichier, sélectionner l'onglet **Fichier**, puis faites glisser le fichier vers la zone indiquée. (Sinon, cliquez n'importe où dans cette zone pour rechercher le fichier sur votre ordinateur, ou sélectionnez **Parcourir OneDrive**). Entrez un nom pour le fichier, puis sélectionnez **Ajouter**.
    - Pour ajouter un lien, sélectionnez l'onglet **Lien**, entrez un nom et une adresse pour le lien, puis sélectionnez **Ajouter**.
    - Pour ajouter une carte, sélectionnez l'onglet **Carte**, entrez un nom et une adresse pour la carte, puis sélectionnez **Ajouter**. Onboard ajoutera une carte de l'adresse que vous spécifiez.

    ![[Ajout d'une ressource à un guide ou modèle d'intégration](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. Sélectionnez **Enregistrer** pour enregistrer votre travail.

Pour supprimer une ressource, sélectionnez le bouton **Supprimer** (le symbole de poubelle) à droite de la ressource.

Pour modifier une ressource, sélectionnez le bouton **Modifier** (le symbole de crayon) à droite de la ressource.

## <a name="next-steps"></a>Étapes suivantes

- [Partager du contenu avec d'autres contributeurs](./onboard-share-template.md)
- [Afficher le statut d'intégration des employés et des tâches](./onboard-view-status.md)
- [Créer des équipes de recrutement dans Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Voir également :

- [Essayer ou acheter l'application Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Nouveautés ou modifications dans Dynamics 365 Talent](./whats-new.md)
- [Programmes de lancement](https://docs.microsoft.com/business-applications-release-notes/index)
- [Obtenir de l'aide sur Microsoft Dynamics 365 Talent](./talent-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]