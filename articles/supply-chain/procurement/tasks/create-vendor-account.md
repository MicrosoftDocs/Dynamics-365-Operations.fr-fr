---
title: Création d'un compte fournisseur
description: Cette procédure indique comment créer un compte fournisseur, puis ajouter une adresse et des informations de contact.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 98a7c6d209400b754064f2176d1ebca291093304
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838044"
---
# <a name="create-a-vendor-account"></a>Création d'un compte fournisseur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment créer un compte fournisseur, puis ajouter une adresse et des informations de contact. La procédure ne montre pas comment renseigner tous les champs à des fins d'achat et de gestion financière. Pour plus d'informations sur ces champs, lisez les descriptions des champs. Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Les comptes fournisseur sont généralement créés par un professionnel de l'approvisionnement ou de la comptabilité client.


## <a name="create-a-vendor-account"></a>Création d'un compte fournisseur
1. Accédez à Approvisionnements > Fournisseurs > Tous les fournisseurs.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Compte fournisseur.
    * La valeur peut être automatiquement renseignée. Dans ce cas, vous pouvez ignorer cette étape.  
    * Vous pouvez créer des comptes fournisseurs pour une personne ou une organisation. Cela affecte la disponibilité des champs. Dans cet exemple, nous créerons un compte fournisseur pour une organisation.   
4. Saisissez ou sélectionnez une valeur dans le champ Nom.
    * Si votre fournisseur est déjà enregistré dans votre système, vous pouvez utiliser la liste déroulante et le sélectionner dans ce champ. Le compte fournisseur héritera des informations d'adresse et de contact qui sont déjà enregistrées.  
5. Saisissez ou sélectionnez une valeur dans le champ Groupe.
    * Le groupe de fournisseurs permet de regrouper les fournisseurs qui ont l'un des paramètres suivants en commun : Conditions de paiement ; retards de règlement, y compris les groupes de taxes ; comptes généraux par défaut ; codes de filtres produits ou configuration des prévisions d'approvisionnement.  
6. Dans le champ Nombre d'employés, entrez un nombre.
7. Dans le champ Numéro de l'organisation, saisissez une valeur.

## <a name="add-an-address"></a>Ajouter une adresse
1. Développez la section Adresses.
2. Cliquez sur Ajouter.
3. Saisissez ou sélectionnez une valeur dans le champ Objectif.
    * Vous pouvez sélectionner un ou plusieurs objets. Ils sont utilisés pour sélectionner l'adresse correcte pour un objet donné. Par exemple, si l'objet est « Facture » cette adresse est utilisée pour l'envoi des factures.  
4. Tapez une valeur dans le champ Nom ou description.
5. Dans le champ Pays/Région, sélectionnez ou entrez une valeur.
    * Entrez les détails d'adresse. Le pays/la région que vous avez sélectionné déterminera les champs qui apparaîtront, en fonction du format d'adresse pour le pays/la région.   
6. Cliquez sur OK.

## <a name="add-contact-information"></a>Ajouter des informations de contact
1. Cliquez sur Ajouter.
2. Dans le champ Description, entrez une valeur.
3. Sélectionnez une option dans le champ Type.
4. Saisissez une valeur dans le champ Numéro/adresse du contact.
    * Vous pouvez activer la case à cocher Principal s'il s'agit de l'adresse principale du contact.  
5. Cliquez sur Enregistrer.
6. Fermez la page.
7. Fermez la page.

