---
title: Création d'un compte fournisseur
description: Cette procédure indique comment créer un compte fournisseur, puis ajouter une adresse et des informations de contact.
author: mkirknel
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd8cd2bb7b03c0415a5c5656f0e3ffada961973e
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428318"
---
# <a name="create-a-vendor-account"></a>Création d'un compte fournisseur

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment créer un compte fournisseur, puis ajouter une adresse et des informations de contact. La procédure ne montre pas comment renseigner tous les champs à des fins d'achat et de gestion financière. Pour plus d'informations sur ces champs, lisez les descriptions des champs. Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Les comptes fournisseur sont généralement créés par un professionnel de l'approvisionnement ou de la comptabilité client.


## <a name="create-a-vendor-account"></a>Créer un compte fournisseur
1. Allez dans **Volet de navigation > Modules > Approvisionnements > Fournisseurs > Tous les fournisseurs**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Compte fournisseur**, tapez une valeur.
    - La valeur peut être automatiquement renseignée. Dans ce cas, vous pouvez ignorer cette étape.  
    - Vous pouvez créer des comptes fournisseurs pour une personne ou une organisation. Cela affecte la disponibilité des champs. Dans cet exemple, nous allons créer un compte fournisseur pour une organisation.   
4. Dans le champ **Nom**, saisissez ou sélectionnez une valeur. Si votre fournisseur est déjà enregistré dans votre système, vous pouvez utiliser la liste déroulante et le sélectionner dans ce champ. Le compte fournisseur héritera des informations d'adresse et de contact qui sont déjà enregistrées.
5. Saisissez ou sélectionnez une valeur dans le champ **Groupe**. Le groupe de fournisseurs permet de regrouper les fournisseurs qui ont l'un des paramètres suivants en commun : Conditions de paiement ; retards de règlement, y compris les groupes de taxes ; comptes généraux par défaut ; codes de filtres produits ou configuration des prévisions d'approvisionnement.
6. Dans le champ **Nombre d'employés**, entrez un nombre.
7. Dans le champ **Numéro de l'organisation**, saisissez une valeur.

## <a name="add-an-address"></a>Ajouter une adresse
1. Développez la section **Adresses**.
2. Cliquez sur **Ajouter**.
3. Saisissez ou sélectionnez une valeur dans le champ **Objectif**. Vous pouvez sélectionner un ou plusieurs objets. Ils sont utilisés pour sélectionner l'adresse correcte pour un objet donné. Par exemple, si l'objet est « Facture » cette adresse est utilisée pour l'envoi des factures.
4. Dans le champ **Nom ou description**, saisissez une valeur.
5. Dans le champ **Pays/Région**, sélectionnez ou entrez une valeur. Entrez les détails d'adresse. Le pays/la région que vous avez sélectionné déterminera les champs qui apparaîtront, en fonction du format d'adresse pour le pays/la région. 
6. Cliquez sur **OK**.

## <a name="add-contact-information"></a>Ajouter des informations de contact
1. Développez la section **Informations de contact**.
2. Cliquez sur **Ajouter**.
3. Tapez une valeur dans le champ **Description**.
4. Sélectionnez une option dans le champ **Type**.
5. Saisissez une valeur dans le champ **Numéro/adresse du contact**. Vous pouvez activer la case à cocher Principal s'il s'agit de l'adresse principale du contact.  
6. Cliquez sur **Enregistrer**.
7. Fermez la page.
8. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]