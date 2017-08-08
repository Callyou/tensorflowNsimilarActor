# tensorflowNsimilarActor
Testing tensorflow on actors or actresses with similar face features or look alike

I use TensorFlow For Poets to test if it can classify actors or actresses with similar face or if it can classify look alike
I have try to find quality and varied pictures for each actor/actress
https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/?utm_campaign=chrome_series_machinelearning_063016&utm_source=gdev&utm_medium=yt-desc#0

### Why did I choose these actresses ?
You search with Google or Google images "marcia cross carole bouquet" and you will see why, and it intriguates me on a random search.
So I decided that it was the occasion to try Tensorflow and to test if it can classify picture of Marcia Cross at different age with or without make up.

Carole Bouquet (French actress)
Marcia Cross (American actress with similar features as Carole Bouquet)

Audrey Fleurot (French actress), because she a redhead actress.
Audrey Lamy (French actress), because she a blond haired actress.

## What kind of pictures for guessing I have used :
guess_marcia_cross.jpg (young): http://www.letribunaldunet.fr/wp-content/uploads/2017/07/m.jpeg
guess_marcia_cross2.jpg (red carpet make up): http://imagecache2.allposters.com/images/pic/MMPH/263751~Marcia-Cross-Posters.jpg
guess_marcia_cross3.jpg (no make up and with sunglasses): https://resize2-public.ladmedia.fr/img/var/public/storage/images/news/photos/photos-marcia-cross-encore-tres-souple-a-51-ans-387921/marcia-cross-avec-ses-jumelles-savannah-et-eden-a-santa-monica-le-25-mars-2013-387924/4861114-1-fre-FR/Marcia-Cross-avec-ses-jumelles-Savannah-et-Eden-a-Santa-Monica-le-25-mars-2013.jpg
guess_marcia_cross4.jpg (no make up and sideway and laughing) : http://www.cloudpix.co/celebrity-without-makeup--no-makeup-marcia-cross-808504.html

## First test Marcia Cross VS Carole Bouquet :
### Pourcentage of accuracy : 
85%

### Results :
> python label_image.py guess_marcia_cross.jpg
marcia cross (score = 0.97588)
carole bouquet (score = 0.02412)

> python label_image.py guess_marcia_cross2.jpg 
marcia cross (score = 0.89252)
carole bouquet (score = 0.10748)

> python label_image.py guess_marcia_cross3.jpg 
marcia cross (score = 0.83474)
carole bouquet (score = 0.16526)

# Observations : 
Good classification.
---------------------------------------------------------------------------------------------------------------------------
## Second Marcia Cross VS Audrey Fleurot, two redhead:
### Pourcentage of accuracy :
87.5%

### Results :
> python label_image.py guess_marcia_cross.jpg
audrey fleurot (score = 0.68025)
marcia cross (score = 0.31975)

> python label_image.py guess_marcia_cross2.jpg 
audrey fleurot (score = 0.57464)
marcia cross (score = 0.42536)

> python label_image.py guess_marcia_cross3.jpg 
marcia cross (score = 0.76982)
audrey fleurot (score = 0.23018)

> python label_image.py guess_marcia_cross4.jpg 
marcia cross (score = 0.96543)
audrey fleurot (score = 0.03457)

### Observations : 
Tensorflow classify by hair color the first two picture and the last one did recognize that she was older and a dull hair color.
---------------------------------------------------------------------------------------------------------------------------
## Third Marcia Cross VS Audrey Lamy, blond hair :
### Pourcentage of accuracy :
85.7%

### Results :
> python label_image.py guess_marcia_cross.jpg
audrey lamy (score = 0.83114)
marcia cross (score = 0.16886)

> python label_image.py guess_marcia_cross2.jpg 
marcia cross (score = 0.92973)
audrey lamy (score = 0.07027)

> python label_image.py guess_marcia_cross3.jpg 
audrey lamy (score = 0.63763)
marcia cross (score = 0.36237)

> python label_image.py guess_marcia_cross4.jpg 
marcia cross (score = 0.97514)
audrey lamy (score = 0.02486)

### Observations : 
It seems random...

---------------------------------------------------------------------------------------------------------------------------
## Fourth Marcia Cross VS Audrey Lamy VS Audrey Fleurot, because it seems random on the 2 previous tests :
### Pourcentage of accuracy :
77.3%

### Results :
> python label_image.py guess_marcia_cross.jpg
audrey lamy (score = 0.48381)
audrey fleurot (score = 0.35413)
marcia cross (score = 0.16206)

> python label_image.py guess_marcia_cross2.jpg 
marcia cross (score = 0.51561)
audrey fleurot (score = 0.41066)
audrey lamy (score = 0.07374)

> python label_image.py guess_marcia_cross3.jpg 
audrey lamy (score = 0.48258)
marcia cross (score = 0.38794)
audrey fleurot (score = 0.12947)

> python label_image.py guess_marcia_cross4.jpg 
marcia cross (score = 0.93759)
audrey fleurot (score = 0.03756)
audrey lamy (score = 0.02485)

### Observations : 
It seems random... but it's only between Audrey Lamy who is blond and Marcia Cross which is readhead.

---------------------------------------------------------------------------------------------------------------------------
## Last all the 4 actresses together :
Audrey Fleurot (French actress)
Audrey Lamy (French actress)
Carole Bouquet (French actress)
Marcia Cross (American actress with similar features as Carole Bouquet)

### Pourcentage of accuracy : 
73,5%

### Results :
> python label_image.py guess_marcia_cross.jpg
audrey lamy (score = 0.51571)
audrey fleurot (score = 0.26535)
marcia cross (score = 0.20610)
carole bouquet (score = 0.01284)

> python label_image.py guess_marcia_cross2.jpg 
marcia cross (score = 0.49782)
audrey fleurot (score = 0.26476)
carole bouquet (score = 0.16751)
audrey lamy (score = 0.06991)

> python label_image.py guess_marcia_cross3.jpg 
marcia cross (score = 0.40510)
audrey lamy (score = 0.40266)
audrey fleurot (score = 0.10095)
carole bouquet (score = 0.09129)

> python label_image.py guess_marcia_cross4.jpg 
marcia cross (score = 0.90050)
carole bouquet (score = 0.04543)
audrey fleurot (score = 0.02924)
audrey lamy (score = 0.02482)

### Observations : 
It seems random... but finally found the Marcia Cross Hollywood style guess_marcia_cross2.jpg !
------------------------------------------------------------------------------------------------------------------------------------------
At this state we cannot conclude, just observes, but one hypothesis is that I can use better quality data for each actress 
with more differents samples that can help Tensorflow differenciate better.
