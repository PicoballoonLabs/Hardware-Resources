# Hardware-Resources

This repository serves as the central hub for all KiCad symbols, footprints, 3D models, project templates, and color palettes used across Picoballoon's electrical engineering projects.

Our goal is to ensure consistency, reusability, and efficiency in hardware design by providing a unified set of verified assets.

## 📦 Contents

*   **`Picoballoon Color Scheme/`**: KiCad color theme (schematic and PCB editor), inspired by Altium.
*   **`Picoballoon ICs/`**: Symbols, footprints and 3D models for integrated circuits: MCUs, radios, GNSS receivers, sensors, power and interface ICs.
*   **`Picoballoon Mechanical & Misc/`**: Symbols, footprints and 3D models for connectors, switches, antennas, battery holders, solar panels and miscellaneous parts.
*   **`Picoballoon Passives/`**: Symbols, footprints and 3D models for passive components: resistors, capacitors, inductors, crystals, diodes, LEDs...
*   **`Picoballoon Power Symbols/`**: Symbol library with schematic power symbols.
*   **`Templates/`**: KiCad drawing sheet templates and graphics used on them.
*   **`repository.json`**, **`packages.json`**, **`resources.zip`**: Index, package list and icons for the KiCad Plugin and Content Manager.
*   **`construct_repository.py`**: Script that builds the Plugin and Content Manager packages and regenerates the index files.

Each library folder holds its `symbols/`, `footprints/` and `3dmodels/` together with the `metadata.json` and the packaged `*_pcm.zip` served to the Plugin and Content Manager.

## 📄 Licence

Assets authored by Noove s.r.o. are released under the MIT Licence, see [LICENSE](LICENSE). The libraries also contain third-party and supplier-provided assets that keep their original terms, see [ATTRIBUTION.md](ATTRIBUTION.md).

## 🛠️ KiCad Integration Guide

Follow these steps to integrate Picoballoon's hardware resources into your KiCad environment.

### 1. Add to KiCad Plugin and Content Manager (Recommended)

This is the easiest way to access our symbols, footprints, and 3D models for their KiCad projects.

1.  Open KiCad.
2.  Go to `Tools` > `Plugin and Content Manager`.
3.  Click on the `Manage...` button in the top right corner of the manager window.
4.  In the `Manage Repositories` window, click the `+` icon.
5.  Enter the following URL and click `OK`:
    ```
    https://raw.githubusercontent.com/PicoballoonLabs/Hardware-Resources/main/repository.json
    ```
6.  Close the settings window and refresh the Content Manager if prompted.
7.  You should now see "Hardware Resources" as an available repository. Select it and click `Install` to download and add all symbols, footprints, and 3D models managed by the Content Manager.

### 2. Configure KiCad Global Libraries using Path Manager (For contributors)

This setup lets you work with and contribute to the libraries directly via Git.

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/PicoballoonLabs/Hardware-Resources.git /path/to/your/desired/location/Hardware-Resources
    ```
    (Replace `/path/to/your/desired/location/` with where you want the repo on your system.)
2.  Open KiCad.
3.  Go to `Preferences` > `Configure Paths...`.
4.  Click the `+` icon to add a new environment variable.
5.  Set `Name` to `PICOBALLOON_LIBRARY`.
6.  Set `Value` to the path where you cloned this repository (e.g., `/path/to/your/desired/location/Hardware-Resources`).
7.  Click `OK` to save the path.
8.  Now, in `Preferences` > `Manage Symbol Libraries` and `Preferences` > `Manage Footprint Libraries`, you must add all Picoballoon libraries using this path variable as a global library. For example, add `${PICOBALLOON_LIBRARY}/Picoballoon ICs/Picoballoon_ICs.kicad_sym` and `${PICOBALLOON_LIBRARY}/Picoballoon ICs/Picoballoon_ICs.pretty`. Add all other necessary libraries similarly from the `Contents` section above.

## 💡 Contributing to Hardware Resources

*   **External contributions**: Open a pull request against `main`. Please state where any symbol, footprint or 3D model comes from so it can be recorded in [ATTRIBUTION.md](ATTRIBUTION.md).
*   **Team members**: To prevent complex merge conflicts in library files, changes are pushed directly to `main`. Pull before you start, keep commits small, and coordinate larger changes or new library sections with the hardware team lead.
*   **KiCad Cache Refresh**: After pulling updates, you may need to clear your KiCad symbol and footprint caches or restart KiCad to see the latest changes in your projects.

Ensure all new assets meet our established naming conventions and quality standards.
