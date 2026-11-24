# WoW Solo 0.01 Server Preview

This Windows x64 package installs the WoW Solo server, local MySQL databases, prerequisites, and the server launcher. Bring your own **Wrath of the Lich King 3.3.5a client, build 12340**. English clients typically use an `enUS` or `enGB` folder. Keep the client in its own folder outside the server installation.

## Install and start the server

1. Keep the setup executable beside the `Payload`, `Database`, and `Installer` folders. Run **WoWSolo-Server-Setup-0.01.exe**, select **English** if asked, and choose a new destination. Allow the database import to finish.
2. Open **WoW Solo Server** from the desktop. The launcher interface is currently in Russian. On **Управление сервером** (Server management), click **Запустить всё** (Start all) and wait for **Готово** (Ready).
3. For everyday play, open **Консоль сервера** (Server console), select **Создать учётную запись** (Create account), and run the generated command in the worldserver console, without a leading dot. Choose a unique password. `Control\First-Login.txt` contains the local administrator credentials. Keep those private.

Use a clean test PC or VM if the regular WoW Solo installation is already present. Both packages use the same MySQL service, `WoWSoloMySQL`. This preview is a clean install. It does not upgrade an existing world.

## Connect a client in any supported locale

1. Open `Data\<locale>\realmlist.wtf` in your **client** folder, for example `Data\enUS\realmlist.wtf` or `Data\enGB\realmlist.wtf`. Keep a copy of the original.
2. For a server on the same PC, set the following line and save the file:

   ```text
   set realmlist 127.0.0.1
   ```

   For a remote server, replace `127.0.0.1` with the host address supplied by the server owner. The realm must also advertise an address reachable by your client. For friends on a shared LAN or VPN, the host can set the advertised address in **Сеть** (Network). The game uses TCP **3724** and **8085**. Keep MySQL and SOAP local.

3. Start the client directly with **Wow.exe**, then sign in with the WoW Solo game account. Select the realm **WoWSolo**.
4. Optional. Copy the `Optional\WoWSoloBots` folder from the package into the client's `Interface\AddOns` folder. Then enable **WoWSoloBots** on the character selection screen. The launcher can also install the panel from **Управление клиентом** (Client management) after you select your client folder.

## Language and validation

The game client uses its installed language. Server-supplied text depends on the strings available in the world database. Custom WoW Solo messages, character names, and the optional companion panel may still appear in Russian. The installer provides English and Russian, while the bundled server launcher remains Russian.

Before distributing this preview, test it on a clean Windows installation with a 3.3.5a English client. Check the realm list, character creation, entering the world, one quest, and the optional companion panel. To shut down, click **Остановить всё** (Stop all) in the launcher.

Client reference: [AzerothCore client setup](https://www.azerothcore.org/wiki/client-setup).
