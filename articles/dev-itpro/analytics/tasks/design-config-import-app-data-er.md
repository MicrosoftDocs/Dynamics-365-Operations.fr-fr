---
title: Créer des configurations d'états électroniques pour analyser des documents entrants
description: Cette procédure décrit comment créer des configurations d'états électroniques pour analyser un document électronique entrant.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 23004930d2377a3d647435b53b6809cd500f44ac
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741353"
---
# <a name="design-er-configurations-to-parse-incoming-documents"></a>Créer des configurations d'états électroniques pour analyser des documents entrants

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment créer des configurations d'états électroniques pour analyser un document électronique entrant. Dans cette procédure, vous importerez les configurations ER requises qui ont été créées pour la société fictive, Litware, Inc., puis les utiliserez pour l'analyse des documents électroniques entrants. Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Créer un fournisseur de configuration et le marquer comme actif ».

Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté. 

Ces étapes peuvent être effectuées à l'aide d'un ensemble de données quelconque. Avant de commencer, téléchargez et enregistrer les fichiers répertoriés dans la rubrique « Analyser les documents entrants pour mettre à jour les données d'application » (https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/parse-incoming-electronic-documents). Les fichiers sont : Modèle EFSTA.xml, Format EFSTA.xml, Réponse1.xml, Réponse2.xml, Réponse3.xml, Réponse4.xml.

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif. Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure, « Créer un fournisseur de configuration et le marquer comme actif ».  
2. Cliquez sur Configurations des états.
    * Le scénario suivant est utilisé pour afficher les fonctions d'analyse des documents électroniques entrants au format XML : l'application ERP (Dynamics 365 for Finance and Operations) demande des données au service Web (tell que le service fiscal EFESTA http://efsta.org/) et analyse les réponses entrantes pour mettre à jour les données d'application en conséquence. Pour optimiser l'analyse, un format ER unique est utilisé nonobstant la structure différente des documents entrants prévus au format XML.   

## <a name="import-and-review-er-configurations"></a>Importer et examiner les configurations ER
Importez la configuration du modèle ER contenant l'exemple de modèle de données conçu pour stocker les détails du fichier entrant.  
1. Cliquez sur Échanger.
2. Cliquez sur Charger depuis le fichier XML.
    * Cliquez sur Parcourir et sélectionnez le fichier Modèle EFSTA.xml.  
3. Cliquez sur OK.
4. Dans l'arborescence, sélectionnez « Modèle EFSTA ».
5. Cliquez sur Concepteur.
    * Examinez la structure du modèle de données importé. Notez que l'énumération enumType est définie pour reconnaître les types suivants de réponses de service : obtenir la confirmation de l'envoi de la transaction, obtenir des informations sur la dernière transaction envoyée et reconnaître les types de réponse non pris en charge.   
6. Dans l'arborescence, développez « Réponse ».
    * Notez que l'élément racine « Réponse » est défini pour spécifier le type de données à extraire d'une réponse de service prise en charge pour mettre à jour les données d'application en conséquence.   
7. Fermez la page.
    * Vous importerez la configuration du format ER qui spécifie comment les documents entrants sont analysés pour stocker les données dans le modèle de données ER.   
8. Cliquez sur Échanger.
9. Cliquez sur Charger depuis le fichier XML.
    * Cliquez sur Parcourir et sélectionnez le fichier Format EFSTA.xml.  
10. Cliquez sur OK.
11. Dans l'arborescence, développez « Modèle EFSTA ».
12. Dans l'arborescence, sélectionnez « Modèle EFSTA\Format EFSTA ».
13. Cliquez sur Concepteur.
14. Cliquez sur Développer/réduire.
    * Notez que l'élément de format CASE est utilisé comme racine et contient trois éléments FILE imbriqués, ce qui signifie que ce format a été conçu pour analyser les fichiers entrants de plusieurs formats.  
15. Dans l'arborescence, sélectionnez « Réponses\Exécution de la transaction\TraC ».
    * Notez que la réponse sur la transaction envoyée commence à partir de l'élément racine « TraC ».   
16. Dans l'arborescence, sélectionnez « Réponses\Dernière demande de transaction\Tra ».
    * Notez que la réponse sur la dernière transaction envoyée commence à partir de l'élément racine « Tra ».   
17. Dans l'arborescence, sélectionnez « Réponses\Réponse inattendue\Texte ».
    * Le troisième élément FILE avec l'élément TEXT imbriqué a été ajouté pour reconnaître les autres types de réponses qui diffèrent de celles mentionnées ci-dessus.   
18. Cliquez sur Mettre en correspondance vers le modèle.
    * Cette mise en correspondance de modèle contient la définition du flux de données pour stocker les détails du document entrant analysé à l'aide des éléments du modèle de données.  
19. Cliquez sur Concepteur.
20. Dans l'arborescence, développez « format ».
21. Dans l'arborescence, développez « format\Réponses : Incident (Réponses) ».
    * Examinez la structure de la source de données « format ». Notez que les trois types de réponse sont proposés séparément.   
22. Dans l'arborescence, sélectionnez « format\Réponses : Incident (Réponses)\aType ».
    * L'élément de source de données « aType » a été ajouté pour indiquer le type de réponse et est lié à l'élément de modèle de données « Type ».  
23. Cliquez sur l'onglet Validations.
24. Dans l'arborescence, sélectionnez « Type = format.Responses.aType ».
    * Notez que la validation ER a été configurée pour informer l'utilisateur de la situation lorsque la structure de réponse ne correspond pas à la confirmation d'envoi de la transaction ou aux informations sur la dernière transaction envoyée (type de réponse non pris en charge).   
25. Fermez la page.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>Exécuter la mise en correspondance des modèles du format ER configuré pour analyser les fichiers entrants
Vous exécuterez la mise en correspondance de modèle créée aux fins de test pour voir comment le format ER configuré analysera les réponses de service entrantes. Cette étape utilise différents fichiers XML pour simuler différents types de réponses de service Web.   
1. Ouvrez le fichier Réponse1.xml dans un lecteur xml, tel qu'un navigateur Web. Notez que ce fichier contient les détails de confirmation sur la transaction terminée (« TraC » est l'élément racine).   
2. Cliquez sur Exécuter.
    * Cliquez sur Parcourir et sélectionnez le fichier Réponse1.xml.  
3. Cliquez sur OK.
    * Examinez la sortie générée. Notez que le type de réponse a été correctement reconnu et analysé (ERModelEnumDataSourceHandler#EFSTA model#enumType#C indique que la transaction est terminée).   
    * Ouvrez le fichier Réponse2.xml dans un lecteur XML. Notez que ce fichier contient les informations sur la dernière transaction envoyée (« Tra » est l'élément racine).   
4. Cliquez sur Exécuter.
    * Cliquez sur Parcourir et sélectionnez le fichier Réponse2.xml.  
5. Cliquez sur OK.
    * Examinez la sortie générée. Notez que le type de réponse a été correctement reconnu et analysé (ERModelEnumDataSourceHandler#EFSTA model#enumType#R indique que le système a été redémarré).   
    * Ouvrez le fichier Réponse3.xml dans un lecteur XML. Notez que ce fichier commence à partir de l'élément racine TraZ et que cette structure n'est pas configurée à l'aide du format ER.   
6. Cliquez sur Exécuter.
    * Cliquez sur Parcourir et sélectionnez le fichier Réponse3.xml.  
7. Cliquez sur OK.
    * Examinez la sortie générée. Notez que le type de réponse a été correctement reconnu comme non pris en charge (ERModelEnumDataSourceHandler#EFSTA model#enumType#U). Le message correspondant a été placé dans la fenêtre Informations (en fonction du paramètre de validation ER), et la majeure partie du modèle de données n'a pas été renseignée.   
    * Ouvrez le fichier Réponse4.xml dans un lecteur XML. Notez que la structure de ce fichier est presque identique au fichier Réponse1.xml analysé avec succès, à l'exception de la séquence d'éléments imbriqués de l'élément racine « TraC ».   
8. Cliquez sur Exécuter.
    * Cliquez sur Parcourir et sélectionnez le fichier Réponse4.xml.  
9. Cliquez sur OK.
    * Examinez la sortie générée. Notez que le type de réponse a été correctement reconnu comme non pris en charge (ERModelEnumDataSourceHandler#EFSTA model#enumType#U)). Le message correspondant a été placé dans la fenêtre Informations, et la majeure partie du modèle de données n'a pas été renseignée. En effet, le paramètre actuel de ce format ER utilise une certaine séquence d'éléments imbriqués de l'élément racine du fichier entrant.   
10. Fermez la page.
11. Dans l'arborescence, sélectionnez « Réponses\Exécution de la transaction\TraC ».
12. Dans le champ Ordre d'analyse des éléments imbriqués, sélectionnez « N'importe lequel/laquelle ».
    * Sélectionnez N'importe lequel/laquelle dans le champ « Ordre d'analyse des éléments imbriqués » pour autoriser toute séquence d'éléments imbriqués pour cet élément XML racine.  
13. Cliquez sur Enregistrer.
14. Cliquez sur Mettre en correspondance vers le modèle.
15. Cliquez sur Exécuter.
    * Cliquez sur Parcourir et sélectionnez le fichier Réponse4.xml.  
16. Cliquez sur OK.
    * Examinez la sortie générée. Notez que le type de réponse a été correctement reconnu comme identique au fichier Réponse1.xml.  

