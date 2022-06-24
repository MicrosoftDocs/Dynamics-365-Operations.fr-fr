---
title: Créer un compte de stockage Azure dans le portail Azure
description: Cet article explique comment créer un compte de stockage Azure pour la facturation électronique.
author: dkalyuzh
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4380261140086bcb278162f8dc70b39eaa7078fe
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898016"
---
# <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Créer un compte de stockage Azure dans le portail Azure

[!include [banner](../includes/banner.md)]

Tous les fichiers électroniques générés par le service Facturation électronique ou transmis au service lors de leur traitement sont stockés dans vos conteneurs de compte de stockage Microsoft Azure. Pour vous assurer que la facturation électronique peut accéder à ces conteneurs, vous devez fournir le jeton de signature d’accès partagé (SAS) du compte de stockage au service de facturation électronique. De plus, pour vous assurer que le jeton est stocké en toute sécurité, ne fournissez pas le jeton SAS directement. Au lieu de cela, stockez-le dans un coffre de clés Azure et fournissez une clé secrète Azure Key Vault.

1. Ouvrez le compte de stockage que vous prévoyez d’utiliser avec le service de facturation électronique.
2. Accédez à **Paramètres** \> **Configuration**, et assurez-vous que le paramètre **Autoriser l’accès public au blob** est défini sur **Autorisé**.
3. Accédez à **Stockage de données** \> **Conteneurs** et créez un nouveau conteneur.
4. Entrez un nom pour le conteneur et définissez le champ **Niveau d’accès public** sur **Privé (pas d’accès anonyme)**.
5. Ouvrez le nouveau conteneur et accédez à **Paramètres** \> **Stratégie d’accès**.
6. Sélectionnez **Ajouter une stratégie** pour ajouter une stratégie d’accès stockée.
7. Définissez le champ **Identifiant** selon le cas.
8. Dans le champ **Autorisations**, sélectionnez toutes les autorisations.

    ![Toutes les autorisations sélectionnées dans le champ Autorisations de la boîte de dialogue Ajouter une stratégie.](media/e-invoicing-azure-1.png)

9. Entrez les dates de début et de fin. La date de fin doit être dans le futur.
10. Cliquez sur **OK** pour enregistrer la stratégie, puis enregistrez vos modifications du conteneur.
11. Accédez à **Paramètres** \> **Jetons d’accès partagés** et définissez les valeurs de champ.
12. Entrez les dates de début et de fin. La date de fin doit être dans le futur.
13. Dans le champ **Autorisations**, sélectionnez les autorisations suivantes :

    - Lire
    - Ajouter
    - Créer
    - Écriture
    - Supprimer
    - Liste

14. Sélectionnez **Générer un jeton SAS et une URL**.
15. Copiez et stockez la valeur dans le champ **URL SAS du blob**. Cette valeur sera utilisée ultérieurement dans cette procédure et sera appelée *URI de la signature d’accès partagé*.
16. Ouvrez le coffre de clés que vous souhaitez utiliser avec la Facturation électronique.
17. Accédez à **Paramètres** \> **Clés secrètes**, puis sélectionnez **Générer/Importer** pour créer une clé secrète.
18. Sur la page **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.
19. Entrez le nom du secret. Ce nom sera utilisé lors de la configuration du service dans Regulatory Configuration Service (RCS) et sera appelé *nom de la clé secrète du coffre de clés*. Pour plus d’informations sur RCS, voir [Regulatory Configuration Service (RCS) – Fonctionnalités de globalisation](e-invoicing-set-up-rcs.md).
20. Dans le champ **Valeur**, saisissez l’URI de signature d’accès partagé que vous avez copiée précédemment.
21. Cliquez sur **Créer**.
