---
title: FAQ relatif aux carnets d'adresses
description: "Cette rubrique contient les réponses du forum aux questions (FAQ) relatives aux carnets d'adresse dans Microsoft Dynamics 365 for Finance and Operations."
author: kfend
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartyCheckDuplicate, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 23601
ms.assetid: b177fa0f-ac9a-415e-9498-15438e132f60
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 2d148b8bd4a2588d282a9077aa76997399693483
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="address-books-faq"></a>FAQ relatif aux carnets d'adresses

[!include [banner](../includes/banner.md)]

<a name="how-do-i-check-for-duplicate-records"></a>Comment rechercher les enregistrements en double ?
-------------------------------------

Vous pouvez rechercher les enregistrements en double directement à partir de la page **Carnet d'adresses global**. Dans le volet Actions, sous l'onglet **Partie**, dans le groupe **Tenir à jour**, cliquez sur **Rechercher les doublons**. Sélectionnez ensuite les valeurs à inclure dans la vérification des doublons.

## <a name="can-i-bulk-add-or-delete-party-records-from-an-address-book"></a>Puis-je ajouter ou supprimer en masse des enregistrements de parties d'un carnet d'adresses ?
Oui, vous pouvez ajouter plusieurs enregistrements de parties à un carnet d'adresses et également supprimer plusieurs enregistrements de partie.

-   Pour ajouter plusieurs enregistrements de parties à un carnet d'adresses, sur la page de liste **Carnet d'adresses global**, sélectionnez les parties dans la liste. Ensuite, dans le volet Actions, sous l'onglet **Partie**, dans le groupe **Tenir à jour**, cliquez sur **Affecter des parties**. Sélectionnez les carnets d'adresses auxquels ajouter les enregistrements de parties sélectionnés, puis cliquez sur **OK**. Tous les enregistrements de parties sélectionnés sont ajoutés aux carnets d'adresses que vous avez sélectionnés.
-   Pour supprimer plusieurs enregistrements de parties d'un carnet d'adresses, sur la page de liste **Carnet d'adresses global**, sélectionnez les parties dans la liste. Ensuite, dans le volet Actions, sous l'onglet **Partie**, dans le groupe **Tenir à jour**, cliquez sur **Supprimer des parties**. Sélectionnez les carnets d'adresses desquels supprimer les parties, puis cliquez sur **OK**. Tous les enregistrements de parties sélectionnés sont supprimés des carnets d'adresses que vous avez sélectionnés.

## <a name="can-i-change-the-party-type-of-a-record-or-do-i-have-to-delete-the-old-record-and-create-a-new-one"></a>Puis-je modifier le type de partie d'un enregistrement, ou dois-je supprimer l'ancien enregistrement et en créer un nouveau ?
Il peut arriver que vous deviez modifier un enregistrement en faisant passer son type de partie de personne à organisation ou d'organisation à personne. Par exemple, Nancy est membre de l'équipe de vente de Fabrikam U.K. Lors d'un salon commercial à Londres, elle rencontre six nouveaux prospects. Nancy crée un enregistrement de partie de prospect pour chaque prospect. Lorsqu'elle enregistre les enregistrements, chaque enregistrement est également créé dans le carnet d'adresses global. Fabrikam a défini le type de partie par défaut à organisation, mais deux des nouveaux prospects doivent avoir un type d'enregistrement de personne. Par conséquent, lorsque Nancy revient du salon commercial, elle doit modifier le type de partie des deux enregistrements de prospect. Pour modifier le type d'un enregistrement de partie, vous devez d'abord créer un enregistrement de partie ayant le type souhaité dans le carnet d'adresses global. Vous associez ensuite l'ancien enregistrement de partie à ce nouvel enregistrement. Après avoir effectué la nouvelle association de partie, supprimez l'enregistrement de partie d'origine dont le type d'enregistrement est incorrect.

## <a name="how-do-i-change-the-name-or-address-of-a-party-record"></a>Comment modifier le nom ou l'adresse d'un enregistrement de partie ?
Vous pouvez mettre à jour le nom d'un enregistrement de partie, ainsi que les adresses associées à cet enregistrement, à tout moment.

-   Pour mettre à jour le nom d'un enregistrement de partie, ouvrez-l'enregistrement de partie, puis, dans le volet Actions, cliquez sur **Modifier**. Dans l'organisateur **Général**, entrez le nouveau nom de la partie, puis sauvegardez l'enregistrement.
-   Pour mettre à jour une adresse pour un enregistrement de partie, ouvrez l'enregistrement de partie, puis, dans l'organisateur **Adresses**, sélectionnez l'adresse à mettre à jour. Cliquez sur **Modifier**, puis, sur la page, **Modifier l'adresse**, apportez les modifications nécessaires à l'adresse ou aux paramètres d'adresse.

## <a name="can-i-merge-two-or-more-party-records-into-one-record"></a>Puis-je fusionner deux enregistrements de partie ou plus en un seul enregistrement ?
Il est parfois nécessaire de fusionner deux enregistrements de parties, ou plus, en un seul. C'est le cas lorsque vous créez un ou plusieurs enregistrements de parties en double, intentionnellement ou non. Lors de la fusion d'enregistrements de parties, vous sélectionnez un enregistrement à conserver. Les informations des autres enregistrements sont alors fusionnées en cet enregistrement. Imaginons que vous découvrez que les informations concernant Fabrikam sont stockées dans trois enregistrements de parties, A, B et C. Vous décidez de conserver l'enregistrement de partie A. Par conséquent, les informations stockées dans les enregistrements de parties B et C seront fusionnées dans l'enregistrement de partie A. Dans certaines situations, vous ne pouvez pas fusionner d'enregistrements de parties :

-   Il est impossible de fusionner les enregistrements de parties associés au même rôle de partie, par exemple un client ou un fournisseur, dans la même entité juridique. Par exemple, la partie A est associée à un client dans l'entité juridique 123, et la partie B à un autre client dans l'entité juridique 123. Ces enregistrements de parties ne peuvent pas être fusionnés, car s'ils l'étaient, l'enregistrement de partie fusionné serait associé à plusieurs clients dans la même entité juridique, ce qui n'est pas autorisé. Il est cependant possible de fusionner les enregistrements si la partie B est associée à un fournisseur dans l'entité juridique 123 ou à un client dans une autre entité juridique.
-   Il est impossible de fusionner des enregistrements de parties internes à l'organisation dans la même entité juridique, la même équipe ou la unité opérationnelle.

## <a name="should-i-create-a-party-record-in-the-global-address-book-or-in-another-place-such-as-the-customer-or-vendor-page"></a>Dois-je créer un enregistrement de partie dans le carnet d'adresses global ou à un autre emplacement, comme la page Client ou Fournisseur ?
Vous pouvez entrer des enregistrements de parties soit dans le carnet d'adresses global, soit sur la page d'entité appropriée. Lorsque vous ajoutez un enregistrement dans un emplacement, le même enregistrement est toujours ajouté à l'autre emplacement. Par exemple, si vous ajoutez un enregistrement de partie pour un client dans le carnet d'adresses global, l'enregistrement est également ajouté sur la page **Client**. De même, si vous ajoutez un enregistrement de partie pour un client sur la page **Client**, l'enregistrement est également ajouté dans le carnet d'adresses global. Utilisez les instructions suivantes pour décider à quel emplacement vous devez entrer de nouveaux enregistrements de parties :

-   **Création d'un enregistrement de partie lorsque vous ne connaissez pas le type d'entité** – Si vous devez créer un enregistrement de partie mais que vous ne connaissez pas le type d'entité (par exemple, vous ne savez pas si l'entité est un client ou une opportunité), créez l'enregistrement dans le carnet d'adresses global. Vous pouvez sélectionner le type d'entité ultérieurement.
-   **Création d'un enregistrement de partie lorsque vous connaissez le type d'entité** – Si vous connaissez le type d'entité de la partie, vous pouvez créer un enregistrement dans la page applicable pour ce type. Par exemple, pour un client, vous créez un enregistrement sur la page **Client**. Lorsque vous créez et enregistrez un enregistrement par l'intermédiaire de la page d'entité applicable, l'enregistrement est créé automatiquement dans le carnet d'adresses global.

## <a name="can-i-translate-address-information-for-party-records"></a>Puis-je traduire les informations d'adresse pour les enregistrements de partie ?
Vous pouvez paramétrer des traductions des informations d'adresse afin que les informations s'affichent dans votre langue d'utilisateur (langue du système) dans Microsoft Dynamics 365 for Finance and Operations, mais dans une autre langue sur les documents tels que les commandes client. Vous pouvez entrer des traductions pour les noms de pays/régions, les objets d'adresse et les séquences de nom. Par exemple, la langue du système est le Danois et vous créez une commande client pour un client en France. Dans ce cas, vous pouvez afficher l'enregistrement client en danois dans le programme mais afficher les informations d'adresse en français sur la commande client imprimée. Lorsque vous paramétrez des traductions, vous devez entrer une traduction pour chaque article de la liste. Tout article pour lequel vous n'entrez pas de traduction s'affichera dans la langue du système. Par exemple, la langue du système est le Danois et vous envoyez un document à un client en Espagne. Si vous n'avez pas entré de traductions en espagnol (ESP) pour les informations d'adresse, ces informations s'affichent en danois dans le programme et sur le document imprimé.




