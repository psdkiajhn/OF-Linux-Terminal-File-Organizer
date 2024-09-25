# O.F - Органайзер файлов

У вас проблемы с организацией файлов❓ С O.F, больше никаких проблем❗😃
Установка очень проста, даже ребенок 🧒 сможет это сделать! Вы можете увидеть это [здесь](https://github.com/psdkiajhn/OF-Linux-Terminal-File-Organizer/blob/main/russian.md#Установка).
Это приложение может организовать ваши файлы двумя способами:
- Сортировка по типу (много типов расширений встроено, но вы можете добавить или изменить их😄)
- Сортировка по расширениям <br />
[Сайт](https://sl-hapy.github.io/OF-Terminal-File-site/) сейчас обновлен! Проверьте его
> [!NOTE]
> Требуется Python, поэтому установите его

> [!IMPORTANT]
> Используйте sudo, когда хотите использовать `-a` или `-r` <br />
> если вы видите ошибку sudo без использования какого-либо аргумента, это означает, что `file_types.json` в `/usr/OF/` удален, вам нужно использовать sudo, чтобы создать его снова <br />

> [!WARNING]
> "Пожалуйста, используйте sudo" 🟰 команда требует изменения чего-то в папке /usr/ и требует sudo <br />
> "Нельзя использовать verbose и quiet вместе" 🟰 использование `-v` и `-q` в одной команде <br />
> "'/usr/OF/file_types.json' файл был удален!" 🟰 файл типа был удален, и OF должен создать его снова <br />
> "Необходимый файл не существует" 🟰 файлы установки удалены или имеют проблему, скачайте снова <br />

# Установка

просто установите git и выполните эти команды:
```
    git clone https://github.com/psdkiajhn/OF-Linux-Terminal-File-Organizer.git
    cd OF-Linux-Terminal-File-Organizer
    ./install
```
теперь это в вашем терминале, наслаждайтесь❗😃

# Использование
после установки команда of будет добавлена в ваш терминал <br />
вы можете использовать ее с 10 аргументами или использовать ее отдельно:
```
    of -n | of --NO-NEW-FOLDER #OF не будет организовывать файлы без новой папки
    of -h | of --help #показать страницу помощи
    of -d | of --directory #Организация другой директории вместо текущей директории
    of -v | of --verbose #OF будет говорить все
    of -q | of --quiet #OF не будет ничего говорить of -f | of --format #Посмотреть все поддерживаемые расширения и их типы
    of -s | of --search #Поиск в поддерживаемых форматах 
    of -a | of --add #Добавить новый тип для расширения 
    of -r | of --reset #сбросить все пользовательские типы и расширения 
    of -e | of --extension #OF будет организовывать файлы по расширению вместо их типов!
```
## Без новой папки
Это приложение создает папку с типом или расширением (`с использованием -e или нет`) для сортировки файлов, но с этим аргументом OF просто сортирует файлы с существующими папками, <br />
например:
```
        до: | после: 
📁image     | 📁image (с test1.png и test2.jpg)
🖼️test1.png | 🎥test.mp4
🖼️tset2.jpg |
🎥test.mp4  |
```
как видите, файл `.mp4` не был организован, потому что папка видео не существует❗ <br />
Вы можете использовать это, когда у вас есть свои собственные отсортированные папки, но вы добавили новые файлы, вы можете использовать `-n` или `--NO-NEW-FOLDER`, чтобы организовать их с вашими старыми папками <br />

## Директория
если вы хотите организовать директорию, но находитесь в другой директории, <br />
вам не нужно использовать cd для перехода в эту директорию, просто используйте `-d` или `--directory` вот так: <br />
```
    of -d /usr/myfiles/
        или 
    of -d=“/usr/my\ files”
```


## Расширение
если вы хотите сортировать файлы по расширению вместо их типа, <br />
вы можете использовать `-e` или `--extension` <br />
Вот пример: <br />
с -e: <br />
```
до:         | после: 
🖼️test1.png | 📁png 
🖼️tset2.jpg | 📁jpg 
🎥test.mp4  | 📁mp4
```
без -e: <br />
```
до:         | после: 
🖼️test1.png | 📁image 
🖼️tset2.jpg | 📁video 
🎥test.mp4  |
```

## Формат
хотите увидеть все поддерживаемые расширения❓ <br />
используйте `-f` или `--format` и только это <br />
Вы также можете увидеть все встроенные поддерживаемые форматы здесь <br />

## Многословный и тихий
если вы хотите знать все, используйте `-v` или `--verbose` <br />
и если вы не хотите ничего получать и просто организовать, используйте `-q` или `--quiet` <br />

## Поиск
не знаете, поддерживается ли расширение или нет❓ <br />
просто используйте `-s` или `--search`, сообщение скажет вам все❗ <br />

## Добавить
У вас есть файл с неподдерживаемым расширением? <br />
Просто используйте `-a` или `--add` <br />
Сообщение поможет вам добавить, но я также помогу вам здесь: <br />
Для одного расширения вы можете использовать `Extension:Type` <br />
А для нескольких расширений используйте `Extension1:Type, Extension2:Type2` <br />
Например: <br />
`psd:adobe photoshop, pdd:adobe photoshop` <br />
Вы можете изменить встроенное расширение, вот так: <br />
`png:custom, jpg:custom` <br />

## Сброс
Если вы не хотите изменять расширение или случайно их сломали, <br />
Не проблема, просто используйте `-r` или `--reset` и вуаля, ваши типы были сброшены❗ <br />

# Поддерживаемые расширения
```
  bat -> executable
  exe -> executable
  msi -> executable
  sh -> executable
  vb -> executable
  vbs -> executable
  wsf -> executable
  apk -> executable
  ttf -> font
  otf -> font
  fnt -> font
  log -> text
  txt -> text
  tex -> text
  rtf -> text
  png -> image
  bmp -> image
  gif -> image
  ico -> image
  jpeg -> image
  svg -> image
  tif -> image
  scr -> image
  tiff -> image
  jpg -> image
  webp -> image
  mp4 -> video
  mkv -> video
  m4v -> video
  mpg -> video
  mpeg -> video
  mov -> video
  swf -> video
  vob -> video
  webm -> video
  wmv -> video
  mp3 -> audio
  aif -> audio
  cda -> audio
  mpa -> audio
  ogg -> audio
  wma -> audio
  wav -> audio
  bak -> backup
  cab -> windows
  cfg -> windows
  cur -> windows
  dll -> windows
  cpl -> windows
  drv -> windows
  dmp -> windows
  ini -> windows
  ink -> windows
  sys -> windows
  tmp -> windows
  icns -> mac
  7z -> copressed
  rar -> compressed
  zip -> compressed
  tar.gz -> compressed
  tgz -> compressed
  tbz -> compressed
  txz -> compressed
  tzst -> compressed
  tar.br -> compressed
  tar.bz2 -> compressed
  z -> compressed
  arj -> compressed
  tar.xz -> compressed
  tar.zst -> compressed
  deb -> package
  pkg -> package
  rpm -> package
  dmg -> disc image
  iso -> disc image
  toast -> disc image
  vcd -> disc image
  img -> disc image
  csv -> dataset
  dat -> dataset
  sql -> dataset
  db -> dataset
  dbf -> dataset
  mdb -> dataset
  sav -> dataset
  pdf -> document
  doc -> document
  wpd -> document
  docx -> document
  pptx -> document
  ppt -> document
  pps -> document
  odp -> document
  xls -> document
  xlsm -> document
  xlsx -> document
  xml -> programing
  py -> programing
  cpp -> programing
  java -> programing
  go -> programing
  html -> programing
  css -> programing
  cs -> programing
  js -> programing
  jsp -> programing
  php -> programing
  htm -> programing
  xhtml -> programing
  jar -> programing
  c -> programing
  class -> programing
  h -> programing
  cgi -> programing
  pl -> programing
  swift -> programing
```

# Удаление

Просто запустите файл удаления в папке приложения, вот так: <br />
```
    ./uninstall
```
