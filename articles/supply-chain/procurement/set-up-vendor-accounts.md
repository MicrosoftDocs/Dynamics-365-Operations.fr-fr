---
title: "Paramétrer les comptes fournisseur"
description: "Cette rubrique décrit les types d'informations que vous devez spécifier lorsque vous créez un nouveau compte fournisseur."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: smmContactPerson, VendBankAccounts, VendTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 191053
ms.assetid: 06168199-7c54-40e9-a038-4eb274ca958d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e871acb38ccfdbe8bf298ebb05b8420c55e0093f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-vendor-accounts"></a>Paramétrer les comptes fournisseur

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les types d'informations que vous devez spécifier lorsque vous créez un nouveau compte fournisseur.

Lorsque vous créez un compte fournisseur, vous devez entrer des informations concernant le fournisseur. Ces informations permettent d'entrer automatiquement les données dans des documents et de suivre les activités qui impliquent le fournisseur. Par exemple, vous pouvez configurer les informations suivantes pour un fournisseur :

-   Affectez un groupe de fournisseurs. Chaque fournisseur doit être affecté à un groupe de fournisseurs. Les fournisseurs d'un groupe de fournisseurs ont des paramètres qu'ils partagent. Par exemple, ils peuvent avoir les mêmes conditions de paiement.
-   Configurez le fournisseur pour l'importation du catalogue. Les fournisseurs peuvent fournir un fichier qui contient le catalogue de leurs articles et de leurs services. Ce fichier peut être chargé pour que vos collaborateurs puissent commander à partir du fournisseur.
-   Permet d'affecter le fournisseur à des catégories d'approvisionnement.
-   Autorisez un fournisseur existant à exercer son activité avec une autre entité juridique de votre organisation.
-   Mettez un fournisseur en attente pour des types de transaction spécifiques.
-   Paramétrez des informations d'opérations bancaires pour le fournisseur, afin de pouvoir envoyer des paiements par voie électronique.
-   Paramétrez la taxe, la livraison, la facture et les informations de paiement pour le fournisseur. Par défaut, ces paramètres sont copiés dans les documents que vous créez pour le fournisseur.
-   Paramétrez des dimensions financières par défaut utilisées pour valider automatiquement les transactions avec le fournisseur dans les comptes financiers.

Pour accélérer le processus de création des comptes fournisseur, vous pouvez créer des modèles. Pour créer un modèle, dans la page **Fournisseur**, dans le volet Actions, cliquez sur **Options** &gt; **Infos sur l'enregistrement**. Cliquez ensuite sur **Modèle de compte société**. Les modèles de compte société sont partagés avec d'autres utilisateurs.  

Vous pouvez également créer un modèle utilisateur pour votre utilisation personnel. Vous ne pouvez pas supprimer un fournisseur associé à d'autres enregistrements, tels que des contacts ou des produits.

## <a name="vendor-account-numbers"></a>Numéros de compte fournisseur
Le numéro de compte est un identificateur unique pour un fournisseur. Vous pouvez paramétrer des numéros de compte de manière à ce qu'ils soient générés automatiquement lorsque vous créez un fournisseur. Vous pouvez également configurer la souche de numéros pour que les numéros de compte soient entrés manuellement. Par exemple, vous pouvez utiliser le numéro de téléphone du fournisseur comme identificateur.

## <a name="vendor-organizations-and-individual-vendors"></a>Organisations du fournisseur et fournisseurs individuels
Lorsque vous créez un compte fournisseur, vous devez sélectionner si le fournisseur est une organisation ou une personne. Votre sélection affecte les informations que vous devez renseigner pour le fournisseur. Pour une personne, ces informations incluent le prénom, le nom de famille, et la fonction. Pour une organisation, ces informations incluent le numéro d'organisation et le nombre d'employés.

## <a name="addresses"></a>Adresses
Pour chaque fournisseur, vous pouvez définir plusieurs adresses, chacune est utilisée pour un objectif différent. Par exemple, vous pouvez créer une adresse dont l'objectif est **Facture**. Ou, si vous payez le fournisseur à l'aide de chèques, vous pouvez paramétrer une adresse ayant l'objectif **Remise**. Si vous devez spécifier une adresse à utiliser pour les transferts d'argent vers les banques étrangères, l'objectif sera **SWIFT**.

## <a name="vendor-contacts"></a>Contacts fournisseur
Vous pouvez enregistrer des contacts pour un fournisseur. Ces contacts peuvent être utilisés sur des documents tels que des commandes fournisseur ou des demandes de devis.  

Pour ajouter des contacts pour un fournisseur, dans la page **Tous les fournisseurs**, sous l'onglet, **Fournisseur**, dans le groupe **Paramétrage**, cliquez sur **Contacts** &gt; **Ajouter des contacts**.  

Vous pouvez créer des contacts fournisseur de toutes pièces. Sinon, vous pouvez copier les détails d'une autre personne déjà enregistrée dans Microsoft Dynamics 365 for Finance and Operations, et modifier les informations comme vous le souhaitez.  

**Remarque :** Le fait d'ajouter un contact pour un fournisseur n'est pas la même chose qu'ajouter des informations de contact pour ce fournisseur. Bien que vous puissiez ajouter des informations de contact générales pour un fournisseur, vous pouvez également définir plusieurs personnes spécifiques qui sont des contacts à cette société, et qui ont toutes leurs propres informations de contact.  

Vous ne pouvez pas supprimer l'enregistrement d'une personne à contacter si le contact est référencé sur un document. Au lieu de cela, vous pouvez désactiver le contact.  

Vous pouvez ajouter des contacts fournisseur à vos contacts personnels dans Microsoft Office 365. Toutefois, vous devez d'abord paramétrer la synchronisation entre Finance and Operations et Office 365 dans la synchronisation de Microsoft Exchange Server et l'Assistant Paramétrage de Microsoft Outlook.

## <a name="vendors-in-different-legal-entities"></a>Fournisseurs dans plusieurs entités juridiques
Si un fournisseur est enregistré pour une seule entité juridique de votre organisation, et que d'autres entités juridiques doivent enregistrer le même fournisseur, vous pouvez utiliser la page **Ajouter le fournisseur à une autre entité juridique** pour configurer le fournisseur pour qu'il exerce son activité avec une autre entité juridique. Vous devez sélectionner un groupe de fournisseurs, une devise et un statut de blocage pour le fournisseur dans l'entité juridique sélectionnée.  

Si plusieurs entités juridiques de votre organisation travaillent avec le même fournisseur et si chacune tient à jour un compte fournisseur séparé pour ce dernier, vous pouvez fusionner les ID partie global pour les comptes fournisseur. Ainsi, des informations telles que l'adresse et le nombre d'employés peuvent être partagées, et vous devez la mettre à jour dans un seul emplacement.  

Pour fusionner les ID partie, procédez comme suit.

1.  Sur la page **Carnet d'adresses global**, sélectionnez les enregistrements de carnet d'adresses qui représentent le fournisseur dans chaque entité juridique qui doit être incluse dans la mise en correspondance.
2.  Dans le volet Actions, cliquez sur **Fusionner les enregistrements**.

## <a name="agreements"></a>Accords
Lorsque vous paramétrez un compte fournisseur, vous pouvez également souhaiter enregistrer les accords que vous avez avec le fournisseur. Vous pouvez paramétrer des accords de prix et de remise à l'aide des actions dans l'enregistrement de fournisseur. Vous pouvez également paramétrer un contrat d'achat dans la page **Contrats d'achat**.

## <a name="putting-a-vendor-on-hold"></a>Mise en attente d'un fournisseur
Vous pouvez placer un fournisseur en attente pour différents types de transactions. Les options suivantes sont disponibles :

-   **Non** – Le fournisseur n'est associé à aucun blocage.
-   **Facture** – Aucune facture ne peut être créée ou validée pour le fournisseur.
-   **Tout** – Tous les types de transactions sont bloqués pour le fournisseur. Ces types de transactions comprennent les demandes d'achat, les factures et les paiements.
-   **Paiement** – Aucun paiement ne peut être généré pour le fournisseur.
-   **Demande** – Une seule demande d'achat peut être créée à la fois. Aucune autre transaction ne peut être créée.
-   **Jamais** – Le fournisseur n'est jamais suspendu en raison de son inactivité.

Lorsque vous mettez un fournisseur en attente, vous pouvez également indiquer un motif et une date à laquelle le statut en attente prendra fin. Si vous n'entrez aucune date de fin, le blocage du fournisseur est définitif.

Vous pouvez mettre à jour en bloc le statut En attente sur **Tous** pour les fournisseurs en fonction des critères sélectionnés sur la page **Désactivation du fournisseur**, puis affectez un motif expliquant pourquoi le fournisseur est en attente.

Les critères suivants sont utilisés pour inclure les fournisseurs qui ont été inactifs au cours d'une période, incluent ou excluent les fournisseurs qui sont des employés, et excluent les fournisseurs bénéficiant d'un délai de grâce avant la prochaine mise en attente.

- Selon le nombre de jours que vous entrez dans le champ **Période d'activité** sur la page **Désactivation du fournisseur**, l'application calcule la dernière date à laquelle le fournisseur peut avoir eu une activité considérée comme inactive. Cela signifie la date du jour moins le nombre de jours que vous entrez. Si une ou plusieurs factures existent pour le fournisseur dont la date est postérieure à la dernière date calculée, le fournisseur sera exclus de la désactivation. Cela est également validé si le fournisseur a des paiements après la date, ouvre des demandes d'achat, ouvre des commandes fournisseur, demande des devis, ou répond.
- Le nombre de jours dans le champ **Délai de grâce avant la prochaine suspension** permet de calculer la dernière date de grâce. Cela signifie la date du jour moins le nombre de jours que vous entrez. Cela s'applique uniquement aux fournisseurs qui ont été précédemment inactivés. Dans le cas d'une désactivation précédente, l'application vérifie l'historique d'autres occurrences de désactivation du fournisseur et vérifie si la dernière désactivation est survenue avant la dernière date de grâce. Dans ce cas, le fournisseur est inclus dans le processus de désactivation.
- Le paramètre **Inclure les employés** fait référence aux fournisseurs qui sont liés à un employé. Vous pouvez le définir si vous souhaitez inclure les employés.

Ce processus exclura toujours les fournisseurs dont la valeur dans le champ **Blocage fournisseur** est définie sur **Jamais**.

Les fournisseurs qui passent les contrôles avec succès sont mis en attente, ce qui définit la valeur du champ **Blocage fournisseur** sur **Tous** et **Motif** sur ce qui a été sélectionné. Un enregistrement est créé dans l'historique des suspensions pour le fournisseur.

## <a name="vendor-invoice-account"></a>Compte de facturation fournisseur
Si plusieurs fournisseurs possèdent la même adresse de facturation ou si un fournisseur est facturé via un tiers, vous pouvez spécifier un compte de facturation sur l'enregistrement fournisseur. Le compte de facturation est le compte sur lequel le montant de la facture est crédité lorsque vous créez une facture fournisseur à partir d'une commande fournisseur. Si vous n'entrez pas de compte de facturation sur l'enregistrement fournisseur, le compte utilisé sera le compte fournisseur.

## <a name="vendor-bank-accounts"></a>Comptes bancaires fournisseur
Si vous devez effectuer des paiements vers un compte bancaire fournisseur, vous pouvez entrer des informations sur la banque et les comptes bancaires du fournisseur sur la page **Comptes bancaires fournisseur**. Vous pouvez aussi entrer des informations sur le contrôle et les paiements pour le compte bancaire sélectionné. Par exemple, vous pouvez ajouter des notes préliminaires aux comptes bancaires fournisseurs. Les banques utilisent les notes préliminaires pour vérifier la précision des données du compte, telles que les numéros d'acheminement et les numéros de compte. Vous devez spécifier un compte par défaut pour les paiements au fournisseur. Toutefois, lorsque vous effectuez un paiement réel, vous pouvez remplacer ce compte par l'un des autres comptes du fournisseur.

## <a name="ledger-accounts"></a>Comptes généraux
Vous pouvez spécifier les comptes par défaut qui s'affichent automatiquement dans les journaux des factures fournisseur pour le fournisseur spécifié. Cette fonctionnalité peut être utile si vous payez généralement les même articles ou services auprès des mêmes fournisseurs. Si vous spécifiez un compte par défaut, vous pouvez entrer rapidement et efficacement des entrées de journal dans le journal des factures. Les comptes par défaut que vous spécifiez ne sont pas utilisés pour les commandes fournisseur ou les factures fournisseur entrées dans l'écran **Facture fournisseur**.  

Vous devez sélectionner les comptes par défaut dans la page **Paramétrage du compte par défaut**, accessible à partir de l'onglet **Facture** dans l'enregistrement de fournisseur. Les comptes que vous sélectionnez ici s'affichent dans la liste filtrée des comptes du compte fournisseur lorsque vous entrez une entrée de journal. Vous pouvez définir l'un des comptes comme celui par défaut.




