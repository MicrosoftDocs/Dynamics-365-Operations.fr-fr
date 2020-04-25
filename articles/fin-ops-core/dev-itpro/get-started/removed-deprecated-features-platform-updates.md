---
title: Fonctions de plateforme supprimées ou obsolètes
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer dans les mises à jour de plateforme des applications Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 0072ca507301fdb880f0595a06377ff01366ca20
ms.sourcegitcommit: cd8a28be0acf31c547db1b8f6703dd4b0f62940c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3260527"
---
# <a name="removed-or-deprecated-platform-features"></a>Fonctions de plateforme supprimées ou obsolètes

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer dans les mises à jour de plateforme des applications Finance and Operations.

- Une fonction *supprimée* n'est plus disponible dans le produit.
- Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification. 

> [!NOTE]
> Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Mises à jour de la plateforme pour la version 10.0.11 des applications Finance and Operations

### <a name="field-groups-containing-invalid-field-references"></a>Groupes de champ contenant des références de champs non valides

|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | Les groupes de champs dans les définitions de métadonnées de table peuvent contenir des références de champ qui ne sont pas valides. Si ces groupes de champ sont déployés, ils peuvent provoquer des erreurs d'exécution dans Financial Reporting et Microsoft SQL Server Reporting Services (SSRS). Platform Update 23 a introduit un *avertissement* de compilateur qui a permis de résoudre ce problème de métadonnées. Les mises à jour de la plateforme pour la version 10.0.11 des applications Finance and Operations classent ce problème en tant qu'*erreur* de compilateur.<p>Pour régler ce problème, procédez comme suit.</p><ol><li>Supprimez la référence de champ non valide de la définition du groupe de champs de table.</li><li>Recompilez.</li><li>Veillez à ce que toutes les erreurs soient corrigées.</li></ol> |
| **Remplacé par une autre fonctionnalité ?**   | Cette erreur du compilateur remplace définitivement l'avertissement du compilateur.  |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tout |
| **État**                         | **Obsolète :** L'avertissement du compilateur est désormais une erreur du compilateur dans les mises à jour de la plate-forme pour la version 10.0.11 des applications Finance and Operations. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licences ISV créées à l'aide de l'algorithme de hachage SHA1

|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | Le processus de création de licences de fournisseur de logiciels indépendant (ISV) a changé. Pour plus d'informations, voir [Licence de fournisseur de logiciels indépendant (ISV)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Remplacé par une autre fonctionnalité ?**   | Oui. Utilisez Windows PowerShell pour créer des licences. |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tout |
| **État**                         | <strong>Obsolète :</strong> Licences ISV créées à l'aide de l'algorithme de hachage SHA1. Cet algorithme dépendait des certificats créés à l'aide de l'utilitaire MakeCert, et cet utilitaire est obsolète.<p><strong>Obsolète :</strong> L'utilisation de SHA1 à des fins de sécurité ou de hachage. SHA1 cessera de fonctionner au début de 2021. Par conséquent, il ne devrait plus être utilisé.<p><strong>Supprimé :</strong> Prise en charge des demandes entrantes ou sortantes TLS (Transport Layer Security) 1.0 et TLS 1.1. |

## <a name="platform-update-32"></a>Update 32 de la plateforme

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>La boîte de dialogue de demande de modification du workflow n'inclut plus de liste déroulante de sélection de l'utilisateur
|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | Il s'agissait d'un problème de sécurité, car la demande de modification pouvait être envoyée à un utilisateur indésirable. Il s'agissait également d'un problème d'utilisation, car cela obligeait l'utilisateur à déterminer le créateur du workflow et à le sélectionner manuellement.  |
| **Remplacé par une autre fonctionnalité ?**   | Non |
| **Zones de produit affectées**         | Workflow |
| **Option de déploiement**              | Tous |
| **État**                         | La liste déroulante de sélection de l'utilisateur a été supprimée de la boîte de dialogue de demande de modification dans Platform update 32. Les demandes de modification seront automatiquement envoyées à l'expéditeur comme prévu. Pour plus d'informations sur cette fonctionnalité, consultez [Actions dans les processus d'approbation de workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Les liens de suivi intégrés ne sont plus pris en charge dans les documents paginés rendus par le service hébergé par le cloud 
|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | Les URL de navigation intégrées dans des documents rendus par le service peuvent contenir des données de l'entreprise sensibles. Nous supprimons le support des liens de suivi intégrés dans les documents par mesure de prudence pour protéger davantage les données des clients. Les utilisateurs bénéficieront de performances améliorées tout en produisant des documents interactivement suite à ce changement.  |
| **Remplacé par une autre fonctionnalité ?**   | N° |
| **Zones de produit affectées**         | Génération d'états |
| **Option de déploiement**              | Tout |
| **État**                         | Cette fonctionnalité est supprimée activement du service.<br><br>Le client moderne offre de nombreuses options pour produire des vues qui comprennent des liens générés automatiquement pour contribuer à la navigation dans l'application. Les documents paginés rendus par le service sont recommandés pour les communications externes qui sont envoyées par courrier électronique, archivées et imprimées pour les destinataires. Nous avons amélioré l'expérience de prévisualisation des documents directement dans le navigateur, ce qui offre un accès direct aux imprimantes locales. Pour plus d'informations, voir [Afficher un aperçu des documents PDF avec une visionneuse intégrée](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/preview-pdf-documents). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annonces précédentes sur les fonctions supprimées ou obsolètes
Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../migration-upgrade/deprecated-features.md).

