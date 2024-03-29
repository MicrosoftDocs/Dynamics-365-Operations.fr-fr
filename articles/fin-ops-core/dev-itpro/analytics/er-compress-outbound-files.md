---
title: Compresser des documents volumineux générés dans les états électroniques
description: Cet article explique comment compresser des documents volumineux générés par un format d’état électronique (ER).
author: kfend
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 58771
ms.assetid: ''
ms.search.form: EROperationDesigner, ERFormatDestinationTable
ms.openlocfilehash: ebdd84cdf39e21bf3d4721b1f1545b29fe38440b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273276"
---
# <a name="compress-large-documents-that-are-generated-in-electronic-reporting"></a>Compresser des documents volumineux générés dans les états électroniques 

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser la [Structure des états électroniques (ER)](general-electronic-reporting.md) pour configurer une solution qui extrait des données transactionnelles pour générer un document sortant. Ce document généré peut être assez volumineux. Lorsque ce type de document est généré, la mémoire du [Serveur d’objets d’application (AOS)](../dev-tools/access-instances.md#location-of-packages-source-code-and-other-aos-configurations) est utilisée pour le contenir. À un moment donné, le document doit ensuite être téléchargé à partir de votre application Microsoft Dynamics 365 Finance. Actuellement, la taille maximale d’un seul document généré dans ER est limitée à 2 gigaoctets (Go). En outre, Finance [limite](https://fix.lcs.dynamics.com/Issue/Details?kb=4569432&bugId=453907&dbType=3) actuellement la taille d’un fichier téléchargé à 1 Go. Par conséquent, vous devez configurer une solution ER qui réduit la probabilité de dépasser ces limitations et de recevoir une exception **Le flux était trop long** ou **Il y a eu un dépassement de capacité positif ou négatif dans l’opération arithmétique**.

Lorsque vous configurez une solution, vous pouvez ajuster votre format ER dans le concepteur d’opérations en ajoutant un élément racine du type **Dossier** pour compresser le contenu généré par l’un de ses éléments imbriqués. La compression fonctionne « juste à temps », afin que l’utilisation maximale de la mémoire et la taille du fichier téléchargé puissent être réduites.

> [!NOTE]
> La compression de fichiers utilise un pourcentage supplémentaire de l’utilisation du processeur.

Pour en savoir plus sur cette approche, réalisez l’exemple décrit dans cet article.

## <a name="example-compress-an-outbound-document"></a>Exemple : compresser un document sortant

Cet exemple montre comment un utilisateur affecté au rôle **Administrateur système** ou **Consultant fonctionnel des états électroniques** peut configurer un format ER pour compresser un document généré.

### <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les procédures décrites dans cet article, les étapes suivantes doivent être réalisées.

1. [Activer un fournisseur de configuration](er-defer-xml-element.md#activate-a-configuration-provider).
2. [Importer les exemples de configurations ER](er-defer-xml-element.md#import-the-sample-er-configurations).
3. [Examiner le format importé](er-defer-xml-element.md#review-the-imported-format).

> [!NOTE]
> Actuellement, la structure du format commence à partir de l’élément **État** du type **Fichier** et contient des éléments XML. Par conséquent, un document sortant sera généré au format XML et aucune compression ne sera utilisée.

### <a name="generate-an-er-format-to-get-an-uncompressed-document"></a>Générer un format ER pour obtenir un document non compressé

1. [Exécuter le format importé](er-defer-xml-element.md#run-the-imported-format).
2. Notez que la taille du document généré au format XML est de 3 kilo-octets (Ko).

    ![Aperçu du document sortant non compressé.](./media/er-compress-outbound-files1.png)

### <a name="modify-the-format-to-compress-the-generated-output"></a>Modifier le format pour compresser la sortie générée

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle d’apprentissage des éléments différés**.
3. Sélectionnez la configuration **Format d’apprentissage des éléments XML différés**.
4. Sélectionnez **Concepteur** pour modifier la structure du format.
5. Sur la page **Concepteur de formats**, dans l’onglet **Format**, sélectionnez **Ajouter racine** pour ajouter un élément de format racine.
6. Dans la boîte de dialogue **Ajouter**, sélectionnez **Commun\\Dossier**.
7. Cliquez sur **OK** pour confirmer l’ajout du nouvel élément racine.
8. Sélectionnez **Enregistrer**.

> [!NOTE]
> La structure du format commence à partir de l’élément du type **Dossier**. Cet élément générera une sortie sous forme de fichier compressé (zip). Lorsqu’un document généré par l’élément **État** est placé dans un fichier zip sortant, son contenu sera compressé pour réduire la taille du fichier sortant.

### <a name="generate-an-er-format-to-get-a-compressed-document"></a>Générer un format ER pour obtenir un document compressé

1. Dans la page **Concepteur de format**, sélectionnez **Exécuter**.
2. Téléchargez le fichier zip proposé par le navigateur Web et ouvrez-le pour examen.
3. Notez que la taille du document généré au format ZIP est de 1 Ko.

    > [!NOTE] 
    > Le taux de compression du fichier XML contenu dans ce fichier zip est de 87 %%. Le taux de compression dépend des données compressées.

    ![Aperçu du document sortant compressé.](./media/er-compress-outbound-files2.png)

> [!NOTE]
> Si la [destination](electronic-reporting-destinations.md) ER est configurée pour l’élément de format qui génère la sortie (l’élément **État** dans cet exemple), la compression de la sortie sera ignorée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états électroniques](general-electronic-reporting.md)

[Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)

[Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
