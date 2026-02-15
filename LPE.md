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















## Iteration 643da17d-5872-4e10-b169-a363a5a25720

### User
поищи в инете инфу

### Assistant
Вот актуальная информация по LPE эксплоитам для Windows за последний год с ссылками на GitHub:

## 2024 год

### **CVE-2024-26229** — Windows CSC Service
- **Описание**: Heap overflow/symlink abuse в драйвере csc.sys (Offline Files)
- **Техника**: Некорректная обработка IOCTL
- **GitHub PoC**: 
  - https://github.com/michredteam/PoC-26229 (symlink-based)
  - https://github.com/RalfHacker/CVE-2024-26229-exploit (C exploit)
- **Системы**: Windows 10/11, Server 2019/2022
- **Патч**: Апрель 2024 (KB5036893)

### **CVE-2024-21338** — AppLocker Driver
- **Описание**: LPE с возможностью обхода HVCI
- **GitHub PoC**: https://github.com/hakaioffsec/CVE-2024-21338
- **Особенность**: Работает даже с включенным Hypervisor-protected Code Integrity

### **CVE-2024-30804** — ASUS Driver
- **Описание**: Arbitrary kernel read/write через AsInsHelp64.sys
- **GitHub PoC**: https://github.com/ekfkawl/CVE-2024-30804

### **CVE-2024-30090** — LPE
- **GitHub PoC**: https://github.com/Dor00tkit/CVE-2024-30090

## 2025 год (свежие!)

### **CVE-2025-21333** — Hyper-V NT Kernel (активно эксплуатируется!)
- **Описание**: Heap-based buffer overflow в vkrnlintvsp.sys
- **Техника**: WNF state data + I/O ring для arbitrary R/W
- **GitHub PoC**: https://github.com/MrAle98/CVE-2025-21333-POC
- **Системы**: Windows 11 23H2/24H2
- **Требование**: Windows Sandbox enabled

### **CVE-2025-49667** — Win32k Subsystem
- **Описание**: Эксплуатация подсистемы Win32k
- **GitHub PoC**: https://github.com/Yuri08loveElaina/CVE-2025-49667

### **CVE-2025-62215** — Kernel Race Condition
- **Описание**: Double-free в ядре Windows
- **GitHub PoC**: https://github.com/abrewer251/CVE-2025-62215_Windows_Kernel_PE

### **CVE-2025-48799** — Windows Update Service
- **Описание**: Symlink deletion через Storage Sense на мультидисковых системах
- **GitHub PoC**: https://github.com/Wh04m1001/CVE-2025-48799
- **Системы**: Windows 10/11 с несколькими дисками

### **CVE-2025-55680** — Cloud Files Minifilter
- **Описание**: Race condition в драйвере синхронизации облака → LPE
- **Инфо**: https://www.penligent.ai/hackinglabs/cve-2025-55680-poc

### **CVE-2025-0886** — VirtualLockSensor
- **GitHub PoC**: https://github.com/JNDataRT/VirtualLockSensorLPE

## Агрегированные ресурсы

- **ycdxsb/WindowsPrivilegeEscalation** — коллекция Windows LPE PoC  
  https://github.com/ycdxsb/WindowsPrivilegeEscalation

- **nickvourd/Windows-Local-Privilege-Escalation-Cookbook**  
  https://github.com/nickvourd/Windows-Local-Privilege-Escalation-Cookbook

## ⚠️ Важные замечания

- Все эти уязвимости пропатчены Microsoft через Windows Update
- PoC предназначены только для легального тестирования и исследований
- Тестировать только в изолированных средах
- CVE-2025-21333 и CVE-2025-55680 особенно интересны — активно использовались в реальных атаках
- Большинство эксплоитов основаны на: heap overflows, race conditions, symlink attacks, IOCTL mishandling