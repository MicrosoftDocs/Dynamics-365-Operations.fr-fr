---
title: Identifier des candidats avec les viviers de talents dans Attract
description: Cette rubrique explique comment créer et paramétrer des viviers de talents dans Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/28/2019
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
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 97385da9d258cc169a9976be7c7798faa41661c3
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527691"
---
# <a name="source-candidates-with-talent-pools-in-attract"></a>Identifier des candidats avec les viviers de talents dans Attract

[!include [banner](includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Les recruteurs et responsables de l'embauche peuvent organiser leurs candidats à l'aide de la fonctionnalité Vivier de talents dans Attract. Les viviers de talents peuvent vous aider à suivre et à embaucher tous les candidats qui postulent pour un poste dans votre société.

## <a name="create-and-share-a-talent-pool"></a>Création et partage d'un vivier de talents

Tout utilisateur ayant le rôle de recruteur, de responsable de l'embauche ou d'administrateur Attract peut créer des viviers de talents. Le propriétaire d'un vivier de talents peut également partager ce vivier avec d'autres utilisateurs afin que les groupes d'utilisateurs, en particulier les recruteurs, puissent consulter un vivier de candidats partagé.

Les contributeurs à un vivier de talents peuvent afficher la liste des candidats de ce vivier. Ils peuvent également ajouter des candidats au vivier ou supprimer des candidats de celui-ci.

Procédez comme suit pour créer et partager vivier de talents.

1. Sur la page d'accueil d'Attract, dans le volet de navigation de gauche, sélectionnez **Viviers de talents**.

    L'onglet **Mes viviers de talents** affiche tous les viviers de talents auxquels vous avez accès, avec des détails sur chacun d'eux. Ces détails incluent le propriétaire du vivier et le nombre de candidats que celui-ci contient.

1. Dans le coin supérieur droit de la page, sélectionnez **Nouveau** pour ouvrir la boîte de dialogue **Créez un vivier de talents**.
1. Entrez un nom unique pour le vivier de talents.
1. Pour ajouter des personnes comme contributeurs au vivier, recherchez leurs noms à l'aide du sélecteur de personnes, puis ajoutez-les à la liste. Vous pouvez partager un vivier de talents uniquement avec les utilisateurs ayant le rôle de recruteur, de responsable de l'embauche, ou d'administrateur Attract.
1. Sélectionnez **Ajouter** pour créer le vivier de talents.
     > [!NOTE]
     > Sinon, vous pouvez ajouter des contributeurs à un vivier de talents après l'avoir créé. Vous pouvez également gérer l'accès à un vivier de talents. Par exemple, vous pouvez révoquer l'accès d'un utilisateur au vivier de talents.
     > - Pour ajouter des contributeurs à un vivier de talents existant que vous possédez, sous l'onglet **Mes viviers de talents**, dans le coin supérieur droit de la fiche du vivier de talents, sélectionnez le bouton (**...**), puis sélectionnez **Modifier**. Recherchez des personnes à l'aide du sélecteur de personnes, et ajoutez-les à la liste. 
     > - Pour annuler l'accès d'utilisateur au vivier de talents, dans le coin supérieur gauche de la fiche de vivier de talents, sélectionnez le bouton (**...**), puis sélectionnez **Modifier**. Sous l'onglet **Gérer l'accès**, sélectionnez le bouton de poubelle en regard de l'utilisateur.

6. Sélectionnez **Mettre à jour** pour terminer et enregistrer l'opération.

> [!NOTE]
> Pour créer plusieurs viviers de talents, votre organisation doit avoir le Composant additionnel de recrutement complet.

## <a name="add-and-remove-candidates"></a>Ajout et suppression des candidats

Le propriétaire et les contributeurs du vivier de talents peuvent ajouter des candidats au vivier de talents, afficher les candidats dans celui-ci, et supprimer des candidats de celui-ci.

1. Sous l'onglet **Mes viviers de talents**, sélectionnez un vivier de talents pour l'ouvrir.

    Une liste des candidats qui font partie du vivier de talents s'affiche.

1. Pour ajouter des candidats au vivier de talents, sélectionnez **+ Nouveau** dans le coin supérieur droit pour ouvrir la boîte de dialogue **Ajouter un candidat**, puis effectuez l'une des tâches suivantes.

    - Pour ajouter un candidat interne, vous pouvez rechercher la personne par adresse e-mail. Une fois la recherche réussie, l'adresse e-mail du candidat, son prénom, et son nom sont renseignés. Si vous disposez du CV ou de tous documents connexes du candidat, vous pouvez les charger à ce stade. Ensuite, sélectionnez **Ajouter** pour ajouter le candidat au vivier de talents.
    - Pour ajouter un candidat externe, entrez manuellement son adresse e-mail, son prénom, et son nom. Si vous disposez du CV ou de tous documents connexes du candidat, vous pouvez les charger à ce stade. Ensuite, sélectionnez **Ajouter** pour ajouter le candidat au vivier de talents.
    - Pour ajouter plusieurs candidats, sélectionnez l'onglet **À partir de Excel**. Vous pouvez ensuite télécharger le modèle Microsoft Excel approprié, entrer les détails sur les candidats, enregistrer la feuille de calcul Excel, et la charger dans l'application.

        Si des erreurs sont détectées dans la feuille de calcul, vous recevrez des messages sur celles-ci. Vous pouvez ensuite corriger les erreurs et essayer de télécharger la feuille de calcul de nouveau. Si plus aucune erreur n'est détectée, sélectionnez **Ajouter** pour charger la feuille de calcul. La feuille de calcul est traitée en arrière-plan, et vous êtes informé lorsque tous les candidats ont été ajoutés au vivier de talents.

1. Pour supprimer un candidat existant du vivier de talents, dans la colonne **Action**, sélectionnez le bouton de la poubelle pour ce candidat.

## <a name="search-and-view-candidate-profiles"></a>Rechercher et afficher des profils de candidats

> [!NOTE] 
> Cette fonctionnalité est actuellement en mode aperçu. Si vous souhaitez l'essayer, vous devez [l'activer dans les paramètres administrateur d'Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature). 

Les viviers de talents vous permettent de consulter le profil, les informations LinkedIn, les documents associés, et l'historique de candidature des candidats. Vous pouvez effectuer une rechercher dans la base de données complète de tous les candidats ajoutés à n'importe quel vivier de talents, y compris les candidats clôturés et actifs.

>[!NOTE]
> Lorsque vous ajoutez de nouveaux candidats, ces ajouts peuvent demander jusqu'à 15 minutes pour être indexés pour la recherche.

Avec l'expérience de recherche améliorée, vous pouvez effectuer des recherches dans tous les documents des candidats et les filtrer par médaille d'argent, sources, compétences, formation, entre autres. Dans les versions précédentes, vous deviez spécifier l'entité dans laquelle vous souhaitez chercher. Attract peut désormais rechercher dans tous les champs associés au candidat et classer les résultats.

1. Pour démarrer une nouvelle recherche dans la base de données de candidats, entrez le texte à rechercher dans la zone de recherche de l'onglet **Viviers de talents**. 

Vous pouvez taper le nom d'un candidat ou n'importe quel attribut que vous recherchez. Pour séparer les attributs, utilisez un espace.

Vous pouvez limiter les résultats en modifiant votre requête de recherche ou en utilisant les filtres intelligents à gauche de la page.

Les résultats de la recherche mettent en évidence les différents attributs qui correspondent à votre requête de recherche. Sélectionnez le candidat qui vous intéresse pour afficher son profil.

### <a name="syntax-highlights"></a>Éléments de syntaxe 

| Opérateur | Utilisation                                                      | Exemple              |
|----------|------------------------------------------------------------|----------------------|
| \*       | Recherche des sous-chaînes ; permet de renvoyer tous les enregistrements | Entrée : Mi\* <br></br> Résultat : tous les enregistrements contenant un champ commençant par « MI », comme Microsoft, Midtown ou Middleton <br></br>Entrée : \* <br></br> Résultat : tous les enregistrements de la base de données |
| “”       | Recherche d'une correspondance exacte                                | Entrée : « Microsoft » <br></br> Résultat : tous les enregistrements contenant « Microsoft »                    |

>[!WARNING]
> Ne désactivez pas la recherche par pertinence pour votre instance de Common Data Service. Cela désactiverait l'expérience de recherche dans Attract.

Tous les utilisateurs ont un point de vue commun des profils de candidats. L'onglet **Profil** affiche toutes les informations sur les qualifications, l'expérience professionnelle et l'éducation que le candidat a fournies dans le cadre de sa candidature dans le portail de carrière.

- Vous pouvez afficher les détails du contact du candidat. Vous pouvez également modifier ou mettre à jour les informations comme vous le souhaitez à l'aide du bouton **Modifier les détails**.

- Vous pouvez afficher l'historique complet de la candidature du candidat. Vous pouvez voir tous les postes auxquels le candidat a postulé dans votre organisation et le statut de ces candidatures. Si vous faites partie de l'équipe de recrutement d'un poste, vous pouvez sélectionner **Afficher** pour consulter la candidature en détail.

- L'onglet **Documents** affiche tous les documents que le candidat a ajoutés depuis son profil ou lors de candidatures à un poste. Cet onglet permet de gérer les CV du candidat, ses lettres de motivation, son portefeuille d'emploi, etc. Vous pouvez également utiliser cet onglet pour ajouter des documents.

    Pour afficher un document, sélectionnez le nom du document dans la liste des documents. Vous pouvez afficher les documents Microsoft Word dans l'application à l'aide de Microsoft 365. Vous pouvez également télécharger les documents sur votre ordinateur local à l'aide de l'option **Télécharger** pour chaque document.

- L'onglet **LinkedIn** affiche les informations LinkedIn du candidat. Pour utiliser cet onglet, vous devez connecter votre compte LinkedIn dans les paramètres utilisateur, et la connexion à LinkedIn Recruiter de votre environnement doit être établie. Pour plus d'informations, voir [Identifier des candidats avec LinkedIn Recruiter dans Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md).

> [!NOTE]
> Seuls les candidats peuvent actualiser leurs qualifications, leur historique de formation et leur expérience professionnelle.

## <a name="add-candidates-from-a-talent-pool-to-a-job"></a>Ajouter des candidats d'un vivier de talents à un poste

Depuis les résultats d'une recherche ou un vivier de talents, vous pouvez transmettre un candidat à n'importe quel poste actif pour laquelle vous embauchez. Pour transmettre un candidat à un poste spécifique, procédez comme suit.

1. Recherchez le candidat à l'aide de l'option de recherche, puis ouvrez son profil. Sinon, ouvrez le vivier de talents depuis l'onglet **Mes viviers de talents**, recherchez le candidat dans le vivier de talents, puis ouvrez son profil.

1. Dans la page de profil du candidat, sélectionnez **Ajouter au poste** dans le coin supérieur droit. 
     
     Une liste de postes pour lesquelles vous appartenez à l'équipe de recrutement, en tant que recruteur ou responsable de l'embauche, s'affiche.

1. Sélectionnez le poste auquel ajouter le candidat et sélectionnez **Ajouter**. Vous pouvez également rechercher le poste à l'aide du champ de recherche en haut de la boîte de dialogue **Ajouter le candidat au poste**.

    Si la prospection a été activée pour le poste, le candidat est ajouté au stade **Prospect**.

    Si la prospection n'a pas été activée pour le poste, le candidat est ajouté au stade **Postuler**. Selon la configuration du poste, le candidat peut également recevoir un e-mail dans lequel il peut afficher sa candidature.

## <a name="add-candidates-from-a-job-to-a-talent-pool"></a>Ajouter des candidats d'un poste à un vivier de talents

Souvent, plusieurs bons candidats pour un poste ne sont pas sélectionnés, mais vous ne souhaitez pas les perdre de vue. Dans ce cas, vous pouvez ajouter les candidats à un vivier de talents afin de pouvoir les inviter à postuler à d'autres postes à venir.

1. Accédez au poste à partir duquel vous souhaitez ajouter un candidat.

1. Sélectionnez le candidat, puis ouvrez sa candidature.

1. Sur la page de candidature, sélectionnez **Ajouter au vivier de talents**. Une liste des viviers de talents auxquels vous avez accès s'affiche.

1. Sélectionnez ou recherchez le vivier de talents, puis sélectionnez **Ajouter** pour ajouter le candidat à ce vivier de talents.


[!INCLUDE[footer-include](../includes/footer-banner.md)]