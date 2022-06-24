---
title: Configurer les informations de groupe TDS, PAN et TAN pour les fournisseurs et les clients
description: Cet article explique comment configurer les informations sur le groupe de taxe déduite à la source (TDS), le numéro de compte permanent (PAN) et le numéro de compte fiscal (TAN) pour les fournisseurs et les clients.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1a29f59e380360b6f828dcddbe84cad229b42d17
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859764"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a>Configurer les informations de groupe TDS, PAN et TAN pour les fournisseurs et les clients

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer les informations sur le groupe de taxe déduite à la source (TDS), le numéro de compte permanent (PAN) et le numéro de compte fiscal (TAN) pour les fournisseurs et les clients.

1. Accédez à **Comptabilité fournisseur \> Fournisseurs \> Tous les fournisseurs** ou **Comptabilité client \> Clients \> Tous les clients**.

    [![Page Tous les fournisseurs.](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)

2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un fournisseur ou client, puis entrez les détails requis. Vous pouvez également sélectionner un fournisseur ou un client existant.
3. Dans le raccourci **Facture et livraison**, dans la section **Retenue à la source**, définissez l’option **Calcul de la retenue à la source** sur **Oui** pour calculer la retenue à la source, le TDS ou la taxe perçue à la source (TCS) pour le fournisseur ou le client.
4. Le TDS pour une facture d’achat est calculé en fonction du groupe TDS par défaut défini pour le fournisseur ou le client. Dans le champ **Groupe TDS**, sélectionnez le groupe TDS par défaut.

    > [!NOTE]
    > Lorsque vous sélectionnez un groupe TDS dans le champ **Groupe TDS**, les champs **Groupe de retenue à la source** et **Groupe TCS** deviennent indisponibles.

5. Dans le raccourci **Informations fiscales**, dans la section **Informations PAN**, dans le champ **Statut**, sélectionnez le statut du numéro de compte permanent du fournisseur ou du client :

    - **Indisponible** - Le fournisseur ou le client n’a pas de PAN.
    - **Reçu** - Le fournisseur ou le client a un PAN.
    - **Appliqué** - Le fournisseur ou le client a demandé un PAN.
    - **Invalide** - Le fournisseur ou le client a un PAN, mais il n’est pas valide.

6. Si vous avez sélectionné **Reçu** dans le champ **Statut** pour indiquer que le fournisseur ou le client a un PAN, entrez le PAN dans le champ **Numéro**. Le PAN doit être composé de cinq caractères alphabétiques, puis de quatre caractères numériques, puis d’un caractère alphabétique. Voici un exemple : **ABCDE1260A**.
7. Si vous avez sélectionné **Appliqué** dans le champ **Statut** pour indiquer que le fournisseur ou le client a appliqué un PAN, entrez le numéro de référence dans le champ **Numéro de référence**.
8. Dans le champ **Nature de la personne évaluée**, sélectionnez la nature de la catégorie de la personne évaluée à laquelle appartient le fournisseur ou le client :

    - Société
    - HUF
    - Confirmer
    - Personne
    - AOP
    - BOI
    - Autorité locale
    - Autres

    [![Raccourci Informations fiscales.](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)

9. Dans le volet Actions, dans l’onglet **Fournisseur**, dans le groupe **Inscription**, sélectionnez **ID enregistrement** pour ouvrir la page **Gérer les adresses**.
10. Dans la page **Gérer les adresses**, dans le raccourci **Informations fiscales**, sélectionnez **Ajouter** ou **Modifier** pour ouvrir la page **Gérer les informations fiscales** où vous pouvez gérer l’entrée d’enregistrement de taxe.
11. Dans la page **Gérer les informations fiscales**, dans le raccourci **Retenue à la source**, dans le champ **Numéro de compte fiscal (TAN)**, entrez le TAN. Le TAN doit être composé de quatre caractères alphabétiques, puis de cinq caractères numériques, puis d’un caractère alphabétique. Voici un exemple : **AFGH54821T**.
12. Fermez la page.
