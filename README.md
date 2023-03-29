<h1 align="center"> MTS KION </h1>
<table border="1" cellspacing="0"
cellpadding="8" style="background-color:#fff; color:#000">
<tr>
<td><img src="https://github.com/alinahasss/mtsss/blob/main/%D0%91%D1%80%D0%B8%D0%BB%D0%B8%D0%B0%D0%BD%D1%82%D0%BE%D0%B2%D0%B0%D1%8F_%D1%80%D1%83%D0%BA%D0%B0_online_video_cutter_com_1_.gif" width="300" height="180"> </td>
<td><img src="https://github.com/alinahasss/mtsss/blob/main/%D0%91%D1%80%D0%B8%D0%BB%D0%B8%D0%B0%D0%BD%D1%82%D0%BE%D0%B2%D0%B0%D1%8F_%D1%80%D1%83%D0%BA%D0%B0_online_video_cutter_com_5_gif.gif"> </td>
</tr>
<tr>
<td>Большая группа людей на лодке</td>
<td>Мужчина в костюме и галстуке стоит у перил</td>
</tr>
</table>

Эти инструкции позволят вам получить копию проекта, запущенного на локальном компьютере для целей разработки и тестирования.

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
sound1 = AudioSegment.from_file("/content/gdrive/MyDrive/mts1/audio/1.wav", format="wav")
sound2 = AudioSegment.from_file("/content/gdrive/MyDrive/mts1/audio/2.wav", format="wav")

# sound1 6 dB louder
louder = sound1 + 6

# Overlay sound2 over sound1 at position 0  (use louder instead of sound1 to use the louder version)
overlay = sound1.overlay(sound2, position=0)

# simple export
file_handle = overlay.export("/content/gdrive/MyDrive/mts1/audio/output.mp3", format="mp3")
```

<h2> Предложения по масштабированию </h2> 

1. Внедрение голосового помощника для более удобной навигации по приложению <br>
2. Полная адаптация звука (изменение голоса (муж/жен), настройки языка) <br>
3. Описание продолжительного видео, вместо фрагментов видеофайлов <br>
4. Улучшение качества тифлокомментариев  <br>

<h2> Визуальное описание бизнес-процесса, сервисов, сущности БД  </h2> 

<h2> Скриншоты сервиса  </h2> 
