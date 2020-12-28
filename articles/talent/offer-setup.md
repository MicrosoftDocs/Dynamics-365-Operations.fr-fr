---
title: Paramétrer la gestion des offres dans Attract
description: Cette rubrique décrit comment paramétrer les offres dans Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc91a83afd5ce1627376685bcf612d6998ddbc02
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461152"
---
# <a name="set-up-offer-management-in-attract"></a>Paramétrer la gestion des offres dans Attract

[!include [banner](includes/banner.md)]

Lorsqu'un candidat est déplacé vers le stade de l'offre dans Dynamics 365 Talent: Attract, vous devez vous assurer que les offres peuvent être rapidement créées pour le candidat, approuvées au besoin, et soumises au candidat. Comme la plupart des offres sont standard, elles peuvent être créées à partir de modèles réutilisables. Dans Attract, toutes les offres sont regroupées dans un package d'offre, qui est un ensemble d'un ou plusieurs documents d'offre. 

Cette rubrique répertorie toutes les étapes qu'un administrateur Attract doit suivre pour paramétrer différents modèles de package d'offre dans le cadre de la fonctionnalité de gestion des offres d'Attract. Les utilisateurs avec des rôles non-administrateurs n'ont pas accès à ces fonctionnalités.

>[!NOTE]
> Les fonctionnalités de gestion des offres sont disponibles dans le cadre du composant additionnel de recrutement complet.

## <a name="offer-data"></a>Données de l'offre 

Les données de l'offre constituent la plus petite unité à l'intérieur du modèle de package d'offre. Une offre classique consiste en un texte standard et un ensemble de valeurs. Les ensembles de valeurs sont les seuls éléments qui peuvent changer entre les offres. Lors de la création de l'offre, l'aspect le plus important que le créateur de l'offre doit prendre en compte est la liste des espaces réservés des données de l'offre présents dans un modèle de package d'offre. Pour paramétrer les données de l'offre, procédez comme suit.

1.  Accédez à **Gestion des offres**.

1.  Développez la section **Bibliothèque** dans le volet de navigation gauche, puis accédez à **Données de l'offre**.

    >[!NOTE]
    > Dans la page **Données de l'offre** se trouvent les sections **Détails du candidat** et **Détails de la mission**. Attract fournit quelques espaces réservés de données prêts à l'emploi.
    > 
    > Il existe des sections dans la page permettant d'organiser les différents espaces réservés de données de l'offre en groupes logiques. Ces sections peuvent vous aider dans la mise à jour des données de l'offre et le renseignement des données lors du processus de création de l'offre.
    > 
    > Pour créer une liste de valeurs pour un espace réservé, téléchargez une feuille de calcul Excel avec une colonne portant l'espace réservé comme titre de colonne et la liste de choix dans les lignes en dessous. Si le même espace réservé est référencé dans un autre ensemble de règles de données, assurez-vous qu'ils ont un ensemble commun de valeurs.
    
1.  Pour créer une section de données de l'offre, cliquez sur **Ajouter une section** et entrez un nom unique pour la section.

1.  Pour ajouter des espaces réservés de données de l'offre dans une section, cliquez sur **Ajouter des données de l'offre** et entrez un nom unique pour l'espace réservé.

1.  Pour modifier le nom d'une section, placez votre pointeur sur le nom de la section et mettez-le à jour.

1.  Pour modifier le nom d'un espace réservé de données de l'offre existant, assurez-vous d'abord que l'espace réservé ne fait pas déjà partie d'un modèle. Ensuite, placez votre pointeur sur le nom de l'espace réservé de données de l'offre et mettez à jour le nom selon vos besoins.

1. Pour supprimer un espace réservé de données de l'offre existant, assurez-vous d'abord que l'espace réservé ne fait pas partie d'un autre modèle. Ensuite, placez votre pointeur sur l'espace réservé et lorsque l'icône de la poubelle s'affiche, cliquez dessus pour supprimer l'espace réservé de données de l'offre.
    >[!NOTE]
    > Vous pouvez voir le nombre de modèles dont fait partie un espace réservé de données de l'offre grâce à l'indicateur de chiffre en regard de chaque donnée de l'offre. 

1. Pour supprimer une section, placez votre pointeur sur le nom. Si aucun des espaces réservés de données de l'offre dans la section n'apparaît dans aucun modèle, vous pouvez cliquer sur l'icône de la poubelle pour la supprimer. 
    >[!NOTE]
    > La suppression de la section supprimera également tous les espaces réservés de données de l'offre qu'elle contient.

Une fois les espaces réservés des données de l'offre définis, vous pouvez les utiliser dans n'importe quel modèle de document. Les espaces réservés de données de l'offre ne sont pas limités à un modèle spécifique : le même ensemble peut être utilisé dans tous les modèles.

## <a name="offer-data-rules"></a>Règles de données de l'offre

La plupart d'organisation disposent de règles relatives à la création des offres. Par exemple, une organisation peut souhaiter exiger que les offres de salaire annuel maximales pour une combinaison de lieu et de niveau d'ancienneté spécifiques soient situées dans une certaine plage, ou que seules quelques valeurs spécifiques soient possibles au niveau de l'offre pour la nouvelle recrue. Attract prend actuellement en charge toutes ces règles de données à l'aide d'un fichier CSV.

Pour préparer le fichier CSV de règles de données, procédez comme suit.

1.  Déterminez l'espace réservé de données de l'offre pour l'ensemble de règles. Par exemple, **Salaire annuel**.

1.  Identifiez les valeurs de l'espace réservé de données de l'offre dépendantes. Par exemple, **Emplacement de la mission** et **Niveau**.

1.  Spécifiez les colonnes 1 et 2 en **Emplacement de la mission** et **Niveau**.

1.  Pour charger une valeur de plage, faites des colonnes 3 et 4 **Salaire annuel**. Pour charger une valeur spécifique au lieu d'une plage, faites de la colonne 3 **Salaire annuel**.

1.  Renseignez le fichier Microsoft Excel selon vos rôles obligatoires.

1.  Assurez-vous que chaque ligne soit une combinaison unique des valeurs regroupées.

1.  Enregistrez le fichier au format CSV.

Pour charge le fichier de règles de données de l'offre, procédez comme suit.

1.  Accédez à **Gestion des offres**.

1.  Développez la section **Bibliothèque** dans le volet de navigation gauche, puis accédez à **Règles de données de l'offre**.

1.  Cliquez sur **Nouvel ensemble de données** pour afficher la boîte de dialogue **Charger**.

1.  Spécifiez un nom unique pour l'ensemble de règles puis chargez le fichier CSV enregistré.

1.  Cliquez sur **Ajouter**.
    L'ensemble de règles sera traité en arrière-plan et vous sera notifié dans l'application avertie et par courrier électronique lorsque le traitement sera terminé.

    Vous serez averti si des erreurs surviennent lors du traitement du chargement. Vous pouvez ensuite télécharger le journal des erreurs, corriger le fichier, et le charger de nouveau.

1.  L'option du bouton (**...**) si vous souhaitez télécharger l'ensemble de règles et mettre à jour l'ensemble de valeurs. Après la mise à jour, vous pouvez charger le fichier de nouveau.

1.  Vous pouvez supprimer un chargement de l'ensemble de règles existant si l'espace réservé est défini comme inutilisé dans un autre modèle de document.

>[!NOTE]
> - Chaque espace réservé ne peut disposer que d'un seul ensemble de colonnes dont il dépend. Par exemple, si **Salaire annuel** dépend d'**Emplacement de la mission** et de **Niveau**, vous ne pouvez pas charger un autre ensemble de règles où **Salaire annuel** dépend d'un ensemble de colonnes différent.

> - Vous pouvez télécharger des exemples d'ensembles de règles de données de l'offre dans l'onglet **Exemples** de la page **Règles de données de l'offre**.

> - Lorsqu'un créateur d'offre remplace les valeurs recommandées par les règles de données de l'offre, l'offre est marquée comme non standard et le workflow d'approbation de l'offre est obligatoire.

## <a name="document-templates"></a>Modèles de document

Un modèle de document d'offre peut aider les administrateurs à créer des lettres d'offre. Le modèle de document d'offre est une combinaison du texte faisant partie de l'offre et des espaces réservés de données de l'offre définis. 

Pour créer un modèle de document d'offre, procédez comme suit.

1.  Accédez à **Gestion des offres**.

1.  Développez la section **Bibliothèque** dans le volet de navigation gauche et accédez à **Modèles**.

    La page **Modèles** affiche une liste des modèles de documents déjà définis.

1.  Pour créer un modèle de document, cliquez sur **Nouveau modèle**.

1.  Entrez un nom unique pour le modèle, puis cliquez sur **Créer**.

1.  L'éditeur de texte enrichi vous permet d'insérer ou de modifier le contenu du document d'offre. Vous pouvez insérer des tableaux, des images et des liens hypertexte à l'aide des options disponibles en haut de l'éditeur de texte.

1.  Vous pouvez insérer des espaces réservés de données de l'offre dans le modèle de document d'offre en :

    - Les faisant glisser et déplacer depuis le volet droit.

    - Ajoutant une balise de hachage directement à l'emplacement de l'espace réservé de données de l'offre. Entrez **\#** puis commencez à saisir le nom de l'espace réservé de données de l'offre. Des options s'afficheront dans la liste déroulante. Cliquez ou appuyez sur **Entrée** pour insérer l'espace réservé de données de l'offre.

    >[!NOTE]
    > - Pour associer un espace réservé au modèle de document d'offre sans exposer sa valeur au candidat, placez votre pointeur sur l'espace réservé de données de l'offre et cliquez sur l'icône **Épingler**. Cela placera l'espace réservé dans la section **Données de l'offre épinglées** du modèle de document de l'offre. Pour annuler l'épinglage, suivez les mêmes étapes mais cliquez sur **Annuler l'épinglage** dans la liste des espaces réservés de données de l'offre.

    > - Pour afficher la liste des espaces réservés de données de l'offre actifs, basculez vers l'onglet **Actif** dans le volet de droite.

    > - Si vous insérez un espace réservé basé sur un ensemble de règles de données de l'offre, la dépendance de cet espace réservé de données de l'offre s'affiche sur d'autres valeurs.

    > - Sinon, vous pouvez **Importer** le contenu d'un fichier .docx sur votre ordinateur local et le modifier au besoin. Ainsi, vous n'avez pas besoin d'entrer tout le contenu dans l'éditeur.

1. Pour afficher un aperçu du document d'offre, utilisez l'option **Aperçu** en haut de la page.

1. Pour contrôler si un créateur d'offre peut modifier le contenu du document d'offre, utilisez l'option **Gérer les autorisations** en haut de la page. Si vous souhaitez que le créateur de l'offre insère uniquement les valeurs de l'espace réservé sans modifier le texte, définissez la valeur d'autorisation sur **Non**.

1. Cliquez sur **Enregistrer** pour enregistrer votre progression. Le modèle sera enregistré dans un état de brouillon.

1. Pour terminer et marquer le document comme publié, cliquez sur **Terminer**.

1. Vous pouvez afficher les modèles de document actuellement actifs, en mode de brouillon et archivés qui ne sont plus en cours d'utilisation sur l'expérience de page de destination de la bibliothèque de modèles de documents.

>[!NOTE]
> Vous pouvez supprimer un modèle de document d'offre qui ne fait pas partie d'un modèle de package d'offre existant.


## <a name="offer-package-templates"></a>Modèles de packages d'offre

Les packages d'offre sont les artefacts d'offre qui sont partagés avec le candidat et se composent d'une combinaison d'un ou de plusieurs modèles de document d'offre. Pour créer un package d'offre, procédez comme suit.

1.  Accédez à **Gestion des offres**.

1.  Accédez à **Packages** dans volet de navigation de gauche.

    Une liste des modèles de packages d'offre actifs disponibles pour les créateurs d'offres s'affiche.

1.  Pour créer un package d'offre, cliquez sur **Nouveau package**.

1.  Entrez un nom unique et cliquez sur **Créer**.

1.  Cliquez sur **Ajouter un modèle**.

    >[!NOTE]
    > - Vous pouvez choisir de créer un modèle ou d'utiliser un modèle existant.

    > - Si vous choisissez d'ajouter un modèle existant, vous devez vous assurer que le modèle de document d'offre a été enregistré, terminé et marqué comme actif.
    
    > - Vous pouvez choisir autant de modèles de documents que vous le souhaitez. 
    
1.  Cliquez sur **Terminé** pour revenir à **Gestion du package**.

    Vous pouvez configurer la séquence des documents et également marquer si le document d'offre spécifique est obligatoire lors de la création d'une offre. Le créateur d'offre disposera d'une option pour supprimer les documents marqués comme **Non obligatoire**.

1. Pour enregistrer le modèle de package d'offre afin qu'il soit utilisable par tous les créateurs d'offres, cliquez sur **Enregistrer et publier**.

   Pour afficher les brouillons de modèles de packages d'offre, accédez à l'onglet **Brouillons**. Si une modification est apportée au modèle de package d'offre, celui-ci doit être enregistré et republié.

## <a name="configure-an-offer-process"></a>Configurer un processus d'offre

Il existe plusieurs parties du processus de création d'offre qui peuvent être configurées par un administrateur Attract.

- **Approbations de l'offre** : Choisissez si des approbations de l'offre sont requises avant que l'offre puisse être envoyée au candidat. En tant qu'administrateur, vous pouvez également décider si toutes les approbations de l'offre se produiront de manière séquentielle ou via un workflow d'approbation parallèle. Vous pouvez également décider si les approbateurs de l'offre doivent ajouter obligatoirement un commentaire à leur approbation d'offre. Les approbations d'offre sont obligatoires pour toutes les offres non standard.

- **Expérience d'offre du candidat** : En tant qu'administrateur, vous pouvez choisir de définir si toutes les offres ont une date d'expiration et, le cas échéant, quelle doit être la contrepartie par défaut pour la date d'expiration. Vous pouvez également configurer si les candidats peuvent refuser une offre.

- **Signatures électroniques** - Tant donc qu'administrateur, vous pouvez également sélectionner la méthode que les candidats peuvent utiliser pour signer des offres.
    - Adobe Sign - Tous les packages d'offre sont envoyés et signés via Adobe Sign. Chaque créateur d'offre publiant l'offre doit avoir son compte Adobe Sign connecté à Attract. Pour les licences Adobe Sign et une version d'évaluation, consultez ce [lien](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).

    - DocuSign - Tous les packages d'offre sont envoyés et signés via DocuSign. Chaque créateur d'offre publiant l'offre doit avoir son compte DocuSign connecté à Attract. 
    
    - ESign - Il s'agit de l'option par défaut, prédéfinie, permettant à l'utilisateur de signer une offre en entrant son nom et ses initiales.


Pour en savoir plus sur le processus de création d'offre, voir [Créer, approuver et signer des offres](./creating-offers.md).
