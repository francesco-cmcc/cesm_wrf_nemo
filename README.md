#
# **CIME with NEMO and WRF**

This file summarises all the files needed to create, compile and run a coupled model WRF+NEMO.

![](RackMultipart20210524-4-116dlfg_html_cb55ddb5edd60516.gif)

**CIME configuration**

- **Files to determine the components needed:**
  - ✔ $CESMROOT/Externals.cfg
- **Files to configure our supercomputer (i.e. Zeus):**
  - ✔ $CIMEROOT/config/cesm/machines/config\_machines.xml
- **Files to add our custom grids:**
  - ✔ $CIMEROOT/config/cesm/config\_grids.xml
  - ❌ $DIN\_LOC\_ROOT/domains
  - ❌ $DIN\_LOC\_ROOT/mappings

![](RackMultipart20210524-4-116dlfg_html_cb55ddb5edd60516.gif)

**CASE configuration**

- **Files to set $DIN\_LOC\_ROOT**
  - ✔ $CASEROOT/env\_run.xml (modified through xmlchange)
- **Simulation configuration**
  - ✔ $CASEROOT/Buildconf/cplconf/drv\_in

![](RackMultipart20210524-4-116dlfg_html_cb55ddb5edd60516.gif)

**NEMO configuration**

- **Files modified to support the new grid**
  - ✔ $CESMROOT/components/nemo/cime\_config/buildnml0
- **Namelists**
  - ✔ $CESMROOT/components/nemo/nml/SHARED/namelist\_ref
  - ✔ $CASEROOT/Buildconf/nemoconf/namelist\_cfg
- **Boundary conditions and other input files**
  - ❌ $DIN\_LOC\_ROOT/nemo

![](RackMultipart20210524-4-116dlfg_html_cb55ddb5edd60516.gif)

**WRF configuration**

- **Files modified to make CIME aware of WRF**
  - ✔ $CIMEROOT/config/cesm/config\_files.xml
- **Configure file to compile WRF**
  - ✔ $CESMROOT/components/wrf/configure.wrf.zeus
- **Input namelist**
  - ❌ $DIN\_LOC\_ROOT/wrf/namelist\_input\_1
- **Input boundary conditions**
  - ✔ $CASEROOT/Buildconf/wrfconf/namelist\_infile
