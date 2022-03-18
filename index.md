Hello World!
Welcome to my Website.

Check ou my meme
# _Meme_
![Image](my_meme.png)

**This meme was created due to some courses forcing students to turn on their camera.**

```{r}
library(magick)
messy_dog <- image_read("https://i.pinimg.com/564x/4c/0f/c9/4c0fc9dfc604e8d958e004eac4e4a3e3.jpg") %>%
  image_scale(500)

tidy_dog <- image_read("https://onnewslive.com/wp-content/uploads/2021/09/Several-dogs-are-inversely-proportional-to-beauty-and-IQ.png") %>%
  image_scale(500)

audio_text <- image_blank(width = 500, 
                          height = 445, 
                          color = "#000000") %>%
  image_annotate(text = "Zoom\nAudio only",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

video_text <- image_blank(width = 500, 
                         height = 358, 
                         color = "#000000") %>%
  image_annotate(text = "Zoom\nWith video",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")



first_row <- c(messy_dog, audio_text) %>%
  image_append()

second_row <- c(tidy_dog, video_text) %>%
  image_append()



meme <- c(first_row, second_row) %>%
  image_append(stack = TRUE)

image_write(meme, "my_meme.png")
```
