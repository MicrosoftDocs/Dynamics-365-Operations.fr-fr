---
title: Extensibilité de l’énumération de base Gender
description: Cet article donne un aperçu de l’extensibilité de l’énumération (enum) de base Gender.
author: twheeloc
ms.date: 05/23/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom:
- "51941"
- intro-internal
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61a80c16d24d8fda264340d79ed393db3f635908
ms.sourcegitcommit: 1717ff6af1879c6f3a8360936c42ecf55f86acd0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2022
ms.locfileid: "9749313"
---
# <a name="gender-base-enum-extensibility"></a>Extensibilité de l’énumération de base Gender

L’énumération (enum) **Gender**  est maintenant extensible. Cet article décrit les modifications que vous devez apporter à la base de code si vous envisagez d’étendre l’énumération **Gender**.

## <a name="gender-vs-hcmpersongender"></a>Gender et HcmPersonGender

Il existe deux énumérations pour les valeurs de genre :

- **Gender** (plateforme d’applications)
- **HcmPersonGender** (PersonnelManagement)

L’énumération **Gender** est utilisée dans Microsoft Dynamics 365 Finance, tandis que **HcmPersonGender** est spécifique à la fonctionnalité de gestion du capital humain (HCM). Si vous utilisez la fonctionnalité HCM et que vous apportez des modifications à l’énumération **Gender**, vous devriez envisager d’apporter les mêmes modifications à **HcmPersonGender**. Par exemple, si vous ajoutez **Transgender** à l’énumération **Gender**, ajoutez aussi **Transgender** à l’énumération **HcmPersonGender**.

## <a name="hcmpersongendertranformutil-class"></a>HcmPersonGenderTranformUtil (classe)

Une nouvelle classe **HcmPersonGenderTranformUtil** a été créée pour permettre la traduction entre les deux énumérateurs de base. Dans cette classe, il existe deux méthodes : **convertGenderToHcmPersonGender** et **convertHcmPersonGenderToGender**. Vous devez créer une extension en utilisant la classe **Chaîne de commande** ou les **gestionnaires d’événements** et étendre les deux méthodes pour mapper les nouvelles valeurs ajoutées à l’une des énumérations de base.

## <a name="payrollstatewagetaxprepdp-class"></a>PayrollStateWageTaxPrepDP (classe)

**PayrollStateWageTaxPrepDP** est la classe de fournisseur de données pour le rapport **Préparation de la taxe publique sur les salaires** de SQL Server Reporting Services (SSRS). Pour les États-Unis, trois valeurs sont disponibles : **Masculin**, **Féminin** et **Non spécifié**. Dans la méthode **populatePayrollStateWageTaxPrepTmp**, une instruction switch permet de mapper la valeur de l’énumération **HcmPersonGender** sur l’un des trois champs : **IsMale**, **IsFemale** ou **IsUnspecifiedGender**. La valeur par défaut de l’instruction switch est **IsUnspecifiedGender**. Si vous ajoutez des valeurs à l’énumération **HcmPersonGender** pour mapper différemment, vous devez créer une extension en utilisant la classe **Chaîne de commande** sur la méthode **populatePayrollStateWageTaxPrepTmp** pour modifier la valeur si nécessaire.

## <a name="smmoutlooksync_contact-class"></a>smmOutlookSync_Contact (classe)

La classe d’intégration **smmOutlookSync_Contact** relie des valeurs depuis et vers **Outlook** et **Personnes à contacter**. **Outlook** prend en charge trois valeurs : **Masculin**, **Féminin** et **Non spécifié**. La classe a deux méthodes pour vous aider à mapper **Genders** à **OutlookGenders**. La méthode par défaut est **NonSpecific/UnSpecified**. Si vous créez des valeurs supplémentaires pour l’énumération **Gender**, vous devez créer une extension en utilisant la classe **Chaîne de commande** sur les deux méthodes et mapper au besoin.
