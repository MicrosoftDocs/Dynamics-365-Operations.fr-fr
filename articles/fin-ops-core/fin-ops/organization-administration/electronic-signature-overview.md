---
title: Vue d’ensemble des signatures électroniques
description: Cet article fournit une vue d’ensemble des signatures électroniques et décrit la manière de les utiliser.
author: maertenm
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.reviewer: sericks
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 547ab10dabb6bb3f8ea41d0f80db227fc24411a3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747709"
---
# <a name="electronic-signatures-overview"></a>Vue d’ensemble des signatures électroniques

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble des signatures électroniques et décrit la manière de les utiliser.

## <a name="what-is-an-electronic-signature"></a>Qu’est-ce qu’une signature électronique ?

Une signature électronique confirme l’identité d’une personne qui va commencer ou approuver une procédure informatique. Dans certains secteurs, une signature électronique représente un engagement juridique aussi important qu’une signature manuscrite.

La signature électronique est un impératif de conformité aux réglementations pour certaines industries réglementées, telles que les industries pharmaceutique, alimentaire et aérospatiale et de défense. C’est également un élément requis de la conformité aux réglementations 21 CFR Partie 11 émises par la FDA (Food and Drug Administration) aux États-Unis.

> [!NOTE]
> Une signature électronique n’est pas une signature numérique. Une signature électronique n’est qu’un substitut de signature manuscrite, alors qu’une signature numérique est accompagnée de mesures de sécurité supplémentaires. Une signature numérique permet d’identifier si un autre utilisateur ou une autre procédure a falsifié les données. Une signature numérique peut également être vérifiée et cette vérification ne peut pas être réfutée par le détenteur du certificat utilisé pour la signature des données. Conformément à la description ci-dessous, les signatures électroniques disposent d’une fonction de signature numérique intégrée.

## <a name="electronic-signatures"></a>Signatures électroniques

Vous pouvez utiliser des signatures électroniques pour des processus entreprise importants. Certains processus disposent d’une fonction de signature électronique intégrée. Vous pouvez également créer des demandes de signature personnalisées pour les tables et les champs de base de données.

Les signatures électroniques disposent d’une fonction de signature numérique intégrée. Chaque utilisateur qui signe des documents doit obtenir un certificat cryptographique valide. Lorsqu’un document est signé, la clé privée associée à ce certificat est contrôlée. Les informations de signature électronique sont enregistrées dans un journal pour fournir une piste d’audit. Pour configurer les signatures électroniques, consultez [Paramétrage de signatures électroniques](tasks/set-up-electronic-signatures.md).

## <a name="users-who-require-access-to-electronic-signatures"></a>Utilisateurs ayant besoin d’un accès aux signatures électroniques

Trois types d’utilisateurs différents ont généralement besoin d’un accès de sécurité aux signatures électroniques : les administrateurs de signature électronique, les signataires et les auditeurs.

### <a name="electronic-signature-administrator"></a>Administrateur de signature électronique

L’administrateur de signature électronique définit les demandes de signature, les paramètres généraux et les approbateurs, et reçoit des alertes en cas d’échec de la vérification de la signature. Par défaut, un utilisateur qui appartient au rôle de sécurité **Responsable informatique** a l’autorisation d’administrer les signatures électroniques.

### <a name="signer"></a>Signataire

Un signataire fournit des signatures électroniques pour des documents et des procédures nécessitant une signature. Par défaut, un utilisateur qui appartient au rôle de sécurité **Utilisateur système** a l’autorisation de signer les documents électroniquement.

> [!NOTE]
> Le signataire peut avoir besoin d’autorisations supplémentaires avant qu’un accès soit accordé aux données associées au document ou à la procédure à signer. Les utilisateurs qui modifient les données et qui doivent ensuite signer ces modifications doivent avoir l’autorisation de modifier les données. Un utilisateur qui signe au nom d’un autre utilisateur n’a pas systématiquement besoin d’accéder aux données. Un exemple de ce type d’utilisateur est un superviseur qui signe les modifications d’un l’employé.

### <a name="electronic-signature-auditor"></a>Auditeur de signature électronique

L’auditeur de signature électronique revoit le journal de base de données et le journal de révision de la signature disponible dans le journal de base de données. Par défaut, un utilisateur qui appartient au rôle de sécurité **Responsable informatique** a l’autorisation d’auditer les signatures électroniques.

Si vous utilisez un rôle différent de **Responsable informatique**, vérifiez que les privilèges suivants sont affectés au rôle :

- Afficher les échecs de signature électronique
- Afficher le journal de base de données

## <a name="signing-documents-electronically"></a>Signature électronique de documents

### <a name="get-a-certificate"></a>Obtention d’un certificat

Avant de signer électroniquement des documents, vous devez demander un certificat.

> [!NOTE]
> Microsoft SQL Server utilise des fonctionnalités utilisées pour créer des certificats et activer la signature électronique. Aucun certificat ou infrastructure de clé publique supplémentaire n’est requis.

Lorsque vous demandez un certificat, une clé publique et une clé privée sont créées pour vous. La clé privée est chiffrée à l’aide d’un mot de passe que vous êtes le seul à connaître. Lors de la signature électronique d’un document, votre identité est vérifiée lorsque vous entrez le mot de passe.

Pour demander un certificat, sur la page **Options**, dans l’onglet **Comptes**, cliquez sur **Obtenir le certificat**.

Vous devez entrer et confirmer le mot de passe utilisé pour la signature. Le mot de passe permet de protéger votre clé privée et d’autoriser l’utilisation de votre certificat. Ce mot de passe n’est pas stocké dans la base de données et n’est pas disponible pour les autres utilisateurs, notamment l’administrateur.

Si vous oubliez le mot de passe lié à votre certificat, ce dernier doit être réinitialisé. Si vous réinitialisez le certificat, cette opération n’affecte pas les documents signés à l’aide du certificat précédent. Pour réinitialiser le certificat, sur la page **Options**, cliquez sur **Réinitialiser le certificat**.

### <a name="sign-a-document-electronically"></a>Signature électronique d’un document

La page **Signer le document** s’affiche lorsque vous apportez une modification nécessitant une signature électronique.

1. Sur la page **Signer le document**, cliquez sur l’onglet **Document** pour afficher les modifications apportées au document.
2. Sous l’onglet **Signature**, sélectionnez un code de motif.
3. Entrez un commentaire, si un commentaire est requis.
4. Si votre ID utilisateur ne s’affiche pas dans le champ **Signataire**, sélectionnez-le dans la liste.
5. Entrez votre emplacement, si cette information est obligatoire.
6. Cliquez sur **OK**.

### <a name="sign-for-another-users-changes"></a>Signature pour les modifications apportées par un autre utilisateur

Il est possible que vous souhaitiez qu’un utilisateur signe les modifications apportées par un autre utilisateur. Par exemple, un superviseur peut être demandé pour signer des modifications apportées par un employé à une nomenclature. Cette procédure permet de désigner un utilisateur qui signe pour un autre utilisateur.

> [!NOTE]
> Si un utilisateur signe la modification d’un autre utilisateur, la signature doit être fournie au niveau de la station de travail de l’utilisateur qui a fait la modification. L’utilisateur ne peut pas enregistrer la modification tant qu’aucune signature n’a été fournie.

Pour désigner des approbateurs, procédez comme suit :

1. Sur la page **Options**, sur l’onglet **Comptes**, cliquez sur **Désigner l’approbateur**.
2. Dans le champ **ID utilisateur approbateur**, sélectionnez l’ID de l’utilisateur qui doit signer les modifications d’un autre utilisateur.
3. Dans le champ **Signer pour l’ID utilisateur**, sélectionnez l’ID de l’utilisateur dont les modifications doivent être signées.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]