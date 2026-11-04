# VR Educational Game

A Unity VR educational game set in a rice field, with interactive animals and learning content in English and Khmer.

## Features

- Select animals to display their images and localized information.
- Switch between English and Khmer, with language-specific fonts.
- Navigate a main menu, settings, and introductory learning panels.
- Explore an environment with animal movement scripts and audio controls.
- Use Unity's XR interaction tools for VR input and interaction.

## Requirements

- Unity Hub and **Unity 6000.3.2f1**, the version recorded in `ProjectSettings/ProjectVersion.txt`.
- A compatible VR headset and OpenXR runtime for headset testing.
- The Unity build support module for your target platform. Android builds also require Android Build Support, SDK, NDK, and OpenJDK.

Dependencies are declared in `Packages/manifest.json` and restored by Unity. Key packages include the Universal Render Pipeline, Input System, XR Interaction Toolkit, XR Hands, XR Plug-in Management, and OpenXR.

## Getting started

1. Clone or download this repository.
2. In Unity Hub, choose **Add** and select the project root containing `Assets`, `Packages`, and `ProjectSettings`.
3. Open the project with Unity **6000.3.2f1** and allow package restoration and asset import to finish.
4. Open `Assets/Scenes/RiceFieldScene1.unity`, the currently enabled build scene.
5. Configure your headset runtime and check **Edit > Project Settings > XR Plug-in Management** for the target platform.
6. Connect your headset and enter Play mode to test the scene.

The repository also includes XR simulator samples under `Assets/Samples`. Desktop simulation requires configuring the appropriate simulator in the scene.

## Project structure

| Path | Contents |
| --- | --- |
| `Assets/Scenes/` | Rice field, menu, introduction, and other scenes |
| `Assets/Scripts/AnimalDetail/` | Animal data, selection behavior, and information panels |
| `Assets/Scripts/Localization/` | Language switching and localized UI text |
| `Assets/Scripts/UI/` | Menus, settings, and introductory panels |
| `Assets/Scripts/Movement/` | Animal movement behaviors |
| `Assets/Scripts/Manager/` | Audio and scene management |
| `Assets/Resources/Localization/` | English and Khmer translation files |
| `Assets/Samples/` | Imported XR package samples |
| `Assets/VRTemplateAssets/` | VR template assets and scripts |
| `Packages/` | Unity package manifest and dependency lock file |
| `ProjectSettings/` | Unity editor, rendering, input, XR, and build configuration |

## Building

1. Open **File > Build Profiles** in Unity.
2. Select the intended platform and install its build support module if needed.
3. Review the scene list. `RiceFieldScene1` is currently the only enabled scene in the checked-in build settings; enable any additional scenes required by your intended flow.
4. Review XR and Player settings for the target device.
5. Choose **Build**, or **Build And Run** with a compatible device connected.

## Editing learning content

- Update `Assets/Resources/Localization/en.json` and `km.json` with matching translation keys. Each file uses an `items` array containing `key` and `value` pairs.
- Use **Create > Animal Database** in the Project window to create an animal database asset. Each entry provides an animal key, image, and translation key.
- Assign the database to an `AnimalInfoPanel`, then connect each animal's `AnimalInteractable` component to its animal key and panel in the Inspector.
- Keep Unity `.meta` files alongside their assets so scene and prefab references remain intact.
