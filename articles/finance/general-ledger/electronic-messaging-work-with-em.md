---
title: Utiliser la fonctionnalité de messages électroniques
description: Cette rubrique fournit des informations générales sur l'utilisation de la configuration de la fonctionnalité Messages électroniques (ME).
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8fd2301808f7eaec2ea9c01a66f030f527f461a36b3cb8aabddcfbf414f06d2a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779906"
---
# <a name="work-with-the-electronic-messages-functionality"></a>Utiliser la fonctionnalité de messages électroniques

[!include [banner](../includes/banner.md)]

Si vous travaillez au niveau du message, la page **Messages électroniques** (**Taxe** \> **Recherches et états** \> **Messages électroniques** \> **Messages électroniques**) est plus utile. Si vous travaillez au niveau de la collecte de données (niveau élément de message), la page **Éléments du message électronique** (**Taxe** \> **Recherches et états** \> **Messages électroniques** \> **Éléments du message électronique**) est plus utile.

## <a name="electronic-messages"></a>Messages électroniques

La page **Messages électroniques** présente le traitement disponible pour vous, en fonction de votre rôle. Les rôles de sécurité sont associés au traitement dans le paramétrage de celui-ci. Pour chaque traitement disponible pour vous, la page affiche les messages électroniques et les informations connexes.

L’organisateur **Messages** affiche les messages électroniques du traitement sélectionné. Selon le statut du message sélectionné et le traitement prédéfini, vous pouvez exécuter certaines actions en sélectionnant les boutons au-dessus de la grille :

- **Nouveau** : Ce bouton est associé aux actions du type **Créer un message**.
- **Supprimer** : Ce bouton est disponible si la case à cocher **Autoriser la suppression** est activée pour le statut actuel du message sélectionné.
- **Collecte des données** – Ce bouton est associé aux actions de type **Renseigner les enregistrements**.
- **Générer un état** : Ce bouton est associé aux actions du type **Message d’exportation pour la gestion des états électroniques**.
- **Envoyer un état** : Ce bouton est associé aux actions du type **Service Web**.
- **Importer une réponse** – Ce bouton est associé aux actions de type **Importation de la gestion des états électroniques**.
- **Mettre à jour le statut** : Ce bouton est associé aux actions du type **Traitement utilisateur au niveau du message**.
- **Éléments du message** : Ouvre la page **Éléments du message électronique**.

L’organisateur **Journal des actions** présente des informations sur toutes les actions exécutées pour le message sélectionné. Si une action a causé une erreur, les informations relatives à l’erreur sont jointes à la ligne associée dans la grille. Pour vérifier les informations sur l’erreur, sélectionnez la ligne dans la grille, puis sélectionnez le bouton **Pièce jointe** (symbole de trombone) dans le coin supérieur droit de la page.

L’organisateur **Champs supplémentaires du message** affiche tous les champs supplémentaires définis pour les messages dans le paramétrage du traitement. L'organisateur comprend également les valeurs de ces champs supplémentaires.

L’organisateur **Éléments du message** affiche tous les éléments du message liés au message sélectionné. Selon le statut du message sélectionné, vous pouvez exécuter certaines actions en sélectionnant les boutons au-dessus de la grille :

- **Supprimer** - Ce bouton est disponible si la case à cocher **Autoriser la suppression** est activée pour le statut actuel de l’élément de message sélectionné.
- **Mettre à jour le statut** – Ce bouton est associé aux actions de type **Traitement utilisateur**.
- **Document d’origine** – Ouvre une page qui affiche le document d’origine de l’élément de message sélectionné.

Les états qui ont déjà été générés et reçus pour un message sont liés à ce message. Pour examiner les pièces jointes associées à un message, sélectionnez le message, puis sélectionnez le bouton **Pièce jointe** (le symbole du trombone) dans le coin supérieur droit de la page.

![Bouton Pièce jointe](media/attachment-icon.png)

La page **Pièces jointes** affiche toutes les pièces jointes associées au message sélectionné. Pour afficher un fichier, sélectionnez-le dans la liste à gauche, puis sélectionnez **Ouvrir** sur le volet Actions.

![Bouton Ouvrir](media/open-button.png)

Vous pouvez consulter les pièces jointes associées à une action spécifique qui a été précédemment exécutée pour un message. Sur la page **Messages électroniques**, sur l'organisateur **Messages**, sélectionnez le message. Sur l'organisateur **Journal des actions**, sélectionnez l'action, puis sélectionnez le bouton **Pièce jointe** (symbole de trombone) dans le coin supérieur droit de la page.

Vous pouvez exécuter l’ensemble du traitement ou seulement une action spécifique en sélectionnant **Exécuter le traitement** sur le volet Action.

## <a name="electronic-message-items"></a>Éléments du message électronique

La page **Éléments du message électronique** montre tous les éléments du message et un journal des actions exécutées pour chaque élément du message. La page affiche également les champs supplémentaires définis pour les éléments du message et les valeurs de ces champs supplémentaires.

Le tableau suivant décrit les champs de la page **Éléments du message**.

<table>
<thead>
<tr>
<th>Champ</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Traitement</td>
<td>Nom du traitement utilisé pour créer l’élément du message.</td>
</tr>
<tr>
<td>Élément du message</td>
<td>ID de l’élément du message. Cet ID est affecté automatiquement, selon la souche de numéros <b>Élément du message</b> définie sur la page <b>Paramètres de comptabilité</b>.</td>
</tr>
<tr>
<td>Date de l’élément de message</td>
<td>Date de création de l’élément du message.</td>
</tr>
<tr>
<td>Type d’élément de message</td>
<td>Type de l’élément du message. Plusieurs types d’éléments de messages peuvent être paramétrés pour le même traitement (par exemple, <b>Factures entrantes</b> et <b>Factures sortantes</b>). Ce champ peut être défini automatiquement uniquement si une facture est ajoutée à la table Éléments du message.</td>
</tr>
<tr>
<td>Statut de l'élément de message</td>
<td><p>Statut actuel de l’élément du message. Les statuts disponibles varient, en fonction du type de l’élément du message. Voici quelques exemples :</p>
<ul>
<li><b>Renseigné</b> : Un enregistrement a été ajouté à la table Éléments du message.</li>
<li><b>Évalué</b> : Des attributs supplémentaires ont été calculés pour l’élément du message.</li>
<li><b>Déclaré</b> : L’élément du message a bien été ajouté à un état.</li>
<li><b>Exclu</b> : Ce statut peut être utile si des éléments du message doivent être exclus d’un état avant qu’il soit exporté.</li>
</ul>
</td>
</tr>
<tr>
<td>Date de transmission</td>
<td>Pour le traitement qui transmet automatiquement un état généré en dehors du système, date à laquelle l’élément du message a été transmis.</td>
</tr>
<tr>
<td>Numéro de référence</td>
<td>Ce champ est automatiquement défini en fonction du paramétrage de l’action de renseignement des enregistrements. Ce champ peut être défini automatiquement uniquement si une facture est ajoutée à la table Éléments du message.</td>
</tr>
<tr>
<td>Numéro de compte</td>
<td>Numéro de compte d’un client ou d’un fournisseur, ou autre valeur de champ, selon le champ défini dans l’action Renseigner les enregistrements. Ce champ peut être défini automatiquement uniquement si une facture est ajoutée à la table Éléments du message.</td>
</tr>
<tr>
<td>Message </td>
<td>Numéro du message. Ce numéro est affecté automatiquement, selon la souche de numéros <b>Message</b> définie sur la page <b>Paramètres de comptabilité</b>.</td>
</tr>
<tr>
<td>Statut du message</td>
<td>Statut actuel du message électronique.</td>
</tr>
<tr>
<td>Action suivante</td>
<td>Actions suivantes pouvant être démarrées pour le statut actuel de l’élément du message.</td>
</tr>
</tbody>
</table>

L’onglet **Champs supplémentaires** affiche les champs supplémentaires de l’élément du message sélectionné, et leurs valeurs.

### <a name="run-processing"></a>Exécuter le traitement

Sur le volet Actions, sélectionnez **Exécuter le traitement** pour exécuter le traitement des éléments du message. Pour exécuter une action spécifique, dans la boîte de dialogue **Exécuter le traitement**, définissez l’option **Choisir l’action** sur **Oui**, puis sélectionnez une action. Pour exécuter le traitement complet, laissez l’option **Choisir l’action** définie sur **Non**.

### <a name="generate-report"></a>Générer un rapport

Dans le volet Actions, sélectionnez **Générer l'état**. Ce bouton est associé aux actions du type **Exportation pour la gestion des états électroniques**.

### <a name="update-status"></a>Mise à jour du statut

Sur le volet Actions, sélectionnez **Mettre à jour le statut** pour mettre à jour le statut d’un ou de plusieurs éléments du message. Dans la boîte de dialogue **Mettre à jour le statut**, utilisez l’organisateur **Enregistrements à inclure** pour sélectionner les éléments de message à mettre à jour. Assurez-vous de définir correctement les critères de sélection, car les statuts d’élément du message sont mis à jour selon ces critères, le statut initial de l’action sélectionnée et la valeur spécifiée dans le champ **Nouveau statut**. Une fois la mise à jour du statut terminée, il sera difficile de déterminer les éléments mis à jour. Par conséquent, il sera difficile d’annuler la mise à jour de statut.

### <a name="electronic-messages"></a>Messages électroniques

Sur le volet Actions, sélectionnez **Messages électroniques** pour réviser un message électronique associé à l’élément de message sélectionné.

Vous pouvez également réviser les fichiers associés à un élément de message spécifique. Sélectionnez le champ **Message** pour l’élément de message ou, sur le volet Actions, sélectionnez **Messages électroniques**. Sur la page **Message électronique**, sélectionnez le message dont vous souhaitez examiner les fichiers, puis sélectionnez le bouton **Pièce jointe** (symbole de trombone) dans le coin supérieur droit de la page.

La page **Pièces jointes** affiche les pièces jointes associées au message. Pour afficher un fichier, sélectionnez-le dans la liste à gauche, puis sélectionnez **Ouvrir** sur le volet Actions.

### <a name="original-document"></a>Document d'origine

Sur le volet Actions, sélectionnez **Document d’origine** pour ouvrir le document d’origine de l’élément du message sélectionné.
