# Hardware-Resources

This repository serves as the central hub for all KiCad symbols, footprints, 3D models, project templates, and color palettes used across Picoballoon's electrical engineering projects.

Our goal is to ensure consistency, reusability, and efficiency in hardware design by providing a unified set of verified assets.

## 📦 Contents

*   **`Picoballoon Color Scheme/`**: KiCad theme files and color palette definitions.
*   **`Picoballoon ICs/`**: KiCad symbol and footprint libraries specifically for Integrated Circuits.
*   **`Picoballoon Mechanical & Misc/`**: KiCad symbol and footprint libraries for connectors, actuators, batteries and miscellaneous parts.
*   **`Picoballoon Passives/`**: KiCad symbol and footprint libraries for passive components: resistors, capacitors, inductors...
*   **`Picoballoon Power Symbols/`**: KiCad symbol library for schematic power symbols.
*   **`Templates/`**: KiCad drawing sheet templates.
*   **`repository.json`**: Index file for the KiCad Plugin and Content Manager.

---

## 🛠️ KiCad Integration Guide

Follow these steps to integrate Picoballoon's hardware resources into your KiCad environment.

### 1. Add to KiCad Plugin and Content Manager (Recommended for external users)

This is the easiest way for external users to access our official symbols, footprints, and 3D models for their KiCad projects.

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

### 2. Configure KiCad Global Libraries using Path Manager (Essential for Internal Team)

This setup is crucial for internal team members to directly work with and contribute to the libraries via Git.

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

---

## 💡 Contributing to Hardware Resources

This repository uses a streamlined contribution model to ensure rapid updates and minimize merge conflicts.

*   **No Branching for Contributions**: To prevent complex merge conflicts in library files, contributions are made directly to the `main` branch.
*   **Pull/Push Directly**: After making local changes to library files (symbols, footprints, 3D models) in your cloned `Hardware-Resources` repository:
    1.  Ensure your local repository is up-to-date: `git pull origin main`
    2.  Commit your changes: `git commit -am "Your descriptive commit message"`
    3.  Push your changes directly: `git push origin main`
*   **Communication is Key**: For larger changes or new library sections, please communicate with the hardware team lead before pushing to coordinate and avoid simultaneous edits to the same files.
*   **KiCad Cache Refresh**: After pulling updates, you may need to clear your KiCad symbol and footprint caches or restart KiCad to see the latest changes in your projects.

Ensure all new assets meet our established naming conventions and quality standards.