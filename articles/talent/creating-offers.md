---
title: Créer, approuver et signer des offres dans Attract
description: Cette rubrique explique comment créer, approuver, et signer une offre pour un candidat à l'aide de Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 02/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-19
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: dee545b6ca5d2791dea6609b4e1b25eba128f8b7
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832905"
---
# <a name="create-approve-and-sign-offers-in-attract"></a>Créer, approuver et signer des offres dans Attract

[!include [banner](includes/banner.md)]

Dans de nombreux cas, la préparation d'un package d'offre pour un candidat doit être un processus très rapide.
L'utilisation de modèles configurés par l'administrateur Attract permet aux créateurs d'offres de préparer et d'envoyer rapidement et facilement des offres à un candidat.

## <a name="create-an-offer"></a>Créer une offre

Lorsque l'application Gestion des offres est activée, tout utilisateur avec le rôle de responsable de l'embauche ou de recruteur peut préparer un package d'offre pour le candidat. Pour préparer l'offre, procédez comme suit.

1.  Accédez à la mission et à la candidature du candidat pour lesquels vous créez une offre.

1.  Accédez à **Stade de l'offre** et cliquez sur **Préparer l'offre**.

    Vous serez redirigé vers l'application Offre dans laquelle vous pourrez afficher le candidat ayant le statut **Nouveau**. Vous pouvez également afficher d'autres offres auxquelles vous contribuez, comme créateur ou approbateur.

1.  Cliquez sur **Préparer l'offre**. 
    
    Vous verrez différents packages d'offres mis à votre disposition par l'administrateur.

1.  Sélectionnez un package et cliquez sur **Terminé** pour commencer à préparer l'offre.

    Le modèle de package d'offre se charge avec les détails de la mission et du candidat correspondants renseignés dans l'offre.

1.  Tous les espaces réservés pour les données de l'offre qui font partie du package d'offre sont visibles dans la page de destination. Vous pouvez renseigner toutes les valeurs du package sur cette page.

    Sur la page de destination, vous pouvez également afficher tous les modèles de document d'offre qui font partie du package d'offre.

1.  Vous pouvez désormais modifier le contenu de l'offre, en fonction de la manière dont le modèle a été configuré par l'administrateur.

1.  Si vous devez supprimer des documents marqués comme non requis, vous pouvez le faire.

1. Lorsque tous les espaces réservés des données de l'offre sont renseignés, cliquez sur **Enregistrer** pour enregistrer un brouillon de l'offre.

>[!NOTE]
> Une fois qu'un brouillon est enregistré, vous pouvez supprimer la version de brouillon de l'offre ou sélectionner un modèle de package, si nécessaire.


## <a name="approve-an-offer"></a>Approuver une offre

La plupart des offres doivent passer par un processus d'approbation pour vous assurer que l'offre est conforme aux normes nécessaires. Si une offre ne répond pas aux normes, par exemple si le créateur de l'offre n'a pas suivi les règles relatives aux données de l'offre et a remplacé des valeurs de l'offre, le processus d'approbation sera obligatoire. Pour envoyer une offre pour approbation, procédez comme suit.

1.  Lorsque l'offre est dans un état de brouillon, ajoutez les approbateurs dans le **volet Approbateur**. 
    >[!NOTE]
    > Les responsables de l'embauche sont ajoutés comme approbateurs par défaut. Vous pouvez choisir n'importe quel utilisateur de votre organisation en tant qu'approbateur de l'offre.

1.  Au besoin, affectez des approbateurs dans une méthode d'approbation séquentielle ou une méthode d'approbation en parallèle. Cette option est uniquement disponible si celle-ci a été configurée comme telle par l'administrateur.
    >[!NOTE]
    > Si le processus d'approbation est séquentiel, vous pouvez modifier la séquence des approbateurs si nécessaire.

1.  Lorsque vous avez fini de définir la chaîne d'approbation, vous pouvez modifier le contenu du message d'approbation et envoyer la notification aux approbateurs. Cliquez sur **Envoyer aux approbateurs**.
    >[!NOTE]
    > Si l'offre n'était pas standard, vous devez fournir une justification.

1.  Si le créateur de l'offre choisit d'ignorer un approbateur, il peut entrer une remarque et passer à un autre approbateur.

Les approbateurs recevront un e-mail leur demandant d'approuver l'offre. Ils peuvent cliquer sur le lien du courrier électronique pour ouvrir une offre, pour consulter le package d'offre complet, ainsi que l'approuver ou le renvoyer au créateur de l'offre. Les approbateurs de l'offre doivent ajouter une remarque supplémentaire s'ils rejettent le package d'offre à des fins de modifications supplémentaires. 

Lorsqu'il y a une nouvelle version de l'offre créée avant que l'approbateur agisse, l'approbateur ne peut pas approuver ou rejeter l'offre.

## <a name="offer-versioning"></a>Gestion des versions de l'offre 

Lorsque l'offre a été approuvée ou resoumise pour des modifications supplémentaires, vous pouvez choisir l'option **Activer la modification** pour créer une nouvelle version de l'offre. La nouvelle version de la version de l'offre comporte toutes les valeurs de données de l'offre et répertorie les approbateurs reportés de la dernière version. 

Les approbateurs peuvent basculer entre les différentes versions de l'offre si les versions sont partagées avec eux pour approbation. En outre, un approbateur ou créateur de l'offre peut choisir de supprimer une version de brouillon de l'offre spécifique pour revenir à l'état précédent.


## <a name="send-an-offer-to-a-candidate"></a>Envoyer une offre à un candidat 

Lorsque l'offre est enregistrée, approuvée, et prête à être envoyée au candidat, cliquez sur **Envoyer au candidat**.

Il existe plusieurs actions que vous pouvez entreprendre avant d'envoyer l'offre au candidat.
-  Vous pouvez afficher la liste des documents qui font partie du package d'offre qui sera envoyé au candidat.

-  Vous pouvez spécifier une date d'expiration de l'offre. Les candidats doivent accepter ou refuser l'offre avant la date d'expiration.  Le candidat recevra un rappel 48 heures avant que l'offre expire.

-  Il peut y avoir des documents supplémentaires à inclure dans le processus d'acceptation de l'offre. Vous avez la possibilité de répertorier le type de document requis.

- Option de signature électronique : il existe deux façons de se connecter au fournisseur de signature électronique de votre choix. Accédez à **Paramètres utilisateur** dans **Offre**, sous **Connexions**, connectez-vous à **Adobe Sign** ou à **DocuSign**. Sinon, vous êtes invité à vous connecter à la page **Envoyer l'offre au candidat** si la connexion n'a pas encore été établie en fonction des paramètres utilisateur. Le compte de signature électronique doit être connecté une seule fois. La même licence utilisateur est utilisée pour tous les futurs packages d'offre qui seront envoyés par le même utilisateur. 

### <a name="adobe-sign"></a>Adobe Sign
Si Adobe Sign a été sélectionné comme mode favori de signature électronique, les créateurs d'offres doivent connecter leur licence Adobe Sign à cette étape. 

### <a name="docusign"></a>DocuSign
Si DocuSign a été sélectionné comme mode préféré de signature électronique, les créateurs d'offres doivent connecter leur licence DocuSign à cette étape. Une fois connecté, le compte par défaut et les autorisations associées au profil DocuSign de l'utilisateur sont connectés à Talent: Attract. 

-  Vous pouvez afficher et modifier le modèle d'e-mail si nécessaire.

Lorsque l'offre est prête et que vous cliquez sur **Envoyer au candidat**, le candidat reçoit un e-mail lui indiquant qu'une offre est en attente de révision.

>[!NOTE]
> Si vous utilisez Adobe Sign ou DocuSign, et si une erreur survient lors de l'envoi de l'offre au candidat, essayez de déconnecter, puis de reconnecter le compte d'utilisateur de signature électronique depuis **Paramètres d'utilisateur**. Si le problème persiste, veuillez contacter notre support avec le lien **Signaler un problème**.

## <a name="candidates-actions-after-receiving-an-offer"></a>Les actions du candidat après avoir reçu une offre

Une fois que le candidat a été notifié qu'une offre a été partagée avec lui, il peut cliquer sur le lien de l'e-mail pour accéder au tableau de bord de candidature et afficher l'offre. Le tableau de bord affiche au candidat toutes les activités qu'ils doivent effectuer.

1.  Pour afficher l'offre et tous les documents connexes, le candidat doit cliquer sur **Afficher l'offre**.

    Les candidats peuvent également télécharger le package d'offre au format .zip.

1.  Pour accepter l'offre, les candidats doivent cliquer sur **Passer à la signature** pour chaque document faisant partie du package d'offre.

1.  Lorsque tous les documents ont été signés et acceptés individuellement, le candidat doit décider de terminer le processus d'acceptation en cliquant sur **Accepter l'offre** en haut de la page.

1.  Pour refuser l'offre, le candidat doit cliquer sur **Refuser l'offre** en haut de la page, sélectionner un motif approprié, ajouter un commentaire si nécessaire, puis cliquer sur **Refuser**ensuite.

1.  Une fois qu'il a accepté ou refusé l'offre, le candidat peut continuer à rester dans la vue de l'offre ou retourner au tableau de bord de candidature.

1.  Si d'autres documents sont demandés dans le cadre du processus d'acceptation de l'offre, le candidat doit décider de charger les documents au besoin et de les marquer du type de document demandé.

1.  Le créateur de l'offre est notifié lorsque tous les documents ont été chargés et que le package d'offre a été signé.


## <a name="withdrawing-an-offer"></a>Retrait d'une offre

Une offre peut être retirée à un candidat à tout moment pour différents motifs. 
1.  Retirez l'offre en cliquant sur le bouton (**...**), puis cliquez sur **Retirer l'offre**. 

2. Un message s'affiche demandant si le candidat a été contacté sur le changement de statut. S'il n'a pas encore été contacté, vous avez la possibilité d'envoyer un e-mail au candidat l'informant d'autres d'actions. 

   L'offre ne sera plus accessible par le candidat.


## <a name="closing-an-offer"></a>Clôture de l'offre 

Lorsqu'une offre a été acceptée, refusée, ou retirée sans autres actions nécessaires, vous pouvez fermer l'offre afin qu'aucune autre modification ne puisse être effectuée à ce package d'offre.
