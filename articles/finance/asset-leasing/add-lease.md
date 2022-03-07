---
title: Ajouter ou copier des baux (version préliminaire)
description: Cette rubrique décrit comment créer un bail en saisissant des informations pour celui-ci dans Location d’actifs ou en copiant les informations depuis un bail existant.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b09a87c7d4f5ba076647218c3586d17a13e6c558
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967924"
---
# <a name="add-or-copy-leases-preview"></a>Ajouter ou copier des baux (version préliminaire)

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment créer un bail de A à Z dans Location d’actifs et comment créer un bail en copiant un bail existant. Le processus de création d’un bail de A à Z implique de saisir les informations pour le nouveau bail et de créer un échéancier de bail. Après la configuration d’au moins un bail, vous pourriez trouver plus simple de copier les informations à partir d’un bail existant et de modifier ces informations comme l’exige la création d’un nouveau bail.

## <a name="create-a-lease"></a>Créer un bail

Procédez comme suit pour créer un bail dans Location d’actifs.

1. Sur la page **Récapitulatif du bail**, dans le volet Actions, sélectionnez **Nouveau**.
2. Entrez les informations du bail. Les champs obligatoires sont encadrés en rouge.

La date de début du paiement de location ne peut pas être antérieure à la date de début de la location. Si vous entrez une date de début du paiement de location antérieure à la date de début de la location, vous recevrez un message d’erreur.

Par défaut, l’option **Répartir le montant du paiement** du raccourci **Général** de la page **Détails du bail** est définie sur **Non** si l’option **Autoriser la répartition du paiement** de la page **Paramètres de location d’actifs** est définie sur **Oui**. 

Si l’option **Répartir le montant du paiement** est définie sur **Oui**, le champ **Montant du paiement** du raccourci **Lignes d’échéancier de paiement** est verrouillé. Il sera fixé comme le total des montants de paiement saisis ultérieurement dans le catalogue **Répartition du montant du paiement**.

Sélectionnez **Répartition du montant du paiement** pour ouvrir une page où vous pouvez ajouter les types de paiement détaillés. Le bouton **Ajouter des totaux au montant du paiement** déplacera les totaux vers le champ **Montant du paiement**.

> [!NOTE]
> Si vous ajoutez un montant de paiement détaillé, puis sélectionnez la touche **Échap**, les montants saisis ne seront pas ajoutés au champ **Montant du paiement** du raccourci **Lignes d’échéancier de paiement**. Au lieu de cela, ils seront stockés dans la boîte de dialogue **Répartition du montant du paiement**. Si vous voulez que la boîte de dialogue affiche le montant total, sélectionnez la colonne **Montant**, sélectionnez et maintenez (ou cliquez avec le bouton droit), puis sélectionnez **Totaliser cette colonne**. 

Le bouton **Copier la ligne** copiera la ventilation détaillée du paiement.

## <a name="create-a-lease-schedule"></a>Créer un échéancier de bail

Une fois que vous avez terminé de saisir les informations relatives au bail, procédez comme suit pour créer un échéancier de bail.

> [!NOTE]
> Les dimensions financières peuvent changer en fonction des dimensions financières personnalisées.

1. Sélectionnez **Créer des échéanciers** pour générer les registres de location. Les registres de bail comprennent les échéanciers de paiement, d’amortissement et de dépenses.
2. Pour accéder aux registres de bail et afficher les échéanciers récemment créés, sélectionnez l’onglet **Registres**.

    La page **Détails du registre** montre comment le bail est comptabilisé par les registres qui lui ont été attribués. De là, vous pouvez afficher les échéanciers de bail.

    L’échéancier de paiement contient les entrées de l’onglet **Lignes d’échéancier de paiement** sur la page **Ajouter un bail**. Vous pouvez toujours modifier chaque montant de paiement et paiement variable. Le passif locatif est calculé en fonction de l’échéancier de paiement modifié.

    > [!NOTE]
    > La date de début du paiement de location doit être la même ou une date postérieure à la date de début du bail. Vous recevrez un message d’erreur si la date de début du paiement de location est antérieure à la date de début de la location. 

4. Après avoir examiné l’échéancier de paiement, sélectionnez **Confirmer l’échéancier**. Une fois l’échéancier confirmé, le bail n’est plus disponible pour modification.

    > [!NOTE]
    > Le système calcule automatiquement la durée du bail à partir des lignes de l’échéancier de paiement sur la page **Ajouter un bail**.
    >
    > Pour calculer la durée du bail en mois, le système recherche la différence entre la date de début et la date de fin pour une ligne de paiement spécifique. Il passe ensuite à la ligne de l’échéancier de paiement suivante et recherche à nouveau la différence. Enfin, le système additionne tous les montants pour déterminer la durée du bail en mois.

5. Pour afficher les charges d’intérêts de la période calculées, ouvrez la page **Échéancier de l’amortissement du passif**. Pour afficher l’amortissement linéaire calculé, ouvrez la page **Échéancier d’amortissement des actifs**.
6. Après avoir examiné le montant calculé, vous pouvez créer l’écriture de journal de reconnaissance initiale sur la page **Reconnaissance initiale**. Vous recevez un message indiquant que le journal a été créé.

    > [!NOTE]
    > L’écriture de journal n’est pas validée dans le grand livre tant que vous ne validez pas manuellement l’écriture.

7. Pour consulter l’entrée de comptabilisation initiale proposée avant de la publier, sélectionnez **Journal de location d’actifs**.

    > [!NOTE]
    > Le journal de location d’actifs ne peut pas être créé manuellement. Il est automatiquement créé lors de la création des échéanciers de location.

8. Lorsque vous avez terminé de consulter l’écriture initiale du journal de comptabilisation et que vous êtes prêt à la publier, sélectionnez **Publier** pour comptabiliser l’actif au titre du droit d’utilisation (ROU) et le passif de location dans le grand livre.

## <a name="copy-a-lease"></a>Copier un bail

Le leasing d’actifs vous permet de copier les détails d’un bail pour en créer un contenant les mêmes informations. Vous pouvez ensuite modifier les champs du bail avant de créer les échéanciers pour le bail copié.

1. Sur la page **Récapitulatif du bail**, sélectionnez le bail à copier, puis, dans le volet Actions, sélectionnez **Copier le bail**.

    > [!NOTE]
    > Si le paramètre **Manuel** est désactivé pour la séquence de numéros pour les ID de bail, le numéro suivant de la séquence est automatiquement généré comme ID de bail du bail copié. Si le paramètre **Manuel** est activé, vous recevez un message qui vous invite à saisir l’ID du bail avant de procéder à la copie du bail.

2. Sélectionnez **Copie**. Les détails du bail à partir du bail sélectionné sont copiés dans un nouveau bail. Vous pouvez ensuite modifier les détails du nouveau bail avant de l’enregistrer et de créer les échéanciers de bail.

## <a name="asset-leasing-journal"></a>Journal de leasing d’actifs

Toutes les écritures de journal créées dans Leasing d’actifs sont contenues dans le journal Leasing d’actifs. Sur la page **Journal de leasing d’actifs** (**Leasing d’actifs\> Entrées de journal \> Journal de location d’actifs**), vous pouvez filtrer par statut de validation, afficher des écritures de journal spécifiques et les pièces justificatives, et valider les écritures de journal non comptabilisées.

> [!NOTE]
> Le journal de location d’actifs ne peut pas être créé manuellement. Il est automatiquement créé lors de la création des échéanciers de location.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
