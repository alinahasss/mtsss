<h1 align="center"> MTS KION </h1>
<table border="1" cellspacing="0"
cellpadding="8" style="background-color:#fff; color:#000">
<tr>
<td><img src="pictures/Брилиантовая_рука_online_video_cutter_com_1_.gif" width="300" height="180"> </td>
<td><img src="pictures/Брилиантовая_рука_online_video_cutter_com_5_gif.gif"> </td>
</tr>
<tr>
<td>Большая группа людей на лодке</td>
<td>Мужчина в костюме и галстуке стоит у перил</td>
</tr>
</table>

Эти инструкции позволят вам получить копию проекта, запущенного на локальном компьютере для целей разработки и тестирования.
В папке доп.файлы содержатся все материалы, которые были использованы при разработке и обучении нейросети, а также результаты.

<h2> Установка </h2>

Подключаем библиотеки:
    ```
   !pip install datasets
!pip install transformers
!pip install evaluate torch nltk rouge_score numpy
!pip install gtts
!pip install deep_translator
!pip install pyttsx3
from gtts import gTTS
from IPython.display import Audio
import pyttsx3
    ```
<h2> Настройка и запуск </h2>   
    
Процесс описания и озвучивания gif:
```
aud = image_captioner("/content/gdrive/MyDrive/mts1/giff/0001.gif")
from deep_translator import GoogleTranslator
to_translate = str(aud)
translated = GoogleTranslator(source='auto', target='ru').translate(to_translate)
tts = gTTS(str(translated), lang='ru')
tts.save('/content/gdrive/MyDrive/mts1/audio/1.wav')
sound_file = '1.wav'
Audio(sound_file, autoplay=True)
```


Процесс синергии, полученных аудио:

```
!pip install pydub
from pydub import AudioSegment
song1 = AudioSegment.from_mp3("/content/gdrive/MyDrive/mts1/audio/1.wav")
song2 = AudioSegment.from_mp3("/content/gdrive/MyDrive/mts1/audio/2.wav")
beginning = song1
end = song2
without_the_middle = beginning + end
with_style = beginning.append(end)
do_it_over = song1 + song2
awesome = do_it_over.fade_in(2000).fade_out(3000)
awesome.export("/content/gdrive/MyDrive/mts1/audio/itog.mp3", format="mp3")
```

<h2> Предложения по масштабированию </h2> 

1. Внедрение голосового помощника для более удобной навигации по приложению <br>
2. Полная адаптация звука (изменение голоса (муж/жен), настройки языка) <br>
3. Описание продолжительного видео, вместо фрагментов видеофайлов <br>
4. Улучшение качества тифлокомментариев  <br>

<h2> Визуальное описание бизнес-процесса, сервисов, сущности БД  </h2> 

БД содержит уже готовые тифлокомментарии, доступ к которым осуществляется по названию фильма-год.<br>
Использование БД повысит эффективность работы приложения.<br>

![Визуальное описание БП](https://github.com/alinahasss/mtsss/blob/main/business_page-0001.jpg)

<h2> Скриншоты сервиса  </h2> 

<h3>Главная страница:</h3><br>

![Главная страница](https://github.com/alinahasss/mtsss/blob/main/photo_2_2023-03-29_17-26-56.jpg)<br>

<h3>Страница с описанием фильма:</h3><br>

![Страница с описание фильма](https://github.com/alinahasss/mtsss/blob/main/photo_1_2023-03-29_17-26-56.jpg)<br>

<h3>Видеоплеер:</h3><br>

![Видеоплеер](https://github.com/alinahasss/mtsss/blob/main/photo_3_2023-03-29_17-26-56.jpg)<br>
 
