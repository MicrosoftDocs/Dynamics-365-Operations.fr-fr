---
title: Création de modèles d'e-mail dans Attract
description: Cette rubrique fournit des informations sur les modèles d'e-mail que vous pouvez créer et utiliser dans Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 55c12010cfd055ee6977f50e566b70f76a2e1682
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832882"
---
# <a name="create-email-templates-in-attract"></a>Création de modèles d'e-mail dans Attract

[!include [banner](includes/banner.md)]

Grâce à la bibliothèque de modèles d'e-mail, les administrateurs peuvent créer un thème et une personnalisation cohérentes pour tous les e-mails envoyés via Microsoft Dynamics 365 Talent: Attract et Offer. Les administrateurs peuvent également organiser une collection de modèles de contenu d'e-mail que d'autres utilisateurs peuvent consommer. L'équipe de recrutement peut utiliser ces modèles dans leur workflow pour envoyer des e-mails plus efficacement. Certains e-mails sont configurés pour être envoyés automatiquement, et l'administrateur peut utiliser la bibliothèque de modèles d'e-mails pour personnaliser le contenu de ces e-mails.

> [!NOTE]
> Pour utiliser des modèles d'e-mail, votre organisation doit disposer du complément additionnel de recrutement complet.

## <a name="global-template-configurations"></a>Configurations de modèles globaux

Pour créer une personnalisation cohérente pour toutes les communications par e-mail, l'administrateur doit commencer par définir l'en-tête et le pied de page globaux pour tous les modèles d'e-mails. Dans le centre d'administration, sous l'onglet **Paramètres du modèle d'e-mail**, dans la section **En-tête**, l'administrateur peut charger une image à utiliser comme en-tête ou bannière pour tous les e-mails. Cette image peut être un logo de la société, un en-tête de lettre, ou toute autre image représentative. Nous vous recommandons que la largeur soit située entre 25 et 800 pixels, et que la hauteur soit située entre 25 et 150 pixels, car ces dimensions sont optimales pour la plupart des clients e-mail, tels que Microsoft Outlook. L'image doit être un fichier JPEG, JPG, PNG ou SVG, et la taille du fichier doit être inférieure à 1 mégaoctet (Mo). Une fois une image chargée, un aperçu de l'en-tête est généré et affiché. Si l'image de l'en-tête doit être supprimée ou remplacée, l'administrateur peut utiliser l'option **Supprimer** au-dessus de l'aperçu.

Dans la section **Pied de page**, l'administrateur peut fournir des liens vers la stratégie de confidentialité de la société pour les communications, et vers les conditions générales. Ces liens sont incorporés à un pied de page qui est généré automatiquement. Un aperçu de ce pied de page est ensuite affiché. L'administrateur peut également choisir une langue particulière dans laquelle les pieds de page d'e-mail sont envoyés avec tous les e-mails. La même configuration de langue est également utilisée pour constituer le tableau de synthèse des entretiens. 

Veillez à enregistrer vos modifications avant de fermer le centre d'administration.

> [!NOTE] 
> L'en-tête et le pied de page sont des paramètres globaux pour tous les e-mails. Par conséquent, ils s'afficheront dans tous les e-mails envoyés via Attract. Si les paramètres ne sont pas configurés, l'en-tête et le pied de page seront exclus de tous les e-mails.

## <a name="email-template-library"></a>Bibliothèque de modèles d'e-mails 

Une fois les configurations de modèle globaux paramétrées, l'administrateur peut commencer à créer et à organiser les modèles pour tous les e-mails qui affichent sont envoyés depuis Attract et Offer. La bibliothèque de modèles d'e-mails n'est accessible qu'aux administrateurs. Pour ouvrir la bibliothèque, dans le menu principal de la navigation, sélectionnez l'onglet **Modèles d'e-mails**. La bibliothèque est classée par catégories selon les diverses activités dans Attract pour lesquelles les e-mails doivent être envoyés, telles que la planification, l'évaluation, la création de mission et les offres d'emploi. L'administrateur peut sélectionner n'importe quelle catégorie pour afficher tous les types d'e-mails qui sont associés à l'activité. Par exemple, sélectionnez **Planification** pour afficher les différents types d'e-mails envoyés lors du processus de planification et tous modèles disponibles pour chaque type d'e-mail. Chaque sous-section dans une catégorie représente un type d'e-mail.

Certains types d'e-mail peuvent avoir plusieurs destinataires. Par exemple, dans la catégorie **Planification**, les e-mails envoyés lorsque la synthèse du programme d'entretien est nécessaire, sont envoyés aux candidats et aux intervieweurs. Chaque section comporte deux colonnes principales : **Titre du modèle** et **Destinataire**. Chaque ligne d'une section représente un modèle unique pour un type d'e-mail. Au début, un symbole de verrou s'affiche dans la ligne pour chaque modèle. Ce symbole indique que le modèle est le modèle standard fourni avec Attract, et qu'il ne peut pas être supprimé. Pour chaque modèle, l'administrateur peut utiliser le bouton (**...**) pour dupliquer le modèle, le définir comme modèle par défaut, ou le supprimer. Lorsqu'un modèle est défini comme modèle par défaut, l'un des deux comportements peut se produire. Le comportement est indiqué par le ou les badges figurant dans la ligne du modèle :

- **Par défaut** – Ce badge indique que le modèle est le modèle par défaut de l'e-mail envoyé, et que les informations sont entrées lorsqu'un utilisateur envoie un e-mal de ce type spécifique.
- **Par défaut** + **Envoyé automatiquement** – Cette combinaison des badges indique que le modèle est le modèle actif pour les e-mails générés par le système qui sont envoyés automatiquement.

Pour modifier un modèle, sélectionnez la ligne et modifiez le modèle.

> [!NOTE]
> Chaque destinataire d'un type d'e-mail spécifique dispose d'un modèle par défaut. Tous les modèles Attract standard sont définis comme des modèles par défaut avant que l'administrateur crée un nouveau modèle pour un type d'e-mail et le définisse comme modèle par défaut.

## <a name="create-a-template"></a>Créer un modèle

Pour créer un modèle, dans le coin supérieur droit de la bibliothèque de modèles d'e-mails, sélectionnez **+ Nouveau modèle**. Pour sélectionner le type d'e-mail pour lequel vous créez le modèle, sélectionnez le destinataire, le processus, et l'événement pour lequel l'e-mail doit être envoyé. Ensuite, sélectionnez **Créer**.

Le modèle s'ouvre dans la vue de modification, et vous pouvez nommer le modèle. Par exemple, si le modèle est prévu pour des candidats d'une université américaine, mais que le contenu est écrit en français, vous pouvez entrer **Université\_États-Unis\_Francais** comme titre. Le titre, l'objet et le contenu du corps de n'importe quel modèle peuvent prendre en charge des langues autres que l'anglais.

Le champ **À** d'un modèle ne peut pas être modifié, car vous avez déjà sélectionné le destinataire lorsque vous avez créé la première fois le modèle.

Vous pouvez ajouter des personnages comme **Recruteur** ou **Responsable de l'embauche** dans la ligne de copie (Cc). Lorsque l'e-mail est envoyé, ces rôles sont automatiquement remplacés par les utilisateurs appropriés, selon le contexte de la mission.

La ligne d'objet et le contenu du corps prennent en charge les espaces réservés. Vous pouvez insérer des espaces réservés en saisissant **\#**, puis en sélectionnant l'espace réservé correspondant dans la liste déroulante Compléter automatiquement. La liste des espaces réservés disponibles s'affiche à droite de la page. Lorsque l'e-mail est envoyé, les espaces réservés sont automatiquement remplacés, selon le contexte de la mission et le destinataire. Par exemple, un modèle d'e-mail envoyé aux candidats contient l'espace réservé \#{Nom\_Candidat}. Lorsque l'e-mail est envoyé à un candidat nommé Cameron, cet espace réservé est remplacé par le nom de Cameron.

L'éditeur de contenu du corps est un éditeur de texte enrichi qui permet de mettre en forme le texte. Il vous permet également d'ajouter des liens hypertextes et des points d'ancrage.

Une fois qu'un modèle est créé pour un type d'e-mail spécifique, sélectionnez le bouton (**...**) dans la ligne du modèle, et définissez-le comme modèle par défaut.

## <a name="consume-templates"></a>Consommation des modèles

Lorsque l'équipe de recrutement envoie un e-mail, elle peut utiliser les modèles que l'administrateur a créés. Si plusieurs modèles ont été créés pour l'e-mail qu'un utilisateur envoie, une liste déroulante apparaît dans le workflow de composition d'e-mail. Le modèle par défaut est entré automatiquement, mais l'utilisateur peut sélectionner un autre modèle.

> [!NOTE] 
> Pour les e-mails envoyés automatiquement, plusieurs modèles peuvent être créés. Cependant, un seul modèle peut être défini comme modèle actif. Comme ce processus est déclenché par des événements, seul l'administrateur peut déterminer le modèle à utiliser, selon la combinaison des badges **Par défaut** et **Envoyé automatiquement** de la bibliothèque de modèles.
