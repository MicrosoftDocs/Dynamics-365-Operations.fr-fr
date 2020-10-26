---
title: Calculer la date de livraison pour une ligne, en fonction du délai
description: Cette rubrique décrit comment calculer une date de livraison pour une ligne, en fonction du délai du fournisseur et du calendrier des jours ouvrables de votre organisation.
author: velofog
manager: AnnBe
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.search.industry: public sector
ms.author: roschlom
ms.search.validFrom: 2019-9-03
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 22c62969a56f42b78a509b5477cfa595706ae23a
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978252"
---
# <a name="calculate-the-delivery-date-for-a-line-based-on-the-lead-time"></a>Calculer la date de livraison pour une ligne, en fonction du délai

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment calculer une date de livraison pour une ligne, en fonction du délai du fournisseur et du calendrier des jours ouvrables de votre organisation, tels qu'ils sont spécifiés dans l'onglet **Devis** de la page **Réponse à l'appel d'offre**. Les fournisseurs peuvent spécifier un délai pour chaque ligne. Ensuite, lorsqu'une commande fournisseur est confirmée, une date de livraison pour une ligne est calculée à partir de la date de confirmation, en fonction du délai et du calendrier des jours ouvrables. Si aucun délai n'est spécifié, la date de confirmation est utilisée comme date de livraison, sauf si la date de livraison est automatiquement calculée.

Les détails du délai pour une ligne sont disponibles sur les pages suivantes : **Réponse à l'appel d'offre**, **Demandes d'achat**, **Contrats d'achat** et **Commande fournisseur**.

Les détails du délai ne sont pas remplacés lorsque vous calculez les dates de livraison pour toutes les lignes de la page à l'aide du bouton **Dates de livraison** de l'onglet **Calculer** du volet Actions. Vous pouvez mettre à jour les détails du délai pour les enregistrements non confirmés ou non approuvés. Lorsque vous confirmez un ordre de modification, vous pouvez recalculer une date de livraison.

## <a name="set-up-a-lead-time-calendar"></a>Définir un calendrier des délais

Vous devez configurer la possibilité de calculer les dates de livraison et le calendrier utilisé dans ces calculs dans la page **Paramètres d'approvisionnement**.

1. Accédez à **Administration de l'organisation \> Paramétrage \> Calendriers** et déterminez si un calendrier existant indique les jours d'ouverture de votre agence. Si vous trouvez un calendrier existant correspondant aux jours ouvrables de votre organisation (c'est-à-dire les jours où votre bureau est ouvert et peut recevoir des expéditions), passez à l'étape 2. Sinon, suivez ces étapes pour créer un calendrier des jours ouvrables. Vous pouvez créer un calendrier si, par exemple, votre bureau reçoit des expéditions du lundi au jeudi, mais les jours ouvrables de votre organisation sont du lundi au vendredi.

    1. Sélectionnez **Nouveau** pour créer un calendrier. Sinon, sélectionnez **Copier** pour créer un calendrier à partir d'un calendrier similaire existant que vous pouvez mettre à jour rapidement.
    2. Dans le champ **Calendrier**, entrez un identificateur pour le calendrier.
    3. Dans le champ **Nom**, entrez un nom descriptif.
    4. Sélectionnez **Heures de travail**.
    5. Sélectionnez **Composer des heures de travail**.
    6. Pour chaque jour du calendrier qui est un jour ouvrable, désactivez la case à cocher **Clôturé pour prélèvement**.
    7. Sélectionnez **Enregistrer** pour enregistrer les modifications.

    > [!IMPORTANT]
    > Il est déconseillé de modifier un calendrier existant qui est déjà utilisé par une autre partie de votre organisation.

2. Accédez à **Approvisionnements \> Paramétrage \> Paramètres d'approvisionnements**.
3. Sous l'onglet **Général**, définissez l'option **Calculer la date de livraison de la commande fournisseur en fonction du délai et des jours ouvrables** sur **Oui**.
4. Dans le champ **Sélectionner un calendrier pour déterminer les jours ouvrables**, sélectionnez le calendrier indiquant les jours d'ouverture de votre agence.
5. Sélectionnez **Enregistrer** pour enregistrer les modifications.

Une section **Délai** s'affiche maintenant sur les pages **Demandes d'achat**, **Commande fournisseur** et **Contrats d'achat**.

## <a name="edit-the-lead-time-for-a-line"></a>Modifier le délai pour une ligne

### <a name="purchase-requisition"></a>Demande d'achat

Les détails du délai saisis par un fournisseur pour une ligne dans la page **Réponse à l'appel d'offre** s'affichent dans la section **Délai** pour une demande d'achat. Vous pouvez saisir ou modifier les détails du délai pour une ligne de demande d'achat. Les valeurs de délai pour les lignes de demande d'achat sont reportées lors de la création d'une commande fournisseur.

1. Accédez à **Approvisionnements \> Demandes d'achat \> Toutes les demandes d'achat** pour ouvrir la page de liste **Toutes les demandes d'achat**. (Sinon, ouvrez une autre page de liste.)
2. Sélectionnez une demande d'achat dans la liste. Sinon, sélectionnez **Nouveau**.
3. Dans le raccourci **Lignes de demande d'achat**, sélectionnez une ligne, puis sélectionnez **Détails**.
4. Dans la page **Détails de la ligne de demande d'achat**, dans le raccourci **Détails**, dans la section **Délai**, entrez les détails sur la date de livraison.

    - Dans le champ **Délai**, entrez le nombre de jours requis pour le délai.
    - Pour utiliser uniquement les jours ouvrables, et non tous les jours du calendrier, pour calculer le délai, définissez l'option **Jours de travail** sur **Oui**.

7. Sélectionnez **Enregistrer** pour enregistrer les modifications.

### <a name="purchase-agreement"></a>Contrat d'achat

Les détails du délai saisis pour une ligne dans la page **Demande d'achat** s'affichent dans la section **Délai** pour un contrat d'achat. Vous pouvez modifier un contrat d'achat non approuvé existant ou inclure les détails du délai dans un nouveau contrat d'achat. Les valeurs de délai pour les lignes de contrat d'achat sont reportées lors de la création d'une commande fournisseur.

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Contrats d'achat**.
2. Dans la page de liste **Contrats d'achat**, sélectionnez un contrat d'achat dans la liste. Sinon, sélectionnez **Nouveau** (comme dans l'étape 2 de la procédure « Demande d'achat » ci-dessus).
3. Dans la page **Détails du contrat d'achat**, dans le volet Actions, sous l'onglet **Mettre à jour**, sélectionnez **Modifier**.
4. Dans le raccourci **Contrats d'achat**, sélectionnez la ligne de contrat d'achat.
5. Dans le raccourci **Détails de la ligne**, sous l'onglet **Général**, dans la section **Délai**, mettez à jour la date de livraison calculée.

    - Dans le champ **Délai**, entrez le nombre de jours requis pour le délai.
    - Pour utiliser uniquement les jours ouvrables, et non tous les jours du calendrier, pour calculer le délai, définissez l'option **Jours de travail** sur **Oui**.

8. Sélectionnez **Enregistrer** pour enregistrer les modifications.

### <a name="purchase-order"></a>Commande fournisseur

Les détails du délai saisis pour une ligne dans les pages **Contrat d'achat** et **Demande d'achat** s'affichent dans la section **Délai** pour une commande fournisseur. Vous pouvez modifier les détails du délai pour une commande fournisseur non confirmée.

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
2. Dans la page de liste **Toutes les commandes fournisseur**, sélectionnez une commande fournisseur dans la liste. Sinon, sélectionnez **Nouveau** (comme dans l'étape 2 de la procédure « Demande d'achat » ci-dessus).
2. Dans la page **Commande fournisseur**, dans le volet Actions, sous l'onglet **Mettre à jour**, sélectionnez **Modifier**.
3. Dans le raccourci **Détails de la ligne**, sous l'onglet **Livraison**, dans la section **Délai**, dans le champ **Date de livraison**, affichez la date de livraison calculée.
4. Dans le champ **Délai**, modifiez le nombre de jours requis pour le délai.
5. Pour utiliser uniquement les jours ouvrables, et non tous les jours du calendrier, pour calculer la date de livraison, définissez l'option **Jours de travail** sur **Oui**. La date de livraison sera mise à jour lorsque la commande fournisseur sera approuvée et confirmée en fonction du délai spécifié.
6. Sélectionnez **Enregistrer** pour enregistrer les modifications.

> [!NOTE]
> Pour les articles lancés, vous pouvez sélectionner un délai d'achat. Le délai d'achat calculera automatiquement la date de livraison lors de la création d'une commande fournisseur. La date de livraison ne sera pas recalculée si le délai sur la ligne de commande fournisseur est 0 (zéro).
