# Основная информация
   Этот обходник представляет собой версию обхода от Sergeydigl3, адаптированную под новые блокировки от ркн, в частности блокировки aws и cloudflare
   
   Для работы обходника, в него внедрен cloudflare warp, который позволяет обходить блокировки aws и cloudflare, aur: https://aur.archlinux.org/packages/cloudflare-warp-bin
   
   Собран за один вечер на коленке, так что могут быть баги и недоработки

# Начало работы
   Перед клонированием репозитория прочитайте информацию об оригинальном обходнике на линукс: https://github.com/Sergeydigl3/zapret-discord-youtube-linux
   
   После всех выполнения всех инструкций из оригинального репозитория, необходимо также установить сам warp:
   
   ```bash
   yay -S cloudflare-warp-bin
   git clone https://github.com/chirat-dev/zapret-discord-youtube-linux-warp.git
   cd zapret-discord-youtube-linux-warp
   ./main_script.sh
   ```

   Если у вас вечная установка, то:
   
   - Попробуйте перезапустить установку
   - Попробуйте начать установку, включив обходник от Sergeydigl3

   После этого можно сразу же отключить основной скрипт
   
   Далее необходимо перенести файл list-general.txt в папку zapret-latest и снова запустить скрипт, но без включения warp

   ```bash
   cp list-general.txt zapret-latest/
   ./main_script.sh
   ```

   Далее необходимо создать регистрацию в warp, а также выбрать режим его работы, во избежания багов

   ```bash
   sudo systemctl start warp-svc
   warp-cli registration new
   warp-cli mode tunnel_only
   ```

   После перезагрузки все должно заработать правильно

# Важно !!!
   В данной версии пока не предусмотрена работа сервисов warp при установке на автозагрузку
