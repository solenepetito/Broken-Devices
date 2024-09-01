Explications et informations sur les dossiers : 

1 ) Organisation des fichiers : 
  - Les dossiers S... présentent le travail effectué chaque semaine depuis le début du stage
  - Les dossiers S1 et S2 sont avant tout centré sur le nettoyage et le formattage de la base de données
  - Les dossiers S3 à S12 sont centrés sur de l'analyse de données pure et inclut aussi de la datavisualisation
  - Le dossier synthèse regroupe plusieurs dossiers regroupant, pour chaque module du questionnaire, des tableaux de données récapitulant chaque question du module en question
  - Tous ces dossiers comprennent un fichier.RMD (fichier comprenant le code entier), un fichier.html (fichier de présentation soigné) et un dossier data regroupant les données brutes et modifiés du questionnaire

2 ) Version de R-studio et des librairies utlisées : 
  - R-studio : RStudio 2023.06.2 
  - Librairies : Les librairies elles datent de la même version et sont mises à jour régulièrement

3 ) Comment exporter un graphe en SVG su R : 

Pour exporter un graphique en format SVG (Scalable Vector Graphics) avec R, vous pouvez utiliser la fonction svg() du package de base grDevices. Voici les étapes à suivre, avec un exemple de code : 

  - Ouvrir le dispositif graphique SVG : Utilisez la fonction svg() pour indiquer que vous souhaitez créer un fichier SVG. Vous devez spécifier le nom du fichier ainsi que les dimensions (largeur et hauteur) du graphique.

  - Créer votre graphique : Utilisez les fonctions de ggplot2 ou les fonctions de base de R pour créer le graphique que vous souhaitez exporter.

  - Fermer le dispositif graphique : Utilisez dev.off() pour fermer le dispositif graphique et finaliser la création du fichier SVG.

Exemple de code : 

library(ggplot2)

# Exemple de données
df <- data.frame(
  x = 1:10,
  y = c(2, 5, 7, 8, 9, 12, 15, 16, 18, 20)
)

# Ouvrir le dispositif SVG
svg("mon_graphe.svg", width = 8, height = 6)  # Nom du fichier et dimensions

# Créer un graphique avec ggplot2
ggplot(df, aes(x = x, y = y)) +
  geom_line(color = "blue") +      # Ajouter une ligne
  geom_point(color = "red", size = 3) +  # Ajouter des points
  labs(title = "Exemple de Graphique", x = "X-Axis", y = "Y-Axis") +
  theme_minimal()

# Fermer le dispositif SVG
dev.off()





