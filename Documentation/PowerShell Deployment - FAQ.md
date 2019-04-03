# Frequent Asked Questions - PowerShell Deployment Extension Kit
April 2019

This document highlights and captures some of the known issues and limitations of PSD (as of the published date above). 

## Frequently Asked Questions
Q: Does the installer copy over my existing MDT Deployment Share content (e.g. applications, drivers, task sequences, etc) to a new PSD share?
>A: No, users and administrators will need to copy/export any existing components to *new* PSD shares using in-built content management features of MDT. MDT Shares which have been PSD upgraded will continue to have access to any existing object and artifacts.

Q: Does the installer copy over my existing BootStrap.ini or CustomSettings.ini files to the target PSD repositories?
>A: No, if you've created a new PSD-enabled deployment share, users and administrators will need to manually copy or reproduce any existing Bootstrap and CustomSettings files to new repositories.

Q: What are the client/target hardware requirements for baremetal PSD deployments?
>A: 
- At least 1.5GB RAM (WinPE has been extended and requires additional memory)
- At leaast one (1) network adapter(s)
- At least one (1) 50GB hard drive (for New/BareMetal deployments)
- At least one (1) XXX MHz processor (for New/BareMetal deployments)

Q: Does PSD work with 2Pint's ACP solution?
>A: TBD

Q: How does PSD work with 2Pint's ACP solution?
>A: lightweight description here. See [link](http://somedocument.com}

Q: Does PSD work with 1E's Nomad solution?
>A: PSD has not been tested in conjunction with 1E's Nomad product (yet)

Q: Does PSD work with Deployment Optimization?
>A: TBD

Q: Does PSD work with Branch Cache?
>A: TBD

Q: Does PSD work with Peer Cache?
>A: TBD

Q: What is "Transcript Logging"?
>A: Logs (for exmaple PSD.LOG, and BDD.log) are what we explicitly write, Transcript logs captures everything that happens on the screen. PSD Transcript lgos are much better suited and useful for troubleshooting, but may be visually "sub-optimal".

Q: What do I see frequent references to "Stopping Transcript Logging"?
>A: (TBA MiNy)

Q: Do i still need to 'add' PowerShell support to my WinPE images?
>A: No, the PSD installation and scripting takes care of it for you. As a matter of fact, unticking the box on the WinPE Features tab will not affect PSD at all.

Q: Will PSD work on my xxx version of MDT or ADK?
>A: We've only developed and tested against the versions and platforms listed below. If you have success on additional versions and platforms, please be sure and let us know!

Q: What files are copied or injected into the PSD Boot Media?
>A: TBA Johan or Mike

Q: What scripts or files can be safely deleted from my PSD Deployment Share?
>A: TBA Johan or Mike. 
- Do NOT delete any PSD*.ps1 or PSD*.psm1 files. 
- Do NOT delete ZTIGather.xml or ZTIConfigure.xml
- If desired, many of the legacy MDT .wsf scripts and Wizard files can be removed manually from the PSD Deployment Share scripts folder to thin out the environment. 

## Documented Platforms and Scenarios
Q: What operating systems and components has PSD been tested and or evaluated against?
>A: TThe following tables identifies tested and validated components, scenarios as well as testing and development status: 
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-fymr{font-weight:bold;border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-xldj{border-color:inherit;text-align:left}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-fymr">Component</th>
    <th class="tg-fymr">Version</th>
    <th class="tg-fymr">Notes</th>
  </tr>
  <tr>
    <td class="tg-xldj">MDT</td>
    <td class="tg-0pky">8456</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">ADK</td>
    <td class="tg-0pky">1809</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">WinPe addon</td>
    <td class="tg-0pky">1809</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">Target client OS</td>
    <td class="tg-0pky">Windows 10 ENT x64 EN 1809<br>Windows 10 ENT x64 EN 1709</td>
    <td class="tg-0pky">MSDN media tested</td>
  </tr>
  <tr>
    <td class="tg-0pky">BareMetal via UNC</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">Tested and working</td>
  </tr>
  <tr>
    <td class="tg-0pky">BareMetal via HTTP</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">Tested and working</td>
  </tr>
  <tr>
    <td class="tg-0pky">BareMetal via HTTPS</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet tested</td>
  </tr>
  <tr>
    <td class="tg-0pky">IIS</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">WebDAV</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">PXE</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">Host Server OS</td>
    <td class="tg-0pky">Windows Server 2016 ENT </td>
    <td class="tg-0pky"></td>
  </tr>
    <tr>
    <td class="tg-0pky">Virtual Machines</td>
    <td class="tg-0pky">Microsoft Hyper-V </td>
    <td class="tg-0pky">Client deployments tested against Hyper-V.<br>MDT/PSD tested hosted on Hyper-V</td>
  </tr>
    <tr>
    <td class="tg-0pky">Refresh via UNC</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
    <tr>
    <td class="tg-0pky">Refresh via HTTP</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
    <tr>
    <td class="tg-0pky">Refresh via HTTPS</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
  <tr>
    <td class="tg-0pky">Replace via UNC</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
    <tr>
    <td class="tg-0pky">Replace via HTTP</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
    <tr>
    <td class="tg-0pky">Replace via HTTPS</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
  <tr>
    <td class="tg-0pky">BIOS-to-UEFI via UNC</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
    <tr>
    <td class="tg-0pky">BIOS-to-UEFI  via HTTP</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
    <tr>
    <td class="tg-0pky">BIOS-to-UEFI via HTTPS</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
        <tr>
    <td class="tg-0pky">Generic, non-OSD TS via UNC</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
    <tr>
    <td class="tg-0pky">Generic, non-OSD TS via HTTP</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
    <tr>
    <td class="tg-0pky">Generic, non-OSD TS via HTTPS</td>
    <td class="tg-0pky">n/a</td>
    <td class="tg-0pky">not yet implemented</td>
  </tr>
</table>

## Installation Observations

- The PSD installer will create the -psDeploymentShare name *exactly* as specified. The PSD installer does **not** handle or change the hidden share $ character in any form or fashion.

- The PSD installer does **not** automatically mount a new PSD-created deployment share respository. Users will need to mount newly created PSD deployment shares manually.

- The PSD installer does **not** automatically copy over any existing MDT artifacts and components to a new PSD-created deployment share respositories. Users will need to manually copy over, re-import or instatiate applications, drivers, etc. manually.

## Operational Observations
Please review the PSD Installation Guide for additional detailed post-installation configuration recomendations.

- Applications specified in the TS or in BS/CS.ini **MUST** have { } brackets around their GUID
- New TS variables **must** be declared explicity in BS/CS.ini


