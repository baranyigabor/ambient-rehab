# Adaptive Assistance Framework for Ambient Intelligence Rehabilitation
Gábor Baranyi, Zsolt Csibi, Kristian Fenech, Áron Fóthi, Zsófia Gaál, Joul Skaf, András Lőrincz

## Components

![Pipeline](./Images/Pipeline.png)

## Build

Each component has been tested under Ubuntu 22.04 Linux distribution and [Apptainer](https://apptainer.org/). We highly recommend to use virtual environments to avoid conflicts between software modules. For 3D reconstruction (NeRF, Gaussian Splatting, localization), pose estimation (MeTRAbs, HybrIK-X) and privacy protection in case of the mobile application's backend we used a server with 64GB RAM and 2x NVIDIA RTX 3090 GPUs.

DeepRehab mobile application has its own installation guide, please follow its [Readme](./deeprehab/README.md).

### Clone repositories
```
git clone --recursive https://github.com/baranyigabor/ambient-rehab
# If you cloned the repository without the --recursive flag, run the following command:
git submodule update --init --recursive
```
### Apptainer
Create apptainer images for the components using the [definition files](./Apptainer_definitions/), which are based on the software requirements.

```
apptainer build <image>.sif <definition_filename>.def
```

### Virtualenv

Apptainer images mostly contain those components that can be installed only via `apt-get` only. `pip` based packages recommended to be installed within a virtual env. 

[Launcher](./Launcher_files/) folder contains some examples how these should be prepared.

update the launcher file with the `.sif` file created in the previos step then run 
```
./launch_<software>.sh
```

## News

- [2025-03-01] Supplementary materials: LINK
- [2025-02-23] Repository update

## BibTeX

If you find this work useful for your research, please consider citing:

```bibtex
@article{baranyi2025ambientrehab,
  title={TODO},
  author={TODO},
  journal={TODO},
  year={2025},
  volume={?},
  number={?},
  pages={?},
  doi={?}
}
```

## Contributions

- B., G: conceptualization, investigation, methodology, 3D reconstruction methods, human pose estimation methods, data collection, supervision, implementation, writing, figures
- C., Z.: visual language model evaluation, prompt engineering, data processing, implementation & writing
- F., Á.: supervision, mobile application testing
- F., K.: project administration, writing—review and editing
- G., Z.: Rehabilitation dataset creation, exercise descriptions
- L., A.: conceptualization, methodology, project administration, supervision, and writing-review and editing.
- S., J.: localization, path plannning and navigation, implementation

All authors have read and agreed to the published version of the manuscript.

## Acknowledgment

<b>MILAB</b>:
This research was supported by the European Union project RRF-2.3.1-21-2022-00004 within the framework of the Artificial Intelligence National Laboratory. 

<b>BOSCH</b>:
The authors also thank Robert Bosch Ltd., Budapest, Hungary for their generous support to the Department of Artificial Intelligence.

<b>HumanE-AI</b>:
This project has also received funding from the European Union’s Horizon 2020 research and innovation programme under grant agreement No 952026. The support is gratefully acknowledged.

We would like to thank the hard work of <b>Gábor Ambrus</b> and <b>Dávid Tokár</b> on DeepRehab mobile application development as part of their BSc theses, under the supervision of <b>Áron Fóthi</b> and <b>Gábor Baranyi</b> respectively.

## License 
- Exercise-positioning and DeepRehab mobile application: [MIT License](./LICENSES/LICENSE.txt)

This project includes multiple additional components and users must comply with all licenses of the internal and external components.

- NeRFStudio: [Apache License 2.0](./LICENSES/NeRFStudio_LICENSE.txt) 
  - Splatfacto uses [GSplat](https://github.com/nerfstudio-project/gsplat) implementation which has the same [Apache License 2.0](./LICENSES/NeRFStudio_LICENSE.txt) license
- NeRFBridge: [MIT License](./LICENSES/NeRFBridge_LICENSE.txt)
- MeTRAbs: [MIT License](./LICENSES/MeTRAbs_LICENSE.txt)
- EmbodiedSAM: [MIT License](./LICENSES/EmbodiedSAM_LICENSE.txt)
  - Segment Anything 2: [Apache License 2.0](./LICENSES/SAM2_LICENSE.txt) and [BSD 3-Clause License](./LICENSES/SAM2_LICENSE_cctorch.txt)
- HybrIK-X: [MIT License](./LICENSES/HybrIK_LICENSE.txt)
- Habitat-Lab: [MIT License](./LICENSES/Habitat_LICENSE.txt)

# Nerfies

This is the repository template is from [Nerfies website](https://nerfies.github.io).

# Website License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
