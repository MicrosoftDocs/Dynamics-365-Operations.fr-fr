---
title: Paramétrage des groupes de validation dans la comptabilité de la taxe
description: La taxe est calculée et validée dans les comptes principaux spécifiés dans les groupes de validation dans la comptabilité.
author: twheeloc
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAccountGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c353a4fbed3af0cd7477c9a1543baaf523da6f11
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735753"
---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a>Paramétrage des groupes de validation dans la comptabilité de la taxe

[!include [banner](../../includes/banner.md)]

La taxe est calculée et validée dans les comptes principaux spécifiés dans les groupes de validation dans la comptabilité. Les groupes de validation dans la comptabilité sont associés à chaque code taxe. Vous pouvez paramétrer des groupes de validation dans la comptabilité individuels pour chaque code taxe ; vous pouvez utiliser un groupe de validations dans la comptabilité pour tous les codes taxe ou vous pouvez affecter plusieurs groupes de validations dans la comptabilité aux codes taxe. La société fictive DEMF sert d’exemple dans cet enregistrement. 

1. Accédez à **Volet de navigation > Modules > Taxe > Paramétrage > Taxe > Groupes de validations dans la comptabilité**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Groupe de validations dans la comptabilité**, tapez une valeur.
4. Tapez une valeur dans le champ **Description**.
5. Dans le champ **Taxe collectée**, sélectionnez le compte principal pour les taxes sortantes collectées par l’administration fiscale. Les taxes sont collectées au nom de l’administration fiscale lorsque vous vendez des biens et des services soumis à la taxe.  
6. Dans le champ **Taxe déductible**, sélectionnez le compte principal pour les taxes entrantes transmises par l’administration fiscale. Les fournisseurs collectent des taxes au nom de l’administration fiscale lorsque vous achetez des biens et des services soumis à la taxe. Ce champ n’est pas disponible si l’option Appliquer les règles de taxe est sélectionnée dans la page **Paramètres de comptabilité**. Au lieu de cela, les taxes payées aux fournisseurs sont débitées du même compte que l’achat.   
7. Dans le champ **Dépenses de taxe d’utilisation**, sélectionnez le compte principal pour valider les taxes d’utilisation déductibles qui ne sont pas réclamées ou signalées à l’administration fiscale par les fournisseurs dans le cadre de la taxe GST/HST au preneur de l’UE. L’option **Taxe d’utilisation** doit être activée pour le **code Taxe** dans le **groupe de taxe** utilisé dans la transaction. Ce champ n’est pas disponible si l’option **Appliquer les règles de taxe** est sélectionnée dans la page **Paramètres de comptabilité**.   
8. Dans le champ **Taxe d’utilisation due**, sélectionnez le compte principal pour valider les taxes d’utilisation sortantes collectées par l’administration fiscale. L’option **Taxe d’utilisation** doit être activée dans le **code Taxe** dans le **groupe de taxe** pour valider la **taxe d’utilisation**. Si l’option **Appliquer les règles de taxe** est sélectionnée sur la page **Paramètres de comptabilité**, la contrepartie est validée dans le compte de dépenses de la transaction.   
9. Dans le champ **Compte de règlement**, sélectionnez le compte principal qui contient le solde net des comptes généraux spécifiés dans les champs **Taxe d’utilisation due** et **Taxe déductible**. Le solde est créé lorsque la tâche Régler et valider la taxe est exécutée.  Si l’administration fiscale pour la période de règlement est associée à un compte fournisseur, le solde est validé sur le compte fournisseur à la place.
10. Dans le champ **Fournisseur – Escompte de règlement**, sélectionnez le compte principal pour valider l’escompte de règlement pour les codes taxe associés à ce groupe de validation dans la comptabilité. Ceci est facultatif et si aucun compte n’est entré, le compte principal des **codes escompte de règlement** est alors utilisé. Il peut être utile d’utiliser différents comptes par **groupe de validation dans la comptabilité** si vous utilisez l’option Contrepasser la taxe sur l’escompte de règlement dans les groupes de taxe.  
11. Dans le champ **Client – Escompte de règlement**, sélectionnez le compte principal pour valider l’escompte de règlement pour les **codes taxe** associés à ce **groupe de validation dans la comptabilité**. Ceci est facultatif et si aucun compte n’est entré, le compte principal des **codes escompte de règlement** est alors utilisé. Il peut être utile d’utiliser différents comptes par **groupe de validation dans la comptabilité** si vous utilisez l’option Contrepasser la taxe sur l’escompte de règlement dans les **groupes de taxe**.  
12. Cliquez sur **Enregistrer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
