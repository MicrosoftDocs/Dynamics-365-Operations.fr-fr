---
title: Fonctions de plateforme supprimées ou obsolètes
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer dans les mises à jour de plateforme des applications Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 08/10/2020
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
ms.openlocfilehash: 8b26ad668b6cc15d759e10952c042acd5e85bdea
ms.sourcegitcommit: 4909e55529f03310d24b7e40d52751e24d35259b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2020
ms.locfileid: "3678220"
---
# <a name="removed-or-deprecated-platform-features"></a>Fonctions de plateforme supprimées ou obsolètes

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer dans les mises à jour de plateforme des applications Finance and Operations.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification. 

Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.

## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Mises à jour de la plateforme pour la version 10.0.13 des applications Finance and Operations

> [!NOTE]
> La version 10.0.13 est une version préliminaire. Le contenu et la fonctionnalité peuvent faire l’objet de modifications. Pour plus d’informations sur les préversions, voir [Disponibilité des mises à jour de service](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/public-preview-releases).

### <a name="custom-code-defined-in-ssrs-report-properties"></a>Code personnalisé défini dans les propriétés du rapport SSRS 

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | En général, le code personnalisé offre des avantages limités tout en nécessitant en même temps des ressources et des calculs importants pour être pris en charge. Le code personnalisé est principalement utilisé par les auteurs de rapports pour appeler des méthodes publiques à partir d’un assembly de code personnalisé. Cependant, le service hébergé dans le cloud ne prend pas en charge les références aux assemblys personnalisés pour les rapports SSRS. |
| **Remplacé par une autre fonctionnalité ?**   | Les auteurs de rapports peuvent choisir de continuer à référencer les API .NET publiques pour les opérations Math, Conversion et Format à partir de n’importe quelle expression de zone de texte. Pour plus d’informations, voir la rubrique [Ajouter du code à un rapport (SSRS)](https://docs.microsoft.comsql/reporting-services/report-design/add-code-to-a-report-ssrs?view=sql-server-ver15).  |
| **Zones de produit affectées**         | Sous-ensemble de conceptions de rapport d’application définies dans RDL qui contiennent du code personnalisé. |
| **Option de déploiement**              | Tous |
| **État**                         | Avec la version 10.0.13, le compilateur commencera à émettre un avertissement pour les instances où du code personnalisé est détecté dans une définition de rapport SSRS. Pour résoudre le problème, ouvrez la définition de conception de rapport et supprimez tous les artefacts de code personnalisé. Cet avertissement sera remplacé par une erreur du compilateur dans une future mise à jour.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Mise à niveau de trois bibliothèques de composants jQuery 

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Trois bibliothèques de composants jQuery sont en cours de mise à jour pour des correctifs de sécurité et pour maintenir l’actualité.   
| **Remplacé par une autre fonctionnalité ?**   | Les bibliothèques suivantes sont affectées : jQuery (vers la version 3.5.0 depuis la version 2.1.4), jQuery UI (vers la version 1.12.1 depuis la version 1.11.4), jQuery qTip (vers la version 3.0.3 depuis la version 2.2.1). Des conseils sur la migration ont été fournis en ligne par jQuery.  |
| **Zones de produit affectées**         | Contrôles extensibles, en particulier du code JavaScript personnalisé utilisant des API obsolètes ou supprimées |
| **Option de déploiement**              | Tout |
| **État**                         | Avec la version 10.0.13 /Platform update 37, les clients peuvent éventuellement passer aux dernières bibliothèques en activant la fonction "Mettre à niveau trois bibliothèques de composants jQuery". Le passage aux nouvelles bibliothèques sera obligatoire avec la version d’avril 2021 pour laisser le temps nécessaire à la migration des API concernées.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>Contrôle de grille existant/API forceLegacyGrid()

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le contrôle de grille existant est remplacé par le nouveau contrôle de grille. |
| **Remplacé par une autre fonctionnalité ?**   | Le [nouveau contrôle de grille](../..//fin-ops/get-started/grid-capabilities.md) |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tout |
| **État**                         | Dans la version 10.0.13, le nouveau contrôle de grille est généralement disponible et les clients peuvent éventuellement activer cette fonctionnalité. Le nouveau contrôle de grille deviendra obligatoire dans la version d’octobre 2021. Lorsque le nouveau contrôle de grille deviendra obligatoire, l’API **forceLegacyGrid()** ne sera plus disponible. |

### <a name="personalization-without-saved-views"></a>Personnalisation sans vues enregistrées 

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le sous-système de personnalisation a été remanié avec la fonction de vues enregistrées, afin qu’il ait de meilleures performances et offre des capacités supplémentaires. |
| **Remplacé par une autre fonctionnalité ?**   | Vues enregistrées |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tout |
| **État**                         | Dans la version 10.0.13/Platform Update 37, la fonctionnalité des vues enregistrées est généralement disponible et les clients peuvent éventuellement activer cette fonctionnalité. La fonctionnalité Vues enregistrées deviendra obligatoire dans la version d’octobre 2021. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Mises à jour de la plateforme pour la version 10.0.12 des applications Finance and Operations

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Extensions de formulaire de contrôle de grille ou de groupe contenant des références de champ non valides

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La propriété de groupe de données sur les contrôles de grille ou de groupe est utilisée pour afficher automatiquement tous les champs d’un groupe de champs. Un contrôle de grille ou de groupe ajouté par une extension peut contenir des champs qui ne sont plus définis sur le groupe de champs, ou il peut y avoir des champs manquants qui sont définis sur le groupe de champs. Cela peut entraîner un comportement incohérent lors de l’exécution. Les mises à jour de la plateforme pour la version 10.0.12 des applications Finance and Operations classent désormais ce problème en tant qu’*avertissement* de compilateur. Pour résoudre ce problème, ouvrez l’extension de formulaire et enregistrez-la.
| **Remplacé par une autre fonctionnalité ?**   | Cet avertissement du compilateur sera remplacé par une erreur du compilateur dans une future mise à jour. |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tout |
| **État**                         | Un avertissement de compilateur est introduit dans les mises à jour de la plateforme pour la version 10.0.12 des applications Finance and Operations. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Mises à jour de la plateforme pour la version 10.0.11 des applications Finance and Operations

### <a name="explicit-safe-lists-for-self-service-environments"></a>Liste sécurisée explicite pour les environnements en libre service

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le processus de déplacement de l’IP vers des listes sécurisées a changé. Le libre service ne prend plus en charge les listes sécurisées IP. |
| **Remplacé par une autre fonctionnalité ?**   | Pour plus d’informations, voir [Configuration de l’accès conditionnel Azure Active Directory](https://docs.microsoft.com/appcenter/general/configuring-aad-conditional-access).|
| **Zones de produit affectées**         | Sécurité |
| **Option de déploiement**              | Cloud |
| **État**                         | **Obsolète :** Cette fonctionnalité est totalement obsolète pour les déploiements en libre service. |

### <a name="visual-studio-2015"></a>Visual Studio2015

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Pour prendre en charge les dernières versions de Visual Studio, certaines modifications doivent être apportées aux extensions X++ pour Visual Studio. Ces modifications sont incompatibles avec Visual Studio 2015. |
| **Remplacé par une autre fonctionnalité ?**   | Visual Studio 2017 remplacera Visual Studio 2015 comme version déployée et requise. |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tout |
| **État**                         | Quand la disponibilité des nouvelles machines virtuelles (VM) avec Visual Studio 2017 sera annoncée, les machines virtuelles existantes avec seulement Visual Studio 2015 devront être redéployées lors du Plan de publication 1 de 2021. |

### <a name="field-groups-containing-invalid-field-references"></a>Groupes de champ contenant des références de champs non valides

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les groupes de champs dans les définitions de métadonnées de table peuvent contenir des références de champ qui ne sont pas valides. Si ces groupes de champ sont déployés, ils peuvent provoquer des erreurs d’exécution dans Financial Reporting et Microsoft SQL Server Reporting Services (SSRS). Platform Update 23 a introduit un *avertissement* de compilateur qui a permis de résoudre ce problème de métadonnées. Les mises à jour de la plateforme pour la version 10.0.11 des applications Finance and Operations classent ce problème en tant qu’*erreur* de compilateur.<p>Pour régler ce problème, procédez comme suit.</p><ol><li>Supprimez la référence de champ non valide de la définition du groupe de champs de table.</li><li>Recompilez.</li><li>Veillez à ce que toutes les erreurs soient corrigées.</li></ol> |
| **Remplacé par une autre fonctionnalité ?**   | Cette erreur du compilateur remplace définitivement l’avertissement du compilateur.  |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tout |
| **État**                         | **Obsolète :** L’avertissement du compilateur est une erreur du compilateur dans les mises à jour de la plateforme pour la version 10.0.11 des applications Finance and Operations. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licences ISV créées à l’aide de l’algorithme de hachage SHA1

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le processus de création de licences de fournisseur de logiciels indépendant (ISV) a changé. Pour plus d’informations, voir [Licence de fournisseur de logiciels indépendant (ISV)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Remplacé par une autre fonctionnalité ?**   | Oui. Utilisez Windows PowerShell pour créer des licences. |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tout |
| **État**                         | <strong>Obsolète :</strong> Licences ISV créées à l’aide de l’algorithme de hachage SHA1. Cet algorithme dépendait des certificats créés à l’aide de l’utilitaire MakeCert, et cet utilitaire est obsolète.<p><strong>Obsolète :</strong> L’utilisation de SHA1 à des fins de sécurité ou de hachage. SHA1 cessera de fonctionner au début de 2021. Par conséquent, il ne devrait plus être utilisé.<p><strong>Supprimé :</strong> Prise en charge des demandes entrantes ou sortantes TLS (Transport Layer Security) 1.0 et TLS 1.1. |

## <a name="platform-update-32"></a>Update 32 de la plateforme

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>La boîte de dialogue de demande de modification du workflow n’inclut plus de liste déroulante de sélection de l’utilisateur
|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Il s’agissait d’un problème de sécurité, car la demande de modification pouvait être envoyée à un utilisateur indésirable. Il s’agissait également d’un problème d’utilisation, car cela obligeait l’utilisateur à déterminer le créateur du workflow et à le sélectionner manuellement.  |
| **Remplacé par une autre fonctionnalité ?**   | Non |
| **Zones de produit affectées**         | Workflow |
| **Option de déploiement**              | Tous |
| **État**                         | La liste déroulante de sélection de l’utilisateur a été supprimée de la boîte de dialogue de demande de modification dans Platform update 32. Les demandes de modification seront automatiquement envoyées à l’expéditeur comme prévu. Pour plus d’informations sur cette fonctionnalité, consultez [Actions dans les processus d’approbation de workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Les liens de suivi intégrés ne sont plus pris en charge dans les documents paginés rendus par le service hébergé par le cloud 
|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les URL de navigation intégrées dans des documents rendus par le service peuvent contenir des données de l’entreprise sensibles. Nous supprimons le support des liens de suivi intégrés dans les documents par mesure de prudence pour protéger davantage les données des clients. Les utilisateurs bénéficieront de performances améliorées tout en produisant des documents interactivement suite à ce changement.  |
| **Remplacé par une autre fonctionnalité ?**   | N° |
| **Zones de produit affectées**         | Génération d’états |
| **Option de déploiement**              | Tout |
| **État**                         | Cette fonctionnalité est supprimée activement du service.<br><br>Le client moderne offre de nombreuses options pour produire des vues qui comprennent des liens générés automatiquement pour contribuer à la navigation dans l’application. Les documents paginés rendus par le service sont recommandés pour les communications externes qui sont envoyées par courrier électronique, archivées et imprimées pour les destinataires. Nous avons amélioré l’expérience de prévisualisation des documents directement dans le navigateur, ce qui offre un accès direct aux imprimantes locales. Pour plus d’informations, voir [Afficher un aperçu des documents PDF avec une visionneuse intégrée](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/preview-pdf-documents). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annonces précédentes sur les fonctions supprimées ou obsolètes
Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../migration-upgrade/deprecated-features.md).

