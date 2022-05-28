---
title: Workflow de fournisseur
description: Modifiez les informations du fournisseur et utilisez un workflow pour les approuver.
author: sunfzam
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 1801e3d90bbf80c59bb62329acc593d2c66a179c
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735665"
---
# <a name="vendor-workflow"></a>Workflow de fournisseur

[!include [banner](../includes/banner.md)]

Lorsque le workflow de fournisseur est utilisé, les modifications apportées à des champs spécifiques sont envoyées au workflow pour approbation avant d’être ajoutées au fournisseur.

## <a name="set-up-the-vendor-workflow"></a>Paramétrer le workflow de fournisseur

Avant de pouvoir utiliser la fonctionnalité de workflow, vous devez l’activer.

1. Allez dans **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.
2. Sous l’onglet **Général**, dans l’organisateur **Approbation du fournisseur**, définissez l’option **Activer les approbations de fournisseur** sur **Oui**.
3. Dans le champ **Comportement de l’entité de données**, sélectionnez le comportement à adopter lorsque les données sont importées :

    - **Autoriser les modifications sans approbation** – L’entité de données peut mettre à jour l’enregistrement fournisseur sans le traiter via le workflow.
    - **Rejeter les modifications** – Il est impossible d’apporter des modifications à cet enregistrement fournisseur. L’importation échouera pour les champs activés pour le workflow.
    - **Créer des propositions de modification** – Tous les champs seront modifiés à l’exception des champs activés pour le workflow. Les nouvelles valeurs de ces champs seront proposées au fournisseur en tant que modifications, et le workflow sera lancé automatiquement.

4. Dans la liste des champs du fournisseur, activez la case à cocher **Activer** pour chaque champ qui doit être approuvé avant que les modifications soient appliquées.
5. Allez dans **Comptabilité fournisseur \> Paramétrage \> Workflows de la comptabilité fournisseur**.
6. Sélectionnez **Nouveau**.
7. Sélectionnez **Workflow des modifications proposées du fournisseur**. 
8. Paramétrez le workflow afin qu’il corresponde à votre processus d’approbation. L’élément d’approbation de workflow **Approbation de workflow pour la modification proposée du fournisseur** appliquera les modifications au fournisseur.

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a>Modifier les informations du fournisseur et soumettre les modifications au workflow

Lorsque vous modifiez un champ qui est activé pour le workflow, la page **Modifications proposées** s’affiche. Cette page affiche la valeur initiale du champ et la nouvelle valeur entrée. Le champ que vous avez modifié est rétabli sur sa valeur d’origine. Un message de statut vous indique également que vos modifications n’ont pas été soumises. 

Chaque fois que vous modifiez un champ qui est activé pour le workflow, il est ajouté à la liste dans la page **Modifications proposées**. Pour ignorer la valeur proposée pour un champ, utilisez le bouton **Ignorer** en regard du champ dans la liste. Pour ignorer toutes les modifications, utilisez le bouton **Ignorer toutes les modifications** en bas de la page. Sélectionnez **OK** pour fermer la page.

Une fois que vous avez au moins une modification proposée, deux onglets supplémentaires apparaissent dans le volet Actions : **Modifications proposées** et **Workflow**.

1. Sélectionnez **Modifications proposées** pour ouvrir la page **Modifications proposées** et consulter vos modifications.
2. Sélectionnez **Workflow \> Soumettre pour envoyer les modifications au workflow**.

    Le statut dans la page est remplacé par **Modifications en attente d’approbation**.

Le workflow suit le processus de workflow standard. L’approbateur est dirigé vers la page **Fournisseur**, où les modifications peuvent être vérifiées sur la page **Modifications proposées**, puis il doit sélectionner **Workflow \> Approuver** pour approuver le workflow. Une fois toutes les approbations effectuées, les champs sont mis à jour avec les valeurs que vous avez proposées.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
