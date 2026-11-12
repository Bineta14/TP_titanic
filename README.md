# TP_titanic
email: bineta.faye@chru-strasbourg.fr

TP du cours d'analyse reproductible

Ici la correction du tp ;)

# Génération de token personnel

Voici les étapes :

**Aller sur votre utilisateur puis sur settings**

<img width="303" height="450" alt="image" src="https://github.com/user-attachments/assets/5e982393-93dc-4080-a35c-6c4f4f23be57" />

**Puis tout en bas à droite cliquez sur Developer Settings**

<img width="886" height="290" alt="image" src="https://github.com/user-attachments/assets/77713f8d-327b-4ab9-8085-5a43ce63f0b8" />

**Puis cliquez sur  Generate New Token**

Puis copier le token généré et garder le quelque part (il sera à coller pendant le premier push ou clone à la place du password)

**Une fois le token généré, on peut l'éditer pour donner les bons accès(read, write) au repertoire concerné**

<img width="899" height="428" alt="image" src="https://github.com/user-attachments/assets/ac78a01a-69b8-4735-bd93-d4ce7a21da54" />




#' Calcul du taux de survie en fonction de la variable donnée en entrée
#' 
#' @author Bineta
#' @param data jeuu de données
#' @param variable colonne donnée
#' 
#' @examples 
#' taux_survie(data,'passengerClass')
#' taux_survie(data,'sex')
#' 
#' @export






taux_survie <- function(data,variable) {
  library(dplyr)
  data %>%
    group_by(data[,variable]) %>%
    summarize(TauxSurvie = sum(survived == "yes") / n())
