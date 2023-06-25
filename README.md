# Локалізація  stable-diffusion-webui
## Принципи перекладу:
- Я намагався перекладати всі підказки і тексти описанні налаштувань, але не перекладати власні назви, терміни і назви кнопок.
- Поперше тому що більшість туторіалів англійськолю, краще користуватись англійськими назвами вкладок і кнопок, але підказки щоб булли українською
- По друге Є вже інтуітивно зрозуміла англійська термінологія і заміняти  терміни українським відповідником -це робити інтерфейм більш заплутаним а я намагався робити щоб все було інтуітивно
- Переклад не остаточний і можливо буде змінюватись
- По третє `Лаконічність`  - ми звикли короткі англійські терміни перекладати довкими  словосполученнями  типу **"Роздільна здатність"**  -Я такі вирази намагаюсь в Українському стилі скорочувати **"Роздільність"** - головне щоб інтуітивно була зрозуміло і слово не втратило  суті.
----
*перед установкою локалізації у вас повинен бути встановлений  Stable Diffusion -де його скачати і як встановити читайте кижче.*

- Записав на відео  свій  бубньож для чайників по установці і локалізації #StableDiffusion з нуля  #AI
    - https://youtu.be/QScLDIdTIec


## Установка локалізації:
- скачати файли локалізації:
     - ![image](https://github.com/razorback456/webui-localization-ua_UA/assets/11790479/2a3aa775-5205-4860-8f86-d812f39b77fa)
----
- розпакувати архів
- каталог **webui-localization-ua_UA**    -покласти папку     **...\extensions**  наприклад: C:\sd.webui\extensions\webui-localization-ua_UA

- **hints.js**  -покласти в папку     **...\javascript**   наприклад: C:\sd.webui\javascript\hints.js
----
## Установка Stable Diffusion Portable: потрібна відеокарта NVIDIA 4гб ОЗУ  (для інших карт встановлюй версію EasyDiffusion нижче)
1. скачати `webui.zip` і розпакувати https://github.com/AUTOMATIC1111/stable-diffusion-webui/releases/tag/v1.0.0-pre
2. Запусти скрипт `update.bat`, щоб оновити веб-інтерфейс користувача до останньої версії, зачекайте до завершення та закрийте вікно.
3. Двічі клацніть скрипт `run.bat`, щоб запустити веб-інтерфейс; під час першого запуску він завантажить велику кількість файлів. Після того, як усе було правильно завантажено та встановлено, ви повинні побачити повідомлення `Running on local URL:  127.0.0.1:786` . Скопіюйте адресу `127.0.0.1:786` з консолі і встав в браузер щоб відкрити інтерфейс нейронки.
4. при першому запуску скрипт завантажить оновлення і видасть помилку, просто треба закрити консоль і знову запустити `run.bat` з оновленими даними
5. щоб зробити автоматично відкриття сторінки нейромережі в браузері  потрібно  файл `sd.webui\webui\webui-user.bat`  відкрити в блокноті додати команду `set COMMANDLINE_ARGS=--autolaunch --update-check` - ці команди перевірятимуть оновлення і запускатимуть браузер.
6. я в себе налаштував так:
   - `set COMMANDLINE_ARGS= --xformers   --medvram --no-half  --update-check --autolaunch --ckpt-dir C:\\_AI_SD_P/models/Stable-diffusion`
       - `--xformers` - для оптимізаці відео пам'яті  - при першому запуску буде скачувати бібліотеки до 5гіг
       -  `--medvram --no-half `  - для зменшення навантаження на відеопам'ять щоб уникнути помилок нестачі пам'яті
       -  `--update-check --autolaunch`   -для автоматичного запуску браузера
       -  `--ckpt-dir C:\\_AI_SD_P/models/Stable-diffusion`   -шлях до каталога з чекпоінтами, корисно якщо у вас стоїть декілька нейромереж щоб не дублювати  файли в мене один каталог використовується всіма нейронками.

6.Після установки скачайте додаткові моделі в папку `C:\_sd.webui\webui\models\Stable-diffusion`,</br>
Рекомендую качати модель:
ReV Animated  https://civitai.com/models/7371?modelVersionId=46846
Також при першому запуску  нейронка автоматично скачає стандарту модель 1.5..

----
# КОРИСНІ ПОСИЛАННЯ:
- Локальна версія версія для потужних ПК (рекомендую ставити її)<br/>
- [x] **sd.webui** https://github.com/AUTOMATIC1111/stable-diffusion-webui
-  Онлайн версія для слабких ПК:  
- [ ] **Stable EasyDiffusion:**       https://github.com/easydiffusion/easydiffusion 

-  Вікіпедія по Stable Diffusion:
    - [x] Укр.  https://github.com/razorback456/webui-localization-ua_UA/wiki
    - [ ] Англ. https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki

# Переклад Редмі: 
- Оригінал: https://github.com/AUTOMATIC1111/stable-diffusion-webui

# Stable Diffusion web UI
Інтерфейс браузера на основі бібліотеки Gradio для Stable Diffusion.
![screenshot](https://github.com/razorback456/webui-localization-ua_UA/assets/11790479/268b5e5f-6fe0-4228-bb43-062ce3ed896b)

## Особливості
[Детальна демонстрація функцій із зображеннями](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features):
- Оригінальні режими `txt2img` і `img2img`
- Встановіть і запустіть скрипт одним клацанням миші (але все одно потрібно встановити python і git)
- Outpainting
- Inpainting
- Color Sketch
- Prompt Matrix
- Stable Diffusion Upscale
- Вага: *вкажіть частини тексту, на яку Нейронка  має звернути більше уваги*
    
    - `a man in a ((tuxedo))` - приділить більше уваги смокінгу (tuxedo)
        - *всі промпти повинні бути англійською тому я їх не перекладаю*
    - `a man in a (tuxedo:1.21)` - альтернативний синтаксис
    - виберіть текст і натисніть `Ctrl+Up` чи `Ctrl+Down` (чи `Command+Up` чи `Command+Down` а  MacOS) щоб автоматично налаштувати увагу на виділений текст )

- `Loopback`, *запустіть обробку* img2img *кілька разів*
-  `X/Y/Z Атлас`, *спосіб намалювати  Атлас(таблицю) зображень із різними параметрами*
- Текстова інверсія
    - мати скільки завгодно `embeddings` і використовувати для них будь-які назви
    - використовувати кілька `embeddings` з різною кількістю векторів на `token`
    - працює з числами половинної точності з плаваючою комою
    - тренувати  `embeddings` на 8 Гб (також повідомляли про роботу 6 Гб)
- Вкладка `Extras` з:
    - `GFPGAN`, нейронна мережа, яка покращує обличчя
    - `CodeFormer`, інструмент відновлення обличчя як альтернатива `GFPGAN`
    - `RealESRGAN`, нейронна мережа `upscaler`(збільшення роздільності зоображення)
    - `ESRGAN`, нейронна мережа `upscaler` з великою кількістю сторонніх моделей
    - `SwinIR` та `Swin2SR` ([посилання..](https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/2092)),  нейроннки `upscaler`
    - `LDSR`, Latent diffusion super resolution (Надроздільність латентної дифузії) `upscaler`
- `Resizing` - зміни розміру та пропорції
- вибір методу `Самплінгу`
    - Налаштувати ета-значення семплера (множник шуму)
    - Додаткові параметри налаштування шуму
- Перервати обробку в будь-який час
- Підтримка відеокарти 4 ГБ (також повідомляється про роботу 2 ГБ)
- Правильне `seeds` для партій зображень
- Автоматичне оновлення лічильника токенів
- Параметри генерації
     - параметри, які ви використовували для створення зображень, зберігаються разом із цим зображенням
     - у фрагментах PNG для PNG, у EXIF ​​для JPEG
     - можна перетягнути зображення на інформаційну вкладку PNG, щоб відновити параметри генерації та автоматично скопіювати їх в інтерфейс користувача
     - можна вимкнути в налаштуваннях
     - `drag and drop` зображень/тексту у вікно промпту
- Read Generation Parameters Button, читає промпт з картинки 
- Сторінка налаштувань
- Запуск довільного коду python з інтерфейсу користувача (щоб увімкнути, потрібно запускати з `--allow-code`)
- Підказки при наведенні миші для більшості елементів інтерфейсу (локалізація підказок українською Читайте інструкцію вгорі)
- Possible to change defaults/mix/max/step values for UI elements via text config
- Можливість зміни значень defaults/mix/max/step для елементів UI за допомогою  text config
- Підтримка Тайлових текстур, прапорець для створення зображень, які можна розміщувати як текстури
- Індикатор прогресу та попередній перегляд створення живого зображення
    - Може використовувати окрему нейронну мережу для створення попередніх переглядів майже без вимог до `VRAM` або обчислень
- Негативний промпт, додаткове текстове поле, яке дозволяє вказати те, що ви не хочете бачити на створеному зображенні
- Шаблони, спосіб зберегти частину промпту та легко застосувати їх у спадному списку пізніше
- Варіації, спосіб створення того самого зображення, але з невеликими відмінностями
- Seed ресайз, спосіб створення того самого зображення, але з дещо іншою роздільною здатністю
- CLIP interrogator, кнопка, яка намагається вгадати промпт із зображення
- Prompt Editing, спосіб змінити підказку середнього покоління, скажімо, почати робити кавун і перейти на аніме-дівчинку на півдорозі
- Batch Processing, обробити групу файлів за допомогою img2img
- Img2img Alternative, зворотний метод Ейлера перехресного контролю уваги
- Highres Fix, зручна опція для створення зображень високої роздільної здатності в один клік без звичайних спотворень
- Перезавантаження Чекпоінтів на льоту
- Checkpoint Merger, вкладка, яка дозволяє об'єднати до 3 Checkpoint точок в одну
- [Скрипти](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Custom-Scripts) із багатьма розширеннями від спільноти
- [Composable-Diffusion](https://energy-based-model.github.io/Compositional-Visual-Generation-with-Composable-Diffusion-Models/), спосіб використання кількох промптів одночасно
     - розділяйте промпти великими літерами `AND`
     - також підтримує ваги для підказок: `a cat :1.2 AND a dog AND a penguin :2.2`
- Немає ліміту токенів для підказок (оригінальна stable diffusion дозволяє використовувати до 75 токенів)
- DeepDanbooru інтеграція, створює теги стилю danbooru для підказок аніме
- [xformers](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Xformers), значне збільшення швидкості для вибраних карток: (додайте `--xformers` до аргументів командного рядка)
- через розширення: [вкладка «Історія»](https://github.com/yfszzx/stable-diffusion-webui-images-browser): зручно переглядати, направляти та видаляти зображення в  UI (застаріло)
- Постійно генерувати параметр
- Вкладка навчання
     - hypernetworks та embeddings параметри
     - Preprocessing зображення: кадрування, дзеркальне відображення, автоматичне тегування за допомогою BLIP або deepdanbooru (для аніме)
- Clip пропуск
- `Hypernetworks`
- `Loras` (те саме, що й гіпермережі, але більш гарне)
- Окремий UI, у якому ви можете вибрати (з попереднім переглядом), які `embeddings`, `hypernetworks` чи `Loras` додати до підказки
- Можна вибрати завантаження іншого VAE з екрана налаштувань
- Приблизний час завершення на панелі виконання
- API
- Підтримка спеціальної [моделі малювання](https://github.com/runwayml/stable-diffusion#inpainting-with-stable-diffusion) від RunwayML
- через розширення: [Aesthetic Gradients](https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients), спосіб генерувати зображення з певною естетикою за допомогою вбудованих зображень кліпів (реалізація [https:/ /github.com/vicgalle/stable-diffusion-aesthetic-gradients](https://github.com/vicgalle/stable-diffusion-aesthetic-gradients))
- Підтримка [Stable Diffusion 2.0](https://github.com/Stability-AI/stablediffusion) – див. [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#stable-diffusion) -20) для інструкцій
- Підтримка [Alt-Diffusion](https://arxiv.org/abs/2211.06679) — див. [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#alt-diffusion) інструкції
- Тепер без поганих букв!
- Завантажте Чекпоінти у форматі safetensors
- Полегшене обмеження роздільності: розмір створеного зображення має бути кратним 8, а не 64
- Тепер з ліцензією!
- Змініть порядок елементів в інтерфейсі користувача з екрана налаштувань

## Встановлення та запуск
Переконайтеся, що необхідні [залежності](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Dependencies) виконано, і дотримуйтесь інструкцій, доступних для обох [NVidia](https://github.com/AUTOMATIC1111) /stable-diffusion-webui/wiki/Install-and-Run-on-NVidia-GPUs) (рекомендовано) і [AMD](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and -Run-on-AMD-GPUs) Графічні процесори.

Альтернатива, скористайтеся онлайн-сервісами (наприклад, Google Colab):

-[Список онлайн-сервісів](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Online-Services)

### Встановлення на Windows 10/11 з графічним процесором NVidia за допомогою пакета релізу
1. Завантажте `sd.webui.zip` з [v1.0.0-pre](https://github.com/AUTOMATIC1111/stable-diffusion-webui/releases/tag/v1.0.0-pre) і розпакуйте його вміст.
2. Запустіть `update.bat`.
3. Запустіть `run.bat`.
> Щоб отримати докладнішу інформацію, перегляньте [Install-and-Run-on-NVidia-GPUs](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-NVidia-GPUs)

### Автоматичне встановлення на Windows
1. Установіть [Python 3.10.6](https://www.python.org/downloads/release/python-3106/) (Новіша версія Python не підтримує torch), позначивши «Додати Python до PATH».
2. встановити [git](https://git-scm.com/download/win).
3. Завантажте репозиторій stable-diffusion-webui, наприклад, запустивши `git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git`.
4. Запустіть `webui-user.bat` з Windows Explorer як звичайний користувач без прав адміністратора.
### Автоматичне встановлення на Linux
1. Install the dependencies:
```bash
# Debian-based:
sudo apt install wget git python3 python3-venv
# Red Hat-based:
sudo dnf install wget git python3
# Arch-based:
sudo pacman -S wget git python3
```
2. Navigate to the directory you would like the webui to be installed and execute the following command:
```bash
bash <(wget -qO- https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh)
```
3. Run `webui.sh`.
4. Check `webui-user.sh` for options.
### Установка на Apple Silicon

Знайдіть інструкції [тут](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Installation-on-Apple-Silicon).

## Сприяння
Ось як додати код до цього сховища: [Внесок](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Внесок)

## Документація
Документацію було переміщено з цього README до  ( [ВІКІПЕДІЇ](https://github.com/razorback456/webui-localization-ua_UA/wiki)) проекту.

## Ліцензії
Ліцензії для запозиченого коду можна знайти на екрані `Налаштування - Ліцензії`, а також у файлі `html/licenses.html`.
- Stable Diffusion - https://github.com/CompVis/stable-diffusion, https://github.com/CompVis/taming-transformers
- k-diffusion - https://github.com/crowsonkb/k-diffusion.git
- GFPGAN - https://github.com/TencentARC/GFPGAN.git
- CodeFormer - https://github.com/sczhou/CodeFormer
- ESRGAN - https://github.com/xinntao/ESRGAN
- SwinIR - https://github.com/JingyunLiang/SwinIR
- Swin2SR - https://github.com/mv-lab/swin2sr
- LDSR - https://github.com/Hafiidz/latent-diffusion
- MiDaS - https://github.com/isl-org/MiDaS
- Ideas for optimizations - https://github.com/basujindal/stable-diffusion
- Cross Attention layer optimization - Doggettx - https://github.com/Doggettx/stable-diffusion, original idea for prompt editing.
- Cross Attention layer optimization - InvokeAI, lstein - https://github.com/invoke-ai/InvokeAI (originally http://github.com/lstein/stable-diffusion)
- Sub-quadratic Cross Attention layer optimization - Alex Birch (https://github.com/Birch-san/diffusers/pull/1), Amin Rezaei (https://github.com/AminRezaei0x443/memory-efficient-attention)
- Textual Inversion - Rinon Gal - https://github.com/rinongal/textual_inversion (we're not using his code, but we are using his ideas).
- Idea for SD upscale - https://github.com/jquesnelle/txt2imghd
- Noise generation for outpainting mk2 - https://github.com/parlance-zz/g-diffuser-bot
- CLIP interrogator idea and borrowing some code - https://github.com/pharmapsychotic/clip-interrogator
- Idea for Composable Diffusion - https://github.com/energy-based-model/Compositional-Visual-Generation-with-Composable-Diffusion-Models-PyTorch
- xformers - https://github.com/facebookresearch/xformers
- DeepDanbooru - interrogator for anime diffusers https://github.com/KichangKim/DeepDanbooru
- Sampling in float32 precision from a float16 UNet - marunine for the idea, Birch-san for the example Diffusers implementation (https://github.com/Birch-san/diffusers-play/tree/92feee6)
- Instruct pix2pix - Tim Brooks (star), Aleksander Holynski (star), Alexei A. Efros (no star) - https://github.com/timothybrooks/instruct-pix2pix
- Security advice - RyotaK
- UniPC sampler - Wenliang Zhao - https://github.com/wl-zhao/UniPC
- TAESD - Ollin Boer Bohan - https://github.com/madebyollin/taesd
- Initial Gradio script - posted on 4chan by an Anonymous user. Thank you Anonymous user.
- Переклад **Українською** `razorback456`    https://www.artstation.com/razorback456
