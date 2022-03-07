---
title: Dispositions de l’écran de données de démonstration dans Modern POS (MPOS) et le PDV Cloud
description: Cette rubrique fournit des informations sur les mises en page d’écran incluses dans le jeu de données de démonstration pour les expériences de point de vente (PDV) dans Dynamics 365 Commerce.
author: josaw1
ms.date: 10/05/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: c141325580d698cccc7d186496a0902913961d47764b93fa73c64c3eddf6e791
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761660"
---
# <a name="demo-data-screen-layouts-in-modern-pos-mpos-and-cloud-pos"></a>Dispositions de l’écran de données de démonstration dans Modern POS (MPOS) et le PDV Cloud

[!include [banner](includes/banner.md)]

Cette rubrique fournit des informations sur les mises en page d’écran incluses dans le jeu de données de démonstration pour les expériences de point de vente (PDV) dans Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Les exemple de mises en page d’écran qui sont inclus dans les données de démonstration de Commerce fournissent le contenu qui est optimisé pour différents segments de la vente au détail, rôles de travailleur du magasin et périphériques. Une mise en page unique peut contenir plusieurs tailles de mise en page et des combinaisons de groupes de boutons afin de garantir la couverture à mesure que les travailleurs de magasin passent entre les périphériques et les stations. Cette rubrique décrit les différences entre ces mises en page, les opérations qu’elles fournissent, et les expériences générales qu’elles constituent.

![Mises en page des données de démonstration entre périphériques.](../commerce/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a>Anatomie d’un ID mise en page de l’écran

Pour rechercher des mises en page d’écran, accédez à **Commerce et vente au détail** \> **Paramétrage de canal** \> **Paramétrage PDV** \> **PDV** \> **Mises en page de l’écran**.

![Page Mises en page de l’écran.](../commerce/media/demo-screen-layouts-fig-2-1.png)

Les ID mise en page de l’écran peuvent se composer de 10 caractères au maximum. L’ID est une chaîne composée de trois éléments d’informations, dans cet ordre :

1. Société
2. Version de la mise en page
3. Personnage

### <a name="company"></a>Société

| Lettre | Société         |
|--------|-----------------|
| A      | Adventure Works |
| V      | Fabrikam        |
| C      | Contoso         |

### <a name="layout-version"></a>Version de la mise en page

| Numéro de version | Description                                                                                 |
|----------------|--------------------------------------------------------------------------------------------|
| 3              | La version de base qui prend en charge plusieurs tailles d’écran pour différents périphériques et proportions |
| 3.1            | La version de base qui dispose du support technique supplémentaire du volet **Produits recommandés**        |
| 4              | La version étendue pour la disposition mise à jour de Fabrikam étendue                                  |

### <a name="persona"></a>Personnage

| Abréviation | Personnage       | Sommaire |
|--------------|---------------|----------|
| CSH          | Caissier       | Les mises en page du caissier incluent toutes les opérations liées aux transactions, telles que les commandes client, les retours, les remises, les annulations, et les cartes cadeaux. Ces mises en page incluent également les tâches quotidiennes de la gestion des stocks, notamment les vérifications des prix de vente, les recherches de stock, et les inventaires. La gestion d’équipe de base est également fournie pour les montants de début, l’interruption des équipes, et le pointage. |
| MGR          | Directeur de magasin | Les mises en page du directeur de magasin incluent toutes les opérations liées aux transactions se trouvant dans les mises en page du caissier, ainsi que les remplacements de taxe. Ces mises en page incluent également les tâches quotidiennes de la gestion des stocks, notamment les vérifications des prix de vente, les recherches de stock, et les inventaires. La gestion d’équipe est fournie pour commencer, interrompre, et clôturer les équipes. En outre, les mises en page incluent des opérations de caisse pour les entrées, les annulations, les comptages de caisse, et les mises en coffre-fort et remises en banque. Enfin, ces mises en page incluent l’accès aux états des performances, et activent l’impression des X et Z de caisse. |
| STK          | Employé au stock   | Les mises en page de l’employé au stock sont optimisées pour la gestion des stocks. Elles comprennent l’accès aux tâches quotidiennes pour les vérifications des prix de vente, les recherches de stock, les prélèvements et réceptions, les inventaires et le démontage de kit. Ces mises en page fournissent également des opérations de base pour l’équipe concernant le pointage et l’interruption des équipes. Bien que ces mises en page soient prévues principalement pour les tâches des services administratifs, les employés au stock disposent des mêmes opérations que les caissiers pour les écrans de transactions. |

### <a name="example-layout"></a>Exemple de mise en page

Voici un exemple d’ID mise en page de l’écran pour la société Fabrikam, version 4 de mise en page, et personna Directeur de magasin :

F4MGR

L’illustration suivante présente un exemple de l’écran de bienvenue d’un directeur de magasin de Fabrikam.

![Écran de bienvenue pour le directeur de magasin de Fabrikam.](../commerce/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a>Tailles de mise en page

### <a name="full-vs-compact-layouts"></a>Mises en page complètes ou compactes

Une mise en page de l’écran peut disposer de configurations pour les périphériques complets et les périphériques compacts. Par conséquent, une disposition d’écran unique peut être affectée à un utilisateur qui fonctionnera selon différentes tailles et facteurs de forme au sein du magasin.

- **Modern POS - Complet** – En général, les mises en page complètes sont utilisées pour des écrans plus grands tels que des moniteurs d’ordinateur de bureau ou des tablettes. Les utilisateurs peuvent sélectionner les éléments d’IU inclus dans la mise en page, spécifier la taille et l’emplacement de ces éléments, et configurer leurs propriétés détaillées. Les mises en page complètes prennent en charge les configurations Portrait et Paysage.
- **Modern POS - Compact** – En général, les mises en page compactes sont recommandées pour les téléphones ou les petites tablettes. Les possibilités de conception sont limitées pour les périphériques compacts. Les utilisateurs peuvent configurer les colonnes et les champs pour le volet Ticket de caisse et le volet Totaux.

### <a name="screen-resolutions-that-are-provided"></a>Résolutions d’écran qui sont fournies

Le tableau suivant indique les tailles de mise en page autorisées pour les résolutions d’écran habituelles.

| Type de mise en page | Résolution | Proportions | Affichage cible          |
|-------------|------------|--------------|-------------------------|
| Compacter\*   | 480 x 853  | 16:9         | Téléphones                  |
| Complet        | 1024 × 768 | 4:3          | Tablettes                 |
| Complet\*      | 1280 × 720 | 16:9         | Tablettes                 |
| Complet        | 1366 × 768 | 16:9         | Tablettes, écrans plus grands |
| Complet        | 1440 × 960 | 3:2          | Tablettes, écrans plus grands |
| Complet\*      | 1536 × 864 | 16:9         | Tablettes, écrans plus grands |

\* Ces tailles de mise en page supplémentaires sont disponibles uniquement dans les mises en page Adventure Works et Fabrikam.

> [!TIP]
> Le PDV sélectionne automatiquement les tailles de mise en page, selon la taille la plus proche disponible pour la résolution d’écran de la fenêtre d’application active. Pour trouver l’ID de mise en page de l’écran et la résolution de mise en page qui sont actuellement utilisés, le Modern POS (MPOS) ou Retail Cloud POS (CPOS), ouvrez la page **Paramètres**, et consultez la section **Informations de session**. Vous pouvez également afficher la résolution réelle de la fenêtre pour votre trame d’application ou de navigateur actuelle. Une fois que vous disposez de ces informations, vous pouvez trouver la source du contenu de la mise en page en accédant à **Paramétrage de canal** \> **Paramétrage POS** \> **PDV** \> **Mises en page de l’écran**.

![Mises en page de l’écran et résolutions/tailles de mise en page dans Commerce et PDV.](../commerce/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a>Sociétés et marques

Chaque société fictive est spécifique à un segment de vente au détail différent et inclut des catalogues de produits qui sont adaptés au marché de la société. Chaque société possède une marque visuelle unique et accompagne ses produits. Les éléments de stratégie de marque incluent la couleur d’accentuation, les thèmes Clair ou Foncé, et des photographies qui fournissent des expériences réalistes.

### <a name="company-segment-and-visual-characteristics"></a>Segment de société et spécifications visuelles

| Société         | Entrepôt | Segment        | Accentuation | Thème |
|-----------------|----------|----------------|--------|-------|
| Adventure Works | Seattle  | Articles de sport | Bleu   | Sombre  |
| Fabrikam        | Saint-Nazaire  | Mode        | Vert  | Clair |
| Contoso         | Boston   | Électronique    | Rouge    | Sombre  |

> [!NOTE]
> Adventure Works et Fabrikam sont les deux marques principales. Contoso est disponible, mais toutes les mises en page n’ont pas été livrées.

Les exemples d’illustrations suivantes présentent la page d’accueil et la page de transaction des trois sociétés fictives.

### <a name="adventure-works"></a>Adventure Works

![Page d’accueil de données de démonstration pour Adventure Works.](../commerce/media/demo-screen-layouts-fig-4-1a.png)

![Page de transaction de données de démonstration pour Adventure Works.](../commerce/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a>Fabrikam

![Page d’accueil de données de démonstration pour Fabrikam.](../commerce/media/demo-screen-layouts-fig-4-2a.png)

![Page de transaction de données de démonstration pour Fabrikam.](../commerce/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a>Contoso

![Mises en page de données de démonstration pour Contoso.](../commerce/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a>Matrice de connexion de l’utilisateur

Différentes mises en page de l’écran ont été fournies aux utilisateurs. En utilisant la table suivante, vous devriez pouvoir accéder à tous ces écrans. Il vous suffit de vous connecter à l’aide d’un ID opérateur approprié.

| Société         | ID mise en page de l’écran | Personnage       | ID opérateurs           |
|-----------------|------------------|---------------|------------------------|
| Adventure Works | A3MGR            | Directeur de magasin | 000154, 000137, 000073 |
| Adventure Works | A3CSH            | Caissier       | 000150, 000175, 000165 |
| Adventure Works | A3STK            | Employé au stock   | 000155, 000181, 000152 |
| Fabrikam        | F4MGR            | Directeur de magasin | 000160, 000713         |
| Fabrikam        | F3CSH            | Caissier       | 000161, 000113, 000114 |
| Fabrikam        | F3STK            | Employé au stock   | 000164, 000112, 000123 |
| Contoso         | C3MGR            | Directeur de magasin | 000100, 000111         |
| Contoso         | C3CSH            | Caissier       | 000110, 000120         |
| Contoso         | Non applicable   | Employé au stock   | Non applicable         |

> [!TIP]
> Pour de meilleurs résultats, activez un registre dans l’emplacement du magasin correspondant, puis définissez la société sur la société du personnage que vous comptez utiliser lorsque vous vous connecterez. Ainsi, cela vous garantit que le profil visuel et les images de marque sont alignés tout au long de l’expérience. Par exemple, si vous souhaitez consulter une mise en page de Fabrikam pour un caissier, vous devez activer une caisse enregistreuse dans le magasin de Houston.

<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail and Commerce \> Channel setup \> POS setup \> POS \> Images**. -->

<!-- ![Images in Dynamics 365 Commerce.](../commerce/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../commerce/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->


[!INCLUDE[footer-include](../includes/footer-banner.md)]