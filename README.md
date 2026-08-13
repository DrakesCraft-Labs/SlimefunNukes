<p align="center"><img src="docs/banner.svg" alt="SlimefunNukes" width="100%"></p>

# SlimefunNukes

Explosivos para Slimefun, adaptado al ecosistema Slimefun de **DrakesCraft** (Paper/Purpur 1.21.11, Java 21).

## Qué añade

Cargas explosivas de radio configurable.

## Ojo con esto

> [!WARNING]
> **No está desplegado en DrakesCraft, y no debería estarlo sin revisarlo antes.**
> Destruye bloques con `setType(AIR)` y la comprobación de WorldGuard está comentada en el código original, así que no respeta protecciones. Además lanza hilos sin control. Se portó para tenerlo compilando, no para usarlo.

## Qué cambiamos

Este repositorio **no es un fork**: es el código original integrado en el ecosistema de
DrakesCraft (Paper/Purpur 1.21.11, Java 21). Los cambios comunes a todos nuestros ports son:

**Los paquetes de Slimefun.** El core de DrakesCraft está repaquetado, así que un addon de fuera
no encuentra nada hasta que se remapean sus imports.

**La telemetría, fuera.** bStats abría una conexión a bstats.org cada pocos minutos con datos del
servidor. Se quitaron las llamadas, los imports y la dependencia — no se sustituyó por un stub
inerte, que dejaría el código en pie aparentando que hay telemetría.

**Los autoactualizadores, desarmados.** Este jar está recompilado contra nuestro Slimefun; si se
bajara el de upstream encima, dejaría de cargar. Las actualizaciones se despliegan por SFTP.

**El rastreador de fallos apunta aquí**, no al repositorio original: un fallo de esta versión
casi nunca es un fallo de allí.
