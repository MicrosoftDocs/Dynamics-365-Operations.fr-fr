---
title: Planifier les entretiens dans Attract
description: Cette rubrique fournit des informations sur la planification des entretiens et les activités de commentaires dans Attract.
author: hasrivas
manager: AnnBe
ms.date: 04/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: shielas
ms.openlocfilehash: 33eba9796ca997fde4be9a46050207d313551bde
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461191"
---
# <a name="schedule-interviews-in-attract"></a>Planifier les entretiens dans Attract

[!include [banner](includes/banner.md)]

## <a name="scheduler-activity"></a>Activité du planificateur

L'activité de planification reste en option et se distingue par deux composants : Demande de disponibilité du candidat et Planification. Le composant Disponibilité du candidat permet d'utiliser des e-mails pour demander la disponibilité d'un candidat. Le composant Programme permet de programmer des entretiens avec le candidat et l'équipe de recrutement.

Pour paramétrer l'activité du planificateur de sorte à inclure ou limiter les candidats à programmer, sélectionnez une valeur dans le champ **Qui est programmé**. Les options disponibles sont **Tous les candidats**, **Candidats externes** et **Candidats internes**. Par exemple, si vous souhaitez ignorer les candidats internes au premier tour de la planification, vous pouvez affecter l'activité de planification aux seuls candidats externes en définissant **Qui est programmé** sur **Candidats externes**.

### <a name="candidate-availability-request"></a>Demande de disponibilité du candidat

Pour envoyer un e-mail aux candidats afin de leur demander leur disponibilité, sélectionnez le champ **Demander la disponibilité du candidat**. Si le champ n'est pas sélectionné, cette étape n'apparaît pas dans le processus de recrutement pour le poste concerné.

Pour soumettre la demande de disponibilité, cliquez sur **Envoyer la demande**, sélectionnez les dates disponibles ainsi qu'un modèle d'e-mail, puis envoyez le message électronique au candidat.

[![Vue du recruteur Attract pour envoyer la demande de disponibilité du candidat](./media/scheduler-candidate-request.png)](./media/scheduler-candidate-request.png)

Lorsque le candidat reçoit un e-mail pour répondre à la demande, il peut se connecter à son portail de candidat, sélectionner les dates qui correspondent à ses disponibilités et cliquer sur **Envoyer**.

### <a name="schedule"></a>Planification
Plusieurs configurations sont disponibles pour la planification des entretiens afin de créer et d'envoyer rapidement la boucle de l'entretien aux intervieweurs et au candidat.

1. Cliquez sur **Créer un programme**, puis dans la zone **Ajouter des intervieweurs**, répertoriez tous les intervieweurs qui feront partie de la boucle de l'entretien.
[![Vue du recruteur Attract pour commencer à planifier une boucle d'entretien](./media/schedule-start-over.png)](./media/schedule-start-over.png)   
    Si le candidat a répondu à la demande de disponibilité pour l'entretien, le champ **Date d'entretien** est pré-rempli avec les données de sa sélection. Vous pouvez sélectionner une autre date, le cas échéant.
    
    Si vous sélectionnez le champ **Définir comme entretien collectif**, le groupe d'intervieweurs à gauche passe dans une boucle unique pour créer l'entretien. Vous devez alors définir un ordre spécifique pour les entretiens.
    
    Le programme d'entretien doit être organisé pour mieux correspondre à la disponibilité des participants. Si c'est un candidat interne, vous pouvez inclure cette disponibilité dans le cadre de la recommandation de planification.
    
    Pour avoir une réunion en ligne, sélectionnez le champ **Ajouter des réunions Skype** et chaque événement d'entretien dispose d'un lien **Skype Entreprise** disponible.

2. Sélectionnez la durée d'entretien pour chaque événement d'entretien, puis cliquez sur **OK** pour commencer à créer le programme.

    Si l'option **Recommandations** est sélectionnée, des suggestions sont affichées et la grille d'entretien est pré-remplie. Vous pourrez consulter le calendrier actuel de disponibilité de tous les intervieweurs sélectionnés. Vous pouvez également afficher le calendrier du candidat s'il s'agit d'un candidat interne. Pour les interviewers et les candidats internes, vous pouvez afficher leurs créneaux occupés, leurs heures de travail, leurs heures hors bureau, et également remarquer s'ils ont indiqué dans leur calendrier qu'ils travaillent ailleurs à des créneaux particuliers. 

3. Si aucune suggestion n'est disponible, dans la colonne **Intervieweurs**, cliquez sur un créneau horaire, indiquez le titre de l'entretien, les détails, et remplissez les détails concernant l'emplacement, le cas échéant. Vous pouvez choisir d'inclure le lien **Skype Entreprise** pour l'entretien.

4. Pour inclure des intervieweurs supplémentaires, cliquez dans la colonne de grille **Ajouter un entretien** pour sélectionner un ou plusieurs intervieweurs. Vous pouvez utiliser les points de suspension (...) pour retirer un entretien de la boucle.
    
5. Si les entretiens sont planifiés selon des fuseaux horaires différents, sélectionnez la ville/le fuseau horaire requis depuis la liste déroulante dans la partie supérieure. La grille de disponibilité des intervieweurs sera mise à jour, indiquant le nouveau fuseau horaire. Cette sélection de fuseau horaire s'affiche désormais également dans la vue **Résumé de l'entretien**, qui est partagée avec les intervieweurs et le candidat. 

6. Cliquez sur **Envoyer aux intervieweurs** pour envoyer les invitations de réunion aux intervieweurs concernés.

    Une fois les demandes d'entretien envoyées aux intervieweurs, ils peuvent répondre directement depuis de l'invite reçue par e-mail.

    >[!NOTE]
    > Pour tous les entretiens individuels, des rappels sont envoyés aux interviewers toutes les 24 heures si l'interviewer n'a pas répondu (accepté ou refusé) à la demande d'entretien.

    > Pour tous les entretiens collectifs, il n'existe aucun rappel automatisé pour la demande d'entretien. Pour déclencher un rappel manuellement, modifiez l'entretien et utilisez l'option **Mettre à jour et envoyer** pour renvoyer la demande aux interviewers.

    Les réponses des intervieweurs sont saisies et apparaissent dans Attract. Si un intervieweur refuse l'invitation, vous en êtes informé pour procéder à une modification. Pour afficher leur réponse dans la vue de grille **Planificateur**, cliquez sur l'icône bulle.

[![Vue du recruteur Attract de la réponse d'un intervieweur](./media/schedule-interviewer-response2.png)](./media/schedule-interviewer-response2.png)

7. Une fois le programme d'entretien prêt pour partage avec le candidat, cliquez sur **Envoyer au candidat**. Vous pouvez choisir de masquer ou d'afficher les noms des intervieweurs et les créneaux au candidat.

8. Sélectionnez un modèle d'e-mail et envoyez le récapitulatif de l'entretien au candidat. Le candidat peut visualiser ces informations dans sa boîte de réception ainsi que sur son portail candidat.
    
>[!NOTE] 
> La disponibilité du calendrier d'un candidat s'affiche uniquement si le candidat est interne. De même, l'amélioration des recommandations du programme des entretiens est soumise uniquement aux candidats internes. Actuellement, les candidats (externes ou internes) ne reçoivent pas d'invitation à une réunion par e-mail. Ils ne reçoivent qu'un récapitulatif des entretiens.

Les candidats recevront l'e-mail résumant leur boucle d'entretien. Les e-mail contiennent un fichier .ics qui peut être enregistré dans leur calendrier personnel pour être facilement accessible et recevoir des notifications pour l'entretien.

>[!TIP] 
> Au cas où vous renvoyiez le programme d'entretien au candidat, il reçoit une autre pièce jointe de fichier .ics. Nous vous recommandons de mettre à jour les modèles d'e-mail de synthèse d'entretien des candidats pour vous assurer que les candidats suppriment les événements d'entretien précédemment ajoutés et ne voient pas de doublons dans leur calendrier. 

## <a name="feedback-activity"></a>Activité de commentaire

L'activité de commentaires est facultative dans un modèle de poste. Cette activité permet aux participants de renseigner des recommandations ou des commentaires pour un candidat. 

Pour inclure ou limiter les candidats sur lesquels fournir des commentaires, sélectionnez une valeur dans le champ **Sur qui doit les interviewers doivent fournir des commentaires**.  Les options disponibles sont **Tous les candidats**, **Candidats externes** et **Candidats internes**. Par exemple, si vous souhaitez ignorer les candidats internes au premier tour de la planification, définissez **Sur qui doit les interviewers doivent fournir des commentaires** sur **Candidats externes**.

Si vous sélectionnez le champ **Hériter les participants aux commentaires de l'équipe de recrutement**, le recruteur, le responsable du recrutement et les intervieweurs sont automatiquement renseignés dans l'activité de commentaires. Les organisations peuvent permettre aux intervieweurs d'afficher les commentaires d'autres personnes avant d'envoyer leurs propres commentaires. Les organisations peuvent également autoriser les intervieweurs à modifier leur commentaire l'avoir envoyé. Les intervieweurs doivent envoyer leurs commentaires pour les entretiens récemment menés selon la configuration prédéfinie dans le cadre du modèle de poste. Le responsable du recrutement ou un recruteur peut également choisir de rappeler manuellement à un intervieweur d'envoyer ses commentaires.

## <a name="interview-activity"></a>Activité d'entretien

L'activité d'entretien est une activité facultative avec trois composants : **Demande de disponibilité du candidat**, **Planification** et **Commentaires**. Utilisez l'activité d'entretien dans le modèle de poste si vous souhaitez inclure l'ensemble demande de disponibilité du candidat - programme - commentaires dans le cadre du processus plutôt que de les utiliser de manière individuelle.

Pour inclure ou limiter les candidats à interviewer, sélectionnez une valeur dans le champ **Qui passe l'entretien**. Les options disponibles sont **Tous les candidats**, **Candidats externes** et **Candidats internes**. Par exemple, si vous souhaitez ignorer les candidats internes au premier tour d'entretien, définissez **Qui passe l'entretien** sur **Candidats externes**.
