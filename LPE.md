## Iteration fb0286e6-47b7-4379-bd97-4d93fd9eab18

### User
Слушай какие там актуальные lpe эксплоиты под Винду за последний год , с поками на гитхабе

### Assistant
Вот актуальные LPE эксплоиты под Windows за последний год с поками на GitHub:

## 2024

**CVE-2024-26229** — Windows CSC Service  
- Heap-based buffer overflow в драйвере csc.sys  
- Повышение через некорректную обработку IOCTL  
- GitHub: https://github.com/RalfHacker/CVE-2024-26229-exploit  
- Патч: апрель 2024

**CVE-2024-21338** — Token Manipulation  
- Admin → SYSTEM/Kernel через манипуляцию токенами  
- Работает даже с включенным HVCI  
- GitHub: https://github.com/hakaioffsec/CVE-2024-21338  
- Системы: Windows 10/11

**CVE-2024-30090** — LPE  
- GitHub: https://github.com/Dor00tkit/CVE-2024-30090

## 2025

**CVE-2025-21333** — Hyper-V Driver (свежак!)  
- Heap overflow в vkrnlintvsp.sys (Hyper-V NT Kernel Integration VSP)  
- Использует WNF state data и I/O ring для arbitrary R/W  
- Требует Windows Sandbox  
- GitHub: https://github.com/MrAle98/CVE-2025-21333-POC  
- Системы: Windows 11 23H2/24H2

**CVE-2025-48799** — Windows Update Service  
- Удаление произвольных папок через симлинки + Storage Sense  
- Работает на системах с несколькими дисками  
- GitHub: https://github.com/Wh04m1001/CVE-2025-48799  
- Системы: Windows 10/11

**CVE-2025-55680** — Cloud Files Minifilter  
- Race condition в драйвере синхронизации облака  
- Превращается в надёжный LPE  
- PoC доступны в нескольких репозиториях

**CVE-2025-0886** — VirtualLockSensor  
- GitHub: https://github.com/JNDataRT/VirtualLockSensorLPE

## Примечания

⚠️ Все эти уязвимости уже пропатчены Microsoft через Windows Update  
⚠️ PoC'и предназначены для исследований и тестирования  
⚠️ Запуск может привести к нестабильности системы или краху  

Большинство свежих эксплоитов используют:
- Heap overflows в драйверах
- Race conditions
- Symlink атаки на сервисы
- Token manipulation
- IOCTL mishandling