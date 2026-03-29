# 7.5" Touch, E-ink smart display
* DPTP System - 7.5" Touch, E-ink smart display
* title:		main program, Smart display
* autor:		DPTP System - Tóth Péter
* project:		STM32F + 7.5" E-Paper (GDEY075T7‑T01, UC8179) + GT911 touch
* pcb created:	...
* date:			2026-03-29.
* email:		don_peter[kukac]freemail[pont]hu
* device:		Special adapter and develop device
* platform:		STM32CubeMX 6.4, STM32CubeIDE 1.14.1, C Code
* mcu:			STM32F??? RAM：?K FLASH：?K FREQ：?MHz

# Figyelmeztetés
Az itt közölt adatok, kódok és fejlesztési utmutatók csak tájékoztató jellegűek, főként saját magamnak
szántam, felelősséget és garanciát értük nem vállalok.

# Előzmények
Korábban egy gázkazános rendszerhez készítettem egy E-Paper-es kijelzéssel megoldott információs kijelzést, amelyet itt, ezen a szálon tudtok 
visszanézni: https://github.com/DPTPSystem/Q3RF_SignalMonitoring
Pár képet azért itt is megosztok az előzményről, melyet végül egyébb okok miatt nem üzemeltem be, bár elkészült 99%-ban.

![CC1101](https://github.com/DPTPSystem/Q3RF_SignalMonitoring/blob/master/images/p2.jpg "Padlófátés és hőfok/páratartalom figyelő")

És a kész projekt kijelzése:

![DPTP System](https://github.com/DPTPSystem/Q3RF_SignalMonitoring/blob/master/images/dptpsystem_epaper_0.jpg "DPTP System")

![DPTP System](https://github.com/DPTPSystem/Q3RF_SignalMonitoring/blob/master/images/dptpsystem_epaper_1.jpg "DPTP System")

# Az eszköz működése
Működése egyszerű lesz, külső és belső szenzorokból beérkező jeleket feldolgozza és azt számunkra is érthető módon közli velünk. Mivel érintő képernyőnk lesz, 
így könnyedén a képernyőt adott területen megéríntve egyes információkat, adatokat részleteiben is megjeleníthet. Főbb infórmációk, amelyeket látni szeretnénk
valós időben:
1. Külső hőmérséklet és páratartalom
2. Belső, helységenkénti hőmérséklet és napali páratartalom
3. Padlófűtés köreinek folyamatos hőmérséklet figyelése
4. Pontos dátum és idő kijlezése
5. Adatok elemzése és grafikus megjelenítése (7 napos külömbségek, de napi külömbségek grafikus megjelenítése)
6. ...stb

# Célkitűzés
Fűtés és egyébb szenzorok adatainak megfigyelése és jel-feldolgozása, majd egy külön kijelzőn jelezni, hogy a fűtés rendszer aktív avagy sem.
További célkitúzés lehet, egy optimálisabb vezérlés kialakítása, amely a lakás több helyiségének átlaghömérsékletének alapján 
vezérlné a fűtésrendszert, figyelembe véve a külső hőmérsékleteket és a helyiségekben mért páratartalmat.